## 1.子组件可以向父组件触发事件emit:
```bash
<script setup>
// 声明触发的事件
const emit = defineEmits(['response'])

// 带参数触发
emit('response', 'hello from child')
</script>
```
## 2.`emit()` 的第一个参数是事件的名称。其他所有参数都将传递给事件监听器。

父组件可以使用 `v-on`(@)监听子组件触发的事件——这里的处理函数接收了子组件触发事件时的额外参数并将它赋值给了本地状态:
```bash
<ChildComp @response="(msg) => childMsg = msg" />
```
