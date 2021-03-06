![截屏2020-04-23下午9.41.55](https://tva1.sinaimg.cn/large/007S8ZIlly1ge4196qjj9j30ww0j4dhj.jpg)

图为一个HTTP请求报文的通用格式。报文中的每一个字段都是一些ASCII码。

## 请求行(request line)

请求行有3个字段：方法字段、URL字段和HTTP协议版本字段。

## 首部行(header line)

典型的请求头有：

- Host：请求的主机名。

- Connection：若值为close，该浏览器告诉服务器不希望麻烦地使用持续连接，它要求服务器在发送完被请求的对象后就关闭这条连接。

- User-agent：用来指明用户代理，即向服务器发送请求的浏览器的类型。

- Accept-lange：表示用户想得到该对象的语言版本。
- Accept：告诉服务器，客户端接受什么类型的响应。
- Content-Type：发送的实体体中数据的类型。
- Cookie：携带客户端的cookie信息。
- Cache-Control：缓存控制。

## 实体体(Entity body)

使用GET方法时实体体通常为空。

当用户提交表单时，HTTP客户常常使用POST方法，实体中包含的就是用户在表单字段中的输入值。

## 关于HTTP请求GET和POST的区别

1. GET提交，请求的数据会附在URL之后，以?分割URL和传输数据，多个参数用&连接。如果数据是英文字母/数字，原样发送，如果是空格，转换为+，如果是中文/其他字符，则直接把字符串用BASE64加密。

   POST提交，把提交的数据放置在HTTP报文的实体体中。

   因此，GET提交的数据会在地址栏中显示出来，而POST提交，地址栏不会改变。

2. 传输数据的大小：

   首先声明，HTTP协议没有对传输的数据大小进行限制，HTTP协议规范也没有对URL长度进行限制。实际开发中存在的限制主要有：

   GET：特定浏览器和服务器对URL长度有限制，例如IE对URL长度的限制是2083字节。

   因此对于GET提交时，传输数据就会受到URL长度的限制。

   POST：由于不是通过URL传值，理论上数据不受限。但实际各个WEB服务器会规定对post提交数据大小进行限制。

3. 安全性：

   POST的安全性要比GET的安全性高。