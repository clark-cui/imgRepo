# ImgRepo

个人github图床

------

> 注意 ：此项目已经废弃，本人目前使用alioss作为图床。由于github被墙的原因，现在国内访问github很慢，picgo连接github会失败，下附教程。

#### picgo+github实现图床

> 图床的作用：把图片上传到服务器，获取图片url。
>
> 写项目的时候，把静态资源放到图床，可以减小本地打包的体积。项目部署的时候，也能减少服务器去响应下载静态资源的占用，减轻服务器压力（毕竟没钱，租的最便宜的菜鸡服务器）。



###### 教程

网上有一大堆，我就不写了，百度一下 picgo+github图床，我放一个链接在这里。

[点击这里查看教程](https://www.jianshu.com/p/2756724a5dee)



#### 图床改造（alioss+picgo）

##### typora更新，支持一键picgo

 一觉醒来，打开typora,看到更新，瞅瞅更新日志，

> Support upload images via PicGo or custom commands.

厉害了，这样的话就可以直接在typora中贴图，自动上传到图床，激动地我立马试了下。

##### github图床不再可用

picgo直接报错`服务器失败`

打开日志一看

```javascript
RequestError: Error: read ECONNRESET
```

妈耶，我一拍脑袋，打开小飞机，再试一次

`上传成功`

em...果然是github的原因，受限于国内网络的原因，还是开个alioss，我因为服务器和域名都是买的阿里的，所以用alioss的话，服务器和alioss通信可以走内网，不计流量。

大家也可以用七牛、腾讯之类的，我对比了下，七牛的是最便宜的，效果也不错。如果硬是要免费的话，也可以用微博图床，但稳定性不行，数据丢失不负责哦。

##### 启用alioss

这里就以阿里oss为例了，开通后，新建bucket。账户里新建个accesskey，安全考虑最好开启`子账户`，`仅允许编程访问`，设置权限`仅管理alioss`。阿里云有详细操作文档（良心！！），小白顺着一步步来。



##### 最终效果：

使用snipaste可以快速贴图上传，本地图片可以拖进去上传，大大提高了写文档的效率。

![](https://gif-clark-cui.oss-cn-beijing.aliyuncs.com/blog/%E4%B8%8A%E4%BC%A02020-3-15.gif)

