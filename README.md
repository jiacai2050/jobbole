## 文章分享书签

本书签主要功能是方便用户向[伯乐在线 | 头条](http://top.jobbole.com/)分享文章，虽然官方也提供了[浏览器扩展](http://blog.jobbole.com/93269/)，个人觉得安装扩展显得有些“笨重”，而且最主要的是消耗系统资源。于是，参考 [pocket](https://getpocket.com/add) 与 [一点黑科技](https://1.qinghuai.org/stories/new)，写了本书签，希望对大家有帮助。😊

## 使用方法

将下面的`+ Jobbole` 拖到浏览器的书签栏即可。

<a href="javascript:(function()%20%7Bvar%20meta%20%3D%20document.querySelector(%22meta%5Bname%3D%5C'description%5C'%5D%22)%3B%20if(meta)%20%7Bmeta%20%3D%20meta.getAttribute(%22content%22)%3B%20%7D%20else%20%7Bmeta%20%3D%20%22%22%3B%20%7D%20window.location%3D%22http%3A%2F%2Ftop.jobbole.com%2Fsubmit%2F%3Futm_source%3Dbookmark%26utm_medium%3DtoolBar%26source%3D%22%2BencodeURIComponent(document.location)%2B%22%26title%3D%22%2BencodeURIComponent(document.title)%2B%22%26excerpt%3D%22%2BencodeURIComponent(meta)%3B%20%7D)()%0A" style="border: 1px solid #ddd; padding: 0.5em; background-color:#f8f8f8; line-height: 1.5em; margin-left: 1em;">
+ Jobbole</a>

点击该书签后，当前所在的页面会被自动提交到伯乐在线[投稿页面](http://top.jobbole.com/submit/)。
该书签会智能、自动填写标题、网址和摘要，做到真正的快捷高效。

## 开发过程

1. 编码源代码
    ```
    javascript:(function() {
    var meta = document.querySelector("meta[name=\'description\']");
    if(meta) {
        meta = meta.getAttribute("content");
    } else {
        meta = "";
    }
    window.location="http://top.jobbole.com/submit/?utm_source=bookmark&utm_medium=toolBar&source="+encodeURIComponent(document.location)+"&title="+encodeURIComponent(document.title)+"&excerpt="+encodeURIComponent(meta);
    })()
    ```
2. 对源代码进行`encodeURIComponent`，可使用[开源中国在线编码转换](http://tool.oschina.net/encode?type=4)
    需要注意的是，代码起始处的`javascript:`中的`:`不需要编码，需要手动改过来。