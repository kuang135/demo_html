### 1.节点的层次
#### Node类型，Node接口由DOM中的所有节点类型实现
* 属性
  + nodeType
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