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