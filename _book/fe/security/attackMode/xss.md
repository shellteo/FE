# XSS
跨站脚本攻击

### XSS防御:
- 方法1、对所有用户提交内容进行可靠的输入验证，包括对URL、查询关键字、HTTP头、POST数据等，仅接受指定长度范围内、采用适当格式、采用所预期的字符的内容提交，对其他的一律过滤。
- 方法2、实现Session标记(session tokens)、CAPTCHA系统或者HTTP引用头检查，以防功能被第三方网站所执行。
- 方法3、确认接收的的内容被妥善的规范化，仅包含最小的、安全的Tag(没有javascript)，去掉任何对远程内容的引用(尤其是样式表和javascript)，使用HTTP only的cookie。
- 方法4、使用content-security-policy，例如：Content-Security-Policy: default-src 'self'；csp针对不同比如css，js图片的加载策略，CSP 协议可以控制的内容非常多