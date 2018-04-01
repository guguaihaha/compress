HTML  

<input type='file' id='inputFileSelectorId' />
JAVASCRIPT


Zr.use("compress",function(zr,compress){
        compress.config({
             uploadFlag:false,//禁止使用上传
             compressSuccess:function(data){
               //data为压缩后的数据
             }
        });
        compress.initSelector("#inputFileSelectorId");
})       


当然如果有其他业务，不希望直接使用自己的选择器，可以传入一个图片的地址也可以实现以上效果

JAVASCRIPT


Zr.use("compress",function(zr,compress){
        compress.config({
             uploadFlag:false,//禁止使用上传
             compressSuccess:function(data){
               //data为压缩后的数据
             }
        });
        compress.initImg("http://www.jd.com/some.pic");
})       
compress提供的方法有以下

Methods

# config(OPTIONS)
说明：压缩初始化的配置基本信息
参数：OPTIONS
# initSelector(inputSelector)
说明：压缩并上传
参数：inputSelector上传input的选择器名称。eg:".input" or "#input"
# initImg(imgSrc)
说明：压缩并上传
参数：imgSrc 上传图片的路径
 OPTIONS

# ratio
类型：number
说明：图片大于400w,压缩至400w以下.高于500w,IOS中Canvas大小不能画出图形

默认数值：4000000
# bgColor
类型：string
说明：铺底色,用于转换png到jpg时候出现的黑色背景问题

默认数值：#FFF


# piece
类型：number
说明：图片像素大于200w像素出现无法正常toDataURL,所以选择分段绘制

默认数值：1000000
# fillColor
类型：string
说明：分段绘制弥补色

默认数值：#FFF
# compressType
类型：string
说明：压缩后的图片格式

默认数值：image/jpeg
# fillColor
类型：string
说明：分段绘制弥补色

默认数值：#FFF
# compressRadio
类型：number
说明：压缩后的比率

默认数值：0.4
# compressResultenlightened（新增）
类型：string
说明：压缩的后导出类型，"base64"、"blob"
推荐使用"base64"类型，兼容性好


默认数值：base64
blob兼容注释：
blob类型兼容不是很好，请参考如下兼容列表

桌面浏览器兼容列表

Feature	Chrome	Firefox (Gecko)	Internet Explorer	Opera	Safari
Basic support	50	19 (19)	10ms	(Yes)	(Yes)[1]
Image quality parameter	50	25 (25)	No support	(Yes)	No support
移动端浏览器列表

Feature	Android	Android Webview	Firefox Mobile (Gecko)	IE Mobile	Opera Mobile	Safari Mobile	Chrome for Android
Basic support	No support	50	19.0 (19)	?	No support	?	50
Image quality parameter	No support	50	25.0 (25)	?	No support	?	50




# compressSuccess(data)
类型：function
说明：压缩成功后

默认返回值：data返回的压缩的数据
# uploadFlag
类型：boolean
说明：如果开启上传以下属性：uploadBase64Name、uploadOptions即可使用

默认数值：true
# uploadBase64Name
类型：string
说明：上传图片关键key自定义名称

默认数值：base64str
# uploadOptionsenlightened(新增)
类型：object
说明：ajax方法的配置参数,具体参数请参照jQuery.ajax(OPTIONS)
