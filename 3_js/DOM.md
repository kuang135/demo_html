### 1.节点的层次
#### Node类型，Node接口由DOM中的所有节点类型实现
* 属性
  + nodeType
	- Node.ELEMENT_NODE(1)
	- Node.ATTRIBUTE_NODE(2)
	- Node.TEXT_NODE(3)
	- Node.CDATA_SECTION_NODE(4)
	- Node.ENTITY_REFERENCE_NODE(5)
	- Node.ENTITY_NODE(6)
	- Node.PROCESSING_INSTRUCTION_NODE(7)
	- Node.COMMENT_NODE(8)
	- Node.DOCUMENT_NODE(9)
	- Node.DOCUMENT_TYPE_NODE(10)
	- Node.DOCUMENT_FRAGMENT_NODE(11)
	- Node.NOATATION_NODE(12)
  + nodeName
  + nodeValue
* 节点关系
  + childNodes
  + firstChild
  + lastChild
  + parentNode
  + nextSibling
  + previousSibling
* 操作节点
  + parentNode.appendChild(newNode)
  + parentNode.inertBefore(newNode, childNode)
  + parentNode.replaceChild(newNode, childNode)
  + parentNode.removeChild(childNode)
  + node.cloneNode(true) -- true表示深拷贝
  + node.normalized() -- 处理文本节点
  
### 2.Document类型
* nodeType的值为 9
* nodeName的值为 '#document'
* nodeValue的值为 null
* parentNode的值为 null
### 3.Element类型
* nodeType的值为 1
* nodeName的值为 元素的标签名
* nodeValue的值为 null
* parentNode的值为 Document 或 Element
### 4.Text类型
* nodeType的值为 3
* nodeName的值为 '#text'
* nodeValue的值为 节点所包含的文本
* parentNode的值为 Element
### 5.Attr类型
* nodeType的值为 3
* nodeName的值为 '#text'
* nodeValue的值为 节点所包含的文本
* parentNode的值为 Element
### 5.Comment类型
* nodeType的值为 8
* nodeName的值为 '#comment'
* nodeValue的值为 注释的内容
* parentNode的值为 Document 或 Element
