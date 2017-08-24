#### Node类型，Node接口由DOM中的所有节点类型实现
1. 属性
   + nodeType
     ```
     Node.ELEMENT_NODE(1)
     Node.ATTRIBUTE_NODE(2)
     Node.TEXT_NODE(3)
     Node.CDATA_SECTION_NODE(4)
     Node.ENTITY_REFERENCE_NODE(5)
     Node.ENTITY_NODE(6)
     Node.PROCESSING_INSTRUCTION_NODE(7)
     Node.COMMENT_NODE(8)
     Node.DOCUMENT_NODE(9)
     Node.DOCUMENT_TYPE_NODE(10)
     Node.DOCUMENT_FRAGMENT_NODE(11)
     Node.NOATATION_NODE(12)
     ```
   + nodeName
   + nodeValue
2. 节点关系
   + childNodes
   + firstChild
   + lastChild
   + parentNode
   + nextSibling
   + previousSibling
3. 操作节点
   ```
   parentNode.appendChild(newNode);
   parentNode.inertBefore(newNode, childNode);
   parentNode.replaceChild(newNode, childNode);
   parentNode.removeChild(childNode);
   node.cloneNode(true); // true表示深拷贝
   node.normalized(); // 处理文本节点
   ```

#### Document类型
1. 属性
   + nodeType的值为 9
   + nodeName的值为 '#document'
   + nodeValue的值为 null
   + parentNode的值为 null
2. 子节点
   ```
   var html = document.documentElement;
   var body = document.body;
   ```
3. 文档信息
   ```
   var title = document.title;
   var url = document.URL;
   var domain = document.domain;
   var referrer = document.referrer;
   ```
4. 查找元素
   ```
   var div = document.getElementById('divId');
   var images = document.getElementByTagName('img'); //HTMLCollection对象
   ```

#### Element类型
1. 属性
   + nodeType的值为 1
   + nodeName的值为 元素的标签名
   + nodeValue的值为 null
   + parentNode的值为 Document 或 Element
2. HTML元素(HTMLElement直接继承自Element), 具有以下标准属性:
   + id
   + title
   + className
   + lang -- 语言
   + dir -- 语言的方向
3. 操作特性
   很多对象都有 innerHTML 和 innerText 特性
   ```
   var _id = htmlElement.getAttribute('id');
   var _id = htmlElement.id; //所有特性都是属性，可以直接取值
   //htmlElement.style 和 htmlElement.onclick 返回对象和函数
   //htmlElement.getAttribute('style') 和 htmlElement.getAttribute('onclick') 返回文本
   htmlElement.setAttribute('id', 'btnId');
   htmlElement.id = 'btnId'; //所有特性都是属性，可以直接赋值
   htmlElement.removeAttribute('class');
   ```
4. attributes属性
   + attributes包含一个NameNodeMap
   + 元素的每一个特性都由Attr节点表示，每个节点都保存在NameNodeMap中
5. 创建元素
   ```
   var div = document.createElement('div');
   ```
6. 元素的子节点
   ```
   var ites = ul.getElementByTagName('li');
   ```

#### Text类型
1. 属性
   + nodeType的值为 3
   + nodeName的值为 '#text'
   + nodeValue的值为 节点所包含的文本
   + parentNode的值为 Element
5. 创建
   ```
   var textNode = document.createTextNode('Hello Text Node');
   ```

#### Attr类型
* nodeType的值为 3
* nodeName的值为 '#text'
* nodeValue的值为 节点所包含的文本
* parentNode的值为 Element

#### Comment类型
* nodeType的值为 8
* nodeName的值为 '#comment'
* nodeValue的值为 注释的内容
* parentNode的值为 Document 或 Element
