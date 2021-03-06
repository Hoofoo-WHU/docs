负责人：王硕
## Scroller
跨平台相同操作体验的滚动组件。
> **[info] 新增**
> 使用v-model可以绑定判断是否在顶部的Boolean值
> 



### 基本用法
``` html
<scroller style="flex-grow: 1" ref="scroller" @pullRefresh="refresh" canPullRefresh>
  <div>content</div>
</scroller>
```
```js
import Scroller from '@/components/Scroller'
export default {
  components: {
    Scroller
  },
  methods: {
    scrollTop () {
      this.$refs.scroller.scrollTop()
    },
    refresh (over) {
      // 加载内容
      over()//加载完毕后调用，放在合适的位置
    }
  }
}
```
> **[danger] 注意**
>
> Scroller一定要设置大小且滚动内容不能脱离文档流，否则将无法正常运行。

### BottomBarItem Attributes

|参数|说明|类型|可选值|默认值|
|:-----|:-----|:-----|:-----|:-----|
|can-pull-refresh|开启下拉刷新|`Boolean`|`true`、`false`|`false`|
|refreshing-text|正在刷新提示文字|`String`|-|`加载中...`|
|pullRefresh-text|下拉刷新提示文字|`String`|-|`下拉刷新`|
|activeRefresh-text|激活刷新提示文字|`String`|-|`释放刷新`|
|refresh-icon|刷新图标|`String`|`@/components/Icon/svg/`中的`SVG`文件名|`loading`|

### Events

|事件名称|说明|回调参数|
|:-----|:-----|:-----|
|beforeScrollStart|在用户触摸屏幕但还没有开始滚动时触发|-|
|scrollStart|开始滚动时触发|-|
|scrollEnd|停止滚动时触发|-|
|pullRefresh|下拉刷新时触发|`over`:通知`Scroller`刷新完毕|

### Slots

|name|说明|
|:-----|:-----|
|-|滚动内容|

### Functions

|方法名|说明|参数|
|:-----|:-----|:-----|
|scrollTop|滚动到顶部|-|
|scrollTo|滚动到任意的位置|x:横坐标,y:纵坐标|
|scrollBy|从当前位置进行滚动|x:横坐标,y:纵坐标|
|refresh|刷新滚动区域大小，当滚动内容改动后需要调用|-|









