Study of HTML5 WebSocket for a Multimedia Communication

    HTML5 WebSoket应用在多媒体通信领域的研究
 
Jin-tae Park, Hyun-seo Hwang, Jun-soo Yun and Il-young Moon 

School of Computer Science and Engineering,Korea University of Technology and Education.

    计算机科学与工程学院，韩国技术教育大学。

{wlsxo05, smilebear1, yuntn55, iymoon}@koreatech.ac.kr

Abstract

    摘要

Recently, with the advent HTML5, the performance of Web service has improved. 

    最近几年来，随着HTML5的出现，web服务的性能得到了改善。

It was difficult to configure the web services using only HTML. 

    仅使用HTML去配置web服务是困难的。

However, communication between the client and the server is now possible because of HTML5. 

    然而，因为HTML5的出现，在客户端和服务器端的通信现在是可能的。

HTML5 was designed to be platform independent, and can be used on an increasing number of mobile devices for creating both mobile websites and mobile applications. 

    HTML5是平台独立的，并且可以在越来越多的移动设备上用于创建移动网站和移动应用程序。

It is frequently cited as the primary solution for enabling effective cross-platform deployment onto various smart devices.

    它经常被作为主要的解决方案可以有效的跨平台部署到各种智能设备上。

HTML5 has many new features. One of the most powerful features is the WebSocket.
    
    HTML5有许多新特性。最强大的功能之一是WebSocket。

Updated HTML5 specifications for web sockets, web browsers, and web servers allow sending and receiving data in real time, via an always-on TCP connection. 

    更新规范的HTML5 web sockets、web浏览器和web服务器允许发送和接收实时数据,通过不间断的TCP连接。

The crucial differences between pre-HTML5 communication methods and HTML5 WebSocket are located in the new HTML5 protocol. 

    之前html5通信方法和HTML5 WebSocket之间的关键差异是在于WebSocket采用了新的HTML5协议（WebSocket protocol）。

WebSocket protocol uses HTTP to establish a connection, but the subsequent communication is performed by the WebSocket reader protocol. 

    WebSocket协议采用HTTP建立连接，但随后的通信是通过WebSocket协议执行器。

In addition, the feature header is very small, resulting in reduced communication overhead. 

    此外，特征头是非常小的，从而减少通信开销。

The WebSocket aims to solve the problems of the conventional communication method, though it has several restrictions. 

    WebSocket旨在解决传统通信方式的问题，尽管它有一些限制。

Therefore, in this study, experiments were conducted to measure the performance analysis of WebSocket. 

    因此，在这项研究中，进行了实验测量WebSocket的性能分析。

We conclude by presenting the direction of future research in this field.

    最后，我们提出在这一领域的未来研究的方向。

Keywords: HTML5, WebSocket, Cross-Browser, Multi-media, Polling

    关键词：HTML5, WebSocket, Cross-Browser（跨浏览器）, Multi-media（多媒体）, Polling（轮询）

1.Introduction

    1.引言

HTML5 has attracted significant attention in the recent years.

    HTML5已经在最近几年引起了人们极大的关注。

HTML5 is the nextgeneration standard proposed in HTML [1]. 

    HTML5是HTML的下一代标准的建议。

It is not possible to configure the Web services using only HTML. 

    配置Web服务是不可能只使用HTML。

However, with the advent of HTML5, it is possible for the clients and servers to communicate. 

    然而,随着HTML5的出现,可以为客户端和服务器通信。

HTML5 was designed to be platform independent, and can be used on an increasing number of mobile devices for creating both mobile websites and mobile applications.

    HTML5是平台独立的，并且可以在越来越多的移动设备上用于创建移动网站和移动应用程序。

It is frequently cited as the primary solution for enabling effective cross-platform deployment onto various smart devices. 

    它经常被作为主要的解决方案可以有效的跨平台部署到各种智能设备上。

Some features of HTML5 may be provided to Web services without using external modules [2]. 

    HTML5的某些功能可能会提供给Web服务，而无需使用外部模块。

Market research firm Gartner, Inc. nominated HTML5 as one of the top 10 strategic technology trends for 2013. 

    市场研究公司Gartner Inc (高德纳咨询公司股份有限公司)提名HTML5为2013年十大战略技术趋势。

Gartner stated that many mobile development platforms exist in the market, but did not point out if any of them could sufficiently support development for multiple platforms. 

    Gartner表示,存在于市场上有许多移动开发平台,但没有任何一个平台指出其可以充分支持多个平台的开发。

Therefore, claims that HTML5 can enable crossplatform implementation may exercise powerful influence, and could help it further increase its growing developer base [3]. 

    因此，认为HTML5可以使跨平台的实现发生强大的影响力，并有助于进一步提高其不断增长的开发基地

According to a study by Vision Mobile, 52% of mobile application developers worldwide have used HTML5 as a development platform as of April 2013. 

    根据视觉移动的一项研究显示,全球52%的移动应用程序开发人员使用了HTML5作为开发平台截至2013年四月。

This percentage increased by 2% from January 2013.

    这一比例从2013年的一月上升到2%。

For the same timeframe, 71% of mobile developers responded that they had used the Android development platform while 57% responded that they had used iOS.

    在同一时间，71%的移动开发者回应说，他们使用Android开发平台而57%的回应说,他们使用iOS。

These results demonstrate that utilization of the HTML5 development platform is increasing relative to Android and iOS. 

    这些结果说明利用HTML5开发平台相对于Android和iOS正在增加。

Figure 1 displays a graph of platform utilization ratio trends.

    图1显示了一个图形化的平台利用率趋势。

[](figure1.png)

Figure 1. Proportional Changes in the Use of Application Development Platforms

    图1所示。成比例变化的应用程序开发平台的使用

Developers who have written a mobile application for a particular platform, commonly referred to as a native application, must perform a conversion process to implement the application on other platforms. 

    开发人员编写一个特定平台的移动应用程序,通常被称为一个本地应用程序,必须执行一个转换过程来实现在其他平台上的应用程序。

Therefore, it is frequently necessary to re-design the application so it can be utilized on the new platform, often requiring a substantial time investment and additional funding [4]. 

    因此，经常需要重新设计应用程序，所以它可以利用在新的平台上，往往需要大量的时间投资和额外的资金。

In contrast, mobile developers can use HTML5 to write applications that can be implemented on a wide range of devices, in the same manner that web-based applications can be accessed through web browsers running on many different platforms. 

    相比之下，移动开发者可以使用HTML5编写的应用程序可以在多种设备上的实现，在相同的方式，基于Web的应用程序，可以通过Web浏览器访问许多不同的平台上运行。

According to 58% of developers that were surveyed, reduced costs and development time for mobile applications were identified as the most significant advantage of HTML5.

    根据调查58%的开发者，降低成本和开发移动应用程序的时间被确定为HTML5的最显著的优势。

The browser manufacturers worldwide are cooperating in the development of HTML5.

    全球的浏览器制造商正在HTML5的发展上合作

The most powerful feature is the ability of the WebSocket application programming interface (API) [5]. 

    最强大的功能是WebSocket应用编程接口（API）功能。

One of the early purposes of the Web was to link a document using hyperlinks and facilitate document transfer.

    网络的早期目的之一就是链接文档使用超链接和促进文档传输。

The HTTP protocol for the network is a model that handles this purpose. 

    网络的HTTP协议就是处理这一目的的模型。

However, with changing times and with developments in the environment, the purpose of the Web no longer focuses only on sharing longer documents. 

    然而，随着时代的变化和在环境中的发展，网络的目的不再只是集中在共享更长的文件。

In the HTML5 initiative, many specifications have been developed under the banner of the Web application environment that are not standardized and are inconsistent with the available plug-ins, which was one of its main purposes [6].

    在HTML5的倡议，许多规格已经在Web应用环境不规范，与现有的插件不一致的旗帜下发展起来的，这是它的一个主要目的

Among them is the specification for real-time two-way communication in a pure Web environment. 

    其中之一是在一个纯网络环境中实时双向通信规范。

Updated HTML5 specifications for web sockets, web browsers, and web servers allow sending and receiving data in real time, via an always-on TCP connection [7]. 

    最新的HTML5规范的Web Sockets，Web浏览器和Web服务器允许发送和接收实时数据，通过一个总在运行的TCP连接。

Thus, the utilization of WebSockets, enabling full-duplex communication using TCP sockets, is now possible.

    因此，对WebSockets利用，使用TCP套接字实现全双工通信，现在是可能的。

Instead of evolving from HTTP communication, merely using an existing web socket shows significant improvements in properties [8].

    只通过使用一个现有的Web Socket显示出在性能上的显著改善，而不是通过发展HTTP通信。

In particular, in the event-based Web application, which is based on real-time communication, the effect is even greater. 

    特别是，在基于事件的网络应用程序，它是基于实时通信，效果更大。

The HTML5 WebSocket technology may be able to receive information quickly via the push real time, and it may reduce the wait time for unnecessary network traffic. 

    HTML5 WebSocket技术可以迅速接收信息通过实时推送数据,它可能会减少不必要的网络流量的等待时间。

Therefore, in this paper, we conducted research on the HTML 5 WebSocket performance analysis by comparing the overhead depending on the number of concurrent users and the speed of the real-time multimedia communication.

    因此,在本文中,我们在HTML5 WebSocket性能进行了研究分析，通过比较取决于并发用户的数量的开销和实时多媒体通信的速度。

2.Related Technology Trends 

    2.相关技术趋势

2.1.HTML5 WebSocket Method

    2.1.HTML5 WebSocket 方法

As a Web application platform and a next-generation technology for productivity improvement of Web development, HTML5 is an open Web standard created to provide a better user experience.

    作为一个Web应用平台和提高Web开发生产率的下一代技术，HTML5是一个开放的建立提供更好的用户体验的Web标准。

It has become possible through HTML5 to provide an excellent Web service rapidly [9]. 

    通过HTML5迅速提供一个优秀的Web服务已经成为可能。

The function of the WebSocket technology was to improve performance. 

    WebSocket技术的功能是提高性能。
    
Two-way data communication in real time actually corresponds to numerous concurrent connections. 

    双向实时数据通信实际上相当于多个并发连接。

In this case, the real-time aspects specifically, WebSocket technology is often used. 

    在这种情况下，具体的实时方面，WebSocket技术是常用的。

If the WebSocket technology is used, the unnecessary HTTP header data must be removed first in order to quickly send and receive pure data. 

    如果应用WebSocket技术，不必要的HTTP标头的数据必须先删除为了快速发送和接收纯数据。

This results in a reduction of the amount of data being transmitted and received; consequently, this reduces the load on the server and the network. 

    这将导致减少所发送和接收的数据的量，因此，这减少了服务器和网络的负载。

Then, using the WebSocket Secure (WSS) protocol, security was enhanced with a unique algorithm for encryption / decryption of data.

    其次，使用WebSocket安全（WSS）协议、用独特的加密/解密算法将使安全增强。

Figure 1 is a graph comparing the conventional communication method and new WebSocket system [10]. 

    图1图中是比较传统的通信方法和新的通信系统。

Thus, with the use of the WebSocket technology, connection-oriented full-duplex communication, such as TCP sockets, is possible [11].

    因此，随着通信技术的应用，面向连接的全双工通信，如TCP套接字，是可能的。

Using features such as these, we were able to implement more effectively the development of applications that allow chatting from the Web, real-time games, and multimedia delivery.

    使用功能，如这些，我们能够更有效地实现应用程序的开发，允许网络聊天，实时游戏，多媒体传输。

Table 1. Description of WebSocket Servers

    表1 WebSocket服务器描述

The crucial differences between pre-HTML5 communication methods and HTML5 WebSocket are located in the new HTML5 protocol. 

    之前html5通信方法和HTML5 WebSocket之间的关键差异是在于WebSocket采用了新的HTML5协议（WebSocket protocol）。

WebSocket protocol uses HTTP to establish a connection, but the subsequent communication is performed by the WebSocket reader protocol. 

    WebSocket协议采用HTTP建立连接，但随后的通信是通过WebSocket协议执行器。

In addition, the feature header is very small, resulting in reduced communication overhead. 

    此外，特征头是非常小的，从而导致减少通信开销。

Because a persistent connection is assumed, it is possible for clients and servers to remain in a connected state. 

    因为假定一个持久连接，客户端和服务器可以保持在一个连接的状态。

Accordingly, it is necessary to update existing TCP servers to meet the new WebSocket specification. 

    因此，有必要更新现有的TCP服务器来满足新的WebSocket规范。

WebSockets are present in a variety of servers. 

    WebSockets目前在各种服务器上实现。

These servers may be implemented in languages such as Java, Python, php, and Ruby. 

    这些服务器可能是被诸如java、Python、PHP和Ruby语言实现的。
    
Table 1 provides descriptions for some selected WebSocket-enabled servers.

    表1提供了一些选定的支持WebSocket的服务器。

HTML5 has emerged as Server-Sent-Events (SSE) technology. 

    HTML5已经成为服务器发送的事件（SSE）技术。

This is a standard technique that has been proposed in HTML5 to implement server pushes in a web environment. 

    这是一个标准的技术，提出了在HTML5在Web环境下实现服务器推。

However, SSE can also be utilized for socket communication, rather than as an aggressive communication method from the server to the client; for example, server push is a technology commonly employed by betting websites. 

    然而，SSE也可用于套接字通信，而不是作为一个从服务器到客户端的积极的通信方法，例如，服务器推是一种通常被采用在投注网站的技术。

HTML5 WebSockets provides the capability for pure two-way real-time communication on the web, and does not require browser plug-ins to be installed; this differentiates it from other technologies such as Java applets and ActiveX. 

    HTML5的WebSocket提供纯双向实时通信网络的能力，并且不需要安装浏览器插件；这是区别于其他技术的不同，如java applets和ActiveX控件。

Figure 2 depicts an HTML5-based WebSocket system.

    图2描述了一个基于HTML5的WebSocket系统。

[](figure2.png)

Figure 2. WebSocket Method

    图2 WebSocket方法
    
2.2.Polling Method

    轮询方法

In general, HTTP is a method in which the client sends a request to the server, and subsequently the server responds. 

    总的来说，HTTP是一种客户端向服务器发送请求，然后服务器响应的方法。

Unlike socket programming, HTTP is closer to one-way rather than two-way communication; it was not designed to enable servers to push messages to clients. 

    不同于socket编程，HTTP是更接近单向而不是双向通信；它并不是设计来支持服务器推送消息给客户端。

However, as web communications have gradually become more complex, various technologies to push data from the server to the client have been designed [12]. 

    然而，随着网络通信逐渐变得更加复杂，各种各样的技术被设计将数据从服务器推到客户端。

This led to the invention of Ajax, a periodic polling method. However, Ajax’s polling method is very inefficient, and is lacking in capability to transfer data in real time. 

    这导致了Ajax技术的发明，一个周期轮询的方法。然而，AJAX的轮询方法效率很低，而且缺乏实时数据传输的能力。

Therefore, several other methods began to appear, although none of them really integrated seamlessly with HTTP. 

    因此，其它几种方法开始出现，虽然没有一个真正的无缝集成HTTP。

One resulting method is Comet, also known as Reverse Ajax. Comet employs a long polling method, using a script tag and XHR streaming system utilizing hidden HTML IFrames.

    其中一个解决方法是Comet，也被称为反向Ajax。Comet使用长轮询的方法，使用一个脚本标签和XHR流利用隐藏的HTML内嵌框架系统。

Streaming is a method in which the client and server maintain a connection. 

    流是客户端和服务器保持连接的一种方法。

Each event represents the transmission of data to the client. 

    每一个事件代表数据传输到客户端。

When data is requested by the client, the server side remains connected and sends messages in succession without requiring a response. 
    当客户端请求数据时，服务器端保持连接并不断发送消息，而不需要响应。

This method does not require client requests to continue, but requires simultaneous connections, and can be adversely affected by the number of connections.

    此方法不需要客户端请求继续，但需要同时连接，并且可以通过连接的数目产生不利的影响。

In the long polling method, an HTTP request is sent and a response received, similar to the streaming method. 

    在长轮询方法，HTTP请求发送和收到响应，类似于流的方法。

However, after loading the page, it sends the request using a separate XMLHttpRequest (XHR) script; if the server does not immediately send a response to it, an event is generated on the server side [13]. 

    然而，加载页面后，将请求发送使用一个单独的XMLHttpRequest（XHR）脚本；如果服务器不立即给它发送回应，在服务器端生成一个事件。

A response is then transmitted to the client. 

    然后将响应发送到客户端。

By using this method, when an event occurs in the server, it is possible to transmit the data to the client in real time. 

    通过使用这种方法，当一个事件发生在服务器，它是可能实时传输数据到客户端的。

However, after sending a response, the connection between the client and the server is disconnected. 

    然而，在发送一个响应之后，客户端和服务器之间的连接被中断。

Figure 3 displays a comparison of Ajax, long polling, and streaming methods.

    图3显示了Ajax，长轮询和流的方法的比较。

[](figure3.png)

Figure 3. Polling Method

    图3 轮询方法

2.3.Comparative Analysis of the Polling Method and WebSocket System

    轮询方法的比较分析和WebSocket系统

Ajax and Comet with IFrames are polling methods. 

    Ajax和Comet框架都是轮询方法。

That is, a polling system is used instead of a push method for receiving data. 

    也就是说，一个轮询系统被用来替代一个推方法去接受数据。

The server sends messages to the client, the client sends a response to the server. 

    服务器发送消息到客户端，客户端发送响应到服务器。

The Comet technique has generally been the best choice to stay connected to avoid repeated requests. 

    Comet技术通常是保持联系的最佳选择，以避免重复的请求。

It must be re-connected to close the connection after a certain time period. 

    在一定时间段之后，必须重新连接关闭连接。

This technique is reflected in HTML5, and was a factor leading to the design of WebSockets. 

    这种技术是体现在HTML5，并且是导致WebSockets设计的一个因素。

WebSocket is a protocol that provides a bidirectional connection between the web server and the client. 

    WebSocket是一个协议，提供了Web服务器和客户端之间的双向连接。

Unlike existing sockets, WebSocket provides actual two-way connection [14]. 

    不同于现有的套接字，WebSocket可提供实际的双向连接。

It begins with a HTTP-based handshake, then the WebSocket protocol takes over to facilitate communication. 

    它从一个基于HTTP的握手，然后WebSocket协议接管促进沟通。

Because of its more advanced design compared to existing methods such as Comet, WebSocket establishes two-way connection in a different way; traffic is very light using WebSocket, and it demonstrates superior performance [15]. 

    因为相比于如Comet等现有的方法更先进的设计，WebSocket以不同的方式建立双向连接；传输很轻通过使用WebSocket，它显示了卓越的性能。

Figure 4 displays a comparison of polling methods and the WebSocket system.

    图4显示轮询方法和WebSocket系统的比较。
    
[](figure4.png)

Figure 4. Comparison of WebSocket and Conventional Polling Methods

    图4 WebSocket和传统的轮询方法的比较

3.Design and Implementation of the Experiment

    体验的设计和实现

3.1.Design

    设计

The following assumptions are made:

* WebSocket technology is required.
* Real-time two-way data communication is required.
* There are many concurrent connections.
* It is necessary to extend the TCP-based communication browser.
* The developer is required to use the easy-to-use API net reason.
* It is necessary to extend the SOA beyond environments such as the cloud, and Web.


    下面的假设：
        * WebSocket技术是必需。
        * 实时双向数据通信是必需的。
        * 有很多并发连接。
        * 要使用基于浏览器的TCP通信。
        * 开发人员需要使用易于使用的API的原因。
        * 为了扩展SOA超越如云环境和网络。

Therefore, in this paper, our experimental design functions through the polling conventional manner with real-time two-way data communication using the WebSocket methodology through the transfer delay time. 

    因此,在本文中,我们的实验设计功能是通过向传统轮询方式与使用实时的双向数据通信的WebSocket方式设置传输延迟时间。

We compare the overhead corresponding to the number of concurrent users, and analyze its performance. 

    我们比较了相应的并发用户的数量的开销，并分析其性能。

To ensure that the experiment is accurate, we implemented the Web to execute the polling method and the WebSocket technology to execute the multimedia data communication system. 

    为了确保试验的准确性，我们实现了Web执行轮询方法和WebSocket技术进行多媒体数据通信系统。

For the client polling method, we use the setInterVal() method, and transmit the HTTP requests at regular intervals through the browser.

    对于客户端轮询的方法，我们使用setinterval()方法，定期通过浏览器发送HTTP请求的方法。

3.2.Experiment Environment

    实验环境
    
In this paper, we propose a HTML5-based client/server environment for the experiment.

    在本文中，我们提出了一个基于HTML5的客户端/服务器环境实验。

The client and the server will utilize two-way communication to send and receive multimedia data. 

    客户端和服务器将利用双向通信来发送和接收多媒体数据。

We conducted experiments using WebSocket methods and polling methods to connect the client and server. 

    我们进行了使用WebSocket方法和轮询方法来连接客户机和服务器实验。

The WebSocket and polling system source code for both client and server is displayed in the following section. 

    WebSocket和轮询系统的客户端和服务器系统的源代码在下面的部分显示。

The client requests a WebSocket connection on the server with JavaScript (JS), included in the HTML to be sent to the HTTP server. 

    客户端请求器一个WebSocket连接通过JavaScript的服务端，包含在HTML被发送到http服务器。

Therefore, it transmits the HTML by constructing an HTTP server node.js.

    因此，它发送html通过建立一个HTTP服务器Node.js。

```javascript
var clientScript = function() {
    var ws = new WebSocket("ws://localhost:3000/", ["test", "chat"]); 
    ws.onopen = function() {
        console.log(ws);
        ws.send("Test");
        ws.onmessage = function(message) {console.log(message.data); };
    } 
}
var server = http.createServer(function(req, res) { 
    res.writeHead(200, {'Content-Type': 'text/html'});
    var html = '<html><head><title>Web Socket 서버</title>' +'<script type="text/javascript">' + '('+ clientScript + ')();' +             '</script>' +'</head>' + '<body>WebSocketTest</body>' + '</html>'; 
    res.end(html);
});
```

* Source of the WebSocket server system


    * WebSocket服务器系统源码

```javascript
var ws = new WebSocket("ws://localhost:3000/", ["test", "chat"]); 
ws.onopen = function() {
    ws.send("test");
    ws.onmessage = function(message) {console.log(message.data); };
}
```

* Source of the WebSocket client system


    * WebSocket客户端系统源码

```javascript
<script language='javascript' src='http://ajax.googleapis.com/ajax/libs/jquery/1.4.2/jquery.min.js'></script>
<script>
$(document).ready(function(){
    jQuery.ajax({
        type:"GET",
        url:"test.html",
        success:function(msg){
            alert(msg);
        },
        error: function(xhr,status,error){
            alert(error);
        }
    });
});
</script>
```

* Source of the Polling client system


    * 轮询客户端系统的源程序
    
By comparing the results from the WebSocket and polling method client/server configurations, we analyzed the header information for the server in response to client requests.

4.Analysis Result

    结果分析

4.1.WebSocket and Polling Methods

    WebSocket和轮询方法
    
We compared the overhead of the network implemented via the server and the client. 

    我们比较了通过服务器和客户端实现的网络的开销。

As shown in Figure 5(a), the system is a WebSocket header data request and the response does not exist. 

    如图5（a），该系统是一个WebSocket报头数据请求和响应不存在。

On the other hand, as shown in Figure 5(b), in the polling method, whenever there is a response to the HTTP request, the HTTP headers are passed, and the associated overhead occurs.

    在另一方面，作为显示在图5（b），在轮询方法，每当有一个响应对HTTP的请求，HTTP headers被传递，相关的开销发生。

(a) Value of WebSocket header (b) Value of polling heade

    （a）WebSocket头部报文值（b）轮询头部报文值

Figure 5. Comparison of the ActualOoverhead of WebSocket and Polling Method

    图5 WebSocket和轮询的方法比较的实际开销

In order to communicate multimedia data of one gigabyte, the polling method is used.

    为了沟通1G的多媒体数据，采用轮询的方法。

The WebSocket system needs the capacity of the header data to be about 1,000 bytes; the header is not needed because of the low data capacity. 

    WebSocket通信系统需要的头数据容量约为1000字节；不需要头因为低的数据容量。

It is assumed that when ten persons access the multimedia data of one gigabyte using the polling method, (that the header data capacity is 10,000 bytes, then when 100 people access the multimedia data of one gigabyte, that the header data capacity will be 100,000 bytes.

    假定当十人使用轮询方法访问1G的多媒体数据，（该头的数据容量为10000字节，那么当100人访问1G，多媒体数据，数据量是100000个字节的头）。

On the other hand, with the WebSocket type, the additional capacity does not occur. 

    另一方面，因为WebSocket方式，额外的容量不发生。

These additional header data generate the overhead for a large number of users on the network.

    这些附加的头数据产生大量用户在网络上的开销。

[](figure6.png)

Figure 6. Comparison of the Overhead Generated by the Polling and WebSocket Method based on the Concurrent Number of Users

    图6 通过基于用户并发数的轮询和WebSocket方法产生的开销比较

In addition, we also measured the transfer delay time and the overhead generated by increasing the number of concurrent connections.

    此外，我们还测量了传输延迟时间和所产生的通过增加并发连接数量的开销。

We compared the overhead generated by an increasing number of concurrent users. 

    我们比较的开销是通过越来越多的并发用户产生的。

Figure 6 shows the results. 

    图6显示了结果。

As the concurrent number of users increase, the overhead of the polling method increases, while the overhead of WebSocket system was barely noticeable. 

    随着用户数量的增加的同时，轮询的方法开销增加，而WebSocket的系统开销是几乎不引人注意的。

In the polling method, starting from the client’s request, the forward delay time, the time of 60 ms consuming, and the time while waiting re-request, even if the response occurs after the response time from the server, all become overhead. However, using the WebSocket system, connections that occur after the first connection, resulted in the connection being maintained, with no additional latency.

    在轮询方法中，从客户端的请求开始，转发延迟时间，60毫秒的时间消耗，并且在等待时间的要求，即使响应发生在服务器响应时间后，都成为开销。然而，使用WebSocket系统，连接发生的第一个连接后，导致连接被保持，没有额外的延迟。

Figure 7 is a graph comparing the response times of the system using the polling and WebSocket methods. 

    图7是比较的系统采用轮询和WebSocket的方法的响应时间，。

The x-axis represents the number of requests, and the y-axis represents the response time (ms).

    X轴表示请求的数量，y轴表示响应时间（毫秒）。

[](figure7.png)

Figure 7. Comparison of the Response Time of the WebSocket and Polling Method

    图7。比较的WebSocket和轮询的方法的响应时间

4.2.Cross-Browser

    跨浏览器

In this paper, a comparison was made between the overhead and response time of the polling and WebSocket methods. 

    本文比较的开销和响应时间的投票和WebSocket的方法。

Currently, not all HTML5 functions work across browsers. 

For example, WebStorage is a new feature in HTML5 that provides a function similar to cookies, but allows more advanced data storage on the client.

However, because different browsers store data in different repositories, data access cannot be performed where compatibility is an issue. 

This was subjected to cross-browser tests using the two methods, in order to solve this problem.

* Save each to each Browser
If an inspection has not been performed to determine whether a cookie is present in each browser, use cookie as the recording method.

* Shared Flash Object
Use the Shared Object for shared data storage, for client-side Flash presentation.

The next figure displays an information screen indicating that you are logged into Chrome for either of the previous methods, and is recognized by IE.

[](figure8.png)

Figure 8. Cross-Browser compared with Two Browsers

5. Conclusion

Interest in the new Web Of Things (WoT) standard is rapidly increasing. 

Specific interest in this proposed standard, which connects large numbers of devices together using the web, will continue to increase, thus increasing interest in HTML5. 

In such a situation, with the advent of HTML5, we are able to provide better service, which is significantly faster than the existing Web services. 

HTML5 uses an open Web standard as a Web application platform and is a next-generation productivity improvement for Web development, which works together to create a better user experience.

HTML5 is a concept that includes a JavaScript API extension for CSS3, the web style sheet language.

CSS3 is capable of providing a representation that is consistent with different browsers, in a convenient and effective manner. 

The JavaScript API allows the development of local applications, and can control the various resources and rich features. 

This includes WebStorage, WebWorker, WebSocket, and the GeolocationAPI.

The function of WebSocket technology is to improve performance.

This reduces the network load when compared to conventional methods. 

The WebSocket technology is often used when real-time two-way data communication is required. 

In particular, the positive effects of using the WebSocket technology are more pronounced while using web applications based on real-time two-way data communication. 

On the other hand, not many browsers that support HTML5 support web sockets. 

Further, if security is enabled while using a web socket, it proves to be disadvantageous. 

Currently, technical research is actively promoted for using WebSocket technology to improve its performance. 

In addition, future research can be conducted to study cross-browser compatibility with WebSocket technology, and reduction of its security vulnerability can be researched.

Acknowledgement

    致谢

This research was financially supported by the Ministry of Knowledge Economy(MKE) and Korea Institute for Advancement of Technology(KIAT) through the Research and Development for Regional Industry.

    本研究在经济上得到了韩国知识经济部支持（MKE）和韩国先进技术研究所（Kiat）通过区域产业的研究和开发。

