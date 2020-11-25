# fed-e-task-04-01

1. 请简述 React 16 版本中初始渲染的流程
解答：
- 


2. 为什么 React 16 版本中 render 阶段放弃了使用递归
解答：
V16之前的递归算法有以下几个缺点：
- 任务开始之后，无法中断
- 如果应用中的组件数量庞大，主线程会被长期占用，直到整个DOM树对比更新完成后才被释放
- 占用期间，主线程无法执行其他任务
- 此时有交互或动画任务，无法被立即执行
- 页面可能会出现卡顿，影响用户体验


3. 请简述 React 16 版本中 commit 阶段的三个子阶段分别做了什么事情
解答:
- 处理类组件中的 getSnapShotBeforeUpdate 
- 将workInProgress Fiber树转变为 current Fiber 树
- 重置 nextEffect


4. 请简述 workInProgress Fiber 树存在的意义是什么
解答：
利用workInProgress Fiber 树实现双缓存，加快DOM对象的快速更新
