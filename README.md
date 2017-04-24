# file-uploader
vue模块化组件开发的文件上传
上传文件是基于jQuery的file-uploader。
用法很简单，首先项目中已经添加了jQuery全局包，下载以下文件
https://github.com/holidaying/file-uploader.git。然后将uploadFile文件夹放入到你用第三方插件的目录下


#### 父组件引入方法
```
<up-loader data-id="icon-load" data-type="jpeg,png" v-model="getUploaderData" data-class="uploader-btn">
<span slot="textWord" class="textWord">选择</span>
</up-loader> 
```

* data-id父组件的传入的domId，比传
* data-type父组件控制需要上传文件的类型
* getUploaderData父组件获取后端返回的参数
* data-class 控制上传按钮的样式
* textWord上传文件加入的文字说明

#### 子组件修改的地方
```
<template>
    <label :for="dataId" :style="dataStyle" class="upLoaderFile" :class="dataClass">
        <input type="file" class="dishidden fileSelectUpButton" name="file" :id="dataId" multiple>
        <slot name="textWord" class="textWord"></slot>
    </label>
</template>
<script>
self.$message.warning(message + self.dataType + '格式的文件');
<script>
var server_uploader_ulr = "";
var fileUpLoader = require('./uploadFile/js/jquery.fileupload.js'); //上传图片
```
* server_uploader_ulr:需要添加服务器接口地址
* self.$message.warning:需要改成你们自己弹出信息的方法
