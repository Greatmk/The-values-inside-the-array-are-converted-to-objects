#### 今天和大家分享一下 在开发中经常会调后台给的接口，经常需要后台需要你传一些值过去，比如如下：

```
 现在在前端这边有arr这样的数据，现在后台让你把它转换成newArr的形式给传过去
 let arr = ['abc','ddd','ccc'];

  newArr = [
    {"sort": 0, "serviceDeviceId":'aaa'},
    {"sort": 1, "serviceDeviceId":'bbb'},
    {"sort": 2, "serviceDeviceId":'ccc'},
  ]
  
  ```

  ```
    方法一：如下
    var arr = ['abc','bbb','ccc'];
    function getNewArr(arr) {
        var newArr = [];
        for(var i = 0; i < arr.length; i++){
        var str = {};
        str.sort = i;
        str.serviceDeviceId = arr[i];
        var str1 = JSON.stringify(str);
        var str2 = JSON.parse(str1);
        newArr.push(str2);
        }
        return newArr;
    }

    console.log((getNewArr(arr)));
  ```

```
 方法二： 最简单
   arr.forEach((value,index) => {
   newArr.push({"sort": index, "serviceDeviceId": value})
  });
  console.log(newArr);
```
