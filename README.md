# weixin_across_pay
微信支付的跨公众号支付

先说下我的需求。我有两个公众号（不是订阅号，订阅号无法向公众号支付）分别为A和B，现在我关注公众号A，在公众号A中需要发起公众号B的支付，也就是说我在公众号A中向公众号B支付钱（用户未关注B公众号）。

微信登录分为两类：需要用户确认的授权登录与静默授权，用户确认的授权登录因为要通过用户的个人确认，所以可以获取用户全面的信息，无论是否关注相关微信号都可以获取，静默授权是嵌套在普通网页中的授权方式，不需要用户确认，但只能获取微信用户的唯一标识openid，但有时候这种交互方式更加的友好，对于用户的简单认证还是很有用的。接下来就分别详细介绍下两种登录方式的详细过程，减少没有必要的踩坑，无论什么授权，就是要具有网页授权的基本接口权限。

该方法是使用静默授权方式获取openid
