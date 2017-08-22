#### 选择符API
+ 通过Document, Element类型的实例调用
+ IE8+, Firefox3.5+, Safari3.1+, Chrome, Opera10+完全支持
  ```
  var selected = document.querySelector('.selected'); //返回匹配的第一个元素
  var selecteds = document.querySelectorAll('.selected'); //返回一个NodeList的实例
  ```

#### 元素遍历
+ 对于元素间的空格，IE9及之前版本不会返回文本节点，而其他浏览器会返回文本节点
+ 为了弥补差异，定义了新属性
  - childElementCount: 子元素(不包括文本节点和注释)的个数
  - firstElementChild: 第一个子元素
  - lastElementChild: 最后一个子元素
  - previousElementSibling: 前一个同辈元素
  - nextElementSibling: 后一个同辈元素
```
  var i,
      len,
      child = element.firstChild;
  while(child != element.lastChild) {
      if (child.nodeType == 1) {
          processChild(child);
      }
      child = child.nextSibling;
  }
  //新
  var i,
      len,
      child = element.firstElementChild;
  while(child != element.lastElementChild) {
      processChild(child);
      child = child.nextElementSibling;
  }
```

#### HTML5
1. 与类相关
   + getElementsByClassName()
     ```
     var allCurrentUsernames = document.getEelementsByClassName('username current');
     var selectecd = document.getElementById('myDiv').getEelementsByClassName('selected');
     ```
   + classList, 是新集合类型DOMTokenList的实例
     - add(value): 添加，如果存在，就不添加
     - contains(value): 如果存在返回true，否则返回false
     - remove(value): 删除给定字符串
     - toggle(value): 如果存在，删除；如果不存在，添加
2. 焦点管理
3. HTMLDocument的变化
4. 字符集属性
5. 自定义数据属性
6. 插入标记
7. scrollIntoView()方法