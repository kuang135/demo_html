#### 动态脚本
1. 外部文件
   ```
   function loadScript(url) {
       var script = document.createElement('script');
       script.type = 'text/javascript';
       script.src = url;
       document.body.insertBefore(script, document.body.firstChild);
   }
   loadScript('client.js');
   ```
2. 内部代码
   ```
   function loadScriptString(code) {
       var script = document.createElement('script');
       script.type = 'text/javascript';
       try {
           script.appendChild(document.createTextNode(code));
       } catch (e) {
           script.text = code;
       }
   }
   loadScriptString('function sayHi(){alert("Hi");}');
   ```

#### 动态样式
1. 外部文件
   ```
   function loadStyle(url) {
       var link = document.createElement('link');
       link.rel = 'stylesheet';
       link.type = 'text/css';
       link.href = url;
       document.getElementsByTagName('head')[0].appendChild(link);
   }
   loadStyle('style.css');
   ```
2. 内部代码
   ```
   function loadStyleString(css) {
       var style = document.createElement('style');
       style.type = 'text/css';
       try {
           style.appendChild(document.createTextNode(css));
       } catch (e) {
           style.styleSheet.cssText = css;
       }
       document.getElementsByTagName('head')[0].appendChild(style);
   }
   loadStyleString('body {background-color: pink;}');
   ```

#### 操作表格
1. \<table>元素的属性和方法
   + caption
   + tBodies -- HTMLCollection
   + tFoot
   + tHead
   + rows -- 一个表格中所有的行大HTMLCollection
   + createTHead()
   + createTFoot()
   + createCaption()
   + deleteTHead()
   + deleteTFoot()
   + deleteCaption()
   + deleteRow(pos)
   + insertRow(pos)
2. \<tbody>元素的属性和方法
   + rows -- 保存着tbody中行的HTMLCollection
   + deleteRow(pos)
   + insertRow(pos)
3. \<tr>元素的属性和方法
   + cells -- 保存着tr中单元格的HTMLCollection
   + deleteCell(pos)
   + insertCell(pos)

#### 使用NodeList
  + NodeList, NamedNodeMap, HTMLCollenction都是“动态”的
  ```
  var divs = document.getElementByTagName('div'),
      i,
      len,
      div;
  for (i = 0, len = divs.length; i < len; i++) { //for (i = 0; i < divs.length; i++) 死循环
      div = document.createElement('div');
      document.body.appendChild(div);
  }
  ```