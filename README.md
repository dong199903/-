---
category: UI Kits
subtitle: 固钉
order: 0
title: Affix
---

## API
### Affix props

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- | --- |
| offsetTop  | 距离窗口顶部达到指定偏移量后触发 | Number | 0 |
| offsetBottom  | 距离窗口底部达到指定偏移量后触发 | Number | - |
| getTarget | 设置 `Affix` 需要监听其滚动事件的元素，值为一个返回对应 DOM 元素的函数 | () => HTMLElement | () => window |
| onChange | 在固定状态发生改变时触发| (status: boolean) => void: boolean | - |


----split----

---
category: UI Kits
subtitle: 锚点
order: 0
title: Anchor
---

## API
### Anchor props

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- | --- | --- |
| affix | 固钉模式 | boolean | true |
| offsetTop  | 同Affix固钉组件API，控制固钉的位置，affix为true时才生效 | number | 0 |
| offsetBottom  | 距离窗口底部达到指定偏移量后触发 | number | - |
| scrollOffset | 点击锚点滚动到某个位置后，可以设置额外的滚动距离 | number | 0 |
| bounds | 锚点区域边界，单位：px | number | 5 |
| getContainer | 指定滚动的容器 | () => HTMLElement | () => window |
| showInk | 是否显示高亮滚动条 | boolean | true |
| onSelect | 点击锚点时触发，返回链接 | (href: string): void | - |
| onChange | 链接改变时触发，返回新链接和旧链接 | (newHref: string, oldHref: string): void | - |

### AnchorLink Props
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- | --- | --- |
| href |锚点链接| string | - |
| title | 文字内容 | string | - |


----split----

---
category: UI Kits
subtitle: 公告
order: 0
title: Announcement
---

用于展示系统的重要信息，在页面顶部贯穿静态显示，不会自动消失，用户可点击自行关闭。

## API
### Attributes

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| title | 标题，必填参数 | string\|React.node |  — |
| description |	辅助性内容 | string\|React.node |		— |
| type | 公告类型，可选值为`success`,`warning`,`error`,`info` | string |  warning |
| showIcon | 是否显示左侧提示图标 | boolean |  false |
| closeable | 是否可关闭 | boolean | true |
| closeText | 关闭文案,当closeable为true时才有效 | string\|React.node | — |
| onClose | 关闭 announcement 时触发的事件,当closeable为true时才有效 | ()=>void | - |

----split----

---
category: Form
subtitle: 自动完成
order: 3
title: AutoComplete
---

用于使用户能够从预定义的列表中选择一个或多个选项

## API

### AutoComplete

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size | 组件的尺寸，可选值为 `small|large|normal` 或不设 | string | normal
| value | 选中的值，`multiple` 只支持 array | string \| array<object<[option](/components/auto-complete#option)>> | -
| multiple | 是否多选 | boolean | false |
| loading | 是否在搜索中 | boolean | false
| loadingMessage | `loading` 时弹层中的显示文案 | string \| () => string \ ReactNode | 搜索中
| notFoundMessage | 弹层中无选项时显示的文案 | string \| ReactNode | 无数据 |
| disabled | 是否禁用 | boolean | false
| autoFocus | 是否自动聚焦 | boolean | false
| clearable | 是否显示清除按钮 | boolean | true
| placeholder | 输入框中的提示语 | string | -
| optionLabelProp | 只对 `multiple` 生效，label 取自 [AutoComplete.Option](/components/auto-complete#AutoComplete.Option) 中的哪个属性 | string | children
| maxTagCount | 最多显示多少个 tag， 只对 `multiple` 有效 | number | -
| renderInputLabel | 选择后，自定义输入框上的显示的内容<br/> | (value: array<object<[option](/components/auto-complete#option)>>) => string \| ReactNode | -
| renderTagLabel | 只对 `multiple` 生效，选择后，自定义输入框上的显示的内容，默认显示 `Option` 上的 `label` | (option: object<[option](/components/auto-complete#option)>) => string \ ReactNode | -
| popLayer | 弹层的配置 | object<[popLayer](/components/auto-complete#popLayer)> | -
| tokenSeparators | 分词符, 可用于多项的输入, 只对 `multiple` 有效 | string | -
| onSelect | 选择时触发 | (option: object<[option](/components/auto-complete#option)>, e: Event) => void | -
| onDeselect | 取消选择时触发, 只对 `multiple` 有效 | (option: object<[option](/components/auto-complete#option)>, e: Event) => void | -
| onFilter | 筛选时触发 | (filter: string) => void | -
| onChange | 数据变化时触发 | (value: string \| array<string>) => void | -
| onFocus | 获得焦点时触发 | (e: Event) => void | -
| onBlur | 失去焦点时触发 | (e: Event) => void | -
| onPressEnter | 回车时触发 | (value: string \| object<[option](/components/auto-complete#option)>, e: Event) => void | -

> Autocomplete 的其他事件和 React 自带的 [input](https://facebook.github.io/react/docs/events.html#supported-events) 一致，如onFocus、onBlur、onInput、onKeyDown 等

#### popLayer

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| className | 弹层的样式 | string | -
| width | 弹层的宽度 | number \| string | 与 AutoComplete 输入框同宽
| maxHeight | 弹层的最大高度 | number \| string | 250
| equalTargetWidth | 弹窗是否与输入框同宽 | bool | true
| visibleInit | 设置是否初始可见 | boolean | false
| visibleAfterSelect | 设置选择/取消选择后弹层不收起 | boolean | multiple ? false : true
| visibleAfterBlur | 设置组件失去焦点后弹层不收起 | boolean | true
| visibleAfterClear | 设置清空后弹层不收起 | boolean | false
| align | 弹层定位的设置, 详见 [dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | { points: \['tl', 'bl'\], offset: \[0, 2\], overflow: { adjustX: true, adjustY: true } }
| getContainer | 定义浮层的容器，默认为 body 上新建 div | () => HTMLElement | () => document.body |

#### option

| 参数 | 说明 | 类型
| --- | --- | --- | --- |
| label | 显示的文案，[AutoComplete.Option](/components/auto-complete#AutoComplete.Option) 中 `optionLabelProp` 指定属性的值 | string
| value | [AutoComplete.Option](/components/auto-complete#AutoComplete.Option) 接收的键值 | any
| disabled | 是否禁用 | boolean
| selected | 是否已选中 | boolean

### AutoComplete.OptionGroup

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| label | 选项组的组名 | string | -
| children | 选项列表 | ReactNode | -

### AutoComplete.Option

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| value | 选项的值 | string | -
| children | 选项的内容 | ReactNode | -
| disabled | 是否禁用 | boolean | false
| selected | 是否已选中 | boolean | false
| onSelect | 点击选中时触发 | (option: object<[option](/components/auto-complete#option)>, e: Event) => void | -

## Method

| 方法 | 说明 | 返回值 |
| --- | --- | --- | --- |
| focus() | 使组件获得焦点 | -
| blur() | 使组件失去焦点，并收起下拉框 | -
| forceAlign() | 重新定位弹窗 | -


----split----

---
category: UI Kits
subtitle: 徽标
order: 0
title: Badge
---

指出现在图标或文字右上角的红色标记（圆点、数字或者文字），表示有新内容或者待处理的信息。

## API

### Badge

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 显示值 | string/number | — |
| max  | 最大值，超过最大值会显示 '{max}+'，要求 value 是 Number 类型 | number | — |
| dot | 小圆点 | boolean | false |
| hidden | 是否展示 | boolean |false |


----split----

---
category: UI Kits
subtitle: 面包屑
order: 0
title: Breadcrumb
---

用于显示当前页面的层级、路径、属性等信息，并且能够快速返回之前的任意页面。

## API
### Breadcrumb
| 参数 | 说明 | 类型  | 默认值 |
|--- |--- |--- |--- |
| size	 | 面包屑尺寸，可选值为 `small`、`normal`、`large` 或者不设  | string | normal |
| separator | 分隔符	 | string\|ReactNode |  > |
| separatorClass	 | 图标分隔符 class | string | - |


### Breadcrumb.Item 无

----split----

---
category: UI Kits
subtitle: 按钮
order: 0
title: Button
---

是用于触发一个行动并形成决策的组件。

## API

### Button

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size | Button 的大小，可选值为 `small`、`normal`、`large` 或者不设 | string | normal
| type | 设置按钮的类型，可选值为 `primary`、`success`、`warning`、`danger`、`normal` 或不设 | string | normal
| shape | 按钮的形状，可选值为 `text`、`circle`、`rect` 或者不设 | string | rect
| hoverShape | 是否 hover 上去才显示形状 | boolean | false
| icon | 图标，如果有文案，显示在文案左侧 | string | -
| rightIcon | 文案右侧图标 | string | -
| disabled | 禁用状态 | boolean | false
| loading | 加载状态 | boolean | false
| dashed | 是否边框用虚线描绘, 背景色为透明色 | boolean | false
| ghost | 是否背景色为透明色，表示为幽灵按钮 | boolean | false
| htmlType | 原生 button 的 type 属性，可选值为 `button`、`submit`、`reset` 或者不设 | string | button
| onClick | Button 点击的回调 | (e: Event) => void | -

### Button.Link
> 继承自 Button，除不支持 Button 的 onClick 外，还支持以下特殊属性：

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| href | Button.Link 跳转的链接 | string | -
| target | Button.Link 跳走的方式，可选 `_blank`、`_self`、`_top`、`_parent` 或不设 | string | _self


```html
<Button disabled loading>按钮</Button>
<Button.Link href="" target="_blanck">文字连接</Button.Link>
```


----split----

---
subtitle: 日历
title: Calendar
---
按照日历形式展示数据。当数据是日期划分时，例如考勤表、农历等使用。目前仅支持月。

## API

### Calendar

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| style| 节点样式 | CSSProperties | - |
| className| 节点类名 | string | - |
| value| **受控**,日历组件展示日期 | string/number/Date/Dayjs | - |
| isShortWeek | 周显示是否使用简写 | boolean | false |
| onChange| 日期改变的回调 | (date: Dayjs) => void | - |
| onPanelChange| 面板变化的回调| (date: Dayjs, mode: string) => void | - |
| dateRender| 自定义渲染日期单元格，返回内容会被追加到日期单元格 | (date: Dayjs) => ReactNode | - |
| dateFullRender| 自定义渲染日期单元格，返回内容完全覆盖日期单元格 | (date: Dayjs) => ReactNode | - |
| disabledDate| 不可选日期 | （date: Dayjs）=> boolean | - |
| headerRender | 自定义头部方法，可用于自定义头部 | (props: {value: Dayjs, pageShowDate: Dayjs, mode: 'month', onChangeSelectedDate: (value: Dayjs)=>void, onChangePageShowDate: (value: Dayjs)=>void, onChangeMode: (mode: 'month')=>void}) => ReactNode/void | - |


----split----

---
category: Card
subtitle: 卡片
order: 0
title: Card
---

卡片是用于围绕单个主题相关信息组成的容器。

## API

### Card

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| header | 设置卡片标题区域的内容 | string \| ReactNode | - |
| shadow | 设置阴影显示的时机。可选值为 `always` `hover` `never` | string | `never` |
| headStyle | 设置标题区域的样式 | object | `{padding: 16px 20px; border-bottom: 1px solid #e9eef7;}` |
| bodyStyle | 设置内容区域的样式 | object | `{padding: 20px;}` |


----split----

---
category: UI Kits
subtitle: 走马灯
order: 0
title: Carousel
---
在一定区域内，显示多个平级的图片或卡片，提升用户在有限空间里的阅读内容。

## 何时使用

轮播内容的数量最好在三到六个之间，数量太少没有意义，太多会让网页加载速度变慢。

## API

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| initialIndex | 初始状态索引开始 | number | -- | 0 |
| autoplay | 是否自动切换 | boolean | -- | true |
| indicatorPosition | 指示器位置 | string | outside/inside | inside |
| interval | 自动切换的时间间隔，单位毫秒 | number | -- | 3000 |
| loop | 是否循环展示 | boolean | -- | true |
| arrow | 什么时候出现 | string | always/hover/never | 默认always |

## Events

| 事件名称 | 说明 | 事件说明 | 参数 |
| --- | --- | --- | --- |
| onChange | 当轮播切换时触发 | 接收前一页索引及当前页索引 | （prev, current）=> void |

## Methods

| 方法名 | 说明 | 类型 |
| --- | --- | --- |
| prev | 从当前页左移1 |()=>void |
| next | 从当前页右移1 |()=>void |
| setActiveItem | 跳转到指定索引页，索引index从0开始|(index:number)=>void |


----split----

---
category: Cascader
subtitle: 级联
order: 0
title: Cascader
---

将数据集合，进行分类展示和选择，建议最多展示4级菜单。

## API

### Cascader

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| visible | **受控**，非必须，是否显示下拉 | boolean | - |
| defaultVisible | 默认是否显示下拉 | boolean | - |
| value | 当前选中项 | array | - |
| data | 数据源 | array | - |
| noDataText | 空数据时显示文案 | string | '暂无数据' |
| props | 自定义数据源字段名 | object | `{ label: 'label', value: 'value', children: 'children', loading: 'loading', isLeaf: 'isLeaf' }`
| changeOnSelect | 是否允许选择任意一级的选项 | boolean | false |
| expandTrigger | 展开方式。可选`click`、`hover` | string | `click`|
| formatter | 格式化输入框中显示的内容, labels 为当前匹配到的 label 数组，selectedOptions 为当前选中的 option 数组，vlaue 为当前级联的值 | function (labels, selectedOptions, value): string | - |
| separator | 选项分割符，未配置 formatter 属性时生效 | string | ' / ' |
| loadData | 当 data.isLeaf 为 false 时，并且 children 为空时，展开时调用此方法， activeItems为当前高亮链路的数组 | function (activeItems): void | - |
| filterable | 是否可搜索 | boolean | false |
| debounce | 搜索关键词去抖延迟，毫秒 | number | 300 |
| filterMethod | 过滤方法，接受 query(当前过滤条件)，item(当前项) 2个参数。符合过滤条件时应当返回 true | function(query, item): boolean | - |
| remote | 是否为远程搜索，如果为 true 时，filter-method 属性失效 | boolean | - |
| remoteMethod | 远程搜索的方法 | function (query) | - |
| noMatchText | 搜索条件无匹配时显示的文字 | string | - |
| loading | 是否为加载中状态 | boolean | - |
| loadingText | 搜索时的文案 | string | '正在加载中' |
| disabled | 是否禁用 | boolean | - |
| clearable | 是否支持清空 | boolean | - |
| size | 大小。可选`small`、`large` | string | 不设置
| placeholder | 输入框占位文本 | string | '请选择' |
| appendToContainer | 是否将下拉框插入至容器元素中。在下拉框的定位出现问题时，可将该属性设置为 false | boolean | true |
| activeItemChange | 当 changeOnSelect 为 false 时，父级选项变化时触发，参数为各父级项组成的数组 | (item: array) => void | - |
| onChange | 选择完成后的回调 | (value: array, selectedOptions: array) => void | - |
| onVisibleChange | 显示/隐藏浮层的回调 | (visible: boolean) => void | - |
| multiple | 是否多选 | boolean | false |
| maxTagCount | 最多显示多少个 tag， 只对 `multiple` 有效 | number | -
| checkStrictly | 多选时，父子节点不互相关联（true 时父子节点选中状态不再关联） | boolean | false |
| checkedStrategy | 多选时，定义选中时回填的方式 可选`all`、`parent`、`children` | string | parent |
| isKeywordHighlight | 当`filterable`为`true`时，设置是否高亮搜索关键字 | boolean | false |
| popLayer | 弹层的配置 | object<[popLayer](/components/cascader#popLayer)> | - |
| renderFooter| 自定义全局footer | string/(() => string / ReactNode) | - |

#### popLayer

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| className | 弹层的样式 | string | - |
| maxHeight | 弹层的最大高度 | number \| string | 250
| visibleInit | 是否初始可见 | boolean | false |
| visibleAfterBlur | 设置组件失去焦点后弹层不收起 | boolean | false |
| align | 弹层定位的设置, 详见 [dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | { points: \['tl', 'bl'\], offset: \[0, 2\], overflow: { adjustX: true, adjustY: true } } |
| getContainer | 定义浮层的容器，默认为 body 上新建 div | () => HTMLElement | () => document.body |


## Method

| 方法 | 说明 | 返回值 |
| --- | --- | --- | --- |
| focus() | 使组件获得焦点 | -
| blur() | 使组件失去焦点，并收起下拉框 | -


----split----

---
category: Form
subtitle: 复选
order: 0
title: Checkbox
---

单个复选框允许用户对单个称述语句设置真/假值，多个复选框使用户在一组相互独立的选项中选择多项。

## API

### Checkbox

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size | 大小，继承 CheckboxGroup 组件的 size 值，可选值为 `small`、`normal`、`large` 或者不设 | string | normal
| disabled | 禁用状态，继承 CheckboxGroup 组件的 disabled 值 | boolean | false
| indeterminate | 设置 indeterminate 状态，只负责样式控制 | boolean | false
| checked | 是否选中, 如果在 CheckboxGroup 中将根据 value 值判断得出 | boolean | false
| onChange | 值改变的回调, 通过 e.target.checked 获取是否已勾选 | (e: Event) => void | -

#### Checkbox.Group

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size | 大小, 可选值为 `small`、`normal`、`large` 或者不设 | string | normal
| value | 当前选中项的值 | array | -
| disabled | 禁用状态 | boolean | false
| onChange | 值改变的回调 | (values: Array<any\>, e: Event) => void | -

```html
<Checkbox.Group>
  <Checkbox.Group>
    <Checkbox />
  </Checkbox.Group>
  <Checkbox />
</Checkbox.Group>
```


----split----

看Col


----split----

---
category: UI Kits
subtitle: 折叠面板
order: 0
title: Collapse
---

允许用户折叠和展开一块内容区域，利用折叠面板更加有效利用空间。

## API

### Collapse 
| 参数 | 说明 | 类型  | 默认值 |
|--- |--- |--- |--- |
| value  | 当前展开的面板值，若有value则组件受控，若无则不受控 | string\|array | — | 
| defaultValue  | 默认展开的面板值 | string\|array |  — | 
| type | 面板类型，可选值为`simple`,`normal`,`tile`  | string  | normal |
| accordion | 是否为手风琴样式 | boolean | false | 
| onChange | 点击事件 | (value,e)=>void |  — | 

### Collapse.Item
| 参数 | 说明 | 类型| 默认值 |
|--- |--- |--- |--- |
| code | item的唯一标识，必填 | string\|number | — |
| title | 面板标题，必填 | string\|ReactNode | — |
| children | 子元素| ReactNode | — |
| forbidden  | 是否禁用 | boolean | false |
| showArrow | 是否显示箭头 | boolean | true |

----split----

---
category: container
subtitle: 布局容器
order: 0
title: Container
---

`<Container>`：外层容器。当子元素中包含 `<Header>` 或 `<Footer>` 时，全部子元素会垂直上下排列，否则会水平左右排列。

`<Header>`：顶栏容器。

`<Aside>`：侧边栏容器。

`<Main>`：主要区域容器。

`<Footer>`：底栏容器。

## API

### Container Attributes

| 参数      | 说明                                         | 类型   | 默认值 |
| --------- | -------------------------------------------- | ------ | ------ |
| direction | 子元素的排列方向，可选 `horizontal` / `vertical` | string | 子元素中有 `Header` 或 `Footer` 时为 vertical，否则为 horizontal |

### Header Attributes

| 参数   | 说明     | 类型   | 默认值 |
| ------ | -------- | ------ | ------ |
| height | 顶栏高度 | string\|number | 60px   |

### Aside Attributes

| 参数  | 说明       | 类型   | 默认值 |
| ----- | ---------- | ------ | ------ |
| width | 侧边栏宽度 | string\|number | 300px  |

### Footer Attributes

| 参数   | 说明     | 类型   | 默认值 |
| ------ | -------- | ------ | ------ |
| height | 底栏高度 | string\|number | 60px   |


----split----

---
category: DatePicker
subtitle: 日期选择框
order: 0
title: DatePicker
---

用于选择或输入日期，时间。

## API
以下 API 为 DatePicker、RangePicke 共享的 API。

### 共同 Attributes
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| size  | 组件大小，可选值为`small`，`large` | string | normal |
| className  | 组件 class | string | - |
| style  | 组件 style 样式 | object | - |
| disabled  | 是否禁用 | boolean | false |
| clearable  | 是否可清空 | boolean | true |
| placeholder  | 输入框提示文字，RangePicker 为数组形式 | string \| \[string, string\] | - |
| popLayer | 弹层的配置 | object<[popLayer](/components/date-picker#popLayer)> | - |
| picker | 设置选择器类型，可选值`date`，`week`，`quarter`，`halfyear` | string | date |
| hourStep | 小时选项间隔 | number | 1 |
| minuteStep | 分钟选项间隔 | number | 1 |
| secondStep | 秒选项间隔 | number | 1 |

### 共同 Events
| 事件名称 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| onFocus | 获取焦点时触发 | (event) => void | - |
| onBlur | 失去焦点时触发 | (event) => void | - |

### DatePicker \[picker=date\] Attributes
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 日期组件当前值，可选值为：可被`new Date()`解析的 | Date \| string \| number | - |
| format  | 展示的日期格式，年`YYYY`，月`MM`，日`DD`，时`HH`，分`mm`，秒`ss`，可选值可见 [日期格式](/components/date-picker#日期格式（注意大小写）) | string | YYYY-MM-DD |
| valueFormat  | 可选，绑定 onChange 事件返回值的格式。默认值为 Date 对象，可选值可见 [日期格式](/components/date-picker#日期格式（注意大小写）) | string | date |
| disabledDate | 不可选择的日期，精确到天 | (currentDate: 时间戳) => boolean | - |
| disabledTime  | 不可选择的时分秒，return 一个对象，对象里可写带有不可选择时分秒的 3 个方法和是否隐藏禁用时间属性(默认不隐藏) | (selectedDate) => Object: {<br />disabledHours: (h) => boolean,<br />  disabledMinutes: (m, selectedHour) => boolean,<br />  disabledSeconds: (s, selectedHour, selectedMinute) => boolean,<br /> hideDisabledOptions: boolean<br /> } | - |
| showToday | 是否显示今天 | boolean | false |
| isShowCurrentTimeBtn | 是否显示"此刻"按钮，在设置 format 激活时间选择器时生效 | boolean | true |
| dateRender | 自定义日期单元格的内容 | (currentDate) => React.ReactNode | - |
| renderSidebar | 自定义左侧面板内容。如果要设置 value，建议使用 new Date 转换为时间对象传入 | () => React.ReactNode | - |
| open | 控制弹层是否展开，可配合 renderSidebar 一起使用 | boolean| - |
| onOk | 点击确定按钮的回调 | (value) => void | - |
| onChange | 日期发生变化的回调，默认为 Date 格式，可受 valueFormat 控制 | (value) => void | - |
| multiple | 开启后，可以选择多个日期，仅支持年月日，年份，月份的选择，具体参考 Demo 展示 | boolean | false |
| defaultPanelTime | 用于指定时间面板初始默认时间，在 format 包含 `HH` 时生效，设置值格式如 `00:00:00` | string | HH:mm:ss |

### DatePicker \[picker=week\] Attributes
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 日期组件当前值。按以下顺序的规则解析值：1.valueFormat 指定的格式；2.可被`new Date()`解析的 | Date \| string \| number | - |
| format  | 可选，展示在输入框的日期格式。仅支持年`YYYY`，周`WW`，如`YYYY年第WW周`或`第WW周` | string | YYYY-WW周 |
| valueFormat  | 可选，绑定 onChange 事件返回值的格式。支持`date`、`timestamp`、`YYYY-MM-DD`（返回周一的日期）和`YYYY-WW` | string | date |
| disabledDate | 不可选择的日期，精确到天；一周中有一天不可选择，则此周不可选择 | (currentDate: 时间戳) => boolean | - |
| showToday | 是否显示本周 | boolean | false |
| dateRender | 自定义日期单元格的内容 | (currentDate) => React.ReactNode | - |
| renderSidebar | 自定义左侧面板内容。如果要设置 value，建议使用 new Date 转换为时间对象传入  | () => React.ReactNode | - |
| onChange | 日期发生变化的回调，默认为 Date 格式，可受 valueFormat 控制 | (value) => void | - |
| showSectionOfWeek | 显示周涉及的日期区间，如 2022-51周（12/19-12/25） | boolean | false |

### DatePicker \[picker=quarter\] Attributes
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 日期组件当前值，可选值为：可被`new Date()`解析的 | Date \| string \| number | - |
| valueFormat  | 可选，绑定 onChange 事件返回值的格式。默认值为 Date 对象，可选值可见 [日期格式](/components/date-picker#日期格式（注意大小写）) | string | date |
| disabledDate | 不可选择的日期，精确到天；对应季度中有一天不可选择，则此季度不可选择 | (currentDate: 时间戳) => boolean | - |

### DatePicker \[picker=halfyear\] Attributes
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 日期组件当前值，可选值为：可被`new Date()`解析的 | Date \| string \| number | - |
| valueFormat  | 可选，绑定 onChange 事件返回值的格式。默认值为 Date 对象，可选值可见 [日期格式](/components/date-picker#日期格式（注意大小写）) | string | date |
| disabledDate | 不可选择的日期，精确到天 | (currentDate: 时间戳) => boolean | - |

### RangePicker Attributes
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 日期组件当前值，可选值为：可被`new Date()`解析的，数组形式 | \[Date \| string \| number, Date \| string \| number\] | - |
| format  | 展示的日期格式，年`YYYY`，月`MM`，日`DD`，时`HH`，分`mm`，秒`ss`，可选值可见 [日期格式](/components/date-picker#日期格式（注意大小写）) | string | YYYY-MM-DD |
| valueFormat  | 可选，绑定 onChange 事件返回值的格式。默认值为 Date 对象，可选值可见 [日期格式](/components/date-picker#日期格式（注意大小写）) | string | date |
| separator  | 设置分隔符 | string | '-' |
| single  | RangePicker 类型，目前有单输入框跟双输入框 2 种，值为`true`值显示单框，推荐使用单框 | boolean | false |
| confirmable  | 值为`true`时，增加底部确认面板，在点击确认后才会选择值。仅在 single 为`true`时生效 | boolean | false |
| disabledDate | 不可选择的日期，精确到天。第二个参数只是 single 为`true`的时候才有 | (currentDate:timestamp, selectDate:array) => boolean | - |
| disabledTime  | 不可选择的时分秒，return 一个对象，对象里可写带有不可选择时分秒的 3 个方法和是否隐藏禁用时间属性(默认不隐藏) | ('start'\|'end') => Object: {<br />disabledHours: (h) => boolean,<br />  disabledMinutes: (m, selectedHour) => boolean,<br />  disabledSeconds: (s, selectedHour, selectedMinute) => boolean,<br /> hideDisabledOptions: boolean<br /> } | - |
| rangeMaxDateable  | 只对 RangePicker 生效，值为`true`时，时间段后区间的值为当天的最大值（format 请使用`-` 连接，如 YYYY-MM-DD HH:mm:ss） | boolean | false |
| dateRender | 自定义日期单元格的内容 | (currentDate) => React.ReactNode | - |
| renderSidebar | 自定义左侧面板内容，仅对 single 为`true`有效 | () => React.ReactNode | - |
| open | 控制弹层是否展开，可配合 renderSidebar 一起使用 | boolean| - |
| onChange | 日期发生变化的回调，默认为 Date 格式，可受 valueFormat 控制 | (\[value, value\]) => void | - |
| defaultPanelTime | 用于指定时间面板初始默认时间，在 format 包含 `HH` 时生效，设置值格式如 `['00:00:00', '23:59:59']` | \[string, string\] | HH:mm:ss |

### RangePicker \[picker=week\] Attributes
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 日期组件当前值，数组形式。按以下顺序的规则解析值：1.valueFormat 指定的格式；2.可被`new Date()`解析的 | \[Date \| string \| number, Date \| string \| number\] | - |
| format  | 可选，展示在输入框的日期格式。仅支持年`YYYY`，周`WW`，如`YYYY年第WW周`或`第WW周` | string | YYYY-WW周 |
| valueFormat  | 可选，绑定 onChange 事件返回值的格式。支持`date`、`timestamp`、`YYYY-MM-DD`（返回周一的日期）和`YYYY-WW` | string | date |
| separator  | 设置分隔符 | string | '-' |
| single  | RangePicker 类型，目前有单输入框跟双输入框 2 种，值为`true`值显示单框，推荐使用单框 | boolean | false |
| confirmable  | 值为`true`时，增加底部确认面板，在点击确认后才会选择值。仅在 single 为`true`时生效 | boolean | false |
| disabledDate | 不可选择的日期，精确到天，如果一周中有一天不可选择，则此周不可选择。第二个参数只是 single 为`true`的时候才有 | (currentDate:timestamp, selectDate:array) => boolean | - |
| dateRender | 自定义日期单元格的内容 | (currentDate) => React.ReactNode | - |
| renderSidebar | 自定义左侧面板内容，仅对 single 为`true`有效 | () => React.ReactNode | - |
| open | 控制弹层是否展开，可配合 renderSidebar 一起使用 | boolean| - |
| onChange | 日期发生变化的回调，默认为 Date 格式，可受 valueFormat 控制 | (\[value, value\]) => void | - |

### popLayer

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| className | 弹层的 class | string | - |
| visibleInit | 弹层是否初始可见 | boolean | false |
| visibleAfterSelect | 设置选择日期时间或者点确认后弹层不收起, 日期组件 DatePicker 默认值为`false`，时间组件 TimePicker 默认为`true` | boolean| TimePicker ? true : false |
| visibleAfterBlur | 设置组件失去焦点后弹层不收起 | boolean | false |
| visibleAfterClear | 设置清空后弹层不收起 | boolean | true |
| align | 弹层定位的设置, 详见 [dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | { points: \['tl', 'bl'\], offset: \[0, 2\], overflow: { adjustX: true, adjustY: true } } |
| getContainer | 定义浮层的容器，默认为 body 上新建 div | () => HTMLElement | () => document.body |


使用 format 指定输入框的格式；使用 valueFormat 指定 onChange 返回值的格式。
默认情况下，组件接受并返回 Date 对象。
### 日期格式（注意大小写）
| 格式 | 含义 | 备注 | 举例 |
| --- | --- | --- | --- |
| `YYYY` | year | - | 2019 |
| `MM` | month | - | 01 |
| `DD` | day | - | 02 |
| `HH` | hour | 24-hour clock | 03 |
| `mm` | minute | | 04 |
| `ss` | second | | 05 |
| `timestamp` | JS 时间戳 | 仅 valueFormat 可用；组件绑定值为 Number 类型 | 1483326245000 |
| `date` | Date 格式 | 仅 valueFormat 可用；组件绑定值为 Date 类型 | Thu Dec 06 2018 11:53:11 GMT+0800 (中国标准时间) |


----split----

---
category: UI
subtitle: 穿梭选择
order: 0
title: DragSelect
---

可以多选，并拖拽排序。

## API

## Props
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| draggable  | 是否可拖拽 | boolean | true |
| selectedKeys  | `受控`已选项的键值数组 | array | - |
| left | 左侧选框的对象 | object<[left]> | - |
| right | 右侧选框的对象 | object<[right]> | - |
| onChange | 数据变化后的回调 | (selectedKeys, selectedOptions, options) => void | - |


### left
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| header  | 选框顶部的展示 | ReactNode<{selectedOptions, options}> | - |
| filterable  | 是否显示筛选框 | boolean | false |
| placeholder | 筛选框placeholder | string | 请输入过滤条件
| onFilter | 筛选数据变化后的回调,参数分别为筛选输入的值、右侧选中key、所有项、空数据渲染页面| (filter, selectedKeys, options,renderNodataPage) => void | - |

### right
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| header  | 选框顶部的展示 | ReactNode<{selectedOptions, options}> | - |

## DragSelect.Group

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- | --- |
| label | 分组标题 | string | - |

## DragSelect.Item

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- | --- |
| value | 必填 | string \| number \| boolean | - |
| label | 必填 | string \| number \| boolean | - |
| disabled | 是否可以操作 | boolean | - |
| draggable | 是否不可拖拽 | boolean | - |
| className | 样式| string | - |


----split----

---
category: UI
subtitle: 抽屉
order: 0
title: Drawer
---

抽屉从父窗体边缘滑入，覆盖住部分父窗体内容。用户在抽屉内操作时不必离开当前任务，操作完成后，可以平滑地回到到原任务。

## API

### Drawer Attributes

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| visible  | **受控** 抽屉是否显示  | boolean | false |
| zIndex | 设置zIndex | number | 900 |
| title | 抽屉标题	 | string\|ReactNode | - |
| width | 抽屉宽度，number 时为像素，string 时需要带上单位 | number/string | 232 |
| height | 抽屉高度，在 placement 为 top 或 bottom 时使用 | number/string | 232 |
| closable | 是否显示右上角的关闭按钮，同时是否支持 esc 关闭	 | boolean | true |
| mask | 是否显示蒙层	 | boolean | true |
| maskClosable | 是否允许点击遮罩层关闭 | boolean | true |
| lockScroll | 是否允许整是否在 Drawer 出现时将 body 滚动锁定 | boolean | true |
| placement | 抽屉的方向，可选 top、right、bottom、left | string | right |
| getContainer	| 获取 Drawer 挂载的 HTML 节点方法，需要返回 Element 对象	 | () => HTMLElement | () => document.body |
| onClose | 点击遮罩层或右上角叉的事件 | () => void | - |
| afterVisibleChange | 切换抽屉时动画结束后的回调 | (visible: boolean) => void | - |


----split----

---
category: UI Kits
subtitle: 下拉菜单
order: 1
title: Dropdown
---

收纳更多操作元素，由按钮、操作图标、指示器或其他控件触发。

## API

### Dropdown Attributes

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |--- |
| content | 弹窗内容，必填 | ReactNode | - |
| visible | 控制下拉菜单是否显示 | boolean | false |
| arrow | 下拉框箭头是否显示 | boolean | false |
| autoDestory | 隐藏下拉菜单时是否移除下拉菜单的Dom结构，在下拉菜单特别多的情况下可节约性能 | boolean | false |
| placement | 下拉菜单显示位置,支持 `top` `bottom` `topLeft` `topRight` `bottomLeft` `bottomRight` | string | `bottom` |
| className | 下拉菜单增加类名 | string | - |
| zIndex | 设置下拉弹窗zIndex | number | 1030 |
| trigger | 触发方法，支持 `hover` `click` | string | `hover` |
| disabled | 控制该dropdown组件是否可用 | boolean | false |
| getContainer | 弹出层所挂载的 DOM 节点，默认 body | () => HTMLElement | () => document.body |
| onVisibleChange | 在下拉菜单显示状态改变时触发该回调 | (isShowed:boolean)=> void | - |


----split----

---
subtitle: 文件列表
title: Flielist
---

文件列表展示

## API

### Flielist
> 配合Upload组件使用，用于展示上传后的文件列表

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| type | 列表类型，默认2种list & picture	| string	| list	|

### Flielist.Item
| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| name | 文件名	| string	| -	|
| url | 文件地址	| string	| -	|
| download | 是否支持下载文件	| bool	| true	|
| remove | 是否支持移除文件	| bool | true |
| preview | 是否支持预览图片(type值为picture时才有效) | bool	| true	|
| onRemove | 点击删除文件按钮触发	| (index) => void	| -	|
| onDownload | 替代点击下载时的回调	| (url) => void	| -	|


----split----

---
category: Form
subtitle: 表单
order: 7
title: Form
cols: 2
---

Form主要用来管理数据的录入、校验和数据提交，为输入框、选择器、单选框等组件提供集成的能力。

#### **使用Form之前请注意：**

1.表单（From）
* 表单Form会通过监听`Form.Item`里标明`toFormItem`属性的`onChange`事件来获取表单里面所有值，所以如果你想监听`Form.Item`里组件的`onChange`事件，请用`onFieldValueChange`属性。
* Form第一层节点仅支持表单项Form.Item组件，如果你想用其它的节点加上useContext属性。

2.表单项（Form.Item）
* 如果想监听Form.Item里面组件onChange事件，请用统一用onFieldValueChange。
* 若表单项Form.Item要收集内部数据，需要在表单项上添加`formItemKey`作为表单数据的key值。
* 想要自定义Form.Item内嵌的组件，请参考 [demo](http://mtdui.sankuai.com/mtd/react/components/form#components-form-demo-11-cunstom)
* 表单项Form.Item内允许有多个组件，但对于一个表单项只收集显示标明`toFormItem`属性的组件value值。

## API


### Form

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- | --- |
| useContext | 是否使用context模式，当设置true可以使用非FormItem作为子节点，或者在FormItem外使用其他组件包裹，否则限制只能用FormItem| boolean | false
| defaultFieldsValue | 设置Form默认值，数据类型为：{ \[ form-item-key \] : value } | object | - |
| labelWidth | 设置Form内所有Form.Item标签(label)的宽度，可被Form.Item的设置覆盖 | string | - |
| labelPosition | 设置Form内所有Form.Item标签(label)的位置，可被Form.Item的设置覆盖，可设置为`left|right|top` | string | 'right' |
| onFieldValueChange | 当Form.Item的值发生改变时触发该`回调`，触发逻辑依赖Form.Item中的'trigger'属性，只有手动改变数据时候才触发，setFieldsValue时候不触发 | (formItemKey: string, formItemValue: any) => void | - |

### Form Method

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- | --- |
| validateFields | 校验指定Form.Item的值，若参数为空，则校验整个Form | (fieldNames?: array<string\>) => boolean | - |
| getFieldsValue | 获取指定Form.Item的值，若参数为空，则获取整个Form的值 | (fieldNames?: array<string\>) => object | - |
| setFieldsValue | 设置指定Form.Item的值，若参数为空，则清空整个Form的值 | (fieldObject?: object) => void | - |
| setAllFieldsValue | 设置所有Form.Item的值 | (fieldObject?: object) => void | - |
| reset | 重置整个Form值为 defaultFieldsValue 的默认值，并清空所有校验状态 | () => void | - |
| clearValidateStatus | 清空指定Form.Item的校验状态，若参数为空，则清空整个Form的校验状态 | (fieldNames?:array<string\>)  => void| - |
| getTouchedFields | 获取被手动修改过(touched)的Form.Item元素，返回FormItem的key数组 | () => Arrary | - |
| clearTouchedFields | 将已标记的touchedFields状态清空 | () => void | - |
| asyncValidateFields | 当校验含有异步规则，使用此方法。校验指定Form.Item的值，若参数为空，则校验整个Form。返回一个promise | (fieldNames?: array<string\>) => Promise<{resolve:()=>void,reject:({ invalidFields：array<string\>, errors:array<e\> })=>any}>,校验错误时返回两个错误信息：invalidFields错误字段，errors错误信息内容与validate中callback传参有关，[用法参考示例：动态校验](/components/form#components-form-demo-12-validate) | - | 

### Form.Item

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- | --- |
| formItemKey | 说明该Form.Item需要作为一个表单数据收集内部组件的值，并且设置该表单项的`key值` | string | - |
| label | Form.Item中文本域内容，若值为空或者不设该属性，则label部分不占位，若有值则默认占位为`6em` | string \| ReactNode | - |
| labelWidth | 设置Form.Item中标签(label)的宽度，继承Form中labelWidth的值，没有label或者label为空时值为`0px`，label有值时默认`6em` | string | - |
| labelPosition | 设置Form.Item中标签(label)的位置，继承Form中labelPosition的值，可设置为`left|right|top` | string | 'right' |
| span | 设置栅格布局的跨度单位默认24个栅格，超过24则换行显示，可设置`1-24`的值 | number \| string | 24 |
| offset | 设置栅格距离左侧的间隔格数，可设置`0-24`的值 | number | 0 |
| required | 是否必填，如不设置，则会根据校验规则(rules属性)生成 | boolean | false |
| rules | 校验规则，参考下方文档，更多高级用法可研究 [async-validator](https://github.com/yiminghe/async-validator)| object[] \| object | - |
| message | Form的文案，如不设置，则会根据校验规则(rules属性)生成 | string \| ReactNode | - |
> Input、AutoComplete 作为 toFormItem 时默认在 onBlur、onPressEnter 时触发 onChange
> Input.TextArea 默认在 onBlur 时触发

### 校验规则

此处的校验规则为rules下的规则，并非Form.Item中的规则。当使用rules属性时，Form.Item下的message则会失效，更多高级用法可研究[async-validator](https://github.com/yiminghe/async-validator)。

注意：请确保rules中内容书写正确，如果存在异常报错会出现调用validateFields返回true的问题，且异常错误不会出现在控制台。

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| required | 是否必选 | boolean | false |
| message | 校验文案 | string \| ReactNode | - |
| type | 校验类型可支持：string\|number\|enum\|boolean\|url\|email等，更多参考 [类型可选项](https://github.com/yiminghe/async-validator#type) | string | string |
| enum | 当type为enum类型时，该参数定义枚举内容 | array<string\> | - |
| len | 内容长度 | number | - |
| max | 内容最大长度 | number | - |
| min | 内容最小长度 | number | - |
| pattern | 正则表达式校验 | RegExp | - |
| transform | 校验前对数据字段进行转换处理 | function(value: any) => transformedValue:any | - |
| whitespace | 必填时，空格是否为错误情况 | boolean | false |
| validator | [示例参考](http://mtdui.sankuai.com/mtd/react/components/form#components-form-demo-07-value-basic)， [更多用法参考](https://github.com/yiminghe/async-validator#validator) | function(rule, value, callback, source, options) | - |


----split----

---
category: Grid
subtitle: 布局
order: 0
title: Grid
---

通过基础的 24 分栏，迅速简便地创建布局。

## API

### Row Attributes

| 参数    | 说明                                                                          | 类型   | 默认值 |
| ------- | ----------------------------------------------------------------------------- | ------ | ------ |
| gutter  | 栅格间隔                                                                      | number | 0      |
| type    | 布局模式，可选 flex，现代浏览器下有效                                         | string |
| justify | flex 布局下的水平排列方式，可选值 start/end/center/space-around/space-between | string | start  |
| align   | flex 布局下的垂直排列方式，可选值 top/middle/bottom                           | string | top    |
| tag     | 自定义元素标签                                                                | string | div    |

### Col Attributes

| 参数   | 说明                                   | 类型                                     | 默认值 |
| ------ | -------------------------------------- | ---------------------------------------- | ------ |
| span   | 栅格占据的列数                         | number                                   | 24     |
| offset | 栅格左侧的间隔格数                     | number                                   | 0      |
| push   | 栅格向右移动格数                       | number                                   | 0      |
| pull   | 栅格向左移动格数                       | number                                   | 0      |
| xs     | `<576px` 响应式栅格数或者栅格属性对象  | number/ { span: number, offset: number } |
| sm     | `≥576px` 响应式栅格数或者栅格属性对象  | number/ { span: number, offset: number } |
| md     | `≥768px` 响应式栅格数或者栅格属性对象  | number/ { span: number, offset: number } |
| lg     | `≥992px` 响应式栅格数或者栅格属性对象  | number/ { span: number, offset: number } |
| xl     | `≥1200px` 响应式栅格数或者栅格属性对象 | number/ { span: number, offset: number } |
| xxl    | `≥1620px` 响应式栅格数或者栅格属性对象 | number/ { span: number, offset: number } |
| tag    | 自定义元素标签                         | string                                   | div    |


----split----

---
category: UI Kits
subtitle: 图标
order: 3
title: Icon
---

语义化的矢量图形。

## 图标的命名规范

我们为每个图标赋予了语义化的命名，命名规则如下:


## API

由于图标字体本质上还是文字，可以使用 `style` 和 `className` 设置图标的大小和颜色。

```jsx
<Icon type="question" style={{ fontSize: 16, color: '#08c' }} />
```

| 参数  | 说明                                   | 类型    | 可缺省 | 默认值 |
| ----- | -------------------------------------- | ------- | ------ |
| type  | 图标类型                               | string  | 否 | -      |


----split----

---
category: Form
subtitle: 数字输入框
order: 0
title: InputNumber
---

又称步进器，用于输入标准的数字值，可定义范围

## API

### InputNumber Attributes

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |--- |
| value | 当前值 | number | — |
| size | 输入框大小，可选`large` `small` | string | normal |
| placeholder | placeholder值 | string | - |
| disabled | 禁用 | boolean | false |
| invalid | 无效 | boolean | false |
| max | 最大值 | number | Infinity |
| min | 最小值 | number | -Infinity |
| precision | 数值精度 | number | — |
| round | 按照精度进行四舍五入，仅在 precision 属性存在时生效 | boolean | false |
| step | 每次改变的步数，可以是小数 | number | 1 |
| formatter | 指定输入框展示值的格式 | function(value: number \| string): string | — |
| parser | 指定从 formatter 里转换回数字的方式，和 formatter 搭配使用 | function(value: number \| string): string | — |
| controls | 是否使用控制按钮 | boolean | true |
| controlsPosition | 控制按钮位置，可选`right` | string | default |
| onChange | 数值变化回调 | (value: number) => void | - |
| onFocus | input获得焦点时触发 | (event) => void | - |
| onBlur | input失去焦点时触发 | (event) => void | - |

#### Method

- `inputRef.focus()` 获取焦点
- `inputRef.blur()` 失去焦点


----split----

---
category: Form
subtitle: 输入框
order: 0
title: Input
---

指允许用户在区域内输入文本、数值等内容的组件。


## API

### Input

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| value | 输入框内容， 有 value 时，Input 为[受控组件](https://reactjs.org/docs/forms.html#controlled-components) | string \| number  | - |
| size | 控件大小。可选 `large` `normal` `small` | string | `normal` |
| disabled | 是否禁用状态 | boolean | false |
| readOnly | 是否只读状态 | boolean | false |
| clearable | 是否显示清空按钮 | boolean | true |
| addonAfter | 设置后置标签 | string \| ReactNode | - |
| addonBefore | 设置前置标签 | string \| ReactNode | - |
| prefix | 带有前缀图标的 input | string \| ReactNode | - |
| suffix | 带有后缀图标的 input | string \| ReactNode | - |
| type | 同原生 input 标签的 type 属性，见：[MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#属性)(请直接使用 `Input.TextArea` 代替 `type="textarea"`)。 | string | `text` |
| onPressEnter | 按下回车的回调 | (event) => void |  |
| onChange | 内容修改时的回调 | (event) => void |  |
| dispatchChange | 触发 onChange 的时机，可选值包含：键入 onInput、失焦 onBlur、回车 onPressEnter。注意：当在 `Form` 中使用并且包含 `toFormItem` 属性时，默认值为失焦 onBlur、回车 onPressEnter。 | array | ['onInput']
| maxLength | 限制输入的文本长度 | number \| string | Infinity |
| showCount | 是否显示文字计数 | boolean | false |
> Input 的其他事件和 React 自带的[input](https://facebook.github.io/react/docs/events.html#supported-events) 一致，如onFocus、onBlur、onInput、onKeyDown 等

#### Method

- `inputRef.focus()` 获取焦点
- `inputRef.blur()` 失去焦点

### Input.TextArea

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| autosize | 自适应内容高度，可设置为 `true|false` 或对象：`{ minRows: 2, maxRows: 6 }` | boolean \| object | false |
| disabled | 是否禁用状态 | boolean | false |
| value | 输入框内容 | string |  |
| onPressEnter | 按下回车的回调 | function(event) |  |
| onKeyDown | 按下键盘时的回调 | (event) => void |  |
| onChange | 内容修改时的回调 | (event) => void |  |
| dispatchChange | 触发 onChange 的时机，可选值包含：键入 onInput、失焦 onBlur。注意：当在 `Form` 中使用并且包含 `toFormItem` 属性时，默认值为失焦 onBlur。 | array | ['onInput'] |
| maxLength | 限制输入的文本长度 | number \| string | Infinity |
| showCount | 是否显示文字计数 | boolean | false |

> `Input.TextArea` 的其他事件和 React 自带的[textarea](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) 一致，如onFocus、onBlur、onInput、onKeyDown 等


----split----

---
category: Layer
subtitle: 层
order: 0
title: Layer
cols: 1
---

我们为mtd中的组件提供了一个统一的弹层管理组件分别是：

* 层（Layer）：负责弹出到指定的dom节点上去
* 弹层 （PopLayer）：在Layer的基础上提供了自动计算能力，保障弹出的层可以自动显示在可显示区域内。


## API

### Layer API

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| getContainer | 内容所挂载的 DOM 节点      | () => HTMLElement | 默认会在 body 下新增一个用于挂载内容的空 div 节点 |
| onMounted | 内容挂载到 DOM 上后触发 | (container: HTMLELement) => void | -

### Layer 全局方法(可全局控制所以弹窗层的默认挂载Dom)

| 使用 | 说明 |
| --- | --- |
| Layer.setContainer = () => HTMLElement | 全局设置浮层默认挂载的dom节点，用于系统级全局设置。<br />弹窗默认挂载在document.body下面，该属性可修改默认挂载的dom节点，一个系统建议只用一次<br />文档站所有的弹窗通过Layer.setContainer = () => document.querySelector('.mtd-workspace-content')都挂载在mtd-workspace-content的节点下，因为文档站没有滚动document.body，而是mtd-workspace-content。

### PopLayer API

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| align | 浮层布局位置 | object | 详见 [dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) |
| onAlign | 计算位置后触发回调 | (align: object, popEl: HTMLElement, targetEl: HTMLElement) => void |  |
| equalTargetWidth | 是否与目标节点同宽 | bool | false
| getTargetElement | 获取目标节点的 DOM 元素，用于定位 | () => HTMLElement |  |
| getContainer | 浮层渲染父节点，默认渲染到 PopLayer.setContainer() 上；组件会从目标节点开始向上寻找最近的可滚动的祖先节点，当该节点不等于Container时给其绑定监听事件使其跟随滚动；当组件只能进行单向的跟随滚动时，可设置getContainer使其实现双向跟随滚动 | (popLayerNode: HTMLElement) => HTMLElement | - |
| onMounted | 内容挂载到 DOM 上后触发 | (container: HTMLELement, instance: ReactInstance) => void | -

### PopLayer 方法

| 名称 | 说明 |
| --- | --- |
| forceAlign | 强制重新定位

### 全局方法(可全局控制弹窗层的默认挂载Dom)
| 使用 | 说明 |
| --- | --- |
| PopLayer.setContainer = () => HTMLElement | 全局设置浮层默认挂载的dom节点，用于系统级全局设置。<br />弹窗默认挂载在document.body下面，该属性可修改默认挂载的dom节点，一个系统建议只用一次<br />文档站所有的弹窗通过Layer.setContainer = () => document.querySelector('.mtd-workspace-content')都挂载在mtd-workspace-content的节点下，因为文档站没有滚动document.body，而是滚动mtd-workspace-content。


----split----

---
category: UI Kits
subtitle: 列表
order: 1
title: List
---

最基础的列表展示，可承载文字、列表、图片、段落，常用于后台数据展示页面。

## API

### List

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |--- |
| size  | 列表大小 ，可选`small` `normal` `large` | string   | normal |
| header  | 列表头部 | string/reactNode | — |
| footer | 列表底部 | string/reactNode | — |
| loading | 加载中 | boolean | false |
| loadMore | 加载更多 | reactNode | - |

### List.Item

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |--- |
| children  | 列表项 | string/reactNode   | - |

----split----

---
category: Feedback
subtitle: 加载
order: 0
title: Loading
---

显示加载中状态

## 何时使用

向用户显示系统正在积极响应。

## API

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| loading | 是否为加载中状态 | boolean | true |
| size | 组件大小，支持`small` `normal` `large`  | string | normal |
| children | 使包裹的节点显示模糊加载效果 | ReactNode | - |
| message | 描述文案 | string\|ReactNode | - |
| direction | 方向，支持`horizontal` `vertical` | string | horizontal |
| indicator | 加载指示器 | ReactNode | - |
| delay | 延迟显示加载效果（防止闪烁） | number（毫秒） |- |

### 全局自定义加载指示器

> 推荐在项目入口文件调用 Loading.setDefaultIndicator(indicator: ReactNode) 方法（同上 indicator），全局替换默认加载指示器


----split----

---
category: Form
subtitle: 菜单
order: 6
title: Menu
---

## API

### Menu

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| mode | 菜单类型，支持垂直、水平、和内嵌模式三种，对应的默认值'horizontal'、'vertical'、'inline' | string | inline |
| theme | 主题颜色，可选值值'light'、'dark' | string | light |
| defaultExpandedKeys | 初始化时展开的 SubMenu 子菜单 key 数组，只接收一次值，可以手动关闭 SubMenu。 | array<string\> | - |
| expandedKeys | **受控**，当前展开的 SubMenu 菜单项 key 数组 | array<string\> | - |
| defaultSelectedKeys | 初始化时选中的菜单项 key 数组，只接收一次值，可以手动选择其他 MenuItem | array<string\> | - |
| selectedKeys | **受控**，当前选中的菜单项 key 数组 | array<string\> | - |
| inlineCollapsed | inline 模式时菜单的收起状态 | boolean | - |
| inlineIndent | inline 模式的菜单缩进宽度 | number | 24 |
| onExpandChange | SubMenu 展开/关闭时候触发的回调 | (keys: array<string\>) => void | - |
| onSelectChange | 选中 MenuItem 时调用的回调函数 | (key: string, selectedItem: Object, e: Event) => void | - |
| autoDestory | 隐藏弹窗时是否移除弹窗的Dom结构，在弹窗特别多的情况下可节约性能 | boolean | false |
| getContainer | 弹出层所挂载的 DOM 节点，默认 body | () => HTMLElement | () => document.body |

### Menu.Item

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| key | item 的唯一标识，也是 onClick 和 onSelect 等收集的数据 | string | - |
| disabled | 是否禁用 | boolean | false |

### Menu.SubMenu

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| label | 子菜单名称 | string\|ReactNode | - |
| key | 子菜单的唯一标识，也是数据收集时候的key值 | string | - |
| disabled | 子菜单是否禁用 | boolean | false |
| onTitleClick | 点击子菜单标题	 | (key: string, e: Event) => void | false |
| popClassName | 为 SubMenu 的 popover 添加类名	 | string | - |
| popPlacement | 为 SubMenu 的 popover 改变弹窗位置 | string | - |


### Menu.ItemGroup

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| label | 分组标题 | string\|ReatNode | - |

----split----

---
category: Feedback
subtitle: 消息提示
order: 0
title: Message
---

常用于主动操作后的反馈提示。与 Notification 的区别是后者更多用于系统级通知的被动提醒。


## API

### message

- `message.success(options)`
- `message.warning(options)`
- `message.error(options)`
- `message.info(options)`
- `message.loading(options)`
- `message.open(options)`

需要传入的参数 options 为 object，具体参数如下

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| message| 通知文字 | string \| ReactNode | - |
| duration| 显示时间, 毫秒。设为 Infinity 则不会自动关闭 | number | 3000 |
| closable| 是否显示关闭按钮 | bool | false |
| onClose|  点击关闭时的回调函数, 参数为被关闭的 message 实例  | (instance) => void | - |
| icon| 自定义图标  | string \| ReactNode | - |
| key| 当前提示的唯一标志  | string | number | - |
| className| 自定义 CSS class  | string | - |
| style| 自定义内联样式  | [CSSProperties](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/e434515761b36830c3e58a970abf5186f005adac/types/react/index.d.ts#L794) | - |

#### 方法

```javascript
const msg = message.open({ message: 'hello' });
msg.update({ message: 'Hello World !' });
msg.close();
```
| 方法 | 参数 | 说明 |
| --- | --- |  --- |
| close | 无 | 关闭弹出的message |
| update | { message：要更新的内容 } | 更新的弹出的内容 |


### 全局配置

- `message.config(config)`
- `message.closeAll()`

全局的配置方法 `config()`，在调用前提前配置，全局一次生效。

```javascript
message.config({
  top: 100,
  duration: 4000,
})

```

`message` 的 config

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| duration| 显示时间, 毫秒。设为 Infinity 则不会自动关闭 | number | 3000 |
| maxCount| 最大显示数, 超过限制时，最早的消息会被自动关闭 | number | - |
| top| 消息从顶部弹出时，距离顶部的位置，单位像素。 | number | 16 |
| getContainer| 配置渲染节点的输出位置 | () => HTMLElement | () => document.body |

如需关闭所有通知，请使用：

```javascript
message.closeAll();
```


----split----

---
category: Feedback
subtitle: 模态框
order: 0
title: Modal
cols: 1
---

## 何时使用

在当前页面的基础上，通过浮层承载相关信息和操作，虽然这种方式帮助用户保留特定的上下文信息，但它们会打断用户的工作流程，需谨慎使用。

## API

### Modal

| 参数         | 说明                                                              | 类型                | 默认值              |
| ------------ | ----------------------------------------------------------------- | ------------------- | ------------------- |
| title        | 模态框标题                                                        | string \| ReactNode | -                   |
| children     | 模态框显示的内容，只接收 Modal.Body 和 Modal.Footer               | string \| ReactNode | -                   |
| footer       | 自定义模态框底部， 当 Modal 内部使用 Modal.Footer 时，footer 无效 | string \| ReactNode | -                   |
| mask         | 是否需要遮罩层                                                    | boolean             | true                |
| maskClosable | 点击遮罩层是否可以关闭                                            | boolean             | true                |
| closable     | 是否显示右上角关闭按钮                                            | boolean             | true                |
| onClose      | 点击右上角关闭按钮, 或者遮罩层触发                                               | (e) => void         | -                   |
| getContainer | 模态框挂载的容器节点                                              | () => HTMLElement   | () => document.body |

#### Modal.Body & Modal.Footer

| 参数     | 说明       | 类型                | 默认值 |
| -------- | ---------- | ------------------- | ------ |
| children | 显示的内容 | string \| ReactNode | -      |



#### method

通过 Modal.method(options)) 调起模态框时，包括

- Modal.confirm()
- Modal.info()
- Modal.warning()
- Modal.success()
- Modal.error()

Modal.confirm 默认显示确认和取消按钮，其他均显示【我知道了】

需要传入的参数 options 为 object，具体参数如下

| 参数           | 说明                                                  | 类型                                   | 默认值 |
| -------------- | ----------------------------------------------------- | -------------------------------------- | ------ |
| title          | 模态框标题                                            | string \| ReactNode                    | -      |
| message        | 模态框显示的内容                                      | string \| ReactNode                    | -      |
| okText         | 确定按钮文字, 传false时候不显示该按钮                    | string \| boolean                     | 确定   |
| cancelText     | 取消按钮文字, 传false时候不显示该按钮                    | string \| boolean                     | 取消   |
| okBtnProps     | 确定按钮属性                                          | [Button props](/components/button#API) | -      |
| cancelBtnProps | 取消按钮属性                                          | [Button props](/components/button#API) | -      |
| onOk           | 确定按钮的回调，当返回 Promise 时，resolve 后自动关闭 | (close: Function) => void  \|  Promise |        |
| onCancel       | 取消按钮的回调，当返回 Promise 时，resolve 后自动关闭 | (close: Function) => void  \|  Promise |        |
| mask   |       是否需要遮罩层                         | boolean                                | true   |
| maskClosable   | 点击遮罩层是否可以关闭                                | boolean                                | true   |
| closable   | 是否显示右上角关闭按钮                                | boolean                                | false   |


以上函数调用后，会返回一个引用，可以通过该引用更新或销毁弹窗。

```javascript
const modal = Modal.info();

modal.update({
  title: 'hello world'
});
modal.close();
```


----split----

---
category: Feedback
subtitle: 通知
order: 0
title: Notification
---

悬浮出现在页面角落，显示全局的通知提醒消息。

## API

### notification

- `notification.success(options)`
- `notification.error(options)`
- `notification.info(options)`
- `notification.warning(options)`
- `notification.open(options)`

需要传入的参数 options 为 object，具体参数如下

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| title| 通知标题 | string\|ReactNode | - |
| message| 通知文字 | string\|ReactNode | - |
| duration| 显示时间, 毫秒。设为 Infinity 则不会自动关闭 | number | 3000 |
| closable| 是否显示关闭按钮 | bool | true |
| placement| 控制弹窗的位置，可选值`topLeft` `topRight` `bottomLeft` `bottomRight`  | string | topRight |
| onClose|  点击关闭时的回调函数, 参数为被关闭的 notification 实例  | (instance) => void | - |
| icon| 自定义图标  | string\|ReactNode | - |
| key| 当前提示的唯一标志  | string | number | - |
| className| 自定义 CSS class  | string | - |
| style| 自定义内联样式  | [CSSProperties](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/e434515761b36830c3e58a970abf5186f005adac/types/react/index.d.ts#L794) | - |

#### 方法

```javascript
const toaster = notification.open({ message: 'hello' });
toaster.update({ message: 'Hello World !' });
toaster.close();
```
| 方法 | 参数 | 说明 |
| --- | --- |  --- |
| close | 无 | 关闭弹出的notification |
| update | { message：要更新的内容 } | 更新的弹出的内容 |

### 全局配置

- `message.config(config)`
- `notification.config(config)`
- `message.closeAll()`
- `notification.closeAll()`

全局的配置方法 `config()`，在调用前提前配置，全局一次生效。

```javascript
notification.config({
  bottom: 100,
  placement: 'bottomRight',
  duration: 5000,
})

```

`notification` 的 config

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| placement| 弹出位置，可选`topLeft` `topRight` `bottomLeft` `bottomRight` | string | topRight |
| maxCount| 最大显示数, 超过限制时，最早的消息会被自动关闭 | number | - |
| duration| 显示时间, 毫秒。设为 Infinity 则不会自动关闭 | number | 4500 |
| bottom| 消息从底部弹出时，距离底部的位置，单位像素。 | number | 24 |
| top| 消息从顶部弹出时，距离顶部的位置，单位像素。 | number | 24 |
| getContainer| 配置渲染节点的输出位置 | () => HTMLElement | () => document.body |

如需关闭所有通知，请使用：

```javascript
notification.closeAll();
```


----split----

---
category: Table
subtitle: 分页
order: 1
title: Pagination
cols: 1
---

用于当数据量大时，分开页面展示和浏览数据。

## API

### Pagination

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size | Pagination 的大小，可选值为 `small`、`normal`、`large` 或者不设 | string | normal
| bordered | 设置是否有边框 | boolean | true
| showTotal | 是否显示总数, 若设为 true，默认在最右侧显示 `共 xx 页` | boolean  \|  (current: number, total: number, pageSize: number) => ReactNode | false
| total | 总条数 | number \| string | -
| current | 当前页码 | number \| string | 1
| pageSize | 每页显示条数 | number \| string | 10
| folderCount | 设置页码超过几页进行折叠 | number \| string | 5
| hideOnSinglePage | 仅有一页时，隐藏分页 | boolean | false
| showQuickJumper | 显示快速跳页 | boolean | false
| showSizeChanger | 显示更改每页条数的下拉 | boolean | false
| pageSizeOptions | 每页显示个数选择器 | array | \[10,20,50,100\]
| renderItem | 用于自定义页码的结构，可用于优化 SEO | (page: number, type: string\['page', 'prev', 'next', 'jumpPrev', 'jumpNext'\], originalElement: ReactNode) => ReactNode | -
| locale | 文案, 结构和默认值请看 `locale` | object | -
| onChange | 页码变化时触发 | (current: number, pageSize: number) => void | -
| popLayer | 每页条数的下拉弹层的配置,配置详情同select popLayer | object<[popLayer](/components/select#popLayer)>

### locale

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| prev | 前一页的箭头 hover 时出现文案 | string | 上一页
| next | 后一页的箭头 hover 时出现文案 | string | 下一页
| jumpPrev | 向前几页的箭头 hover 时出现文案 | (folderCount: number) => ReactNode | (folderCount: number) => string
| jumpNext | 向后几页的箭头 hover 时出现文案 | (folderCount: number) => ReactNode | (folderCount: number) => string
| jumpTo | 快速跳页的说明文案 | string | 前往
| sizeUnit | 每页条数显示的单位 | string | 条/页

```html
<Pagination 
    current={1} 
    total={10} 
    locale={{
        prev: '上一页',
        next: '下一页',
        jumpPrev: '向前五页',
        jumpNext: '向后五页',
        jumpTo: '前往',
        sizeUnit: '条/页',
    }} />
```


----split----

---
subtitle: 弹出框确认框
title: Popconfirm
---

## 何时使用

点击元素，弹出气泡式的确认框。

## API

### Popconfirm

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| message| 内容 | string/ReactNode | - |
| icon| 图标 | string/ReactNode | - |
| okText| 确认按钮文案 | string/ReactNode | - |
| cancelText| 取消按钮文案 | string/ReactNode | - |
| okBtnProps | 确定按钮属性 | [Button props](/components/button#API) | - |
| cancelBtnProps | 取消按钮属性 | [Button props](/components/button#API) | - |
| onOk| 点击确认按钮触发 | ( ) => viod | - |
| onCancel| 点击取消按钮触发 | ( ) => viod | - |
| trigger | 触发方式 `click` `hover` `focus`  | string | `hover` |
| autoDestory | 隐藏弹窗时是否移除弹窗的Dom结构，在弹窗特别多的情况下可节约性能 | boolean | false |
| getContainer | 弹出层所挂载的 DOM 节点，默认 body | () => HTMLElement | () => document.body |
| defaultVisible | 默认是否显示 | boolean | false |
| visible | **受控**，是否显示浮层 | boolean | false |
| onVisibleChange | 显示/隐藏时的调用 | (visible: boolean) => void | - |
| autoAdjustOverflow| 自动调整弹出框位置 | bool | true |
| placement| 弹出层位置，可选 top left right bottom topLeft topRight bottomLeft bottomRight leftTop leftBottom rightTop rightBottom | string | `top` |
| align | 该值将合并到 placement 的配置中，设置参考[dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | - |
| delayShow | 延迟显示, 单元：毫秒 | number | 100 |
| delayHide | 延迟隐藏, 单元：毫秒，如果设置为0，鼠标不能移动至弹层| number | 100 |

### Popconfirm Method

| 名称 | 说明 |
| --- | --- |
| forceAlign | 强制重新定位(一般用于弹层内容变化的时候重新定位)

#### 注意
请确保 Popconfirm 的子元素能接受 onMouseEnter、onMouseLeave、onFocus、onClick 事件。


----split----

---
subtitle: 弹出框
title: Popover
---

## 何时使用

用于鼠标点击或 hover 时，弹出的气泡式非模态浮层，在内容较少、操作较轻时使用。

## API

### Popover

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size| 大小，可选`small` `normal` | string | `normal` |
| title| 弹出框标题 | string/ReactNode | - |
| content| 弹出框的内容 | string/ReactNode | - |
| trigger | 触发方式 `click` `hover` `focus`  | string | `hover` |
| autoDestory | 隐藏弹窗时是否移除弹窗的Dom结构，在弹窗特别多的情况下可节约性能 | boolean | false |
| zIndex | 设置zIndex | number | - |
| getContainer | 弹出层所挂载的 DOM 节点，默认 body | () => HTMLElement | () => document.body |
| defaultVisible | 默认是否显示 | boolean | false |
| visible | **受控**，是否显示浮层 | boolean | false |
| onVisibleChange | 显示/隐藏时的调用 | (visible: boolean) => void | - |
| onDocumentClick | trigger为`click`的时候才生效，点击弹窗以外的dom触发 | (visible: boolean) => void | - |
| autoAdjustOverflow| 自动调整弹出框位置 | bool | true |
| placement| 弹出层位置，可选 top left right bottom topLeft topRight bottomLeft bottomRight leftTop leftBottom rightTop rightBottom | string | `top` |
| align | 该值将合并到 placement 的配置中，设置参考[dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | - |
| delayShow | 延迟显示, 单元：毫秒 | number | 100 |
| delayHide | 延迟隐藏, 单元：毫秒，如果设置为0，鼠标不能移动至弹层| number | 100 |
| maxHeight | 最大高度 | number | - |

### Popover Method

| 名称 | 说明 |
| --- | --- |
| forceAlign | 强制重新定位(一般用于弹层内容变化的时候重新定位)

#### 注意
请确保 Popover 的子元素能接受 onMouseEnter、onMouseLeave、onFocus、onClick 事件。


----split----

---
category: UI Kits
subtitle: 进度条
order: 0
title: Progress
---

## 何时使用

向用户传达特定进程的进度，告知用户当前状态和预期。

## API

### Switch

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| percentage  | 百分比  | number    | 0 |
| status  | 状态,可选`success` `error` `default` | string | default |
| type  | 类型,可选`line` `circle` | string  | line |
| color  | 进度条背景色（会覆盖 status 状态颜色）  | string   | - |
| strokeWidth  | 进度条大小，type='line'时默认为8，type='circle'时默认为2 | string   | - |
| width  | 环形进度条画布宽度（只在 type=circle 时可用）  | number   | 28 |
| showInfo  | 是否显示进度数值或状态图标  | boolean    | true |



----split----

---
category: Form
subtitle: 单选
order: 0
title: Radio
---

用于在多个互斥的选项中选择一项，成组出现。

## API

### Radio

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size | 大小，继承 RadioGroup 组件的 size 值，可选值为 `small`、`normal`、`large` 或者不设 | string | normal
| disabled | 禁用状态，继承 RadioGroup 组件的 disabled 值 | boolean | false
| checked | 是否选中，如果在 RadioGroup 中将根据 value 值判断得出 | boolean | false
| value | 当前选项的值，配合 RadioGroup 使用 | string | - |
| onChange | 值改变的回调，通过 e.target.checked 获取是否已勾选 | (e: Event) => void | -

#### Radio.Group

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| children | 选项，可以是 Radio，或者自定义 | array | - |
| size | Radio 的大小，可选值为 `normal`、`large`、`small` 或者不设 | string | normal |
| value | 已选中项的值 | any | - |
| disabled | 禁用状态 | boolean | false |
| onChange | Radio.Group 的值改变的回调 | (value: any, e: Event) => void | - |

#### Radio.Button

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size | 大小，继承 RadioGroup 组件的 size 值，可选值为 `small`、`normal`、`large` 或者不设 | string | normal
| disabled | 禁用状态，继承 RadioGroup 组件的 disabled 值 | boolean | false
| checked | 是否选中，如果在 RadioGroup 中将根据 value 值判断得出 | boolean | false
| value | 当前选项的值，配合 RadioGroup 使用 | string | - |
| onChange | 值改变的回调，通过 e.target.checked 获取是否已勾选 | (e: Event) => void | -


----split----

---
category: UI Kits
subtitle: 评分
order: 0
title: Rate
---

## API

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |--- |
| value | 当前绑定值，受控 | number | — |
| defaultValue | 默认值 | number | 0 |
| allowHalf | 是否允许半选 | boolean | false |
| allowClear | 是否允许清除 | boolean | false |
| count | 最大分值 | number | 5 |
| disabled | 是否为只读 | boolean | false |
| classes | root元素的class，不同分段。key 值为分段的界限值，value 为对应的 class | { [value]: className } | - |
| icon | icon 的 class，object 类型时 key 值为分段的界限值。value 为对应 class | string / { [value]: icon } | 'mtdicon-star' |
| voidIcon | 未选中 icon 的类名 | string | - |
| disabledVoidIcon | 只读时未选中 icon 的类名 | string | - |
| color | icon 的颜色，object 类型时 key 值为分段的界限值，value 为对应的颜色 | string / { [value]: color } | - |
| voidColor | 未选中 icon 的颜色 | string | - |
| disabledVoidColor | 只读时未选中 icon 的颜色 | string | - |
| texts | 辅助文字数组 | array | - |
| textRender | 辅助文字自定义内容 | (value: number): string \| element | - |
| tooltipProps | tooltip 的额外配置 | object | - |
| tooltipRender | tooltip自定义内容 | (value: number): string \| element | - |
| onChange | 分值改变时触发 | (rate: string): void | - |


----split----

看Grid


----split----

---
category: Form
subtitle: 选择器
order: 3
title: Select
---

用于使用户能够从预定义的列表中选择一个或多个选项

## API

### Select

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size | 组件的尺寸，可选值为 `small|large|normal` 或不设 | string | normal
| value | 选中的值，`multiple` 只支持 array | string \| object<[option](/components/select#option)> <br > 多选multiple： array<string \| object<[option](/components/select#option)>> | -
| multiple | 是否多选 | boolean | false |
| onlyKeyValue | 值为true时，onChange方法参数为 [option](/components/select#option) 中的value值。默认参数为[option](/components/select#option)对象 | boolean | false |
| loading | 是否在搜索中 | boolean | false
| loadingMessage | `loading` 时弹层中的显示文案 | string \| () => string \ ReactNode | 搜索中
| notFoundMessage | 弹层中无选项时显示的文案 | string \| () => string \ ReactNode | 无数据
| filterable | 是否支持筛选 | boolean | true
| filterOption | 是否支持本地筛选, 当与`onFilter`同时存在，则默认远程筛选 | boolean \| (inputValue: [string], option: [object]) => boolean | false
| disabled | 是否禁用 | boolean | false
| autoFocus | 是否自动聚焦 | boolean | false
| clearable | 是否显示清除按钮 | boolean | true
| autoClearSearchValue | 是否在选中项后清空搜索框，只在 `multiple=true ` 时有效 | boolean | true
| icon | 右侧下拉图标 | string \| bool \| () => ReactNode | down-thick
| placeholder | 输入框中的提示语, `filterable` 时默认 `请输入`，否则 `请选择` | string | -
| popLayer | 弹层的配置 | object<[popLayer](/components/select#popLayer)> | -
| optionLabelProp | label 取自 [Select.Option](/components/select#Select.Option) 的哪个属性 | string | children
| renderInputLabel | 选择后，输入框内容的自定义渲染方法 | value => string \ ReactNode | -
| renderTagLabel | 只对 `multiple` 生效，选择后，输入框内 tag 的自定义渲染方法，默认显示 `Option` 上的 `label` | option => string \ ReactNode | -
| renderPopHeader | 自定义弹窗Header内容 | option => string \ ReactNode | -
| renderPopFooter | 自定义弹窗Footer内容 | option => string \ ReactNode | -
| maxTagCount | 最多显示多少个 tag， 只对 `multiple` 有效 | number | -
| onSelect | 选择时触发 | (option: object<[option](/components/select#option)>, e: Event) => void | -
| onDeselect | 取消选择时触发, 只对 `multiple` 有效 | (option: object<[option](/components/select#option)>, e: Event) => void | -
| onChange | 选择变化时触发，参数value默认为[option](/components/select#option)对象，当`onlyKeyValue`为true时，value为 [option](/components/select#option) 中的value值 | (value: string \| array<[string]> \| object<[option](/components/select#option)>, e: Event, keyValue: string \ array) => void | -
| onFilter | 筛选时触发 | (filter: string) => void | -
| onKeyDown | 输入框聚焦时键盘按键触发 | (e: Event) => void | -
| onFocus | 输入框聚焦时触发 | (e: Event) => void | -
| onBlur | 输入框失去焦点时触发 | (e: Event) => object | -
| onVisibleChange | 弹层展开收起时触发 | (visible: boolean) => void | -
| onPopupScroll | 下拉列表滚动时的回调 | (e: Event) => void | -

#### popLayer

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| className | 弹层的样式 | string | -
| width | 弹层的宽度 | number \| string | 与输入框同宽
| maxHeight | 弹层的最大高度 | number \| string | 250
| zIndex | 设置下拉弹窗zIndex | number | 1030 |
| equalTargetWidth | 弹窗是否与输入框同宽 | bool | true
| visibleInit | 是否初始可见 | boolean | false
| visibleAfterSelect | 设置选择/取消选择后弹层不收起 | boolean | multiple ? false : true
| visibleAfterBlur | 设置组件失去焦点后弹层不收起 | boolean | true
| visibleAfterClear | 设置清空后弹层不收起 | boolean | false
| align | 弹层定位的设置, 详见 [dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | { points: \['tl', 'bl'\], offset: \[0, 2\], overflow: { adjustX: true, adjustY: true } }
| getContainer | 定义浮层的容器，默认为 body 上新建 div | () => HTMLElement | () => document.body |

#### option

| 参数 | 说明 | 类型
| --- | --- | --- | --- |
| label | 显示的文案，[Select.Option](/components/select#Select.Option) 中 `optionLabelProp` 指定属性的值 | string
| value | [Select.Option](/components/select#Select.Option) 接收的键值 | any
| disabled | 是否禁用 | boolean
| selected | 是否已选中 | boolean
| originOption | [Select.Option](/components/select#Select.Option) 中 `originOption` 指定属性的值 | any | -

### Select.OptionGroup

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| label | 选项组的组名 | string | 否 | -
| children | 选项列表 | ReactNode | 否 | -

### Select.Option

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| value | 选项的值 | string | 否 | -
| children | 选项的内容 | ReactNode | -
| disabled | 是否禁用 | boolean | false
| selected | 是否已选中 | boolean | false
| originOption | 原始的option数据，使用时需手动传入 | any | -

## Method

| 方法 | 说明 | 返回值 |
| --- | --- | --- | --- |
| focus() | 使组件获得焦点 | -
| blur() | 使组件失去焦点，并收起下拉框 | -



----split----

---
subtitle: 滑块
title: Slider
---

## 何时使用

用于在一个数值区间内进行数值选择，并展示当前值。

## API

### Slider

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size| 尺寸，可选`small` `normal` | string | normal |
| value| 当前滑块的值 | number\|Array<number\> | - |
| disabled| 禁用 | boolean | false |
| range| 是否为范围选择 | boolean | false |
| min| 滑动区域最小值 | number | 0 |
| max| 滑动区域最大值 | number | 100 |
| thresholds| 自定义区域颜色 <br /> key 的类型必须为 number 且取值在闭区间 [min, max] 内，value 为区域颜色色值 | { number: string } <br /> 例如 { 60: '#333', 80: '#666', 100: '#999' } | - |
| step| 步长，取值必须大于 0，并且可被 (max - min) 整除。当 marks 不为空对象时，可以设置 step 为 null，此时 Slider 的可选值仅有 marks 标出来的部分。 | number \| null | 1 |
| marks| key 的类型必须为 number 且取值在闭区间 [min, max] 内，每个标签可以单独设置样式 | { number: string\|ReactNode } | - |
| vertical| 是否显示为垂直样式 | boolean | false |
| showTooltip| 是否显示滑块的文字提示 | boolean | true |
| tooltipFormator| 自定义文字提示 | (value) => ReactNode | true |
| onChange | 值改变的回调  | (value) => void | - |
| onAfterChange | 值改变时触发（使用鼠标拖曳时，只在松开鼠标后触发） | (value) => void | - |

### Slider Method

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| focus() | 获取焦点 |  |  |
| blur() | 失去焦点 |  |  |


----split----

---
category: UI Kits
subtitle: 步骤条
order: 0
title: Steps
---

是引导用户按照流程完成任务的分步导航条，可根据实际应用场景设定步骤。

## API

### Steps Attributes

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| size | 指定大小，目前只支持普通和迷你（small） | string | — |
| dot | 点状步骤条 | boolean | false |
| direction | 指定步骤条方向。目前支持水平（horizontal）和竖直（vertical）两种方向 | string | horizontal |
| active | 指定当前步骤，从 0 开始记数  | number | 0 |
| status | 指定当前步骤的状态，可选 wait/process/finish/error/cancel | string | process |
| space | 每个横向 step 的宽度，不填写则自适应，支持百分比。 | number / string | - |
| labelPlacement | 指定title&description放置位置，默认水平放图标右侧，可选 vertical 放图标下方 | string | horizontal |

## Step Attributes
| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| title | 标题 | string/ReactNode | — |
| description | 描述性文字 | string/ReactNode | — |
| icon | 传入 Icon 组件的type，或者自定义 Icon | string/ReactNode | - |
| status | 设置当前步骤的状态，不设置则根据 steps 的active确定状态，可选值：wait / process / finish / error / cancel | string | - |



----split----

---
subtitle: 开关
title: Switch
---

## 何时使用

表达同一行为两种互斥状态之间的切换。

## API

### Switch

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| size| 尺寸，可选`small` `normal` | string | normal |
| checked| 当前是否选中 | boolean | false |
| disabled| 禁用 | boolean | false |
| checkedChildren| 选中时的内容 | string/ReactNode | - |
| unCheckedChildren| 非选中时的内容 | string/ReactNode | - |
| autoFocus | 是否自动聚焦  | boolean | - |
| loading| 是否加载中 | boolean | false |
| onChange | 值改变的回调, 通过 e.target.checked 获取是否开启  | (e: Event) => void | - |
| onFocus | 获得焦点的回调  | (e: Event) => void | - |
| onBlur | 失去焦点的回调  | (e: Event) => void | - |

#### Method

- `switchRef.focus()` 获取焦点
- `switchRef.blur()` 失去焦点


----split----

---
category: Table
subtitle: 表格
order: 0
title: Table
cols: 1
---

为一个二维数组,其中数据出现在单元格中,从行和列的交集中获取其上下文。用表格展示的信息易于扫描,便于用户查找和比较。

## API

### Table

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| emptyText | 无数据时的提示文案 | string \| () => ReactNode | 是 | 暂无数据
| size | 组件的尺寸,可选值为 `small|large|normal` 或不设 | string | 是 | normal
| bordered | 是否使用边框, 可选值为 `cell`、`row`、`none` 或不设 | string | 是 | row
| striped | 是否使用条纹底色 | boolean | 是 | false
| rowClassName | 行样式 | string \| (row, index) => string | 是 | -
| cellClassName | 单元格样式 | (row, column, rowIndex, colIndex) => string | 是 | -
| useSticky | 表头固定或表列固定是否使用 position:sticky 实现，该设置可提升表格性能，（注：IE 11 及以下版本浏览器不支持该属性） | boolean | 是 | false
| magnet | 表格头吸顶固定, 如果启用吸顶固定, 那么表头滚动到视口顶部 `magnet` 像素时将吸附, `magnet` 可设置为 `true|false`, 或者 `100|100px`, 建议设置一个数字, 默认单位为 px, 如果设置为 `true`, 默认使用 0 像素时吸附 | number \| string \| boolean | 是 | -
| scroll | 横向、纵向滚动的配置。如果 `scroll.y` 不为 `false`, 代表表头固定，表体滚动 | object<[scroll](/components/table#scroll)> | 是 | scroll: { x: false, y: false }
| rowKey | 表格行的主键，默认会自动生成唯一key，注：rowKey不能重复 | string \| (row: object) => string | 是 | -
| selectOnClickRow | 点击行时触发选中 | boolean | 是 | false
| expandOnClickRow | 点击行时触发展开 | boolean | 是 | false
| disabledKey | 行数据中用于控制选择、展开是否禁用的字段名 | string | 是 | disabled
| data | 表格的数据 | array | 是 | -
| columns | 表头的配置 | array<object<[column](/components/table#column)>> | 是 | -
| rowExpansion | 行中展开按钮的配置 | bool \| object<[rowExpansion](/components/table#rowExpansion)> | 是 | -
| rowSelection | 行中选择框的配置 | bool \| object<[rowSelection](/components/table#rowSelection)> | 是 | -
| resizable | 表格伸缩宽度的支持(只支持 '基本使用' 和 'useSticky' 的简单表头，如上，useSticky 情况下，需要设置列的宽度) | boolean | 是 | false
| getResizedTableDOMInfo | 拖拽列后触发，获取 index, columnWidth, tableWidth 等信息 | ({index, columnWidth, tableWidth}) => void | 是 | -
| onRowClick | 行点击的时候触发 | (row: object, index: number, e: Event) => void | 是 | -
| onRowMouseEnter | 某一行触发mouse enter事件的时候触发 | (row: object, index: number, e: Event) => void | 是 | -
| onRowMouseLeave | 某一行触发mouse leave事件的时候触发 | (row: object, index: number, e: Event) => void | 是 | -
| onSelect | 可用于阻止行选中, 点击选项框时调用, 配合 `rowSelection.selectedKeys` 使用, 需要主动更改表格的已选行, `selectedKeys` 是点击操作前已选行主键 | (row: object, index: number, { selectedKeys: array<any\>, selectedRows: array<object\> }, e: Event) => void | 是 | -
| onSelectAll | 可用于阻止全选, 点击表头全选时调用,不会更新 `rowSelection.selectedKeys`, 需要主动更改表格的已选行, 其中 `keys` 是所有行主键, `selectedKeys` 是点击操作前已选行主键 | (keys, selectedKeys: array<any\>, selectedRows: array<object\>, e: Event) => void | 是 | -
| onSelectChange | 点击表头全选且未传 `onSelectAll` 时调用,或在点击表体选项框且未传 `onSelect` 时调用, 如果未传 `rowSelection.selectedKeys`, 会默认更新 `selectedKeys` | (selectedKeys: array<any\>, selectedRows: array<object\>, e: Event) => void | 是 | -
| onExpand | 可用于阻止展开收起, 点击展开收起时调用不会更新 `rowExpansion.expanedKeys`, 需要主动更改表格的展开行, `expanedKeys` 是点击操作前已展开行主键 | (row: object, index: number, { expandedKeys: array<any\>, expandedRows: array<object\> }, e: Event) => void | 是 | -
| onExpandChange | 点击展开收起且未传 `onExpand` 时调用，如果未传 `rowExpansion.expanedKeys`, 会默认更新 `expandedKeys` | (expandedKeys: array<any\>, expandedRows: array<object\>, e: Event) => void | 是 | -

#### scroll

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| x | 横向滚动的宽度, 可设置为 `true|false` 或 `100|'100px'`, 建议设置一个数字, 默认单位为 px | boolean \| number \| string | 是 | false
| y | 纵向滚动的高度, 可设置为 `true|false` 或 `100|'100px'`, 建议设置一个数字, 默认单位为 px | boolean \| number \| string | 是 | false

#### column

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| dataKey | 表列的主键, 表格行中每列显示 `data` 中的相应字段的值 | string | 否 | -
| label | 表头的文案 | string \| (column: object<[column](/components/table#column)>, index: number) => string \ ReactNode | 是 | -
| className | 列样式 | string | 是 | -
| thClassName | 表头列样式 | string \| (column) => string | 是 | -
| width | 表列的宽度, `100|'100px'`, 建议设置一个数字, 默认单位为 px | number \| string  | 是 | -
| fixed | 设置表列是否固定、及固定的方位, 可设置为 `true|false` 或 `left`, `true` 等同于 `left` | boolean \| string | 是 | false
| columnGroup | 表列合并时子表头的配置 | array<object<[column](/components/table#column)>> | 是 | -
| columnVisible | 合并表头时子表头是否显示 | boolean | 是 | true
| render | 渲染单元格时调用 | (value: any, row: object, column: object<[column](/components/table#column)>, { index: number, level: number }) => ReactNode  \|   { children: ReactNode, props: { colSpan: number, rowSpan: number } | 是 | -

#### rowSelection

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| multiple | 是否可多选 | boolean | 是 | true
| checkallVisible | 是否显示全选按钮 | boolean | 是 | true
| className | 选择框的样式 | string | 是 | -
| style | 选择框的样式, 例如 paddingRight, width 等, width 支持 `100|'100px'`, 建议设置一个数字, 默认单位为 px | object | 是 | -
| fixed | 设置选项框是否固定、及固定的方位, 可设置为 `true|false` 或 `left|right`, `true` 等同于 `left` | boolean \| string | 是 | false
| parentSelectable | 是否能选中非叶子节点 | bool | 是 | true
| disabledSelectKey | 行数据中用于控制选择是否禁用的字段名 | string | 是 | disabledSelect
| leafSelectable | 是否能选中叶子节点 | bool | 是 | true
| selectStrictly | 设置父子节点不联动 | bool | 是 | true
| selectStrategy | 选择节点后，返显策略，只在 `selectStrictly` 为 `false` 时有效，可选值为 `all(返回所有的节点)|parent(当父子节点都选中时返回父节点)|child(当父子节点都选中时只返回子节点)` | bool | 是 | true
| selectedKeys | `受控`,当前选中的行主键的数组 | array | 是 | -
| defaultSelectedKeys | 默认选中的行主键的数组, 优先级高于 `defaultSelectAll` | array | 是 | -
| defaultSelectAll | 默认全选 | boolean | 是 | true
| getCheckboxProps | 设置选项框的属性,参照 `Checkbox` 接收的属性 | (row: object, index: number) => object | 是 | -
| indeterminable | 设置是否显示半选状态 | boolean | 是 | true

#### rowExpansion

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| childrenKey | 树形展示时, 匹配 `data` 中的哪个属性来显示子节点 | string | 是 | children
| accordion | 展开一个节点时关闭其他同级节点；如果设置为true时autoExpandParent不可为true | bool | 是 | -
| expandedKeys | `受控`,当前展开的行主键的数组，设置后忽略 `defaultExpandAll | defaultExpandLevel | defaultExpandedKeys` | array | 是 | -
| defaultExpandedKeys | 默认展开的行主键的数组, 设置后忽略 `defaultExpandAll | defaultExpandLevel` | array | 是 | -
| defaultExpandAll | 默认展开全部, 设置后忽略 `defaultExpandLevel | autoExpandParent | defaultExpandParent` | boolean | 是 | -
| autoExpandParent | 是否自动展开 expandedKeys 节点的父节点，父节点收起时同时收起子节点，_需要配合 expandedKeys || defaultExpandedKeys 使用_, 设置后忽略 `defaultExpandLevel | defaultExpandParent` | bool | 是 | false
| defaultExpandParent | 是否初始状态下自动展开父节点, 设置后忽略 `defaultExpandLevel` | bool | 是 | false
| defaultExpandLevel | 默认展开到第几层级 | number | 是 | -
| disabledExpandKey | 行数据中用于控制展开是否禁用的字段名 | string | 是 | disabledExpand
| loadingKeys | 展开按钮处于加载状态的行健集合 | string[] | 是 | []
| render | 自定义展开行的渲染, 优先级高于从 `data` 中获取 `childrenKey` 来展示 | (row: object, index: number, level: number) => ReactNode | 是 | -
| icon | 自定义展开收起图标的渲染 | string \| (expanded: bool, row: object, index: number, level: number, { leaf: bool, parentRow: object, loading: bool }) => ReactNode | 是 | triangle

### Table.ColumnGroup

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| children | 被合并的表头, 只接收 `Table.Column` | reactNode | 否 | -
| label | 合并表头的文案 | string \| (column: object, index: number) => string \ ReactNode | 否 | -
| columnVisible | 被合并的表头是否可见 | boolean | 是 | true
| fixed | 设置表列固定, 可选值为 `true|false` 或 `left|right`, `true` 等同于 `left` | string | 是 | -

### Table.Column

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| dataKey | 表列的主键, 表格行中每列显示 `data` 中的相应字段的值 | string | 否 | -
| children | 表头的文案, 优先级高于 `label` | reactNode | 否 | -
| label | 表头的文案 | string \| (column: object<[column](/components/table#column)>, index: number) => string \ ReactNode | 是 | -
| render | 渲染单元格时调用 | (value: any, row: object, column: object<[column](/components/table#column)>, { index: number, level: number }) => ReactNode | 是 | -
| fixed | 表列固定, 可选值为 `true|false` 或 `left|right`, `true` 等同于 `left`。当该列头隐藏时, 需要在 `ColumnGroup` 上设置 `fixed`, 此处 `fixed` 失效。 | string | 是 | -
| width | 表列的宽度, 可设置为 `true|false` 或 `100|'100px'`, 建议设置一个数字, 默认单位为 px | string | 是 | -

``Table 接收的 Table.ColumnGroup 和 Table.Column 是 columns 的语法糖。``

## Method

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| getSelectedRows | 获取当前已选择的项 | () => array<object\> | -
| getExpandedRows | 获取当前已展开的项 | () => array<object\> | -


```html
<Table>
  <Table.ColumnGroup>
    <Table.Column />
  </Table.ColumnGroup>
  <Table.Column />
</Table>
```


----split----

---
subtitle: 标签页
title: Tabs
---

## 何时使用

用于展示同一信息对象的不同类别或视角，可以互相之间快速切换。

## API

### Tabs

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| activeKey| 当前选中的标签页 | string | - |
| defaultActiveKey| 非受控使用时，默认显示的标签页 | string | - |
| size| 尺寸，可选`small` `normal` `large` | string | normal |
| type| 风格类型， 可选`line` `card` `bordred-card` `editable-card` | string | line |
| tabBarPosition| 选项卡位置， 可选 `top` `left` `right` `bottom` | string | top |
| tabBarExtraContent | 右侧额外的操作区域 | ReactNode | - |
| onAdd | 点击添加按钮时触发 | ( ) => void| - |
| onRemove | 点击关闭按钮时的回调  | (removedKey: string) => void | - |
| hideAdd| 是否隐藏加号图标，在 type="editable-card" 时有效 | boolean | false |
| onChange | 切换标签页时触发，和 activeKey配合实现受控 | (activeKey: string) => void | - |
| onPrevClick | 点击向前翻页按钮时的回调 | ( ) => void | - |
| onNextClick | 点击向后翻页按钮时的回调 | ( ) => void | - |
| autoDestory | 是否渲染隐藏Tab的DOM结构，默认渲染 | boolean | false |

### Tabs.TabPane

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| key| 对应 activeKey | string | - |
| label| 选项卡标题 | string/ReactNode | - |
| children| 选项卡内容 | string/ReactNode | - |
| closable| 编辑模式时，是否可关闭 | boolean | true |
| disabled| 禁用 | boolean | false |


----split----

---
subtitle: 标签
title: Tag
---

小块的信息项

## 何时使用

小块的信息项，用来通过视觉快速区分选择的内容。


## API

### Tag

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| theme| 预设颜色，传入`预设名` | `green`、`orange`、`red`、`blue`、`gray` |`blue` |
| size| 尺寸，可选`small` `normal` `large` | string | normal |
| type| 类型 | `pure` `text` `bordered` | `bordered` |
| closeable| 是否可以关闭 | boolean | false |
| color| 自定义颜色，传入有效色值，如`#d3fdda` `red`  | string | - |
| onClose | 点击关闭按钮时的回调  | e => void | - |
| onClick | 点击时触发 | e => void | - |


----split----

---
category: TimePicker
subtitle: 时间选择框
order: 0
title: TimePicker
---

## API

### TimePicker Attributes

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 时间组件的当前值，如 '11:00'，'13:00'	 | string | - |
| format  | 展示的time格式，时`HH`，分 `mm`，秒 `ss` ，启用12小时制使用`hh`| string | HH:mm |
| size  | 组件大小，可选值为`small|large` | string | - |
| disabled  | 是否禁用 | boolean | false |
| clearable  | 是否可清空 | boolean | true |
| confirmable  | 是否需要确认时间按钮，点击确认后才触发onchange | boolean | false |
| placeholder  | 输入框提示文字 | - |
| disabledHours | 禁止选择部分小时选项 | (h) => boolean  | - |
| disabledMinutes	| 禁止选择部分分钟选项，传入第二个参数指定小时 | (m, selectedHour) => boolean  | - |
| disabledSeconds | 禁止选择部分秒选项，传入第二个参数指定小时，第三个参数指定分钟 | (s, selectedHour, selectedMinute) => boolean  | - |
| hideDisabledOptions | 与`disabledHours` `disabledMinutes` `disabledSeconds`连用，设置是否隐藏禁用的选项 | boolean | false |
| popLayer | 弹层的配置 | object<[popLayer](/components/time-picker#popLayer)> | - |
| hourStep | 小时选项间隔 | number | 1 |
| minuteStep | 分钟选项间隔 | number | 1 |
| secondStep | 秒选项间隔 | number | 1 |
| defaultPanelTime | 用于指定初始默认时间，设置值格式如 `00:00:00` | string | HH:mm:ss |

### RangePicker Attributes

| 参数 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| value  | 时间组件的当前值，如 \['11:00', '22:00'\]	 | string | - |
| format  | 展示的time格式，时`HH`，分 `mm`，秒 `ss` | string | HH:mm |
| separator | 设置分隔符 | string | '-' |
| size  | 组件大小，可选值为`small|large` | string | - |
| disabled  | 是否禁用 | boolean | false |
| clearable  | 是否可清空 | boolean | true |
| placeholder  | 输入框提示文字, RangePicker为数组形式\[string, string\]| string/\[string, string\] | - |
| disabledHours | 禁止选择部分小时选项| (h) => boolean  | - |
| disabledMinutes	| 禁止选择部分分钟选项，传入第二个参数指定小时 | (m, selectedHour) => boolean  | - |
| disabledSeconds | 禁止选择部分秒选项，传入第二个参数指定小时，第三个参数指定分钟 | (s, selectedHour, selectedMinute) => boolean  | - |
| hideDisabledOptions | 与`disabledHours` `disabledMinutes` `disabledSeconds`连用，设置是否隐藏禁用的选项 | boolean | false |
| popLayer | 弹层的配置 | object<[popLayer](/components/time-picker#popLayer)> | - |
| hourStep | 小时选项间隔 | number | 1 |
| minuteStep | 分钟选项间隔 | number | 1 |
| secondStep | 秒选项间隔 | number | 1 |
| autoExchange | 确认选择时间后自动交换位置，保证开始时间小于结束时间 | boolean | true |
| defaultPanelTime | 用于指定初始默认时间，设置值格式如 `['00:00:00', '23:59:59']` | [string, string] | HH:mm:ss |

### TimePicker Events
| 事件名称 | 说明 | 类型 | 默认值 |
|--- |--- |--- |--- |
| onChange | 时间发生变化的回调 (有确认按钮的时候，点击确认按钮才触发) | (value) => void | - |
| onFocus | 获取焦点时触发 | (event) => void | - |
| onBlur | 失去焦点时触发 | (event) => void | - |

### popLayer

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| className | 弹层的class | string | - |
| visibleInit | 弹层是否初始可见 | boolean | false |
| visibleAfterSelect | 选择时间后弹层是否显示(范围时间选择组件中的确认时间按钮始终显示，该属性不生效) | boolean | true |
| visibleAfterBlur | 组件失去焦点后弹层是否显示 | boolean | false |
| visibleAfterClear | 清空后弹层是否显示 | boolean | true |
| align | 弹层定位的设置, 详见 [dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | { points: \['tl', 'bl'\], offset: \[0, 2\], overflow: { adjustX: true, adjustY: true } } |
| getContainer | 定义浮层的容器，默认为 body 上新建 div | () => HTMLElement | () => document.body |

### 日期格式（注意大小写）
| 格式 | 含义 | 备注 | 举例 |
| --- | --- | --- | --- |
| `HH` | hour | 24-hour clock | 15 |
| `hh` | hour | 12-hour clock | 下午 03 |
| `mm` | minute | | 30 |
| `ss` | second | | 59 |

----split----

---
category: UI Kits
subtitle: 时间轴
order: 0
title: Timeline
---

按时间顺序垂直展示的信息

## API

### Timeline

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
|--- |--- |--- |--- |--- |
| mode | 通过设置 mode 可以改变时间轴和内容的相对位置，可选值为 `left` `right` `alternate` | string | 是 | `right` |

### Timeline.Item

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
|--- |--- |--- |--- |--- |
| title | 节点的标题 | string \| ReactNode | 是 | - |
| content | 节点的内容 | string \| ReactNode | 是 | - |
| icon | 节点图标 | string \| ReactNode | 是 | - |


----split----

---
subtitle: 文字提示
title: Tooltip
---

简易文本浮层

## 何时使用

用于更多信息的缩略展示，不承载复杂文本和操作。通过鼠标移入显示、移出消失查看。

## API

### Tooltip

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| message| 文字提示的内容 | string/ReactNode | - |
| size| 大小，可选`small` `normal` | string | `normal` |
| color | 颜色，可选 `dark` `light` | string | `dark` |
| trigger | 触发方式 `click` `hover` `focus`  | string | `hover` |
| autoDestory | 隐藏弹窗时是否移除弹窗的Dom结构，在弹窗特别多的情况下可节约性能 | boolean | false |
| zIndex | 设置zIndex | number | - |
| getContainer | 弹出层所挂载的 DOM 节点，默认 body | () => HTMLElement | () => document.body |
| defaultVisible | 默认是否显示 | boolean | false |
| visible | **受控**，是否显示浮层  | boolean | false |
| onVisibleChange | 显示/隐藏时的调用；通过 `visible` 改变显隐时不会触发 `onVisibleChange` | (visible: boolean) => void | - |
| onDocumentClick | trigger为`click`的时候才生效，点击弹窗以外的dom触发 | (visible: boolean) => void | - |
| autoAdjustOverflow| 自动调整弹出框位置 | bool | true |
| placement| 弹出层位置，可选 top left right bottom topLeft topRight bottomLeft bottomRight leftTop leftBottom rightTop rightBottom | string | `top` |
| align | 该值将合并到 placement 的配置中，设置参考[dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | - |
| delayShow | 延迟显示, 单元：毫秒 | number | 100 |
| delayHide | 延迟隐藏, 单元：毫秒，如果设置为0，鼠标不能移动至弹层| number | 100 |

### Tooltip Method

| 名称 | 说明 |
| --- | --- |
| forceAlign | 强制重新定位(一般用于弹层内容变化的时候重新定位)

#### 注意
请确保 Tooltip 的子元素能接受 onMouseEnter、onMouseLeave、onFocus、onClick 事件。


----split----

---
subtitle: 数据选择
title: Transfer
---

直观的展现数据转移

## 何时使用

- 需要在多个可选项中进行多选时。
- 比起 Select 和 TreeSelect，穿梭框占据更大的空间，可以展示可选项的更多信息。

## API

### Transfer

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| data| 接受整个数据源，除去targetKeys集合其余显示在左侧 | array | - |
| empty | 内容为空插槽 | array: [string, ReactNode]，从左到右对应穿梭框从左到右 | - |
| filterable | 是否可搜索 | boolean | false |
| filterMethod | 自定义搜索方法 | (filter, option) => boolean; | - |
| filterPlaceholder | 搜索框默认提示 | string | 请输入 |
| leftFooter | 左侧底部插槽 | string, ReactNode | - |
| operations | 方向按钮标题，数组从左至右对应按钮从上至下 | array: [string/ReactNode] | - |
| props| 指定用于取值的字段名 | {key: string, label: string, disabled: string} | {key: 'key', label: 'label', disabled: 'disabled'} |
| selectedKeys | 选中项 | Array<string \| number> | - |
| targetKeys | 显示在右侧，key 集合 | Array<string \| number> | - |
| titles | 标题集合，顺序从左至右 | array: [string/ReactNode] | - |
| render | 条目渲染函数 | (item) => ReactElement | - |
| rightFooter | 右侧底部插槽 | string, ReactNode | - |
| onChange | 数据转移时的回调。targetKeys：显示在右侧的数据key集合，direction：数据转移方向，moveKeys：被移动的数据key集合 | (targetKeys, direction, moveKeys) => void | - |
| onSelectedChange | 数据选中、取消时的回调。sourceSelectedKeys：左侧选中的数据集，targetSelectedKeys：右侧选中的数据集 | (sourceSelectedKeys, targetSelectedKeys) => void | - |


----split----

---
category: Form
subtitle: 树选择器
order: 4
title: TreeSelect
---

用于可选项是一个树型结构，如组织架构。

## API

### TreeSelect

| 参数 | 说明 | 类型 | 默认值 | 版本 |
| --- | --- | --- | --- | --- |
| size | 组件的尺寸，可选值为 `small|large|normal` 或不设 | string | normal 
| value | 选中的值，object类型，`multiple`为true时，数组类型array<object\> | object \| array<object\>  | - |
| multiple | 是否多选 | boolean | false |
| loading | 是否在搜索中 | boolean | false
| data | 树显示数据 | array | -
| loadingMessage | `loading` 时弹层中的显示文案 | string \| () => string \ ReactNode | 搜索中
| notFoundMessage | 弹层中无选项时显示的文案 | string \| () => string \ ReactNode | 无数据
| filterable | 是否支持筛选 | boolean | true
| disabled | 是否禁用 | boolean | false
| autoFocus | 是否自动聚焦 | boolean | false
| clearable | 是否显示清除按钮 | boolean | true
| autoClearSearchValue | 是否在选中项后清空搜索框，只在 `multiple=true ` 时有效 | boolean | true | 1.1.13
| icon | 右侧下拉图标 | string \| bool \| () => ReactNode | down-thick
| placeholder | 输入框中的提示语 | string | `filterable` 时默认 `请输入`，否则 `请选择`
| renderInputLabel | 选择后，输入框内容的自定义渲染方法 | (value) => string \ ReactNode | -
| renderTagLabel | 只对 `multiple` 生效，选择后，输入框内 tag 的自定义渲染方法，默认显示 `Option` 上的 `label` | (option: object => string \ ReactNode | -
| maxTagCount | 最多显示多少个 tag， 只对 `multiple` 有效 | number | -
| renderPopHeader | 自定义弹窗Header内容 | option => string \ ReactNode | -
| renderPopFooter | 自定义弹窗Footer内容 | option => string \ ReactNode | -
| treeProps | 树接收的属性 | object<[tree](/components/tree#Tree)> | -
| popLayer | 弹层的配置 | object<[popLayer](/components/tree-select#popLayer)> | -

#### Event

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| onSelect | 选择时触发 | (option: object, index: number, level: number) => void | -
| onDeselect | 取消选择时触发, 只对 `multiple` 有效 | (option: object, index: number, level: number) => void | -
| onChange | 选择变化时触发，多选时返回数组 | (option: object \| array, value: string \| array ) => void | -
| onFilter | 筛选时触发 | (filter: string) => void | -
| onKeyDown | 输入框聚焦时键盘按键触发 | (e: Event) => void | -
| onFocus | 输入框聚焦时触发 | (e: Event) => void | -
| onBlur | 输入框失去焦点时触发 | (e: Event) => void | -
| onVisibleChange | 弹层展开收起时触发 | (visible: boolean) => void | -

#### popLayer

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| className | 弹层的样式 | string | -
| width | 弹层的宽度 | number \| string | 与 AutoComplete 输入框同宽
| maxHeight | 弹层的最大高度 | number \| string | 250
| equalTargetWidth | 弹窗是否与输入框同宽 | bool | true
| visibleInit | 是否初始可见 | boolean | false
| visibleAfterSelect | 设置选择/取消选择后弹层不收起 | boolean | multiple ? false : true
| visibleAfterBlur | 设置组件失去焦点后弹层不收起 | boolean | true
| visibleAfterClear | 设置清空后弹层不收起 | boolean | false
| align | 弹层定位的设置, 详见 [dom-align](https://github.com/yiminghe/dom-align#alignconfig-object-details) | object | { points: \['tl', 'bl'\], offset: \[0, 2\], overflow: { adjustX: true, adjustY: true } }
| getContainer | 定义浮层的容器，默认为 body 上新建 div | () => HTMLElement | () => document.body |

## Method

| 方法 | 说明 | 返回值 |
| --- | --- | --- | --- |
| focus() | 使组件获得焦点 | -
| blur() | 使组件失去焦点，并收起下拉框 | -



----split----

---
category: Tree
subtitle: 树
order: 0
title: Tree
---

单列内，多层级的数据可视化展示，结构包括根节点、节点、叶子等层级。

## API

### Tree

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| nodeClassName | 节点的样式 | string \| (node: object<[node](/components/tree#node)>, index: number, level: number) => string | -
| disabled | 禁用选择和展开, 优先级高于 `disabledSelect` | boolean | false
| disabledSelect | 禁用选择，如果选择联动 `!selectStrictly`, 父节点禁用后，子节点都不可选择 | boolean | false
| data | 数据，支持打平的数据，树形数据(需要设置 useTreeData) | array | []
| keyField | 数据中对应主键的属性名 | string | 'key'
| labelField | 数据中对应显示字段的属性名 | string | 'label'
| childrenField | 数据中对应子节点的属性名，树形数据必须设置 | string | 'children'
| parentKeyField | 数据中对应父节点的属性名 | string | 'parentKey'
| leafField | 数据中对应是否为叶子节点的属性名 | string | 'leaf'
| indent | 两级节点的左缩进 | string \| number | 20
| expandOnClickNode | 是否单击节点任意位置触发展开，为false时只能点击前面触发展开收起 | boolean | false
| selectOnClickNode | 是否单击节点任意位置触发的选中，为false时只能点击前面选择框出发选中 | boolean | true
| useTreeData | 是否使用树形数据 | boolean | true
| showLine | 是否显示连线 | boolean | false
| draggable | 设置节点是否可拖拽 | boolean | true 
| nodeExpansion | 节点展开收起的配置，不设则不支持折叠 | boolean \| object<[nodeExpansion](/components/tree#nodeExpansion)> | true
| nodeSelection | 节点选择的配置，不设则不支持选择 | boolean \| object<[nodeSelection](/components/tree#nodeSelection)> | -
| loadingKeys | 加载中的节点 | array | -
| filterNode | 筛选节点，根据返回的布尔值控制显示。父节点返回`true`时，子节点均显示；父节点返回`false`，子节点返回`true`时会显示该子节点及所有父节点 | (node: object<[node](/components/tree#node)>, index: number, level: number) => boolean | -
| renderNodeContent | 自定义渲染节点 | (node: object<[node](/components/tree#node)>, index: number, level: number, leaf: bool) => ReactNode | node: object<[node](/components/tree#node)> => node[labelField]
| onLoadData | 点击展开时，如果该节点没有子节点，会调用 onLoadData | (node: object<[node](/components/tree#node)>, index: number, level: number) => void | -
| onExpand | 可用于阻止展开收起, 点击展开收起时调用不会更新 `nodeExpansion.expandedKeys`, 需要主动更改树的展开行, ,`expandedKeys` 是点击操作前已展开节点主键 | (node: object<[node](/components/tree#node)>, index: number, level: number, { expandedKeys: array, expandedNodes: array }, e: Event) => void | -
| onExpandChange | 点击展开收起且未传 `onExpand` 时调用，如果未传 `nodeExpansion.expandedKeys`, 会默认更新 `expandedKeys` | (expandedKeys: array, expandedNodes: array, e: Event) => void | -
| onSelect | 可用于阻止行选中, 点击选项框时调用, 不会更新 `nodeSelection.selectedKeys`(需要主动更改树的已选节点), `selectedKeys` 是点击操作前已选节点主键 | (node: object<[node](/components/tree#node)>, index: number, level: number, { selectedKeys: array, selectedNodes: array }, e: Event) => void | -
| onSelectChange | 在选项且未传 `onSelect` 时调用, 如果未传 `nodeSelection.selectedKeys`,会默认更新 `selectedKeys` | (selectedKeys: array, selectedNodes: array, e: Event, node: any) => void | -
| onDrop | 节点上拖拽结束的回调 | ({event, targetNode, dragNode, dropPosition, oldData, newData}) => void | -

#### nodeSelection

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| checkbox | 是否显示选择框 | boolean | 是 | false
| className | 选择框的样式 | string | 是 | -
| style | 选择框的样式, 例如 paddingRight, width 等, width 支持 `100|'100px'`, 建议设置一个数字, 默认单位为 px | object | 是 | -
| selectedKeys | `受控`,当前选中的行主键的数组 | array | 是 | -
| parentSelectable | 是否能选中父节点 | boolean | 是 | true
| leafSelectable | 是否能选中子节点 | boolean | 是 | true
| defaultSelectedKeys | 默认选中的行主键的数组, 优先级高于 `defaultSelectAll` | array | 是 | -
| defaultSelectAll | 默认全选 | boolean | 是 | false
| selectStrictly | 设置父子节点不联动 | boolean | 是 | true
| selectStrategy | 选择节点后，返显策略，只在 `selectStrictly` 为 `false` 时有效，可选值为 `all(返回所有的节点)|parent(当父子节点都选中时返回父节点)|child(当父子节点都选中时只返回子节点)` | string | 是 | parent

#### nodeExpansion

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| className | 展开节点的样式 | string | 是 | -
| accordion | 展开一个节点时关闭其他同级节点；如果设置为true时autoExpandParent不可为true | boolean | 是 | false
| expandedKeys | `受控`,当前展开的行主键的数组 | array | 是 | -
| autoExpandParent | 是否自动展开 expandedKeys 节点的父节点，父节点收起时同时收起子节点，_需要配合 `expandedKeys|defaultExpandedKeys`  使用_ | boolean | 是 | false
| defaultExpandedKeys | 默认展开的行主键的数组, 优先级高于 `defaultExpandAll` | array | 是 | -
| defaultExpandAll | 默认展开全部, 优先级高于 `defaultExpandParent` | boolean | 是 | -
| defaultExpandParent | 是否自动展开父节点, 优先级高于 `defaultExpandLevel`, 与 `autoExpandParent` 的区别在于该属性只在初始化时生效 | boolean | 是 | false
| defaultExpandLevel | 默认展开到第几个层级 | number \| string | 是 | -
| render | 自定义展开节点的渲染, 优先级高于从 `data` 中获取 `childrenKey` 来展示 | (node: object<[node](/components/tree#node)>, index: number, level: number) => ReactNode | 是 | -
| icon | 自定义展开收起图标的渲染 | string \| (expanded: bool, node: object<[node](/components/tree#node)>, index: number, level: number, { parentNode: object, leaf: bool, loading: bool, selected: bool }) => ReactNode | 是 | triangle-right
| action | 设置触发展开收起的操作，可选值为 `click`,`doubleClick`,`none` | string | click

#### node

| 参数 | 说明 | 类型 | 可缺省 | 默认值 |
| --- | --- | --- | --- |
| ${keyField} | 节点的键，`data` 中 keyField 对应的值 | string | 否 | -
| ${labelField} | 节点的名称，`data` 中 labelField 对应的值 | string | 是 | -
| ${parentKeyField} | 父主键对应的属性 | string | 是 | -
| ${childrenField} | 子节点对应的属性 | string | 是 | -
| ${leafField} | 是否叶子节点 | boolean | 是 | -
| disabled | 是否禁用选择和展开，优先级 `disabledSelect > disabledSelect` | boolean | 是 | false
| disabledSelect | 是否禁用选择，优先级 `Tree.disabled > Tree.disabledSelect > node: object.disabled>node: object.disabledSelect` | boolean | 是 | false

```html
<Tree data={[
  { id: '1', label: '第一章', parentId: 'null' },
]} keyField="id" parentKeyField="parentId" labelField="label" />
```

### Method

| 方法 | 说明 | 返回值 |
| --- | --- | --- | --- |
| getNodesMap() | 获得组件的数据隐射关系 | -


----split----

---
subtitle: 上传
title: Upload
---

通过选择和拖拽方式, 将文件上传至服务端。Upload组件用于实现上传，Filelist用于展示文件列表。

## API

### Upload

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| action | 上传的地址	| string	| —	|
| multiple| 是否支持多选文件  | boolean | false |
| data | 上传时附带的额外参数	| object | — |
| name | 上传的文件字段名	| string | file |
| draggable| 是否支持拖拽上传  | boolean | false |
| disabled| 是否禁用 | boolean | false |
| accept| 接受上传的文件类型, 英文逗号隔开, 详见: [input accept Attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file#accept) | string | - |
| credentials | 支持发送 cookie 凭证信息, 默认`same-origin`只有当URL与响应脚本同源才发送cookies，`omit`从不发送cookies, `include`总是发送cookies | string	|	same-origin |
| headers	| 设置上传的请求头部	| object	| —	|
| onBeforeUpload | 上传文件之前的钩子，参数为上传的文件，若返回 false 或者返回 Promise 且被 reject，则停止上传 | (files: array<File>) => boolean/Promise<any>/void | - |
| onUpload | 文件上传时的钩子 | file => void | - |
| onSuccess | 文件上传成功时的钩子 | (response, file) => void | - |
| onError | 文件上传失败时的钩子 | (error, file) => void | - |
| disableOnUploading | 是否在上传期间禁用 | boolean | false |

### Upload.helper
> Upload.helper包含3个方法，可通过Upload.helper.upload方法自定义上传的内容。

| 方法 | 类型 | 说明 |
| --- | --- | --- |
| getFileSizeWithKB | (file: File) => number | 获得文件大小，单位为 kb
| getFileSizeWithMB | (file: File) => number | 获得文件大小，单位为 mb
| upload | (url, file, options: object) => void | 上传单个文件

```
Upload.helper.upload(
  url: string, // 上传地址,
  file: File, // 上传文件,
  options: {
    name: string, // 上传文件的参数名，默认为 file,
    params: Object, // 上传附带参数,
    headers: Object, // 上传请求的自定义 header，
    credentials: // 是否携带 cookie, 默认 same-origin
    onSuccess: (response, file) => void,
    onError: (error, file) => void,
  },
)
```


### Flielist
> 配合Upload组件使用，用于展示上传后的文件列表

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| type | 列表类型，默认2种list & picture	| string	| list	|

### Flielist.Item
| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| name | 文件名	| string	| -	|
| url | 文件地址	| string	| -	|
| download | 是否支持下载文件	| bool	| true	|
| remove | 是否支持移除文件	| bool | true |
| preview | 是否支持预览图片(type值为picture时才有效) | bool	| true	|
| onRemove | 点击删除文件按钮触发	| (index) => void	| -	|
| onDownload | 替代点击下载时的回调	| (url) => void	| -	|
