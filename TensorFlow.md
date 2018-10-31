<font size=5><b>使用TensorFlow，首先需要明白</b></font>
+ 使用图(graph)来表示计算任务
+ 在被称之为<code>回话(Session)</code>的上下文(context)中执行图
+ 通过<code>tensor</code>表示数据
+ 通过<code>变量(Variable)</code>维护状态
+ 使用<code>feed和fetch</code>可以为任意的操作赋值或者从其中获取数据

<font size=5><b>综述</b></font>
 + TensorFlow是一个编程系统，使用图来表示计算任务，图中的节点被称之为*op*，一个*op*可以获得0个或多个<code>Tensor</code>，执行计算，产生0个或多个<code>Tensor</code>。每一个<code>Tensor</code>是一个类型化的多维数组。
 + 一个TensorFlow图描述了计算的过程，为了进行计算，图必须在<code>会话</code>里被启动<code>会话</code>将图的*op*分发到诸如CPU或GPU之类的<code>设备</code>上，同时提供执行*op*的方法。
 
<font size=5><b>计算图</b></font>
> *TensorFlow*通常被组织成一个构建阶段和一个执行阶段。在构建阶段，*op*的执行步骤被描述成一个图在执行阶段，使用回话执行图中的*op*

<font size=5><b>构建图</b></font>
> 构建图的第一步，是创建源*op*，源*op*不需要任何输入，例如，常量(Constant)。源*op*的输出被传递给其它*op*运算
> *Python*中，*op*构造器的返回值代表被构造出的*op*的输出，这些返回值可以传递给其它*op*构造器作为输入。

<font size=5><b>在一个会话中启动图</b></font>
> 构造阶段完成后，才能启动图，启动图的第一步是创建一个<code>Session</code>对象，如果无任何参数，会话构造器将启动默认图。

<font size=5><b>Tensor</b></font>
> *TensorFlow*程序使用*Tensor*数据结构来代表所有的数据，计算图中，操作间传递的数据都是*tensor*；你可以把*TensorFlow tensor*看成是一个*n*维的数组或列表。一个*tensor*包含一个静态类型*rank*和一个*shape*。