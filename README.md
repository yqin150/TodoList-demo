# TodoList-demo
this is a practice
一、搭建页面结构
1：先用bs搭建页面

2：第一块使用的是BS的列表组件

3：第二块用的是BS的form



二、用vuejs去做交互事件
1.要是你想在界面里面看到你data的变化，你可以{{ $data }}，但是有一点你要注意的就是这行代码一定要写在你整个vue声明的里面，否则就没有结果

2.我们第一个要实现的效果就是把data对象里面的todos的title属相传递到li列表里面
  那么这里我们使用的语法就是v-for="(index,todo) in todos"                                                                                                                                           "我们把数据渲染出来就是{{todo.title}}
3.我们第二个想要实现的效果就是在把新输入的数据显示在form里面的input上面
  那么这里我们使用的语法就是 v-model="newTodo.title"
  
4.我们第三个想要实现的效果就是通过点击按钮（因为这里我们最外面的属form所以我们要把他的默认   行为给阻止掉），我们把data 里面newTodo里面的数据取出来，并且放在todos数组里面，那么这里我们就需要一个事件来做这件事情addNewTodo(newTodo)

 点击按钮的时候去触发这个事件，每次压进一个新的数据后，要记得把newTodo还原为最初的状态，since v-model="newTodo.title"
5.我们第四个想要实现的效果就是可以去删除一个todo任务，所以我们就应该从todos数组里面去删除一个对象，所以这里我们给按钮绑定事件v-on:click="deleteTodo(index)"

如果我们想要删除当前选中的任务，就必须使用index参数，又因为我们要从当前的数组里面删掉一条数据所以我们使用的是this.todos.splice(index,1)
