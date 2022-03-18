---
description: JS 判斷字串中是否包含某個字串（方法總結）
---

# Java script

## JS 判斷字串中是否包含某個字串（方法總結）

#### 方法一：**indexOf()**

```
var groupName="小白A組";
alert('groupName.indexOf() =' + (groupName.indexOf("組") != -1));  //true
```

indexOf() 方法可回傳某個指定的字串值在字串中首次出現的位置，如果要檢索的字串值沒有出現，則該方法回傳 -1，

#### 方法二： search()

```
var groupName="小白A組";
alert('groupName.search()=' + (groupName.search("組") != -1));  //true
```

search() 方法用于檢索字串中指定的子字串，或檢索與正則運算式相匹配的子字串，如果沒有找到任何匹配的子串，則回傳 -1，

#### 方法三：match()

```
var groupName="小白A組";
var reg = RegExp(/組/);
alert('groupName.match(reg)=' + (groupName.match(reg)));  //組
```

match() 方法可在字串內檢索指定的值，或找到一個或多個正則運算式的匹配，但你有木有發現列印出來的是 ‘ 組 ’ ，如果是在字串中找不到的話列印 null ，神奇的是可以把它放在 if 里面做判斷，如下：

```
var str="123";
var reg3 = RegExp(/3/);
if(str.match(reg3)){
    alert(true);
}
```

## RegExp 物件方法

#### 方法四：test()

```
var groupName="小白A組";
var reg = RegExp(/組/);
alert('reg.test(groupName)=' + (reg.test(groupName)));  //true
```

test() 方法用于檢索字串中指定的值，回傳 true 或 false，

#### 方法五：exec()

```
var groupName="小白A組";
var reg = RegExp(/組/);
alert('reg.exec(groupName)=' + (reg.exec(groupName)));  //組
```

exec() 方法用于檢索字串中的正則運算式的匹配，回傳一個陣列，其中存放匹配的結果，如果未找到匹配，則回傳值為 null，

