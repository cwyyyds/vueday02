<template>
  <div></div>
</template>

<script>
const url1 = 'http://www.baidu.com?name=zhangsan&age=18&sex=nan#'
const process = (url) => {
  const index1 = url.indexOf('?'),
    index2 = url.indexOf('#'),
    params = url.slice(index1 + 1, index2).split('&')
  // console.log(params)

  return params.reduce((pre, item) => {
    const [key, value] = item.split('=')
    // console.log([key, value])
    // console.log(key)
    // console.log(value)
    // console.log(1)
    pre[key] = value
    // console.log(pre)
    return pre
  }, {})
}

console.log(process(url1))
</script>

<style></style>
