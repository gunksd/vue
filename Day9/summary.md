## 1.异步函数：
```JS
async function fetchData() {
  if (isFetching.value) return
  isFetching.value = true
  todoData.value = null
```
是一个异步函数，用于从 API 获取数据。

避免重复请求：

`if (isFetching.value) return`：如果 isFetching 为 true，表示当前已经有一个数据请求正在进行，函数会立即返回，不会再发起新的请求。这防止了多次快速点击按钮导致多个未完成的异步请求。
开始请求：

`isFetching.value = true`：将 isFetching 设为 true，表示数据请求开始。
todoData.value = null：将 todoData 设为 null，表示当前数据正在加载，防止显示旧数据。
请求数据：

`const res = await fetch(...)`：使用 fetch API 向给定的 URL 发起请求。这是一个异步操作，`await` 关键字用于等待请求完成。</br>
`if (!res.ok) throw new Error('Failed to fetch data')`：检查响应是否成功（状态码在200-299之间），如果不成功，则抛出一个错误。</br>
处理响应：

`todoData.value = await res.json()`：将响应数据解析为 JSON 格式，并赋值给 todoData。</br>
错误处理：

`catch (error)`：如果在 try 块中发生了任何错误（例如网络问题或解析错误），将捕获并处理错误。</br>
`todoData.value = { error: error.message }`：将错误信息存储在 todoData 中，以便在模板中显示。</br>
请求结束：

`finally { isFetching.value = false }`：无论请求成功与否，都会在最后将 isFetching 设为 false，表示数据请求结束。

## 2.watch监听：</br>
```JS
fetchData()
watch(todoId, fetchData)
```
初始数据加载和监听 todoId 变化：</br>
`fetchData()`：在组件加载时立即调用 fetchData，获取初始任务数据。</br>
`watch(todoId, fetchData)`：使用 Vue 的 watch 函数监听 todoId 的变化。当 todoId 变化时，会自动调用 fetchData 函数，获取新的任务数据。</br>

## 3.template：</br>
`:disabled="isFetching`：按钮在 isFetching 为 true 时被禁用，表示正在进行数据请求，防止用户多次点击触发多个请求。</br>

## 4.GPT link:

https://chatgpt.com/share/2694e7b8-1490-4d50-83a7-c8376572647a