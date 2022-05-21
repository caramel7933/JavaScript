## `1`- 求任意两个数的和

```js
        function getSum(num1,num2) {
            return num1 + num2;
        }
        console.log(getSum(20,40));
```

## `2`- 利用函数求任意两个数的最大值

```js
        //方法一
        function getMax(num1,num2) {
            if (num1 > num2) {
                return num1;
            }   else {
                return num2;
            }
        }
        console.log(getMax(4,9));
        // //方法二
        function getMax(num1,num2) {
            return num1 > num2 ? num1 : num2;
        }
        console.log(getMax(5,22));
```

## `3`- 求数组 [5,2,99,101,67,77] 中的最大数值

```js
        function getArrMax(arr) {
            var max = arr[0];
            for (var i = 1; i <= arr.length; i++) {
                if (arr[i] > max) {
                    max = arr[i];
                }
            }
            return max;
        }
        var re = getArrMax([5,2,99,101,67,77]);
        console.log(re);
```

## `4`- 求任意两个数的加减乘数结果

```js
        function getResult(num1,num2) {
            return [num1 + num2, num1 - num2, num1 * num2, num1 / num2]; 
        }
        var re = console.log(getResult(1,2));
```

## `5`- 创建一个函数，实现两个数之间的加减乘除运算，并将结果返回

```js
        var num1 = parseFloat(prompt('请输入第一个数:'));
        var num2 = parseFloat(prompt('请输入第二个数:'));
        function count(num1,num2) {
            var arr = [num1 + num2, num1 - num2, num1 * num2, num1 / num2];
            return arr;
        }
        var re = count(num1,num2);
        console.log(re);
```

## `6`- 写一个函数，能返回传入的任意三个数字的最大值

```js
        function getMax(num1,num2,num3) {
            var arr = [num1,num2,num3];
            var max = arr[0];
            for (var i = 0; i < arr.length; i++) {
                if (arr[i] > max) {
                    max = arr[i];
                }
            }
            return max;
        }
        var re = getMax(55,66,121);
        console.log('最大值是:' + re);
```

## `7`- 写一个函数，能判断传入的一个数值是否是质数，如果是质数返回true，如果不是质数返回false(质数：从2开始只能被1和自身整除的数)

```js
        var num = parseInt(prompt('请输入一个数:'));
        function getResult(num) {
            if (num < 2) {
                return false;
            }
            for (var i = 2; i < num; i++) {
                if (num % i == 0) {
                    return false;
                }   else {
                    return true;
                }
            }
        }
        var re = getResult(num);
        console.log(re);
```

## `8`- 写一个函数，能翻转传入的任意数组，并把翻转结果通过返回值返回

```js
            function getNewArr(arr) {
                var newArr = [];
                for (var i = arr.length - 1; i >= 0; i--) {
                    newArr[newArr.length] = arr[i];
                }
                return newArr;
            }
            var re = getNewArr([8,9,3,6,3,7,1]);
            console.log(re);
```

## `9`- 简易计算器

```js
        function calculate(content) {
            switch(content) {
                case '1': 
                    var num1 = prompt('请输入第一个数据:');
                    var num2 = prompt('请输入第二个数据:');
                    return parseFloat(num1) + parseFloat(num2);
                case '2': 
                    var num1 = prompt('请输入第一个数据:');
                    var num2 = prompt('请输入第二个数据:');
                    return num1 - num2;
                case '3': 
                    var num1 = prompt('请输入第一个数据:');
                    var num2 = prompt('请输入第二个数据:');
                    return num1 * num2;
                case '4':
                    var num1 = prompt('请输入第一个数据:');
                    var num2 = prompt('请输入第二个数据:');
                    return num1 / num2;
                default: 
                    return '没有这种运算，请重新输入';
            }
        }
        var content = prompt('欢迎使用简易计算器:\n1.加法运算\n2.减法运算\n3.乘法运算\n4.除法运算\n5.退出\n请输入您的选择:');
        var re;
        while(content != 5) {
            re = calculate(content);
            alert('结果为:' + re);
            var content = prompt('欢迎使用简易计算器:\n1.加法运算\n2.减法运算\n3.乘法运算\n4.除法运算\n5.退出\n请输入您的选择:');
        }
        alert('正在退出');
```

 ## `10`- 创建一个电脑对象，该对象要有颜色、重量、品牌、型号，可以看电影、听音乐、打游戏和敲代码

```js
        var computer = {
            color: 'white',
            weight: '100kg',
            logo: 'lenovo',
            num: 456777,
            func: function() {
                console.log('可以看电影、听音乐、打游戏和敲代码');
            }
        }
        console.log(computer.color);
        console.log(computer['logo']);
        computer.func();
```