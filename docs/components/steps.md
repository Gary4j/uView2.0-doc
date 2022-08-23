## Steps 步骤条 <to-api/>

<demo-model url="/pages/componentsC/steps/steps"></demo-model>

该组件一般用于完成一个任务要分几个步骤，标识目前处于第几步的场景。

### 平台差异说明

|App（vue）|App（nvue）|H5|小程序|
|:-:|:-:|:-:|:-:|
|√|√|√|√|

### 基本使用

:::warning 说明
由于安卓`nvue`下，`overflow`属性不支持`visible`值，故此组件暂不支持安卓`nvue`环境。
:::

- 通过`current`参数标识目前处于第几步，从0开始

```html
<template>
	<u-steps current="0">
		<u-steps-item title="已下单" desc="10:30">
		</u-steps-item>
		<u-steps-item title="已出库" desc="10:35" ></u-steps-item>
		<u-steps-item title="运输中" desc="11:40"></u-steps-item>
	</u-steps>
</template>
```

### 错误状态

如果设置```u-steps-item```的```error```参数为```true```的话，当前步骤将会为“失败”的状态

```html
<u-steps current="1">
	<u-steps-item title="已下单" desc="10:30"></u-steps-item>
	<u-steps-item error title="仓库着火" desc="10:35"></u-steps-item>
	<u-steps-item title="破产清算" desc="11:40"></u-steps-item>
</u-steps>
```

### 步骤条模式

```u-steps```的```dot```参数设置为```true```的话，将会以点状的形式展示步骤条样式。

```html
<u-steps current="1" dot>
	<u-steps-item title="已下单" desc="10:30"></u-steps-item>
	<u-steps-item title="已出库" desc="10:35"></u-steps-item>
	<u-steps-item title="运输中" desc="11:40"></u-steps-item>
</u-steps>
```


### 竖向模式

```u-steps```的```direction```参数设置为```column```的话，组件将会以竖向的形式展示步骤条内容。

```html
<template>
	<u-steps current="1" direction="column">
		<u-steps-item title="已下单" desc="10:30">
		</u-steps-item>
		<u-steps-item title="已出库" desc="10:35">
		</u-steps-item>
		<u-steps-item title="运输中" desc="11:40"></u-steps-item>
	</u-steps>
</template>
```


### 自定义图标

- 通过```activeIcon```可以设置激活状态的图标
- 通过```inactiveIcon```可以设置非激活状态的图标

```html
<u-steps
	current="1" activeIcon="checkmark" inactiveIcon="arrow-right">
	<u-steps-item title="已下单" desc="10:30"></u-steps-item>
	<u-steps-item title="已出库" desc="10:35"></u-steps-item>
	<u-steps-item title="运输中" desc="11:40"></u-steps-item>
</u-steps>
```

### 通过插槽自定义样式

通过默认插槽，可以自定义某个步骤当前状态的特殊标识

```html
<u-steps :current="1">
	<u-steps-item title="已下单" desc="10:30"></u-steps-item>
	<u-steps-item title="已出库" desc="10:35"></u-steps-item>
	<u-steps-item title="运输中" desc="11:40">
		<text class="slot-icon" slot="icon">运</text>
	</u-steps-item>
</u-steps>

<style lang="scss">
	.slot-icon {
		width: 21px;
		height: 21px;
		background-color: $u-warning;
		border-radius: 100px;
		font-size: 12px;
		color: #fff;
		line-height: 21px;
		text-align: center;
	}
</style>
```

### 此页面源代码地址

:::tip 页面源码地址
<br/>

<a href="https://github.com/umicro/uView2.0/blob/master/pages/componentsC/steps/steps.vue" target="_blank" style="display: flex;align-items: center">
   <img height="30" src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-8f7e1d02-dcb1-46ba-90db-ae32fea44f22/4b2bf3e5-68ad-4a15-b0d1-00b7a5246eab.png" title="github" width="30"/>&nbsp;github
</a>

<a href="https://gitee.com/umicro/uView2.0/blob/master/pages/componentsC/steps/steps.vue" target="_blank" style="display: flex;align-items: center;margin-top: 10px">
   <img height="30" src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-8f7e1d02-dcb1-46ba-90db-ae32fea44f22/0d0bc2dc-64e3-4ea1-a641-9c23d198e36d.png" title="github" width="30"/>&nbsp;gitee
</a>

<br/>
:::

### API

### Steps Props

| 参数			| 说明					| 类型					| 默认值		|  可选值	|
|:-				|:-						|:-						|:-			|:-			|
| direction		| row-横向，column-竖向	| String				| row		| column	|
| current		| 设置当前处于第几步		| Number &#124; String	| 0			| -			|
| activeColor	| 激活状态颜色			| String				| #3c9cff	| -			|
| inactiveColor	| 未激活状态颜色			| String				| #969799	| -			|
| activeIcon	| 激活状态的图标			| String				| -			| -			|
| inactiveIcon	| 未激活状态图标			| String				| -			| -			|
| dot			| 是否显示点类型			| Boolean				| false		| true		|
	

### Steps Item Props
| 参数		| 说明						| 类型					| 默认值	|  可选值	|
|:-			|:-							|:-						|:-		|:-			|
| title		| 标题文字					| String				| -		| -			|
| desc		| 描述文本					| String				| -		| -			|
| iconSize	| 图标大小					| String &#124; Number	| 17	| -			|
| error		| 当前步骤是否处于失败状态		| Boolean				| false	| true		|


### Slot

| 名称	| 说明				|
|:-		|:-					|
| -		| 自定步骤状态内容	|


<style >
h3[id=slot] + table thead tr th:nth-child(2){
	width: 50%;
}
</style>
