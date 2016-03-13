Study of HTML5 WebSocket for a Multimedia Communication

HTML5 WebSoket应用在多媒体通信领域的研究
 
Jin-tae Park, Hyun-seo Hwang, Jun-soo Yun and Il-young Moon 

School of Computer Science and Engineering,Korea University of Technology and Education.

计算机科学与工程学院，韩国技术教育大学。

{wlsxo05, smilebear1, yuntn55, iymoon}@koreatech.ac.kr

Abstract

摘要

Recently, with the advent HTML5, the performance of Web service has improved. 

最年来，随着HTML5的出现，web服务的性能得到了改善。

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

1. Introduction
1. 引言

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

Gartner stated that many mobile development platforms exist in the market, but did not point out if any of them could sufficiently support
development for multiple platforms. 

Therefore, claims that HTML5 can enable crossplatform implementation may exercise powerful influence, and could help it further increase its growing developer base [3]. 

According to a study by Vision Mobile, 52% of mobile application developers worldwide have used HTML5 as a development platform
as of April 2013. 

This percentage increased by 2% from January 2013.

For the same timeframe, 71% of mobile developers responded that they had used the Android development platform while 57% responded that they had used iOS.

These results demonstrate that utilization of the HTML5 development platform is increasing relative to Android and iOS. 

Figure 1 displays a graph of platform utilization ratio trends.

[](figure1.png)

Figure 1. Proportional Changes in the Use of Application Development Platforms

Developers who have written a mobile application for a particular platform, commonly referred to as a native application, must perform a conversion process to implement the application on other platforms. 

Therefore, it is frequently necessary to re-design the application so it can be utilized on the new platform, often requiring a substantial time investment and additional funding [4]. 

In contrast, mobile developers can use HTML5 to write applications that can be implemented on a wide range of devices, in the same manner that web-based applications can be accessed through web browsers running on many different platforms. 

According to 58% of developers that were surveyed, reduced costs and development time for mobile applications were identified as the most significant advantage of HTML5.

The browser manufacturers worldwide are cooperating in the development of HTML5. The most powerful feature is the ability of the WebSocket application programming interface (API) [5]. One of the early purposes of the Web was to link a document using hyperlinks and facilitate document transfer. The HTTP protocol for the network is a model that handles this purpose. However, with changing times and with developments in the environment, the purpose of the Web no longer focuses only on sharing longer documents. In the HTML5 initiative, many specifications have been developed under the banner of the Web application environment that are not standardized and are inconsistent with the available plug-ins, which was one of its main purposes [6]. Among them is the specification for real-time two-way communication in a pure Web environment. Updated HTML5 specifications for web sockets, web browsers, and web servers allow sending and receiving data in real time, via an always- on TCP connection [7]. Thus, the utilization of WebSockets, enabling full-duplex communication using TCP sockets, is now possible. Instead of evolving from HTTP communication, merely using an existing web socket shows significant improvements in properties [8]. In particular, in the event-based Web application, which is based on real-time communication, the effect is even greater. The HTML5 WebSocket technology may be able to receive information quickly via the push real time, and it may reduce the wait time for unnecessary network traffic. Therefore, in this paper, we conducted research on the HTML 5 WebSocket performance analysis by comparing the overhead depending on the number of concurrent users and the speed of the real-time multimedia communication.

2. Related Technology Trends 
2.1. HTML5 WebSocket Method
As a Web application platform and a next-generation technology for productivity improvement of Web development, HTML5 is an open Web standard created to provide a better user experience. It has become possible through HTML5 to provide an excellent Web service rapidly [9]. The function of the WebSocket technology was to improve performance. Two-way data communication in real time actually corresponds to numerous concurrent connections. In this case, the real-time aspects specifically, WebSocket technology is often used. If the WebSocket technology is used, the unnecessary HTTP header data must be removed first in order to quickly send and receive pure data. This results in a reduction of the amount of data being transmitted and received; consequently, this reduces the load on the server and the network. Then, using the WebSocket Secure (WSS) protocol, security was enhanced with a unique algorithm for encryption / decryption of data. Figure 1 is a graph comparing the conventional communication method and new WebSocket system [10]. Thus, with the use of the WebSocket technology, connection-oriented full-duplex communication, such as TCP sockets, is possible [11]. Using features such as these, we were able to implement more effectively the development of applications that allow chatting from the Web, real-time games, and multimedia delivery.

Table 1. Description of WebSocket Servers



The crucial differences between pre-HTML5 communication methods and HTML5 WebSocket are located in the new HTML5 protocol. WebSocket protocol uses HTTP to establish a connection, but the subsequent communication is performed by the WebSocket reader protocol. In addition, the feature header is very small, resulting in reduced communication overhead. Because a persistent connection is assumed, it is possible for clients and servers to remain in a connected state. Accordingly, it is necessary to update existing TCP servers to meet the new WebSocket specification. WebSockets are present in a variety of servers. These servers may be implemented in languages such as Java, Python, php, and Ruby. Table 1 provides descriptions for some selected WebSocket-enabled servers.

HTML5 has emerged as Server-Sent-Events (SSE) technology. This is a standard technique that has been proposed in HTML5 to implement server pushes in a web environment. However, SSE can also be utilized for socket communication, rather than as an aggressive communication method from the server to the client; for example, server push is a technology commonly employed by betting websites. HTML5 WebSockets provides the capability for pure two-way real-time communication on the web, and does not require browser plug-ins to be installed; this differentiates it from other technologies such as Java applets and ActiveX. Figure 2 depicts an HTML5-based WebSocket system.

[](figure2.png)

Figure 2. WebSocket Method

2.2. Polling Method

In general, HTTP is a method in which the client sends a request to the server, and subsequently the server responds. Unlike socket programming, HTTP is closer to one-way rather than two-way communication; it was not designed to enable servers to push messages to clients. However, as web communications have gradually become more complex, various technologies to push data from the server to the client have been designed [12]. This led to the invention of Ajax, a periodic polling method. However, Ajax’s polling method is very inefficient, and is lacking in capability to transfer data in real time. Therefore, several other methods began to appear, although none of them really integrated seamlessly with HTTP. One resulting method is Comet, also known as Reverse Ajax. Comet employs a long polling method, using a script tag and XHR streaming system utilizing hidden HTML IFrames.

Streaming is a method in which the client and server maintain a connection. Each event represents the transmission of data to the client. When data is requested by the client, the server side remains connected and sends messages in succession without requiring a response. This method does not require client requests to continue, but requires simultaneous connections, and can be adversely affected by the number of connections.

In the long polling method, an HTTP request is sent and a response received, similar to the streaming method. However, after loading the page, it sends the request using a separate XMLHttpRequest (XHR) script; if the server does not immediately send a response to it, an event is generated on the server side [13]. A response is then transmitted to the client. By using this method, when an event occurs in the server, it is possible to transmit the data to the client in real time. However, after sending a response, the connection between the client and the server is disconnected. Fig 3 displays a comparison of Ajax, long polling, and streaming methods.

[](figure3.png)

Figure 3. Polling Method

2.3. Comparative Analysis of the Polling Method and WebSocket System

Ajax and Comet with IFrames are polling methods. That is, a polling system is used instead of a push method for receiving data. The server sends messages to the client, the client sends a response to the server. The Comet technique has generally been the best choice to stay connected to avoid repeated requests. It must be re-connected to close the connection after a certain time period. This technique is reflected in HTML5, and was a factor leading to the design of WebSockets. WebSocket is a protocol that provides a bidirectional connection between the web server and the client. Unlike existing sockets, WebSocket provides actual two-way connection [14]. It begins with a HTTP-based handshake, then the WebSocket protocol takes over to facilitate communication. Because of its more advanced design compared to existing methods such as Comet, WebSocket establishes two-way connection in a different way; traffic is very light using WebSocket, and it demonstrates superior performance [15]. Figure 4 displays a comparison of polling methods and the WebSocket system.

[](figure4.png)

Figure 4. Comparison of WebSocket and Conventional Polling Methods

3. Design and Implementation of the Experiment

3.1. Design

The following assumptions are made:

* WebSocket technology is required.
* Real-time two-way data communication is required.
* There are many concurrent connections.
* It is necessary to extend the TCP-based communication browser.
* The developer is required to use the easy-to-use API net reason.
* It is necessary to extend the SOA beyond environments such as the cloud, and Web.

Therefore, in this paper, our experimental design functions through the polling conventional manner with real-time two-way data communication using the WebSocket methodology through the transfer delay time. We compare the overhead corresponding to the number of concurrent users, and analyze its performance. To ensure that the experiment is accurate, we implemented the Web to execute the polling method and the WebSocket technology to execute the multimedia data communication system. For the client polling method, we use the setInterVal () method, and transmit the HTTP requests at regular intervals through the browser.

3.2. Experiment Environment

In this paper, we propose a HTML5-based client/server environment for the experiment. The client and the server will utilize two-way communication to send and receive multimedia data. We conducted experiments using WebSocket methods and polling methods to connect the client and server. The WebSocket and polling system source code for both client and server is displayed in the following section. The client requests a WebSocket connection on the server with JavaScript (JS), included in the HTML to be sent to the HTTP server. Therefore, it transmits the HTML by constructing an HTTP server node.js.

```javascript

var clientScript = function() {
var ws = new WebSocket("ws://localhost:3000/", ["test", "chat"]); ws.onopen = function() {
console.log(ws);
ws.send("Test");
ws.onmessage = function(message) {
console.log(message.data); };
} }
var server = http.createServer(function(req, res) { res.writeHead(200, {'Content-Type': 'text/html'});
var html = '<html><head><title>Web Socket 서버</title>' +
'<script type="text/javascript">' + '('+ clientScript + ')();' + '</script>' +
'</head>' + '<body>WebSocketTest</body>' +
'</html>'; res.end(html);
});

```


