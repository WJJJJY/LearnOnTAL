###使用TensorFlow，首先需要明白<p>
+ 使用图(graph)来表示计算任务<p>
+ 在被称之为<code>回话(Session)</code>的上下文(context)中执行图<p>
+ 通过<code>tensor</code>表示数据<p>
+ 通过<code>变量(Variable)</code>维护状态<p>
+ 使用<code>feed和fetch</code>可以为任意的操作赋值或者从其中获取数据<p>

###综述
 + TensorFlow是一个编程系统，使用图来表示计算任务，图中的节点被称之为*op*，一个*op*可以获得0个或多个<code>Tensor</code>，执行计算，产生0个或多个<code>Tensor</code>。每一个<code>Tensor</code>是一个类型化的多维数组。<p>
 + 一个TensorFlow图描述了计算的过程，为了进行计算，图必须在<code>会话</code>里被启动<code>会话</code>将图的*op*分发到诸如CPU或GPU之类的<code>设备</code>上，同时提供执行*op*的方法。