## `1`- 求100以内所有能被3和7整除的数的和

- 题目描述：
  - 把1-100之间所有能够被3和7同时整除的数找出来，计算累加和

```js
        var sum = 0;
        for (var i = 1; i <= 100; i++) {
            if (i % 3 == 0 && i % 7 == 0) {
                sum += i;
            }
        }
        console.log('100以内所有能被3和7整除的数的和:' + sum);
```

## `2`- 使用for循环打印三角形

- 题目描述：

  - 在控制台一次性打印形状如下：

    ☆
    ☆☆
    ☆☆☆
    ☆☆☆☆
    ☆☆☆☆☆

- 题目提示：

  - 利用双重for循环

```js
        var str = '';
        for (var i = 1; i <= 5; i++) {
            for (var j = 1; j <= i; j++) {
                str = str + '☆';
            }
            str = str + '\n';
        }
        console.log(str);
```

## `3`- 使用for循环打印99乘法表

- 题目描述：

  - 使用for循环，打印99乘法表

```js
        var str = '';
        for(var i = 1; i <= 9; i++) {
            for(var j = 1; j <= i; j++) {
                str = str + j + 'x' + i + '=' + j * i + '\t';
            }
            str = str + '\n';
        }
        console.log(str);
```

## `4`- 用户登录验证

- 题目描述：
  - 接收用户输入的用户名和密码，若用户名为 “admin” ,且密码为 “123456” ,则提示用户登录成功!  否则，让用户一直输入
- 题目提示：
  - 利用while循环或者do while 循环

```js
        var userName = prompt('请输入您的用户名:');
        var passWord = prompt('请输入您的密码:');
        while (userName != 'admin' && passWord != '123456') {
            var userName = prompt('请输入您的用户名:');
            var passWord = prompt('请输入您的密码:');
        }
        alert('登录成功');
```

## `5`- 求1-100之间个位数不为3的数的累加和

- 题目描述：
  - 求整数1～100的累加值，但要求跳过所有个位为3的数。
- 题目提示：
  - 使用%判个位数是否为3
  - 用continue实现

```js
        var sum = 0;
        for(var i = 1; i <= 100; i++) {
            if(i % 10 == 3) {
                continue;
            }
            sum = sum + i;
        }
        console.log('1-100之间个位数不为3的数的累加和:' + sum);
```

## `6`- 简易ATM

- 题目描述：

  - 里面现存有  100 块钱。

  - 如果存钱，就用输入钱数加上先前存的钱数, 之后弹出显示余额提示框

  - 如果取钱，就减去取的钱数，之后弹出显示余额提示框

  - 如果显示余额，就输出余额

  - 如果退出，弹出退出信息提示框

```js
        var myMoney = 100;
        while(true) {
            var atm = prompt('请输入您要的操作:\n1.存钱\n2.取钱\n3.显示余额\n4.退出');
            if(atm == '1') {
                var inM = prompt('请输入您要存入的金额:');
                myMoney += parseFloat(inM);
                alert('您当前的余额为:' + myMoney + '元');
            }   else if (atm == '2') {
                var outM = prompt('请输入您要取出的金额:');
                if(outM > myMoney) {
                    alert('您的余额不足');
                    continue;
                }
                myMoney -= parseFloat(outM);
                alert('您当前的余额为:' + myMoney + '元');
            }   else if (atm == '3') {
                alert('您当前的余额为:' + myMoney + '元');
            }   else if (atm == '4') {
                alert('退出成功');
                break;  
            }
        }
```

## `7`- 求从1开始第35个能被7和3整除的整数数

- 题目描述：
  - 求从1开始第35个能被7和3整除的整数

```js
        var count = 0;
        for (var i = 1; i > count; i++) {
            if (i % 3 == 0 && i % 7 == 0){
                count++;
                if (count == 35) {
                    console.log('从1开始第35个能被7和3整除的整数数是:' + i);
                    break;  
                }
            }
        }
```

## `8`- 利用函数计算1-100之间的累加和

```js
        function getSum() {
            var sum = 0;
            for (var i = 0; i <= 100; i++) {
                sum = sum + i;
            }
            console.log(sum);
        }
        getSum();
```

## `9`- 利用函数求任意两个数的和

```js
        function getSum(num1,num2) {
            console.log(num1 + num2);
        }
        getSum(50,50);
```

## `10`- 利用函数求任意两个数之间的和

```js
        function getSum(start,end) {
            var sum = 0;
            for (var i = start; i <= end; i++) {
                sum = sum + i;
            }
            console.log(sum);
        }
        getSum(1,10);
        getSum(1,100);
```