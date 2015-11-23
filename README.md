## 文章分享书签

本书签主要功能是方便用户向[伯乐在线 | 头条](http://top.jobbole.com/)分享文章，虽然官方也提供了[浏览器扩展](http://blog.jobbole.com/93269/)，个人觉得安装扩展显得有些“笨重”，而且最主要的是消耗系统资源。于是，参考 [pocket](https://getpocket.com/add) 与 [一点黑科技](https://1.qinghuai.org/stories/new)，写了本书签，希望对大家有帮助。😊

## 使用方法

Github 出于[某些原因](https://github.com/github/markup)，不允许在 `README.md` 里面使用 `script` 标签，内敛样式（ inline-styles），所以我只能创建 [Github pages](http://liujiacai.net/jobbole/) 来做安装演示。囧

## 开发过程

1. 编码源代码

    ```javascript
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
