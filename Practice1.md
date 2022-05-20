## `1`- 获取用户信息

- 题目描述

   - 依次询问并获取用户的姓名、年龄、性别，收集数据之后在控制台依次打印出来。


```js
        var yourName = prompt('请输入您的姓名：');
        var sex = prompt('请输入您的性别：');
        var age = prompt('请输入您的年龄：');
        console.log('用户的姓名：' + yourName + '\n用户的性别:' + sex + '\n用户的年龄:' + age);
```
- 题目提示

   - 通过prompt来弹出提示框，收集用户信息
   - 通过变量保存数据


## `2`- 增加年龄

- 题目描述

  - 询问用户年龄，用户输入年龄后，把用户输入的年龄增加5岁
  - 增加5岁后，通过弹出框提示用户 “ 据我估计，五年后，你可能XX岁了”

```js
        var age = prompt('你现在多少岁了？');
        var sum = parseInt(age) + 5;
        console.log('据我估计，五年后，你可能' + sum + '岁了');
```

- 题目提示

  - 通过prompt来弹出提示框，收集用户信息
  - 通过变量保存数据
  - 转换数据类型

## `3`- 判断闰年

- 题目描述：

  - 算法：`能被4整除且不能整除100的为闰年`（如2004年就是闰年，1901年不是闰年）`或者能够被 400 整除的就是闰年`
  - 弹出prompt 输入框，让用户输入年份，把这个值取过来保存到变量中
  - 使用 if 语句来判断是否是闰年，如果是闰年，就执行 if 大括号里面的输出语句，否则就执行 else里面的输出语句 

```js
        var year = prompt('请您输入年份：');
        if (year % 4 == 0 && year % 100 != 0 || year % 400 == 0) {
            alert('您输入的年份是闰年');
        } else {
            alert('您输入的年份是平年');
        }
```

## `4`- 数字补0
- 用户输入0~59之间的一个数字
- 如果数字小于10，则在这个数字前面补0,（加0拼接）否则不做操作
- 用一个变量接收这个返回值，输出

```js
        var time = prompt('请您输入一个 0 ~ 59 之间的一个数字');
        // 三元表达式   表达式 ？ 表达式1 ：表达式2 
        var result = time < 10 ? '0' + time : time; //   把返回值赋值给一个变量
        alert(result);
```
## `5`- 判断时间阶段

- 题目提示：
  - 通过比较运算符判定输入的时间的范围，弹出相应的问候信息


```js
        var time = prompt('现在几点钟了?');
        if ( time >= 22) {
            alert('现在已经' + time + '点了,赶紧睡觉去');
        }   else if (time >= 18) {
            alert('现在已经' + time + '点了，晚上好' );
        }   else if (time >= 13) {
            alert('现在已经' + time + '点了，下午好');
        }   else if (time >= 9) {
            alert('现在已经' + time + '点了，中午好');
        }   else if (time >= 6 && time <= 8) {
            alert('现在已经' + time + '点了，早上好');
        }   else {
            alert('zzzzzzzzz')
        }
```

## `6`- 比较两个数的最大值

- 题目描述：
  - 用户依次输入2个值，最后弹出最大的那个值

- 题目提示：
  - 通过比较运算符弹出最大值

```js
        var num1 = prompt('请输入第一个数:');
        var num2 = prompt('请输入第二个数:');
        if ( num1 > num2) {
            alert('最大值是:' + num1);
        }   else {
            alert('最大值是:' + num2);
        }
        作业3
        var num = prompt('请输入一个数:');
        if (num % 2 == 0) {
            alert('这个数是偶数');
        }   else {
            alert('这个数是奇数');
        }
```

## `7`- 判断奇偶性

- 题目描述：
  - 用户输入一个数，判断是奇数还是偶数

- 题目提示：
  - 通过%运算符可以得出数字的奇偶性

```js
        var num = prompt('请输入一个数:');
        if (num % 2 == 0) {
            alert('这个数是偶数');
        }   else {
            alert('这个数是奇数');
        }
```

## `8`- 判断星期

- 题目描述：
  - 假设这个月1号是星期三，提示用户输入本月的日期（即1日-31日），返回用户输入的那一天是星期几

- 题目提示：
  - 利用%和7取余，再判定是星期几

```js
        var date = prompt('请输入本月的日期(1-31日):');
        switch(true) {
            case(date % 7 == 1): 
                alert('今天星期三');
                break;
            case(date % 7 == 2):
                alert('今天星期四');
                break;
            case(date % 7 == 3):
                alert('今天星期五');
                break;
            case(date % 7 == 4):
                alert('今天星期六');
                break;
            case(date % 7 == 5):
                alert('今天星期天');
                break;
            case(date % 7 == 6):
                alert('今天星期一');
                break;
            default:
                alert('今天星期二');
        }
```

## `9`- 请客吃饭

- 题目描述：
  
        - 接收班长口袋里的钱数？

        - 若大于等于2000，请大家吃西餐。

        - 若小于2000，大于等于1500，请大家吃快餐。

        - 若小于1500，大于等于1000，请大家喝饮料。

        - 若小于1000，大于等于500，请大家吃棒棒糖。

        - 否则提醒班长下次把钱带够

- 题目提示：
  - 使用switch或者if else if 来进行逻辑书写

```js
        var money = prompt('班长口袋里的钱数:');
        if (money >= 2000) {
            alert('请大家吃西餐');
        }   else if (money >= 1500) {
            alert('请大家吃快餐');
        }   else if (money >= 1000) {
            alert('请大家喝饮料');
        }   else if (money >= 500) {
            alert('请大家吃棒棒糖');
        }   else {
            alert('班长下次记得把钱带够');
        }
```

## `10`- 成绩表

```js
        var score = prompt('请输入分数:');
        switch(true) {
            case(score >= 90 && score <= 100):
                alert('等级为A');
                break;
            case(score >= 80 && score < 90):
                alert('等级为B');
                break;
            case(score >= 70 && score < 80): 
                alert('等级为C');
                break;
            case(score >= 60 && score < 70): 
                alert('等级为D');
                break;
            case(score >= 0 && score < 60): 
                alert('好好反省一下');
                break;
            default:
                alert('输入错误');
        }
``` 


