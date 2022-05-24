## `1`- 要求用户猜 1~50之间的一个数字,但是只有10次猜的机会

```js
        function getRandom(min,max) {
            return Math.floor(Math.random() * (max - min + 1)) + min;
        }   
        var random = getRandom(1,50);
        for ( var i = 1; i <= 10; i++) {
            var num = prompt('请从1-50之间猜一个数(只有10次机会哦)');
            if (num > random) {
                alert('你猜大了');
            }   else if (num < random) {
                alert('你猜小了');
            }   else {
                alert('恭喜你，猜对了');
                break;
            }
        }
```

## `2`-  ['red', 'blue', 'red', 'green', 'pink', 'red'], 求 red 出现的位置和次数

```js
        var arr =  ['red', 'blue', 'red', 'green', 'pink', 'red'];
        var index = arr.indexOf('red');
        var num = 0;
        while (index !== -1) {
            console.log(index);
            num++;
            index = arr.indexOf('red', index + 1);
        }
        console.log('red出现的次数:' + num + '次');
```

## `3`- 有一个字符串 'abcoefoxyozzopp'  要求把里面所有的 o 替换为 *

```js
        // 方法一
        var str = 'abcoefoxyozzopp';
        while (str.indexOf('o') !== -1) {
            str = str.replace('o', '*');
        }
        console.log(str);
        // 方法二
        var str = 'abcoefoxyozzopp';
        for (var i = 0; i < str.length; i++) {
            if (str.indexOf('o') !== -1) {
                str = str.replace('o', '*');
            }
        }
        console.log(str);
```

## `4`- 给定一个字符串,如:"abaasdffggghhjjkkgfddsssss3444343"

```js
        // 1、 字符串的长度
        var str = 'abaasdffggghhjjkkgfddsssss3444343';
        console.log(str.length);
        // 2、 取出指定位置的字符，如：0,3,5,9等
        console.log(str[0],str[3],str[5],str[9]);
        // 3、 查找指定字符是否在以上字符串中存在，如：i，c ，b等
        var index = str.indexOf('b');
        if (index !== -1) {
            console.log('存在');
        }   else {
            console.log('不存在');
        }
        // 4、 替换指定的字符，如：g替换为22,ss替换为b等操作方法
        for (var i = 0; i < str.length; i++) {
            if (str.indexOf(str[i]) !== -1) {
                str = str.replace('g', '22');
                str = str.replace('ss', 'b');
            }
        }
        console.log(str);
        // 5、 截取指定开始位置到结束位置的字符串，如：取得1-5的字符串
        console.log(str.substr(0,5));
        // 6、 找出以上字符串中出现次数最多的字符和出现的次数
        var o = {};
        for (var i = 0; i < str.length; i++) {
            var chars = str.charAt(i);
            if (o[chars]) {
                o[chars]++;
            }   else {
                o[chars] = 1;
            }
        }
        console.log(o);
        var max = 0;
        var ch = '';
        for (var k in o) {
            if (o[k] > max) {
                max = o[k];
                ch = k;
            }
        }
        console.log('出现最多次数的字符是:' + ch);
        console.log('出现的次数为: ' + max + '次');
        // 7、 遍历字符串，并将遍历出的字符两头添加符号“@”   
        var newStr = str.split('');
        console.log(newStr);
        var newArr = '';
        for (var i = 0; i < str.length; i++) {
            newArr = newArr + '@' + str[i] + '@' + '\t';
        }
        console.log(newArr);
```

## `5`- 把下面数组的首尾两个元素互换

```js
        //方法一
        var arr = ["鹿晗","王俊凯","蔡徐坤","彭于晏","周杰伦","刘德华","赵本山"];
        var removed1 = arr.splice(0, 1, '赵本山');
        var removed2 = arr.splice(-1, 1, '鹿晗');
        console.log(arr);

        // 方法二
        var arr = ["鹿晗","王俊凯","蔡徐坤","彭于晏","周杰伦","刘德华","赵本山"];
        var first = arr[0];
        var end = arr[arr.length - 1];
        arr[0] = end;
        arr[arr.length - 1] = first;
        console.log(arr);
```

## `6`- 计算指定日期是今年的第几天

```js
        // 题目描述：制作一个函数，getDayNum( 年月日日期 )，可以返回指定日期是当前年的第几天
        // 例：  getDayNum( “2022-1-5”)    返回值为：5   
        // 1、默认系统起始时间  01 1970 08:00:00 GMT+0800 (中国标准时间) 1970年1月1日8点
        // 2、+new Date()后面必须接字符串型变量
        // var firstDay = +new Date(getYear.toString());等同于 var firstDay = +new Date(’2022‘);
        // 3、拿输入时间减去这年的1月1日8点的毫秒数，用Math.ceil向上取整，取最大值，然后还要算上当天，所以算法最后加1
        function getDayNum(time) {
            var now = new Date(time);   // 2022-1-5
            var getYear = now.getFullYear();    // 2022
            var firstYear = + new Date(getYear.toString()); // 1970-2022年1月1日8点毫秒数
            var thisYear = + new Date(time);   // 1970-2022年1月5日0点毫秒数
            var Times = (thisYear - firstYear) / 1000;  // 1 ms = 1000 s
            var d = Math.ceil(Times / 60 / 60 / 24) + 1;
            return d + '天';
        }  
        console.log(getDayNum('2022-1-5'));
```

## `7`- 16进制随机颜色

```js
        // 题目描述：使用Math对象，制作一个16进制的随机颜色
        // ​题目提示：16进制包括 “ 0  1  2  3  4  5  6  7  8  9  A  B  C  D  E  F ”
        // ​例： “#f23a4b”    
        // 方法一
        function getColor() {
            var str = '#';
            for (var i = 0; i < 6; i++) {
                str += Math.floor(Math.random() * 16).toString(16); // 从16个数当中随机抽取6个数并通过.toSting(16)转换成十六进制
            }
            return str;
        }
        var re = getColor();
        console.log(re);

        // 方法二
        function getColor() {
            var str = '#';
            var arr = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'A', 'B', 'C', 'D', 'E', 'F'];
            for (var i = 0; i < 6; i++) {
                var num = parseInt(Math.random() * 16);
                str += arr[num];
            }
            return str;
        }
        var re = getColor();
        console.log(re);
```

## `8`- 随机选学员

```js
        // 从以下学员名单中随机选出4个学员：
        // ​	var arr = ["鹿晗","王俊凯","蔡徐坤","彭于晏","周杰伦","刘德华","赵本山"]；
        // ​	注意：不要有重复的学员
        var arr = ["鹿晗", "王俊凯", "蔡徐坤", "彭于晏", "周杰伦", "刘德华", "赵本山"];
        var newArr=[];//创建一个新数组用来接收随机选出来的值
        while(newArr.length < 4) {//判断条件：当数组大于等于4的时候跳出循环
            var num=Math.floor(Math.random() * arr.length) //随机生成0-7个数组的索引号，是可重复的
            if(newArr.indexOf(arr[num])=== -1){//判断新数组中是否在旧数组中存在，当返回值（不存在-1）如果不存在就执行下面
                newArr.push(arr[num]);//把旧数组的元素用push()方法推给新数组newArr
            }
        }
        console.log(newArr);
```

## `9`-  随机排序

```js
        // 对以下学员随机排序，生成一个新数组：
        // ​var arr = ["鹿晗","王俊凯","蔡徐坤","彭于晏","周杰伦","刘德华","赵本山"];
        var arr = ["鹿晗","王俊凯","蔡徐坤","彭于晏","周杰伦","刘德华","赵本山"];
        function getRandom(arr) {
            for (var i = 0; i < arr.length; i++) {
                var rand = Math.floor(Math.random() * arr.length);
                var temp;
                temp = arr[rand];
                arr[rand] = arr[i];
                arr[i] = temp;
            }
            return arr;
        }
        var re = getRandom(arr);
        console.log(re);
```

## `10`- 数组去重 ['c', 'a', 'z', 'a', 'x', 'a', 'x', 'c', 'b'] 要求去除数组中重复的元素

```js
        // 1.目标： 把旧数组里面不重复的元素选取出来放到新数组中，重复的元素只保留一个， 放到新数组中去重
        // 2.核心算法： 遍历旧数组， 拿着旧数组元素去查询新数组， 如果该元素在新数组里面没有出现过，我们就添加，否则不添加
        var arr = ['c', 'a', 'z', 'a', 'x', 'a', 'x', 'c', 'b'];
        var newArr = [];
        for (var i = 0; i < arr.length; i++) {
            if (newArr.indexOf(arr[i]) === -1) {
                newArr.push(arr[i]);
            }
        }
        console.log(newArr);
```