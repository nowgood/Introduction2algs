# 二叉搜索树

搜索树结构支持很多动态集合操作, 我们既可以把搜索树当做一个字典又可以当做一个队列

## 二叉搜索树性质

设 x 是二叉搜索树的一个节点, 
如果 y 是 x 的左子树中的一个节点, 那么 y.key ≤ x.key; 
如果 y 是 x 的右子树中的一个节点, 那么 y.key ≥ x.key.

> 中序遍历为升序排列

## 查询二叉搜索树

1. 查找
2. min, max
3. 排序
4. 插入
5. 删除
6. 遍历

### 删除操作

1. 删除节点为叶节点, 直接删除, 置父节点的对应子树为 None
2. 删除节点只有一个孩子, 则用该孩子节点替代删除节点
3. 删除节点有左右孩子, 这是需要左子树的最大值(即删除节点的前驱)或者右子树的最小值(即删除节点的后继), 
   前驱没有右子树, 后继没有左子树, 使用这种方式来删除节点, 能一定程度保证二叉搜索树的平衡性,
   这里以右子树的最小值, 即`后继`为例说明删除节点的过程
   
   1) 如果后继就是删除节点的右儿子节点, 那么直接用该节点替换删除节点就好了;
   2) 如果后继位于删除节点右子树中, 那么, 使用后继替换删除节点, 并用后继的右儿子替换后继
 

