---
title: 'Popover - 弹出框'
---
# Popover 弹出框

<h2 style="margin-bottom:1em;">基本用法</h2>    

<clientOnly>
<popover-demos></popover-demos>
</clientOnly>

<h2>代码展示</h2>

```vue
<n-popover position="left">
      <template v-slot:content>
        <h3>标题</h3>这是一段内容,这是一段内容,这是一段内容,这是一段内容。
      </template>
      <n-button>左边</n-button>
    </n-popover>
    <n-popover position="top">
      <template v-slot:content>
        <h3>标题</h3>这是一段内容,这是一段内容,这是一段内容,这是一段内容。
      </template>
      <n-button>上边</n-button>
    </n-popover>
    <n-popover position="bottom">
      <template v-slot:content>
        <h3>标题</h3>这是一段内容,这是一段内容,这是一段内容,这是一段内容。
      </template>
      <n-button>下边</n-button>
    </n-popover>
    <n-popover position="right">
      <template v-slot:content>
        <h3>标题</h3>这是一段内容,这是一段内容,这是一段内容,这是一段内容。
      </template>
      <n-button>右边</n-button>
    </n-popover>
```

<h2>Attributes</h2>

| 参数     |     说明     |  类型   | 可选值 | 默认值 |
| -------- | :----------: | :-----: | :----: | -----: |
| position |   弹出框位置   | String  |   left/right/top/bottom    |   left |