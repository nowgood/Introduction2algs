
```c++
#include<iostream>
#include<vector>
#include <map>
using namespace std;

int main() {
    vector<int> vec = {2, 3, 5, 1, 34, 5};
    make_heap(vec.begin(), vec.end(), greater<int>());
    for (auto e : vec) {
        cout << e << " ";
    }
    cout << endl;

    // 不管是 push 还是 pop, 都要提供 comp 函数, 不然有错

    // 1. 先在容器中加入元素, 然后调用push_heap进行调整
    vec.push_back(10);
    push_heap(vec.begin(), vec.end(), greater<int>());

    for (auto e : vec) {
        cout << e << " ";
    }
    cout << endl;
    // 2. 删除容器元素, 先调用pop_heap, 将删除元素放到容器末尾, 然后删除
    pop_heap(vec.begin(), vec.end(), greater<int>());
    vec.pop_back();
    for (auto e : vec) {
        cout << e << " ";
    }
    return 0;
}
```


下面再介绍STL中与堆相关的4个函数——建立堆make_heap()，在堆中添加数据push_heap()，在堆中删除数据pop_heap()和堆排序sort_heap()：

头文件 #include <algorithm>

        下面的_First与_Last为可以随机访问的迭代器（指针），_Comp为比较函数（仿函数），其规则——如果函数的第一个参数小于第二个参数应返回true，否则返回false。

建立堆

make_heap(_First, _Last, _Comp)

默认是建立最大堆的。对int类型，可以在第三个参数传入greater<int>()得到最小堆。



在堆中添加数据

push_heap (_First, _Last)

要先在容器中加入数据，再调用push_heap ()



在堆中删除数据

pop_heap(_First, _Last)

要先调用pop_heap()再在容器中删除数据


堆排序

sort_heap(_First, _Last)

排序之后就不再是一个合法的heap了
