## `1`- 创建一个按钮对象，该对象中需要包含宽，高，背景颜色和点击行为

```js
        var button = {
            width: 100,
            height: 500,
            background_color: 'red',
            click: function() {
                console.log('快点点我');
            }
        }
        console.log('宽：' + button.width);
        console.log('高：' + button['height']);
        button.click();
``` 

## `2`- 创建一个车的对象，该对象要有重量、颜色、牌子，可以载人、拉货和耕田

```js
        var car = {
            weight: '500kg',
            color: 'purple',
            logo: '小菠萝',
            skill: function() {
                console.log('可以载人、拉货和耕田');
            }
        }
        for (var k in car) {
            console.log(k);
            console.log(car[k]);
        }      
``` 

## `3`- 写一个函数，实现反转任意数组

```js
        function getArr(arr) {
            var newArr = [];
            for (var i = arr.length - 1; i >= 0; i--) {
                newArr[newArr.length] = arr[i];
            }
            return newArr;
        }
        var re = getArr([9,8,4,3,6,5,1]);
        console.log(re);
```

## `4`- 写一个函数，实现对数字数组的排序

```js
        function getResult(arr) {
            for (var i = 0; i < arr.length - 1; i++) {
                for (var j = 0; j < arr.length - i -1; j++) {
                    if (arr[j] > arr[j+1]) {
                        var temp;
                        temp = arr[j];
                        arr[j] = arr[j+1];
                        arr[j+1] = temp;
                    }
                }
            }
            return arr;
        }
        var re = getResult([7,8,4,3,6,1]);
        console.log(re);
```

## `5`- 书写一个构造函数，用来创建学生对象，学生对象包括的内容有：姓名（name）、学号（id）、性别（sex）、年级（grade）、打招呼（sayHi）—— 在弹出框中提示：“你好我是XXX”，其中XXX代表对象的name属性值

```js
        function Objec(name,id,sex,grade) {
            this.name = name;
            this.id = id;
            this.sex = sex;
            this.grade = grade;
            this.sayHi = function() {
                console.log('你好我是' + name);
            }
        }
        var xbl = new Objec('小菠萝','3456789','公','五年级');
        console.log(xbl.name);
        console.log(xbl['grade']);
        xbl.sayHi();
```

## `6`- 请描述下面代码的输出结果以及运行原因

```js
        var num = 1;
        function demo(){
            console.log(num);
            function demoSon(){
                console.log(num);
                num = 3;
                console.log(num);
            }
            var num = 2
            demoSon();
        }
        demo();
        // 相当于以下代码
        var num;
        function demo(){
            var num;
            console.log(num);  // undefined
            function demoSon(){
                console.log(num); // 2
                num = 3;
                console.log(num);  // 3
            }
            num = 2
            demoSon();
        }
        num = 1;
        demo();
```

## `7`- 遍历下面对象

```js
        var dog = {
            dName:"coco",
            type:"阿拉斯加犬",
            age:"5岁",
            color:"棕红色"
        }
        // --------------------
        for (var k in dog) {
            console.log(k);
            console.log(dog[k]);
        }
```

## `8`- 请使用arguments完成函数getResult，实现得到输入的所有的数值中的最小值、最大值、平均数、总和等功能

    题目要求：
        ​1.函数名：getResult
        ​2.函数调用方式：getResult(数值1，数值2，数值3，数值4)
        ​3.函数功能：返回值是一个对象，这个对象有sum, max, min, averages等属性，分别表示实参的总和、最大值、最小值、平均数等

```js
        function getResult() {
            var max = arguments[0];
            var min = arguments[0];
            var sum = 0;
            var averages = 0;
            for (var i = 0; i < arguments.length; i++) {
                if (arguments[i] > max) {
                    max = arguments[i];
                }   else if (arguments[i] < min) {
                    min = arguments[i];
                }
                sum = sum + arguments[i];
            }
            averages = sum / arguments.length;
            return [sum,max,min,averages];
        }
        var re = getResult(6,7,3,2);
        console.log(re);
        console.log(typeof re);
```

## `9`- 书写一个函数，判断指定数据是否存在于指定数组中

    要求：
    	1.函数名称：exist
   	    2.函数调用方式：exist(数据data，数组arr)
    	3.函数功能：判断“数据data”是否存在于“数组arr”中，如果是函数返回值为true，如果不是函数返回值为false

```js
        function exist(data,arr) {
            for (var i = 0; i < arr.length; i++) {
                if (data == arr[i]) {
                    return true;
                }
            }
            return false;
        }
        var re = exist(7,[7,3,5,4]);
        console.log(re);
```

## `10`- 以下有两个数组，一个数组arr是班级里所有的学员的名称，一个数组currentArr是提交了每日反馈的学员名单，请创建一种算法，把未提交每日反馈的学员筛选出来

```js
        var arr = ["张瑞淑", "徐海涛", "谢岗岗", "薛鹏", "魏明杨"];
        var currentArr = ["张瑞淑", "徐海涛", "谢岗岗"];
        function getNewArr(arr,currentArr) {
            var newArr = [];
            for (var i = 0; i < arr.length; i++) {
                if (currentArr.indexOf(arr[i]) == -1) {
                    newArr.push(arr[i]);
                }
            }
            return newArr;
        }
        var re = getNewArr(arr,currentArr);
        console.log(re);
```