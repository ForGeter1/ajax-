# ajax-
ajax 的请求过程

ajax:一种局部刷新的前后端数据交互技术。
          网站开发套路：
          1：后端渲染(传统)：网站版本更新麻烦，代码杂乱混合不利于后期项目的修改和管理
          2：前后端分离：前后端代码独立开来，互不干扰，开发速度快，项目质量更高，益于后期维护 
        

ajax请求步骤如下：

 <script>
    
        // 1：相当于拿出手机
        var http = new XMLHttpRequest()

        // 2：相当于输入正确的号码，拨号方式等
        /**
         * methods：请求方式
         * URL：请求地址
         * async：是否异步
         */
        http.open("GET", "http://youku.com/", true)

        // 3: 点击播放按键，开始拨号
        http.send()

        // 4: 拨号中，判断电话是否打通，没有打通给予提示，打通了则进行通话
        http.onreadystatechange = function () {
            if (http.statusText == "OK") {
                console.log(http.responseText)
            } else {
                alert("网络不好，稍后再试")
            }
        }

        /**
         * 如果你ajax请求一个网址出现错误：
         * Access-Control-Allow-Origin 
         * 
         * 表示 跨域请求，被浏览器限制了。
         * 
         * 导致的原因：
         *  浏览器出于安全考虑，基于同源策略 
         * 
         * 当访问的URL  请求协议://域名:端口 只要有一个不相同，则跨域，全相同则成功请求
         * 
         * 
         * 解决跨域：
         *   
         *   1：JSONP
         *      将跨域的接口URL地址作为  <script src="URL"><//script>，以一种文件读取的方式来请求资源(不存在跨域名)
         *      前端需要向后端传入callback，后端数据计算完成后，通过 callback 将数据返回回去
         * 
         *      案例地址：http://www.runoob.com/json/json-jsonp.html
         * 
         * 
         *   2：后端允许跨域
         *      后端语言配置 header 的 Access-Control-Allow-Origin 字段，指定允许访问的对象
         * 
         *   3：后端代理转发前端请求
         * 
         *      前端A直接请求别人的C网站，被浏览器同源策略阻挡，这时候我们可以自己写个后端B。
         *      
         *      A(浏览器) -->  B(自己的服务器)  --> C(别人的服务器)
         * 
         *      数据返回的流程：C --> B --> A  
         * 
         */


    </script>
