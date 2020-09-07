## Ramda 柯里化核心之 _curryN 实现

**通常柯里化**
```javascript
function curry (fn) {
  return function f () {
    const args = [].slice.call(arguments)
    if(args.length < fn.length) {
      // 参数数量不满足原始函数数量，返回curry函数
      return function () {
        return f.apply(this, args.concat([].slice.call(arguments)))
      }
    } else {
      // 参数数量满足原始函数，触发执行
      return  fn.apply(this, args)
    }
  } 
}
```

**辅助函数**
```javascript
const _ = { '@@functional/placeholder': true }

function _isPlaceholder (a) {
  return a != null &&
         typeof a === 'object' &&
         a['@@functional/placeholder'] === true
}

function _arity (n, fn) {
  switch (n) {
    case 0: return function () { return fn.apply(this, arguments) }
    case 1: return function (a0) { return fn.apply(this, arguments) }
    case 2: return function (a0, a1) { return fn.apply(this, arguments) }
    case 3: return function (a0, a1, a2) { return fn.apply(this, arguments) }
    // ... 省略剩余冗余代码
     case 10: return function(a0, a1, a2, a3, a4, a5, a6, a7, a8, a9) { return fn.apply(this, arguments); };
    default: throw new Error('First argument to _arity must be a non-negative integer no greater than ten')
  }
}
```

**核心方法**
```javascript
// length： 柯里化函数参数的个数
// recived: 初始化接收的参数数组，
// fn : 柯里化的函数
function _curryN (length, received, fn) {
  return function () {
    // 存放每次调用函数参数的数组, 在递归调用中就是 recived
    var combined = [];
    var argsIdx = 0;
    var left = length;
    var combinedIdx = 0;
    /* 
      这里同时迭代 recived 和 arguments。
      我们要循环取出每一次 curryN 初始化接收到的参数和调用函数时传入的参数保存在 combined 中，
      这里用一个额外的变量 argsIdx 用于迭代 arguments 的。
    */
    while (combinedIdx < received.length || argsIdx < arguments.length) {
      var result;
      //首先迭代 recived，取出不是占位符的参数放入 combined 中
      if (combinedIdx < received.length && (!_isPlaceholder(received[combinedIdx]) || argsIdx >= arguments.length)) {
        result = received[combinedIdx];
      } else {
        // 如果 recived 已经迭代完了那么将 arguments 放入 combined 中
        result = arguments[argsIdx];
        argsIdx += 1;
      }
      combined[combinedIdx] = result;
      // 如果当前参数不是占位符，则长度减1
      if (!_isPlaceholder(result)) {
        left -= 1;
      }
      combinedIdx += 1;
    }
    // 如果传入参数满足fn参数个数，则直接调用fn，否则递归调用curry函数,反复过滤掉recived的占位符
    return left <= 0 ? fn.apply(this, combined) : _arity(left, _curryN(length, combined, fn));
  };
}
```
现在我们得到一个带有占位符功能的柯里化函数
```javascript
function say (name, age, like) { console.log(`我叫${name},我${age}岁了, 我喜欢${like}`) };
const msg = _curryN(3, [], say)
// => 我叫大西瓜,我20岁了, 我喜欢妹子
msg(_, 20)('大西瓜', _,) ('妹子')
// => 我叫吴亦凡,我25岁了, 我喜欢唱rap
msg(_, _, '唱rap')(_, '25')('吴亦凡')
// => 我叫小明,我22岁了, 我喜欢小红
msg('小明')(_, _)(22,  '小红')
```
