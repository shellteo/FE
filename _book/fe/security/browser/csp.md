# CSP 
内容安全策略


CSP 的主要目标是减少和报告 XSS 攻击 ，XSS 攻击利用了浏览器对于从服务器所获取的内容的信任。恶意脚本在受害者的浏览器中得以运行，因为浏览器信任其内容来源，即使有的时候这些脚本并非来自于它本该来的地方。


CSP通过指定有效域——即浏览器认可的可执行脚本的有效来源——使服务器管理者有能力减少或消除XSS攻击所依赖的载体。一个CSP兼容的浏览器将会仅执行从白名单域获取到的脚本文件，忽略所有的其他脚本 (包括内联脚本和HTML的事件处理属性)。


作为一种终极防护形式，始终不允许执行脚本的站点可以选择全面禁止脚本执行。


你可以使用  Content-Security-Policy HTTP头部 来指定你的策略，像这样:
```javascript
Content-Security-Policy: policy
```