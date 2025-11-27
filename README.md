# @chzky/style

* 通用的样式表,使用Scss进行预处理

## 使用
依照使用级别引入
### 全部引入

+ 引入所有样式 :

`@use '@chzky/style/lib/mod.scss'`

### 按需引入

+ 引入通用样式

`@use '@chzky/style/lib/cmomond.scss'`

+ 引用浏览器默认消除样式

`@use '@chzky/style/lib/reset.scss'`

+ 引用主题样式

`@use '@chzky/style/lib/theme.scss'`

+ 引用可变布局样式

`@use '@chzky/style/lib/themeLayout.scss'`

## 暗黑主题
当启用`<html class="dark"/>`的时候启用暗黑主题  
默认暗黑配色 : [Dracula Theme](https://draculatheme.com/contribute)

### 使用`@mixin dark-mode`定义暗黑样式
```scss
@use '@chzky/style/lib/theme.scss' as * ;

.custom-style{
  color:$primary-color;
  @include dark-mode{
    color:$dk-primary-color; // or other dark color
  }
}
```

## 更改主题

通过scss的`@use ... with( )`语法更改主题颜色

### 示例

```scss
@use '@chzky/style/lib/variable.scss' with (
  $unit:rm //将基础单位修改 : px -> rm
);
@use '@chzky/style/lib/mod.scss';
```


### 默认主题样式

#### @unit : 样式单位 

+ `$unit : px`

#### @color : 主题颜色 

+ `$primary: #409eff `
+ `$success: #67c23a` 
+ `$warning: #e6a23c `
+ `$danger: #f56c6c `
+ `$info: #909399`
+ `$page: #f2f3f5 `
+ `$dk-primary: #bd93f9`
+ `$dk-success: #50fa7b`
+ `$dk-warning: #f1fa8c`
+ `$dk-danger: #ff5555`
+ `$dk-info: #8be9fd`

#### @text-color : 文字颜色 

+ `$primary-t: #303133`
+ `$regular: #606266`
+ `$secondary: #909399` 
+ `$placeholder: #a8abb2` 
+ `$disabled: #c0c4cc` 
+ `$dk-primary-t: #f8f8f2`
+ `$dk-regular: #e0e0e0` 
+ `$dk-secondary: #bfbfbf`
+ `$dk-placeholder: #6272a4`
+ `$dk-disabled: #44475a`

#### @border : 边框颜色 

+ `$darker: #cdd0d6` 
+ `$dark: #d4d7de` 
+ `$base: #dcdfe6` 
+ `$light: #e4e7ed` 
+ `$lighter: #ebeef5` 
+ `$extra-light: #f2f6fc` 
+ `$dk-darker: #44475a` 
+ `$dk-dark: #505361`
+ `$dk-base: #6272a4`
+ `$dk-light: #707382`
+ `$dk-lighter: #808394`
+ `$dk-extra-light: #9093a4`

#### @shadow : 阴影颜色 

+ `$basic-shadow: 0px 12px 32px 4px rgba(0, 0, 0, 0.04), 0px 8px 20px rgba(0, 0, 0, 0.08) `
+ `$light-shadow: 0px 0px 12px rgba(0, 0, 0, 0.12)`
+ `$lighter-shadow: 0px 0px 6px rgba(0, 0, 0, 0.12) `
+ `$dark-shadow: 0px 16px 48px 16px rgba(0, 0, 0, 0.08), 0px 12px 32px rgba(0, 0, 0, 0.12),0px 8px 16px -8px rgba(0, 0, 0, 0.16) `
+ `$dk-basic-shadow: 0 4px 12px rgba(0, 0, 0, 0.25), 0 2px 6px rgba(0, 0, 0, 0.3)`
+ `$dk-light-shadow: 0 0 8px rgba(0, 0, 0, 0.3)`
+ `$dk-lighter-shadow: 0 0 4px rgba(0, 0, 0, 0.25)`
+ $`dk-dark-shadow: 0 8px 24px rgba(0, 0, 0, 0.35), 0 4px 12px rgba(0, 0, 0, 0.4),0 2px 6px -2px rgba(0, 0, 0, 0.4)`
  
#### @gap : 间距 

+ `$mini-gap: 4px`
+ `$small-gap: 8px`
+ `$medium-gap: 16px`
+ `$large-gap: 24px`

#### @radius : 圆角 

+ `$mini-radius:2px`
+ `$small-radius: 4px`
+ `$medium-radius: 6px `
+ `$large-radius: 8px`

#### @font-size : 字体大小 

+ `$mini-font-size: 12px`
+ `$small-font-size: 14px`
+ `$medium-font-size: 16px`
+ `$large-font-size`

## 使用VScode进行智能提示

使用vscode 提示后不需要记住所有的类名,只需要输入部分即可联想补全

1. 安装插件: [SCSS Everywhere](https://marketplace.visualstudio.com/items?itemName=gencer.html-slim-scss-css-class-completion)
2. 创建工作空间 `.vscode > setting.json` or `xxx.code-workspace`
3. 在settings中设置 : 

```json
"settings":
  {  
  // 实际在代码中引入什么样式就写什么样式  `lib/xxx.css`
  "html-css-class-completion.remoteStyleSheets": ["https://cdn.jsdelivr.net/npm/@chzky/style/lib/mod.css"] 
  }
```