Study of HTML5 WebSocket for a Multimedia Communication
HTML5 WebSoket应用在多媒体通信领域的研究

Jin-tae Park, Hyun-seo Hwang, Jun-soo Yun and Il-young Moon
School of Computer Science and Engineering,
Korea University of Technology and Education.
计算机科学与工程学院，高丽大学教育技术与教育。
{wlsxo05, smilebear1, yuntn55, iymoon}@koreatech.ac.kr

Abstract
摘要
Recently, with the advent HTML5, the performance of Web service has improved. 
最年来，随着HTML5的出现，网络服务的性能有了提高。
It was difficult to configure the web services using only HTML. 
仅使用HTML去搭建web服务是困难的。
However, communication between the client and the server is now possible because of HTML5. 
然而，因为HTML5的出现，在客户端和服务器端的通信是可能的。
HTML5 was designed to be platform independent, and can be used on an increasing number of mobile devices for creating both mobile websites and mobile applications. 
HTML5被设计成一个独立的平台，可以应用在越来越多的移动设备去创建移动网站和移动应用。
It is frequently cited as the primary solution for enabling effective cross-platform deployment onto various smart devices.
它经常被引为实现有效的跨平台部署到各种智能设备的主要解决方案。
HTML5 has many new features. One of the most powerful features is the WebSocket.
HTML5有很多新的功能。 最强大的功能之一是WebSocket。
Updated HTML5 specifications for web sockets, web browsers, and web servers allow sending and receiving data in real time, via an always-on TCP connection. 
最新的HTML5 Web Sockets规范，Web浏览器和Web服务器允许发送和接收实时数据，通过一个TCP
长连接。
The crucial differences between pre-HTML5 communication methods and HTML5 WebSocket are located in the new HTML5 protocol. 
之前html5通信方法和HTML5 WebSocket之间的关键差异是在于新的HTML5协议的出现。
WebSocket protocol uses HTTP to establish a connection, but the subsequent communication is performed by the WebSocket reader protocol. 
WebSocket协议采用HTTP建立连接，但随后的通信是通过WebSocket协议执行器。
In addition, the feature header is very small, resulting in reduced communication overhead. 
此外，特征头是非常小的，从而导致减少通信开销。
The WebSocket aims to solve the problems of the conventional communication method, though it has several restrictions. 
WebSocket旨在解决传统通信方式的问题，尽管它有一些限制。
Therefore, in this study, experiments were conducted to measure the
performance analysis of WebSocket. 
因此，在这项研究中，进行了实验测量WebSocket的性能分析。
We conclude by presenting the direction of future research in this field.
我们的结论是在这一领域的未来研究的方向。
Keywords: HTML5, WebSocket, Cross-Browser, Multi-media, Polling
关键词：HTML5, WebSocket, Cross-Browser, Multi-media, Polling
1. Introduction
1. 引言
HTML5 has attracted significant attention in the recent years.
HTML5已经在最近几年引起了人们极大的关注。
HTML5 is the nextgeneration standard proposed in HTML [1]. 
HTML5是HTML的下一代标准的建议。
It is not possible to configure the Web services using only HTML. 

However, with the advent of HTML5, it is possible for the clients and servers to communicate. 

HTML5 was designed to be platform independent, and can be used on an increasing number of mobile devices for creating both mobile websites and mobile applications. 

It is frequently cited as the primary solution for
enabling effective cross-platform deployment onto various smart devices. Some
features of HTML5 may be provided to Web services without using external modules
[2]. Market research firm Gartner, Inc. nominated HTML5 as one of the top 10 strategic
technology trends for 2013. Gartner stated that many mobile development platforms
exist in the market, but did not point out if any of them could sufficiently support
development for multiple platforms. Therefore, claims that HTML5 can enable crossplatform
implementation may exercise powerful influence, and could help it further
increase its growing developer base [3]. According to a study by Vision Mobile, 52% of
mobile application developers worldwide have used HTML5 as a development platform
as of April 2013. This percentage increased by 2% from January 2013. For the same
timeframe, 71% of mobile developers responded that they had used the Android 
development platform while 57% responded that they had used iOS. These results
demonstrate that utilization of the HTML5 development platform is increasing relative
to Android and iOS. Figure 1 displays a graph of platform utilization ratio trends.







