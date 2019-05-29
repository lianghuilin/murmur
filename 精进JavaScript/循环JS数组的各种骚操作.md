## 判断数组中是否存在某元素
```
// 1. jQuery方式
var target = 1;
var arr = [1, 2, 3];
console.log($.inArray(target,arr));

// 2. 原生JS的indexOf方式
if (!Array.indexOf) {
    Array.prototype.indexOf = function (obj) {
        for (var i = 0; i < this.length; i++) {
            if (this[i] == obj) {
                return i;
            }
        }
        return -1;
    }
}

var target = 1;
var arr = [1, 2, 3];
console.log(arr.indexOf(target));
```

## 删除数组指定元素
```
arr.splace(index,1);
```

## 旋转跳舞闭着眼
### for
### for in
### each
### forEach
### map
### filter
### reduce
### some
### every
