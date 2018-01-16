~~~mermaid
graph TD
a(model点云)-->c(建立model的KDtree)
c-->b(初始化ICP)
a2(target点云)-->b
A(R/T初始值)-->d
b-->d(初匹配:最近邻搜素)
d-->e(初匹配:求解R/T,用Rn-1/Tn-1迭代)
e-->f(精匹配:最近邻搜素)
f-->g(精匹配:求解R/T,用Rn-1/Tn-1迭代)

id1[max_iteration]-.-b
id2[min_deta]-.-b
id31[最近邻点法]-.-d
id32[normal shooting法]-.-d
id33[投影法]-.-d
id34[基于向量间角度或颜色的兼容度量方法compatibility metric]-.-d
id4[point to point:SVD求解,需要匹配很好的点]-.-e
id5[point to plane:可以不需要匹配很好的点做control point,不能用svd分解,需要用LM方法]-.-e
id6[带限制条件的最近邻搜索,比如要求最小距离不大于某个值]-.-f


~~~