1.对于这个filterTodos的计算属性的规则理解不透彻，实际是返回一个数组，而不是改变原来的这个数组里面的值。<br>
2.`？XX:XX`的写法需要熟悉：
```JavaScript
  return hideCompleted.value
    ? todos.value.filter((t) => !t.done)
    : todos.value
详解：
hideCompleted.value:

这是一个布尔值（true 或 false），表示是否隐藏已完成的待办事项。
三元运算符 (? :):

这是 JavaScript 中的一种简洁的条件表达式，用于根据条件返回不同的值。其基本语法是：condition ? expr1 : expr2。当 condition 为 true 时，返回 expr1 的值；否则返回 expr2 的值。

hideCompleted.value 是条件部分：

如果 hideCompleted.value 为 true，说明用户选择隐藏已完成的待办事项。
todos.value.filter((t) => !t.done) 是 expr1 部分：

如果 hideCompleted.value 为 true，执行这个表达式。它会过滤 todos.value 数组中的每个元素，仅保留那些 done 属性为 false 的待办事项，也就是未完成的事项。
todos.value 是 expr2 部分：

如果 hideCompleted.value 为 false，返回整个 todos.value 数组，这意味着显示所有待办事项，不论是否已完成。
```
3.双向绑定的应用，渲染列表的逻辑都大可深究，详细见GPT链接<br>

4.GPT Link:https://chatgpt.com/share/510cf0ae-634c-4deb-aa56-2ab67eca606c
