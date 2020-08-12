# AutoComplete 自动生成



#### Maker

```js
maker.auto('自动完成', 'auto', 'xaboy').props({
	search: function (inject, value) {
    inject.self.props({dataSource : !value ? [] : [value, value + value, value + value + value]});
  }
}).emitPrefix('xaboy').emit(['change']).inject(true)
```

#### JSON

```json
{
    type: "autoComplete",
    title: "自动完成",
    field: "auto",
    value: "xaboy",
    inject: true,
    props: {
    	search: function (inject, value) {
        inject.self.props.dataSource = !value ? [] : [value, value + value, value + value + value];
      }
	}
}
```

参考:[Ant-design-vue_AutoComplete](https://www.antdv.com/components/cascader-cn/)

**value** :`String`

#### props

| 参数                          | 说明                                                         | 类型                                                         | 默认值      |
| :---------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :---------- |
| allowClear                    | 支持清除, 单选模式有效                                       | boolean                                                      | false       |
| autoFocus                     | 自动获取焦点                                                 | boolean                                                      | false       |
| backfill                      | 使用键盘选择选项的时候把选中项回填到输入框中                 | boolean                                                      | false       |
| slot="default" (自定义输入框) | 自定义输入框                                                 | HTMLInputElement / HTMLTextAreaElement                       | `<Input />` |
| dataSource                    | 自动完成的数据源                                             | slot \| [DataSourceItemType](https://github.com/vueComponent/ant-design-vue/blob/724d53b907e577cf5880c1e6742d4c3f924f8f49/components/auto-complete/index.vue#L9)[] |             |
| dropdownMenuStyle             | dropdown 菜单自定义样式                                      | object                                                       |             |
| defaultActiveFirstOption      | 是否默认高亮第一个选项。                                     | boolean                                                      | true        |
| disabled                      | 是否禁用                                                     | boolean                                                      | false       |
| filterOption                  | 是否根据输入项进行筛选。当其为一个函数时，会接收 `inputValue` `option` 两个参数，当 `option` 符合筛选条件时，应返回 `true`，反之则返回 `false`。 | boolean or function(inputValue, option)                      | true        |
| optionLabelProp               | 回填到选择框的 Option 的属性值，默认是 Option 的子元素。比如在子元素需要高亮效果时，此值可以设为 `value`。 | string                                                       | `children`  |
| placeholder                   | 输入框提示                                                   | string \| slot                                               | -           |
| defaultOpen                   | 是否默认展开下拉菜单                                         | boolean                                                      | -           |
| open                          | 是否展开下拉菜单                                             | boolean                                                      | -           |



#### events

| 事件名称              | 说明                                              | 回调参数                |
| :-------------------- | :------------------------------------------------ | :---------------------- |
| change                | 选中 option，或 input 的 value 变化时，调用此函数 | function(value)         |
| blur                  | 失去焦点时的回调                                  | function()              |
| focus                 | 获得焦点时的回调                                  | function()              |
| search                | 搜索补全项的时候调用                              | function(value)         |
| select                | 被选中时调用，参数为选中项的 value 值             | function(value, option) |
| dropdownVisibleChange | 展开下拉菜单的回调                                | function(open)          |