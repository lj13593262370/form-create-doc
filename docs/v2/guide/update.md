---
 title: 更新日志 (1.0.20)
---

### 当前版本 1.0.20

--------

#### 1.0.20 (2020-11-01)
- 优化 错误提示
- 优化 `group`组件`expand`配置项
- 优化 `upload`组件被禁用时无法预览问题 #268
- 修复 `hidden` 配置项可能失效问题
- 修复 `hidden` 组件无法重置问题
- 修复 `maker.group` 方法不存在

#### 1.0.19 (2020-09-11)
- 新增 `Group` 组件 expand 属性,控制默认打开个数
- 新增 通过 `Group` 组件监听子表单的事件
    ```js
    {
        type:'group',
        //...
        props: {
            rules: [
                {
                    type: 'input',
                    field: 'test',
                    emit: ['change'],
                    //...
                }   
            ]   
        },
        on: {
            ['test-change']: function () {
                //TODO input 组件 change 事件
            }
        }
    }
    ```
- 修复 `Group`组件value可能会不同步问题
- 修复 `upload` 组件`previewMask`参数无效问题
- 优化 `emit` 事件触发
- 新增 `emit-event` 事件,有 `emit` 时触发

#### 1.0.18 (2020-08-12)
- 修复 `Group` 组件可能出现赋值失效问题 [#240](https://github.com/xaboy/form-create/issues/240)
- 修复 `ElmentUI.Upload`组件可能出现报错问题 [#207](https://github.com/xaboy/form-create/issues/207)
- 修复 `emit` 事件可能会触发两次的问题
- 更新 `TypeScript`

#### 1.0.17 (2020-07-16)
- 修复 `hidden` 可能会失效问题
- 修复 `group` 组件可能会额外生成多组的问题
- 修复 `control` 可能会失效的问题
- 修复 `datePicker`,`timePicker`组件 `formatValue` 可能导致报错的问题
- 新增 `frame` 组件支持通过`previewMask`配置预览图片弹窗的遮罩是否显示
- 优化 `$emit` 事件
- 优化 表单销毁时可能报错
- 优化 `frame`组件助手方法加载时机
- 新增 支持设置 `title` 的 `class,style` 等属性
    ```javascript
   let rule = {
      title:{
          class:'titleClass',
          style:'backgroundColor:red',
          title:'商品名称'
      }
      //title:'商品名称'    
  }
    ```


#### 1.0.16 (2020-06-17)
- 修复 渲染时可能出现死循环
- 修复 `antd.switch` 组件修改值问题
- 修复 `antd.select` placeholder 不显示
- 更新 `TypeScript`
- 修复 `group` 组件`remove`事件修改值时UI可能不更新问题
- 修复 `frame` 组件预览可能无法正常显示问题
- 新增 `group` 组件支持控制按钮隐藏按钮大写和自定义按钮,
    - 配置项 `fontSize,button,`
    - 插槽 `button,default`


#### 1.0.15 (2020-05-31)
- 优化 `parseJson`,`toJson` 方法,避免错误解析`function`
- 优化 对生成规则的深拷贝
- 优化 `group` 组件生成的子表单自动跟随父表单的配置
- 新增 `control.handle` 方法增加第二个参数`$f`
- 新增 `frame` 组件支持`reload,okBtn,closeBtn`配置,`form_create_helper`增加`onOk`,`onClose`方法可设置页面关闭回调事件
- 重构 `frame,upload` 组件的弹出框,移除原有的`modal`
- 修复 `upload` 预览可能死循环问题
- 修复 `group` 组件验证可能不通过问题
- 修复 `toJson` 可能出现规则丢失问题
- 修复 全局配置`labelCol,wrapperCol`不生效问题
- 修复 `hidden` 组件可能会渲染问题

#### 1.0.14 (2020-05-14)
- 优化 `frame` 组件 value 类型
- 修复 `frame` 组件 在`safari`浏览器下无法正常关闭问题

#### 1.0.13 (2020-05-11)
- 优化 `$f.append`,`$f.prepend`方法
- 修改 内置的`copyRule`方法
- 优化 自动拷贝生成规则的条件
- 支持 控制是否自动生成`col`,`row`组件和设置`class`

#### 1.0.12 (2020-04-30)
- 修复 局部挂载时`fragment`组件报错
- 修复 `removeField`可能无效问题
- 新增 双向数据绑定的 formData `$f.form`
- 新增 `control`事件,`control`生效或移除时触发

#### 1.0.11 (2020-04-21)
- 移除 `ElementUI label`多行的样式
- 修复 ts `vue.use(formCreate)`类型报错问题 #196
- 新增 `maker` 实例增加`inject,model`方法
- 新增 内置`fragment`组件
- 修复 `maker` 二次追加属性不生效问题
- 支持 `ant-design-vue` [文档](/v2/ant-design-vue/)
    ```sh
    npm i @form-create/ant-design-vue
    ```

#### 1.0.10 (2020-04-18)
- 修复 `timePicker`组件偶尔无法选择问题
- 修复  在`ie10`中可能报错问题
- 修复 `parseJson`方法可能报错问题
- 修复 `control`可能不生效问题
- 重构 `vData`类,支持事件重复监听
- 修复 `onSubmit`方法报错问题
- 修复 `frame`组件`width,height`属性类型错误问题
- 修复 `checkbox`组件可能报错问题
- 修复 `control`控制的规则多包裹一层`div` #199
- 新增 `frame`组件增加`srcKey`配置项,支持`value`为对象
- 新增 `group` 组件增加`change`事件
- 新增 表单整体的`change`事件
- 优化 `ElementUI label`多行的样式
- 优化 ts #196

#### 1.0.9 (2020-03-24)
- 修复 `field` 可能重复问题
- 修复 `DatePicker` 组件验证时可能报错问题

#### 1.0.8 (2020-03-15)
- 修复 合并公共布局规则时报错问题 #181
- 修复 `group` 组件有可能会报错的问题
- 修复 **追加组件后验证失效问题**
- 修复 `DatePicker` 组件值转换问题
- 更新 `TypeScript`
- 增加 优化`method`方法,可拿到返回值
- 增加 在`group`组件的事件中传入`index` #183
- 增加 **增加`control`配置项,可用于控制其他组件显示**
- 增加 `options.form.className` 配置项,支持设置表单的`class`

#### 1.0.7 (2020-03-02)
- 修复 初始化全局配置时的字段错误 #166
- 修复 `DatePicker`组件验证报错问题
- 更新 `TypeScript`
- 修复 `frame`组件`src`修改后,没有实时更新问题
- 增加 **`group`组件,可实现数组组件,hash组件功能**
- 优化 组件生成规则复用
- 优化 组件信息提示按钮位置

#### 1.0.6 (2020-01-16)
- 支持`TypeScript`
- 修复`elm.frame`组件在`input`类型`icon`不显示问题
- 修复`iview.tree`组件首次渲染没有选中问题


#### 1.0.5 (2019-12-7)
- 重构 `hidden`,`visibility`功能
- 生成规则增加 `hidden`,`visibility` 配置项
- 修复 `value` 可能会意外发生改变问题
- 修复 `value` 改变后,页面组件有可能没有渲染问题


#### 1.0.4 (2019-11-21)
- 新增 `formData`配置项,可设置表单初始值
- 修复 `type` 未定义时可能出现死循环问题
- 修复 `type` 大写时可能未识别组件问题
- 支持 `iview v4`版本
```
npm i @form-create/iview4
```

#### 1.0.3 (2019-08-26)

- 修复 多次v-if后表单内控件绑定的事件失效 [#125](https://github.com/xaboy/form-create/issues/125)
- 修复 toJson方法函数转json
- 修复 内置按钮不显示时,移除多余的布局 div
- 新增 手动触发事件方法`$f.trigger`
- 新增 获取组件`vm`方法`$f.el`
- 增强 `props` 中的函数支持事件注入
- 增强 `removeField`,`updateRule`返回当前规则
- 增强 事件注入参数中增加`self`当前规则
- 增强 vm 参数支持设置为`Function`
```js
{
    vm:function(){
        return new Vue;
    }
}
```


#### 1.0.2 (2019-08-11)

- 修复 样式被覆盖问题 [#121](https://github.com/xaboy/form-create/issues/121#issuecomment-519348579)
- 修复 datePicker,timePicker 组件验证问题,取值问题 [#118](https://github.com/xaboy/form-create/issues/118)
- 修复 `append`,`prepend` 方法报错
- 增强 生成规则定义`name`后,可通过`component`方法获取
- 增加 `on`,`off`,`once` 方法绑定 emit 事件

#### 1.0.1 (2019-07-29)

- 增加 `$f.updateValidate`,`$f.updateValidates` 方法 [#116](https://github.com/xaboy/form-create/issues/116)
- 修复 输入框设置最大最小字符无效 [#115](https://github.com/xaboy/form-create/issues/115)
- 修复 upload组件同时上传多张图片报错问题
- 修复 ElementUI.upload组件加载动画不显示问题

#### 1.0.0 (2019-07-21)

- 修复 timePicker 组件无法选择问题
- 修复 type为template时会引发栈溢出问题 [#110](https://github.com/xaboy/form-create/issues/110)
- 新增 自定义组件props中自动注入`$f`,可以用`props.formCreate`接收
- 新增 `$f.getRule`方法,获取指定`field`的生成规则


#### 0.0.5 (2019-07-07)

- 优化 `$f.toJson` 方法,不支持转换 `template` 组件
- 新增 `$f.updateRule`,`$f.updateRules` 方法
```js
//更新 goods_name
$f.updateRule('goods_name',{
    props:{
        disabled:true
    }
})
//批量更新
$f.updateRules({
    'goods_name':{
        props:{
            disabled:true
        }
    }
})
```
- 新增 `injectEvent` 全局配置项,设置是否开启事件注入,注入$f,rule等参数.开启后事件的第一个参数为注入的参数
```js
//注入参数的数据结构
{
    $f:Object,//api
    rule:Array,//生成规则
    option:Object,//全局配置
    inject:Any,//自定义注入的参数
}

```
```js
//全局开启
{
    injectEvent:true
}
//指定事件开启
rule:{
    //inject为事件额外的自定义注入参数
    emit:[{name:'click',inject:true}]
}
```
- 修复 移除组件的同时又新增`field`与移除组件相同的组件时组件收到值`undefined`问题

#### 0.0.4 (2019-06-30)

- 新增 `$f.toJson`和`formCreate.parseJson` 方法, 将生成规则转为 json 和反转
- 新增 `info` 配置项,配置组件的提示信息
- 新增 `option.info`配置项,设置组件提示信息的相关配置
- 移除 对时间组件,日期组件的值得二次处理
- 增加 `$f.method` 方法不存在时的错误提示
- 增加 `frame` 组件的 `modal` 配置项,可设置`modal`的属性
- 修复 `element-ui` 部分组件 `placeholder` 属性无效问题
- 更新 `element-ui` 时间组件,日期组件 `maker` 生成器

#### 0.0.3

内部功能重构、
功能精简和优化、
扩展更简单


**新功能**
- 自定义组件可转换为表单组件,具有验证和内置组件的功能
- 增加组件的全局配置
- 增加 `name`配置项,自定义组件可配置
- 增加 判断表单是否修改的方法 `changeStatus`
- 增加 获取组件隐藏状态方法`hiddenStatus`
- 增加 `rule.native` 配置项
- 增加 `$f.method` 方法,可调用组件方法

**修改**
- 将 `switch` 组件 `slot` 配置,移动到 `props.slot` 中
- 修改 `$f.validate` 方法的参数
- 修改 `$f.hidden`,`$f.visibility`,`$f.disabled` 方法的参数顺序
- 修改 方法名`$f.submitStatus` => `$f.submitBtnProps`
- 修改 方法名`$f.resetBtnStatus` => `$f.resetBtnProps`
- 重构 `frame` 组件,移动`event`到 `props` 中

**移除**

- 移除 自定义组件相关事件
- 移除 `frame` 组件 spin 配置项
- 移除 全局配置中 `upload` 配置项
- 移除 表单最外层的 `margin` 20px
- 移除 `$f.btn.finish`和`$f.resetBtn.finish` 方法
- 移除 `defaultSlot` 配置项
- 移除 内置组件自动填充默认属性
- 移除 组件规则中的`hidden`和`visibility`属性
- 移除 `upload` 组件 `onSuccess` 中返回 url 自动添加功能
- **移除 `iview`版 event 配置项自动添加`on-`前缀功能**