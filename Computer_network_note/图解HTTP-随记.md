# 第1章 了解Web及网络基础

## 1.1 使用 HTTP 协议访问 Web

**客户端(client)：**通过发送请求获取服务器资源的 Web 浏览器等。

<img src="图解HTTP-随记/image-20201228182050005.png" alt="image-20201228182050005" style="zoom:80%;" />



## 1.2 HTTP 的诞生

<img src="图解HTTP-随记/image-20201228182406523.png" alt="image-20201228182406523" style="zoom:80%;" />

**Apache：**Web 服务器标准之一

<img src="图解HTTP-随记/image-20201228182923007.png" alt="image-20201228182923007" style="zoom:80%;" />



## 1.3 网络基础 TCP/IP

<img src="图解HTTP-随记/image-20201228183041750.png" alt="image-20201228183041750" style="zoom:80%;" />



**协议：**

<img src="图解HTTP-随记/image-20201228183256921.png" alt="image-20201228183256921" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201228183411263.png" alt="image-20201228183411263" style="zoom:67%;" />



**TCP/IP：**

<img src="图解HTTP-随记/image-20201228183528736.png" alt="image-20201228183528736" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228183541273.png" alt="image-20201228183541273" style="zoom:67%;" />





### TCP/IP 的分层管理

<img src="图解HTTP-随记/image-20201228184032769.png" alt="image-20201228184032769" style="zoom:80%;" />

**分层的好处：**

<img src="图解HTTP-随记/image-20201228184001986.png" alt="image-20201228184001986" style="zoom:80%;" />



**各层的作用：**

+ **应用层**

  <img src="图解HTTP-随记/image-20201228184218073.png" alt="image-20201228184218073" style="zoom:80%;" />

+ **传输层**

  <img src="图解HTTP-随记/image-20201228184802159.png" alt="image-20201228184802159" style="zoom: 80%;" />

+ **网络层**

  <img src="图解HTTP-随记/image-20201228184855932.png" alt="image-20201228184855932" style="zoom:80%;" />

+ **链路层**

  <img src="图解HTTP-随记/image-20201228185004818.png" alt="image-20201228185004818" style="zoom:80%;" />





### TCP/IP 通信传输流

<img src="图解HTTP-随记/image-20201228185318055.png" alt="image-20201228185318055" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201228185420208.png" alt="image-20201228185420208" style="zoom:60%;" />

<img src="图解HTTP-随记/image-20201228185754109.png" alt="image-20201228185754109" style="zoom:67%;" />

**封装：**

<img src="图解HTTP-随记/image-20201228185813444.png" alt="image-20201228185813444" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228185940571.png" alt="image-20201228185940571" style="zoom:67%;" />



## 1.4 与 HTTP 关系密切的协议 : IP、TCP 和 DNS

<img src="图解HTTP-随记/image-20201228190336634.png" alt="image-20201228190336634" style="zoom: 80%;" />



### 负责传输的 IP 协议

<img src="图解HTTP-随记/image-20201228192243663.png" alt="image-20201228192243663" style="zoom:80%;" />



<img src="图解HTTP-随记/image-20201228192441300.png" alt="image-20201228192441300" style="zoom:80%;" />



#### 使用 ARP 协议凭借 MAC 地址进行通信

**IP 间的通信依赖 MAC 地址**

**ARP 是一种用以解析地址的协议，根据通信方 的 IP 地址就可以反查出对应的 MAC 地址。**

<img src="图解HTTP-随记/image-20201228192803886.png" alt="image-20201228192803886" style="zoom:80%;" />



**路由选择（routing）：**

<img src="图解HTTP-随记/image-20201228193157172.png" alt="image-20201228193157172" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201228193330475.png" alt="image-20201228193330475" style="zoom:67%;" />



### 确保可靠性的 TCP 协议

<img src="图解HTTP-随记/image-20201228193537987.png" alt="image-20201228193537987" style="zoom:80%;" />

**可靠的字节流服务：**

<img src="图解HTTP-随记/image-20201228193715849.png" alt="image-20201228193715849" style="zoom:80%;" />



#### 三次握手

<img src="图解HTTP-随记/image-20201228193817057.png" alt="image-20201228193817057" style="zoom:80%;" />



<img src="图解HTTP-随记/image-20201228194009313.png" alt="image-20201228194009313" style="zoom: 80%;" />

<img src="图解HTTP-随记/image-20201228194226077.png" alt="image-20201228194226077" style="zoom:65%;" /><img src="图解HTTP-随记/image-20201228194234483.png" alt="image-20201228194234483" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20201228194300105.png" alt="image-20201228194300105" style="zoom: 80%;" />





## 1.5 负责域名解析的 DNS 服务

<img src="图解HTTP-随记/image-20201228194601611.png" alt="image-20201228194601611" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201228204146403.png" alt="image-20201228204146403" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20201228195342735.png" alt="image-20201228195342735" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228195402293.png" alt="image-20201228195402293" style="zoom:67%;" />





## 1.6 各种协议与 HTTP 协议的关系

<img src="图解HTTP-随记/image-20201228195825635.png" alt="image-20201228195825635" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201228200346439.png" alt="image-20201228200346439" style="zoom:80%;" />



## 1.7 URI 和 URL

<img src="图解HTTP-随记/image-20201228200903591.png" alt="image-20201228200903591" style="zoom:80%;" />



### URI

<img src="图解HTTP-随记/image-20201228201208313.png" alt="image-20201228201208313" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20201228201422959.png" alt="image-20201228201422959" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228201648097.png" alt="image-20201228201648097" style="zoom:70%;" />





#### URL

**URL是 URI 的子集**

<img src="图解HTTP-随记/image-20201228201600908.png" alt="image-20201228201600908" style="zoom:80%;" />



#### URI 格式

<img src="图解HTTP-随记/image-20201228204900234.png" alt="image-20201228204900234" style="zoom:80%;" />

+ **绝对URI**

  <img src="图解HTTP-随记/image-20201228205740904.png" alt="image-20201228205740904" style="zoom:80%;" />

  + **协议方案名**

    <img src="图解HTTP-随记/image-20201228205804192.png" alt="image-20201228205804192" style="zoom: 80%;" />

  + **登录信息(认证)**

    <img src="图解HTTP-随记/image-20201228210004609.png" alt="image-20201228210004609" style="zoom:80%;" />

  + **服务器地址**

    <img src="图解HTTP-随记/image-20201228205920605.png" alt="image-20201228205920605" style="zoom:80%;" />

  + **服务器端口号**

    <img src="图解HTTP-随记/image-20201228205949500.png" alt="image-20201228205949500" style="zoom:80%;" />

  + **带层次的文件路径**

    <img src="图解HTTP-随记/image-20201228210055946.png" alt="image-20201228210055946" style="zoom:80%;" />

  + **查询字符串**

    <img src="图解HTTP-随记/image-20201228210123125.png" alt="image-20201228210123125" style="zoom:80%;" />

  + **片段表示符**

    <img src="图解HTTP-随记/image-20201228210249857.png" alt="image-20201228210249857" style="zoom:80%;" />



### RFC标准

<img src="图解HTTP-随记/image-20201228210708372.png" alt="image-20201228210708372" style="zoom:80%;" />





# 第 2 章 简单的 HTTP 协议

## 2.1 HTTP 协议用于客户端和服务器端之间的通信

<img src="图解HTTP-随记/image-20201228211500893.png" alt="image-20201228211500893" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228211514266.png" alt="image-20201228211514266" style="zoom:67%;" />





## 2.2 通过请求和响应的交换达成通信

<img src="图解HTTP-随记/image-20201228211749617.png" alt="image-20201228211749617" style="zoom:65%;" /><img src="图解HTTP-随记/image-20201228211758642.png" alt="image-20201228211758642" style="zoom:67%;" />



### 请求报文

<img src="图解HTTP-随记/image-20201228212220077.png" alt="image-20201228212220077" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228212229815.png" alt="image-20201228212229815" style="zoom:67%;" />

**具体示例：**

<img src="图解HTTP-随记/image-20201228211909703.png" alt="image-20201228211909703" style="zoom: 67%;" />

<img src="图解HTTP-随记/image-20201228212113607.png" alt="image-20201228212113607" style="zoom: 67%;" />



### 响应报文

<img src="图解HTTP-随记/image-20201228212412462.png" alt="image-20201228212412462" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228212421709.png" alt="image-20201228212421709" style="zoom:67%;" />

**具体示例：**

<img src="图解HTTP-随记/image-20201228212541453.png" alt="image-20201228212541453" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228212621637.png" alt="image-20201228212621637" style="zoom:67%;" />





## 2.3 HTTP 是不保存状态的协议

<img src="图解HTTP-随记/image-20201228212809502.png" alt="image-20201228212809502" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228212837130.png" alt="image-20201228212837130" style="zoom:67%;" />



**cookie：**

<img src="图解HTTP-随记/image-20201228212925075.png" alt="image-20201228212925075" style="zoom:80%;" />





## 2.4 请求 URI 定位资源

<img src="图解HTTP-随记/image-20201228213300468.png" alt="image-20201228213300468" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20201228214316838.png" alt="image-20201228214316838" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228214328877.png" alt="image-20201228214328877" style="zoom:67%;" />



**查询HTTP服务器端支持的HTTP方法种类：**

<img src="图解HTTP-随记/image-20201228214535235.png" alt="image-20201228214535235" style="zoom:80%;" />





## 2.5 告知服务器意图的 HTTP 方法

**HTTP/1.1 中可使用的方法：**

### GET：获取资源

+ **请求的是文本：**保持原样返回
+ **请求的是像CGI那样的程序：**返回经过执行后的输出结果

<img src="图解HTTP-随记/image-20201228214905145.png" alt="image-20201228214905145" style="zoom:80%;" />

+ **实例：**

  <img src="图解HTTP-随记/image-20201228214952863.png" alt="image-20201228214952863" style="zoom:80%;" />

### POST：传输实体主体

<img src="图解HTTP-随记/image-20201228215044954.png" alt="image-20201228215044954" style="zoom: 80%;" />

+ **实例：**

  <img src="图解HTTP-随记/image-20201228215116488.png" alt="image-20201228215116488" style="zoom:80%;" />

### PUT：传输文件

<img src="图解HTTP-随记/image-20201228215429151.png" alt="image-20201228215429151" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201228215600878.png" alt="image-20201228215600878" style="zoom:67%;" />

+ **实例：**

  <img src="图解HTTP-随记/image-20201228215729651.png" alt="image-20201228215729651" style="zoom:80%;" />

### HEAD：获取报文首部

<img src="图解HTTP-随记/image-20201228220124756.png" alt="image-20201228220124756" style="zoom:80%;" />

+ **实例：**

  <img src="图解HTTP-随记/image-20201228220148619.png" alt="image-20201228220148619" style="zoom:80%;" />

### DELETE：删除文件

<img src="图解HTTP-随记/image-20201228220352060.png" alt="image-20201228220352060" style="zoom:80%;" />

+ **实例：**

  <img src="图解HTTP-随记/image-20201228220430336.png" alt="image-20201228220430336" style="zoom:80%;" />

### OPTIONS：询问支持的方法

<img src="图解HTTP-随记/image-20201228220600322.png" alt="image-20201228220600322" style="zoom:80%;" />

+ **实例：**

  <img src="图解HTTP-随记/image-20201228220619769.png" alt="image-20201228220619769" style="zoom:80%;" />

### TRACE：追踪路径

<img src="图解HTTP-随记/image-20201230190045135.png" alt="image-20201230190045135" style="zoom:80%;" />

+ **实例：**

  <img src="图解HTTP-随记/image-20201228221141449.png" alt="image-20201228221141449" style="zoom:80%;" />

### CONNECT：要求用隧道协议连接代理**

<img src="图解HTTP-随记/image-20201228221333189.png" alt="image-20201228221333189" style="zoom: 80%;" />

+ **实例：**

  <img src="图解HTTP-随记/image-20201228221359094.png" alt="image-20201228221359094" style="zoom:80%;" />





## 2.6 使用方法下达命令

<img src="图解HTTP-随记/image-20201228234539574.png" alt="image-20201228234539574" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228234553843.png" alt="image-20201228234553843" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20201228234721435.png" alt="image-20201228234721435" style="zoom:80%;" />





## 2.7 持久连接节省通信量

<img src="图解HTTP-随记/image-20201228235240810.png" alt="image-20201228235240810" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201228235313734.png" alt="image-20201228235313734" style="zoom:60%;" />



### 持久连接：

<img src="图解HTTP-随记/image-20201228235455468.png" alt="image-20201228235455468" style="zoom:65%;" /><img src="图解HTTP-随记/image-20201228235531478.png" alt="image-20201228235531478" style="zoom: 58%;" />

<img src="图解HTTP-随记/image-20201228235655081.png" alt="image-20201228235655081" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201228235732125.png" alt="image-20201228235732125" style="zoom:67%;" />



### 管线化：

<img src="图解HTTP-随记/image-20201229000330078.png" alt="image-20201229000330078" style="zoom:80%;" />





## 2.8 使用 Cookie 的状态管理

<img src="图解HTTP-随记/image-20201229000713359.png" alt="image-20201229000713359" style="zoom:60%;" /><img src="图解HTTP-随记/image-20201229000724406.png" alt="image-20201229000724406" style="zoom:67%;" />



<img src="图解HTTP-随记/image-20201229000847447.png" alt="image-20201229000847447" style="zoom:65%;" /><img src="图解HTTP-随记/image-20201229000915917.png" alt="image-20201229000915917" style="zoom:65%;" /><img src="图解HTTP-随记/image-20201229000935916.png" alt="image-20201229000935916" style="zoom:65%;" /><img src="图解HTTP-随记/image-20201229001005781.png" alt="image-20201229001005781" style="zoom:63%;" />





# 第 3 章 HTTP 报文内的 HTTP 信息

<img src="图解HTTP-随记/image-20201229001506014.png" alt="image-20201229001506014" style="zoom:80%;" />

## 3.1 HTTP 报文

<img src="图解HTTP-随记/image-20201229002032464.png" alt="image-20201229002032464" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229002111013.png" alt="image-20201229002111013" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229002125205.png" alt="image-20201229002125205" style="zoom:67%;" />





## 3.2 请求报文及响应报文的结构

<img src="图解HTTP-随记/image-20201229002838658.png" alt="image-20201229002838658" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229003310699.png" alt="image-20201229003310699" style="zoom:60%;" />a

<img src="图解HTTP-随记/image-20201229003341622.png" alt="image-20201229003341622" style="zoom:80%;" />





## 3.3 编码提升传输速率

<img src="图解HTTP-随记/image-20201229084414548.png" alt="image-20201229084414548" style="zoom:80%;" />



**报文主体和实体主体的差异：**

+ 通常，**报文主体等于实体主体**。

+ 只有**当传输中进行编码操作时，实体主体的内容发生变化**，才导致它和报文主体产生差异。

<img src="图解HTTP-随记/image-20201229085055090.png" alt="image-20201229085055090" style="zoom:80%;" />



**服务器端：**

+ **压缩传输的内容编码：**

  <img src="图解HTTP-随记/image-20201229085525532.png" alt="image-20201229085525532" style="zoom: 65%;" /><img src="图解HTTP-随记/image-20201229085545846.png" alt="image-20201229085545846" style="zoom:63%;" />

  <img src="图解HTTP-随记/image-20201229085634790.png" alt="image-20201229085634790" style="zoom:80%;" />

+ **分割发送的分块传输编码：**

  **把实体主体分块的功能称为分块传输编码（Chunked Transfer Coding）**

  <img src="图解HTTP-随记/image-20201229090023223.png" alt="image-20201229090023223" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229090608006.png" alt="image-20201229090608006" style="zoom:67%;" />

  + <img src="图解HTTP-随记/image-20201229090807202.png" alt="image-20201229090807202" style="zoom:80%;" />
  + <img src="图解HTTP-随记/image-20201229090918316.png" alt="image-20201229090918316" style="zoom:80%;" />
  + <img src="图解HTTP-随记/image-20201229091013593.png" alt="image-20201229091013593" style="zoom:80%;" />





## 3.4 发送多种数据的多部分对象集合

<img src="图解HTTP-随记/image-20201229092114170.png" alt="image-20201229092114170" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201229092133125.png" alt="image-20201229092133125" style="zoom:67%;" />



<img src="图解HTTP-随记/image-20201229092530764.png" alt="image-20201229092530764" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201229092824826.png" alt="image-20201229092824826" style="zoom:67%;" />





## 3.5 获取部分内容的范围请求

<img src="图解HTTP-随记/image-20201229093059939.png" alt="image-20201229093059939" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201229093119604.png" alt="image-20201229093119604" style="zoom:67%;" />



<img src="图解HTTP-随记/image-20201229093736494.png" alt="image-20201229093736494" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201229093953716.png" alt="image-20201229093953716" style="zoom:67%;" />





## 3.6 内容协商返回最合适的内容

<img src="图解HTTP-随记/image-20201229094232021.png" alt="image-20201229094232021" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201229094417094.png" alt="image-20201229094417094" style="zoom:67%;" />



**有以下 3 种类型的内容协商技术：**

+ **服务器驱动协商（Server-driven Negotiation）**

  <img src="图解HTTP-随记/image-20201229094627386.png" alt="image-20201229094627386" style="zoom:80%;" />

+ **客户端驱动协商（Agent-driven Negotiation）**

  <img src="图解HTTP-随记/image-20201229094828062.png" alt="image-20201229094828062" style="zoom:80%;" />

+ **透明协商（Transparent Negotiation）**

  <img src="图解HTTP-随记/image-20201229094933192.png" alt="image-20201229094933192" style="zoom:80%;" />





# 第 4 章 返回结果的 HTTP 状态码

HTTP 状态码负责表示**客户端 HTTP 请求的返回结果**、**标记服务器端的处理是否正常**、**通知出现的错误等工作**。



## 4.1 状态码告知从服务器端返回的请求结果

<img src="图解HTTP-随记/image-20201229100614614.png" alt="image-20201229100614614" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229100642364.png" alt="image-20201229100642364" style="zoom:67%;" />



**状态码，以3位数字和原因短语组成：**

<img src="图解HTTP-随记/image-20201229100854119.png" alt="image-20201229100854119" style="zoom:80%;" />





## 4.2 2XX 成功

**2XX 的响应结果表明请求被正常处理了**



### 200 OK

<img src="图解HTTP-随记/image-20201229101639324.png" alt="image-20201229101639324" style="zoom:80%;" />



###  204 No Content

<img src="图解HTTP-随记/image-20201229102404176.png" alt="image-20201229102404176" style="zoom:80%;" />



### 206 Partial Content

<img src="图解HTTP-随记/image-20201229102552061.png" alt="image-20201229102552061" style="zoom:80%;" />





## 4.3 3XX 重定向

**3XX 响应结果表明浏览器需要执行某些特殊的处理以正确处理请求**



### 301 Moved Permanently

<img src="图解HTTP-随记/image-20201229103011262.png" alt="image-20201229103011262" style="zoom:80%;" />



### 302 Found

<img src="图解HTTP-随记/image-20201229103642770.png" alt="image-20201229103642770" style="zoom:80%;" />



### 303 See Other

<img src="图解HTTP-随记/image-20201229103808923.png" alt="image-20201229103808923" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229104018287.png" alt="image-20201229104018287" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20201229104229999.png" alt="image-20201229104229999" style="zoom:80%;" />



### 304 Not Modified

<img src="图解HTTP-随记/image-20201229104716009.png" alt="image-20201229104716009" style="zoom:80%;" />



### 307 Temporary Redirect

<img src="图解HTTP-随记/image-20201229104827895.png" alt="image-20201229104827895" style="zoom:80%;" />





## 4.4 4XX 客户端错误

**4XX 的响应结果表明客户端是发生错误的原因所在**



### 400 Bad Request

<img src="图解HTTP-随记/image-20201229104955898.png" alt="image-20201229104955898" style="zoom:80%;" />



### 401 Unauthorized

<img src="图解HTTP-随记/image-20201229105302764.png" alt="image-20201229105302764" style="zoom:80%;" />



### 403 Forbidden

<img src="图解HTTP-随记/image-20201229105556638.png" alt="image-20201229105556638" style="zoom:80%;" />



### 404 Not Found

<img src="图解HTTP-随记/image-20201229105631786.png" alt="image-20201229105631786" style="zoom:80%;" />





## 5XX 服务器错误

**5XX 的响应结果表明服务器本身发生错误**



### 500 Internal Server Error

<img src="图解HTTP-随记/image-20201229105812513.png" alt="image-20201229105812513" style="zoom:80%;" />



### 503 Service Unavailable

<img src="图解HTTP-随记/image-20201229105916606.png" alt="image-20201229105916606" style="zoom:80%;" />





# 第 5 章 与 HTTP 协作的 Web 服务器

<img src="图解HTTP-随记/image-20201229110902312.png" alt="image-20201229110902312" style="zoom:80%;" />



## 5.1 用单台虚拟主机实现多个域名

<img src="图解HTTP-随记/image-20201229111255283.png" alt="image-20201229111255283" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229111312911.png" alt="image-20201229111312911" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20201229111806357.png" alt="image-20201229111806357" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201229111828424.png" alt="image-20201229111828424" style="zoom:67%;" />





## 5.2 通信数据转发程序 ：代理、网关、隧道

<img src="图解HTTP-随记/image-20201229113010765.png" alt="image-20201229113010765" style="zoom:80%;" />



### 代理

<img src="图解HTTP-随记/image-20201229113043422.png" alt="image-20201229113043422" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229113343976.png" alt="image-20201229113343976" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229113739835.png" alt="image-20201229113739835" style="zoom:80%;" />



+ **使用代理服务器的理由**

  <img src="图解HTTP-随记/image-20201229114005641.png" alt="image-20201229114005641" style="zoom:80%;" />

+ **代理中的方法**

  <img src="图解HTTP-随记/image-20201229114041171.png" alt="image-20201229114041171" style="zoom:80%;" />

  + <img src="图解HTTP-随记/image-20201229114547897.png" alt="image-20201229114547897" style="zoom:80%;" />
  + <img src="图解HTTP-随记/image-20201229114846576.png" alt="image-20201229114846576" style="zoom:80%;" />



### 网关

<img src="图解HTTP-随记/image-20201229120154194.png" alt="image-20201229120154194" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229120037091.png" alt="image-20201229120037091" style="zoom:80%;" />



### 隧道

<img src="图解HTTP-随记/image-20201229120245285.png" alt="image-20201229120245285" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229121645076.png" alt="image-20201229121645076" style="zoom:80%;" />





## 5.3 保存资源的缓存

**缓存：**

<img src="图解HTTP-随记/image-20201229193829754.png" alt="image-20201229193829754" style="zoom:80%;" />

**缓存服务器：**

<img src="图解HTTP-随记/image-20201229194059196.png" alt="image-20201229194059196" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229194238171.png" alt="image-20201229194238171" style="zoom: 80%;" />



### 缓存的有效期限

<img src="图解HTTP-随记/image-20201229194406995.png" alt="image-20201229194406995" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201229194420041.png" alt="image-20201229194420041" style="zoom:67%;" />



### 客户端的缓存

<img src="图解HTTP-随记/image-20201229194819520.png" alt="image-20201229194819520" style="zoom:80%;" />



<img src="图解HTTP-随记/image-20201229195026807.png" alt="image-20201229195026807" style="zoom:80%;" />





# 第 6 章 HTTP 首部

**HTTP 协议的请求和响应报文中必定包含 HTTP 首部**



## 6.1 HTTP 报文首部

<img src="图解HTTP-随记/image-20201229200401782.png" alt="image-20201229200401782" style="zoom:80%;" />



+ **HTTP请求报文**

  <img src="图解HTTP-随记/image-20201229202422659.png" alt="image-20201229202422659" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229202452713.png" alt="image-20201229202452713" style="zoom:67%;" />

+ **HTTP 响应报文**

  <img src="图解HTTP-随记/image-20201229202656584.png" alt="image-20201229202656584" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229202727089.png" alt="image-20201229202727089" style="zoom:67%;" />





## 6.2 HTTP 首部字段

**HTTP 首部字段传递重要信息**

<img src="图解HTTP-随记/image-20201229203134108.png" alt="image-20201229203134108" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229203151203.png" alt="image-20201229203151203" style="zoom:67%;" />



### HTTP 首部字段结构

<img src="图解HTTP-随记/image-20201229203426531.png" alt="image-20201229203426531" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229203519097.png" alt="image-20201229203519097" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201229203541041.png" alt="image-20201229203541041" style="zoom:67%;" />



### 4 种 HTTP 首部字段类型

+ **通用首部字段**

  <img src="图解HTTP-随记/image-20201229203712595.png" alt="image-20201229203712595" style="zoom:80%;" />

  <img src="图解HTTP-随记/image-20201229205106040.png" alt="image-20201229205106040" style="zoom:80%;" />

+ **请求首部字段**

  <img src="图解HTTP-随记/image-20201229203813289.png" alt="image-20201229203813289" style="zoom:80%;" />

  <img src="图解HTTP-随记/image-20201229205153539.png" alt="image-20201229205153539" style="zoom:80%;" />

+ **响应首部字段**

  <img src="图解HTTP-随记/image-20201229204102693.png" alt="image-20201229204102693" style="zoom:80%;" />

  <img src="图解HTTP-随记/image-20201229205335207.png" alt="image-20201229205335207" style="zoom:80%;" />

+ **实体首部字段**

  <img src="图解HTTP-随记/image-20201229204938239.png" alt="image-20201229204938239" style="zoom:80%;" />

  <img src="图解HTTP-随记/image-20201229205353160.png" alt="image-20201229205353160" style="zoom:80%;" />



### 非 HTTP/1.1 首部字段

<img src="图解HTTP-随记/image-20201229205935432.png" alt="image-20201229205935432" style="zoom:80%;" />



**End-to-end 首部和 Hop-by-hop 首部：**

<img src="图解HTTP-随记/image-20201229210112061.png" alt="image-20201229210112061" style="zoom:80%;" />

+ **End-to-end 首部**

  <img src="图解HTTP-随记/image-20201229210157007.png" alt="image-20201229210157007" style="zoom:80%;" />

+ **Hop-by-hop 首部**

  <img src="图解HTTP-随记/image-20201229210411027.png" alt="image-20201229210411027" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229210542682.png" alt="image-20201229210542682" style="zoom:80%;" />





## 6.3 HTTP/1.1 通用首部字段

**通用首部字段是指，请求报文和响应报文双方都会使用的首部**

### Cache-Control

<img src="图解HTTP-随记/image-20201229211244603.png" alt="image-20201229211244603" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229211515543.png" alt="image-20201229211515543" style="zoom: 67%;" />

#### Cache-Control 指令一览

+ **缓存请求指令**

  <img src="图解HTTP-随记/image-20201229211725028.png" alt="image-20201229211725028" style="zoom:80%;" />

+ **缓存响应指令**

  <img src="图解HTTP-随记/image-20201229211746841.png" alt="image-20201229211746841" style="zoom:80%;" />



#### 表示是否能缓存的指令

##### public 指令

<img src="图解HTTP-随记/image-20201229212418661.png" alt="image-20201229212418661" style="zoom:80%;" />

##### private 指令

<img src="图解HTTP-随记/image-20201229212540003.png" alt="image-20201229212540003" style="zoom:80%;" />

##### no-cache 指令

<img src="图解HTTP-随记/image-20201229212822857.png" alt="image-20201229212822857" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201229213037129.png" alt="image-20201229213037129" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201229213726838.png" alt="image-20201229213726838" style="zoom:67%;" />



#### 控制可执行缓存的对象的指令

##### no-store 指令

<img src="图解HTTP-随记/image-20201229214454851.png" alt="image-20201229214454851" style="zoom:80%;" />



#### 指定缓存期限和认证的指令

##### s-maxage 指令

<img src="图解HTTP-随记/image-20201229214832497.png" alt="image-20201229214832497" style="zoom:80%;" />

##### max-age 指令

<img src="图解HTTP-随记/image-20201229215402270.png" alt="image-20201229215402270" style="zoom:80%;" />

##### min-fresh 指令

<img src="图解HTTP-随记/image-20201229220116221.png" alt="image-20201229220116221" style="zoom:80%;" />

##### max-stale 指令

<img src="图解HTTP-随记/image-20201229220218139.png" alt="image-20201229220218139" style="zoom:80%;" />

##### only-if-cached 指令

<img src="图解HTTP-随记/image-20201229221111034.png" alt="image-20201229221111034" style="zoom:80%;" />

##### must-revalidate 指令

<img src="图解HTTP-随记/image-20201229221303145.png" alt="image-20201229221303145" style="zoom:80%;" />

##### proxy-revalidate 指令

<img src="图解HTTP-随记/image-20201229222959049.png" alt="image-20201229222959049" style="zoom:80%;" />

##### no-transform 指令

<img src="图解HTTP-随记/image-20201229223243935.png" alt="image-20201229223243935" style="zoom:80%;" />



#### Cache-Control 扩展

##### **cache-extension token**

<img src="图解HTTP-随记/image-20201229223637809.png" alt="image-20201229223637809" style="zoom:80%;" />





### Connection

<img src="图解HTTP-随记/image-20201230131334051.png" alt="image-20201230131334051" style="zoom:80%;" />

+ **控制不再转发给代理的首部字段**

<img src="图解HTTP-随记/image-20201230131656724.png" alt="image-20201230131656724" style="zoom: 80%;" />

+ **管理持久连接**

  <img src="图解HTTP-随记/image-20201230132030593.png" alt="image-20201230132030593" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201230135801924.png" alt="image-20201230135801924" style="zoom:67%;" />





### Data

<img src="图解HTTP-随记/image-20201230140112389.png" alt="image-20201230140112389" style="zoom:80%;" /><img src="图解HTTP-随记/image-20201230140141720.png" alt="image-20201230140141720" style="zoom: 67%;" />



### Pragma

<img src="图解HTTP-随记/image-20201230140406296.png" alt="image-20201230140406296" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201230140525217.png" alt="image-20201230140525217" style="zoom:67%;" />



### Trailer

<img src="图解HTTP-随记/image-20201230141655892.png" alt="image-20201230141655892" style="zoom:80%;" />



### Transfer-Encoding

<img src="图解HTTP-随记/image-20201230141755564.png" alt="image-20201230141755564" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201230142006987.png" alt="image-20201230142006987" style="zoom:67%;" />



### Upgrade

<img src="图解HTTP-随记/image-20201230142926238.png" alt="image-20201230142926238" style="zoom: 67%;" />



### Via

<img src="图解HTTP-随记/image-20201230185655298.png" alt="image-20201230185655298" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201230185923019.png" alt="image-20201230185923019" style="zoom:67%;" />



### Warning

<img src="图解HTTP-随记/image-20201230190238353.png" alt="image-20201230190238353" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201230190250815.png" alt="image-20201230190250815" style="zoom:67%;" />





## 6.4 请求首部字段

<img src="图解HTTP-随记/image-20201230192551690.png" alt="image-20201230192551690" style="zoom:80%;" />



### Accept







## 6.5 响应首部字段

**（只过了一遍，笔记略）**







## 6.6 实体首部字段

**（只过了一遍，笔记略）**









## 6.7 为 Cookie 服务的首部字段

<img src="图解HTTP-随记/image-20201230194047800.png" alt="image-20201230194047800" style="zoom:80%;" />



**至 2013 年 5 月，Cookie 的规格标准文档有以下 4 种：**

+ <img src="图解HTTP-随记/image-20201230194222996.png" alt="image-20201230194222996" style="zoom:80%;" />

+ <img src="图解HTTP-随记/image-20201230194147818.png" alt="image-20201230194147818" style="zoom:80%;" />

+ <img src="图解HTTP-随记/image-20201230194232715.png" alt="image-20201230194232715" style="zoom:80%;" />

+ <img src="图解HTTP-随记/image-20201230194247219.png" alt="image-20201230194247219" style="zoom: 80%;" />

<img src="图解HTTP-随记/image-20201230194337926.png" alt="image-20201230194337926" style="zoom:80%;" />



<img src="图解HTTP-随记/image-20201230194610311.png" alt="image-20201230194610311" style="zoom:80%;" />

### Set-Cookie

<img src="图解HTTP-随记/image-20201230194803811.png" alt="image-20201230194803811" style="zoom:70%;" /><img src="图解HTTP-随记/image-20201230194816030.png" alt="image-20201230194816030" style="zoom: 67%;" />



#### expires 属性

<img src="图解HTTP-随记/image-20201230195431796.png" alt="image-20201230195431796" style="zoom:80%;" />

#### path 属性

<img src="图解HTTP-随记/image-20201230195518965.png" alt="image-20201230195518965" style="zoom:80%;" />

#### domain 属性

<img src="图解HTTP-随记/image-20201230195922364.png" alt="image-20201230195922364" style="zoom:80%;" />

#### secure 属性

<img src="图解HTTP-随记/image-20201230200049516.png" alt="image-20201230200049516" style="zoom:80%;" />

#### HttpOnly 属性

<img src="图解HTTP-随记/image-20201230200419627.png" alt="image-20201230200419627" style="zoom:80%;" />



### Cookie

<img src="图解HTTP-随记/image-20201230200659129.png" alt="image-20201230200659129" style="zoom:80%;" />





## 6.8 其他首部字段

<img src="图解HTTP-随记/image-20201230201457378.png" alt="image-20201230201457378" style="zoom:80%;" />



**（只过了一遍，笔记略）**







# 第 7 章 确保 Web 安全的 HTTPS

<img src="图解HTTP-随记/image-20201231092157201.png" alt="image-20201231092157201" style="zoom:80%;" />

## 7.1 HTTP 的缺点

<img src="图解HTTP-随记/image-20201231092502400.png" alt="image-20201231092502400" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201231092818927.png" alt="image-20201231092818927" style="zoom:80%;" />



### 通信使用明文可能会被窃听

+ **TCP/IP是可能被窃听的网络**

  **通信时不加密是一个缺点，通信内容在所有的通信线路上都有 可能遭到窥视**

  <img src="图解HTTP-随记/image-20201231093246549.png" alt="image-20201231093246549" style="zoom: 80%;" /><img src="图解HTTP-随记/image-20201231094537379.png" alt="image-20201231094537379" style="zoom:67%;" />



+ **加密处理防止被窃听**

  <img src="图解HTTP-随记/image-20201231095004622.png" alt="image-20201231095004622" style="zoom:80%;" />

  + **通信的加密**

    <img src="图解HTTP-随记/image-20201231095510177.png" alt="image-20201231095510177" style="zoom: 67%;" />

  + **内容的加密**

    <img src="图解HTTP-随记/image-20201231100203758.png" alt="image-20201231100203758" style="zoom: 67%;" />

  



### 不验证通信方的身份就可能遭遇伪装

<img src="图解HTTP-随记/image-20201231100548286.png" alt="image-20201231100548286" style="zoom:80%;" />

+ **任何人都可发起请求**  

  <img src="图解HTTP-随记/image-20201231101016094.png" alt="image-20201231101016094" style="zoom:80%;" /><img src="图解HTTP-随记/image-20201231101058663.png" alt="image-20201231101058663" style="zoom: 67%;" />

  ​                                                                                                                                                                                          

+ **查明对手的证书**

  <img src="图解HTTP-随记/image-20201231101420540.png" alt="image-20201231101420540" style="zoom: 67%;" />



### 无法证明报文完整性，可能已遭篡改

<img src="图解HTTP-随记/image-20201231101500326.png" alt="image-20201231101500326" style="zoom:80%;" />

+ **接收到的内容可能有误**

  <img src="图解HTTP-随记/image-20201231102204256.png" alt="image-20201231102204256" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201231111327427.png" alt="image-20201231111327427" style="zoom:70%;" />

+ **防止篡改**

  <img src="图解HTTP-随记/image-20201231113057951.png" alt="image-20201231113057951" style="zoom: 67%;" />



## 7.2 HTTP+ 加密 + 认证 + 完整性保护 = HTTPS

### HTTP 加上加密处理和认证以及完整性保护后即是 HTTPS

<img src="图解HTTP-随记/image-20201231124316771.png" alt="image-20201231124316771" style="zoom:67%;" />



### HTTPS 是身披 SSL 外壳的 HTTP

<img src="图解HTTP-随记/image-20201231124701246.png" alt="image-20201231124701246" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201231124718914.png" alt="image-20201231124718914" style="zoom:67%;" />



### 相互交换密钥的公开密钥加密技术

<img src="图解HTTP-随记/image-20201231125256911.png" alt="image-20201231125256911" style="zoom: 67%;" />

+ **共享密钥加密的困境**

  **用对称密钥加密会产生的问题：**

  <img src="图解HTTP-随记/image-20201231125507574.png" alt="image-20201231125507574" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201231125655024.png" alt="image-20201231125655024" style="zoom:67%;" />

+ **使用两把密钥的公开密钥加密**

  <img src="图解HTTP-随记/image-20201231130543191.png" alt="image-20201231130543191" style="zoom:67%;" /><img src="图解HTTP-随记/image-20201231130600531.png" alt="image-20201231130600531" style="zoom:67%;" />

  

+ **HTTPS采用混合加密机制**

  <img src="图解HTTP-随记/image-20201231130825108.png" alt="image-20201231130825108" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201231130854032.png" alt="image-20201231130854032" style="zoom:75%;" />



###  证明公开密钥正确性的证书

<img src="图解HTTP-随记/image-20201231152235093.png" alt="image-20201231152235093" style="zoom: 70%;" /><img src="图解HTTP-随记/image-20201231152919586.png" alt="image-20201231152919586" style="zoom:70%;" />



<img src="图解HTTP-随记/image-20201231153134546.png" alt="image-20201231153134546" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201231153349414.png" alt="image-20201231153349414" style="zoom:70%;" />



+ **可证明组织真实性的 EV SSL 证书**

  <img src="图解HTTP-随记/image-20201231153917032.png" alt="image-20201231153917032" style="zoom:80%;" />

+ **用以确认客户端的客户端证书**

  <img src="图解HTTP-随记/image-20201231154433571.png" alt="image-20201231154433571" style="zoom:67%;" />

+ **认证机构信誉第一**

  <img src="图解HTTP-随记/image-20201231154646635.png" alt="image-20201231154646635" style="zoom: 67%;" />

+ **由自认证机构颁发的证书称为自签名证书**

  <img src="图解HTTP-随记/image-20201231155010340.png" alt="image-20201231155010340" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201231155424326.png" alt="image-20201231155424326" style="zoom:67%;" />



### HTTPS 的安全通信机制

**HTTPS 的通信步骤(十二步)：**

<img src="图解HTTP-随记/image-20201231155539167.png" alt="image-20201231155539167" style="zoom: 57%;" /><img src="图解HTTP-随记/image-20201231161823831.png" alt="image-20201231161823831" style="zoom: 75%;" />

+ **步骤 1**

  <img src="图解HTTP-随记/image-20201231155644166.png" alt="image-20201231155644166" style="zoom:80%;" />

+ **步骤 2**

  <img src="图解HTTP-随记/image-20201231155716409.png" alt="image-20201231155716409" style="zoom:80%;" />

+ **步骤 3**

  <img src="图解HTTP-随记/image-20201231155946983.png" alt="image-20201231155946983" style="zoom:80%;" />

+ **步骤 4**

  <img src="图解HTTP-随记/image-20201231160001090.png" alt="image-20201231160001090" style="zoom:80%;" />

+ **步骤 5**

  <img src="图解HTTP-随记/image-20201231160027302.png" alt="image-20201231160027302" style="zoom:80%;" />

+ **步骤 6**

  <img src="图解HTTP-随记/image-20201231160012564.png" alt="image-20201231160012564" style="zoom:80%;" />

+ **步骤 7**

  <img src="图解HTTP-随记/image-20201231161006093.png" alt="image-20201231161006093" style="zoom:80%;" />

+ **步骤 8**

  <img src="图解HTTP-随记/image-20201231161017476.png" alt="image-20201231161017476" style="zoom:80%;" />

+ **步骤 9**

  <img src="图解HTTP-随记/image-20201231161102365.png" alt="image-20201231161102365" style="zoom:80%;" />

+ **步骤 10**

  <img src="图解HTTP-随记/image-20201231161235314.png" alt="image-20201231161235314" style="zoom:80%;" />

+ **步骤 11**

  <img src="图解HTTP-随记/image-20201231161314196.png" alt="image-20201231161314196" style="zoom:80%;" />

+ **步骤 12**

  <img src="图解HTTP-随记/image-20201231161333030.png" alt="image-20201231161333030" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20201231161555731.png" alt="image-20201231161555731" style="zoom: 80%;" />



+ **SSL和TLS**

<img src="图解HTTP-随记/image-20201231162538746.png" alt="image-20201231162538746" style="zoom: 80%;" />

+ **SLL速度慢**

  <img src="图解HTTP-随记/image-20201231162949162.png" alt="image-20201231162949162" style="zoom: 74%;" /><img src="图解HTTP-随记/image-20201231163054992.png" alt="image-20201231163054992" style="zoom:70%;" />



+ **为什么不一直使用HTTPS**

  <img src="图解HTTP-随记/image-20201231163746203.png" alt="image-20201231163746203" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20201231163819226.png" alt="image-20201231163819226" style="zoom:67%;" />





# 第 8 章 确认访问用户身份的认证

## 8.1 何为认证

**核对的信息通常是指以下这些：**

<img src="图解HTTP-随记/image-20210102002444104.png" alt="image-20210102002444104" style="zoom: 80%;" />

**HTTP使用的认证方式：**

<img src="图解HTTP-随记/image-20210102004343052.png" alt="image-20210102004343052" style="zoom:80%;" />



## 8.2 BASIC 认证

**BASIC 认证（基本认证）是从 HTTP/1.0 就定义的认证方式，是 Web 服务器与通信 客户端之间进行的认证方式。**



### BASIC 认证的认证步骤

<img src="图解HTTP-随记/image-20210102004718322.png" alt="image-20210102004718322" style="zoom:80%;" />

+ **步骤 1**

  <img src="图解HTTP-随记/image-20210102004952888.png" alt="image-20210102004952888" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210102113005714.png" alt="image-20210102113005714" style="zoom:80%;" />

+ **步骤 2**

  <img src="图解HTTP-随记/image-20210102005103027.png" alt="image-20210102005103027" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210102005157098.png" alt="image-20210102005157098" style="zoom:67%;" />

  <img src="图解HTTP-随记/image-20210102113034746.png" alt="image-20210102113034746" style="zoom:80%;" />

+ **步骤 3**

  <img src="图解HTTP-随记/image-20210102005313553.png" alt="image-20210102005313553" style="zoom:80%;" /><img src="图解HTTP-随记/image-20210102113057742.png" alt="image-20210102113057742" style="zoom:72%;" />



<img src="图解HTTP-随记/image-20210102005415144.png" alt="image-20210102005415144" style="zoom:80%;" />



## 8.3 DIGEST 认证

<img src="图解HTTP-随记/image-20210102112157747.png" alt="image-20210102112157747" style="zoom:80%;" />

**质询响应方式：**

<img src="图解HTTP-随记/image-20210102112222145.png" alt="image-20210102112222145" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210102112312860.png" alt="image-20210102112312860" style="zoom:72%;" />



### DIGEST 认证的认证步骤

<img src="图解HTTP-随记/image-20210102112509747.png" alt="image-20210102112509747" style="zoom:75%;" />

+ **步骤 1**

  <img src="图解HTTP-随记/image-20210102112839801.png" alt="image-20210102112839801" style="zoom:70%;" /><img src="图解HTTP-随记/image-20210102113135166.png" alt="image-20210102113135166" style="zoom:80%;" />

+ **步骤 2**

  <img src="图解HTTP-随记/image-20210102114230534.png" alt="image-20210102114230534" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210102114246608.png" alt="image-20210102114246608" style="zoom:80%;" />

+ **步骤 3**

  <img src="图解HTTP-随记/image-20210102114410212.png" alt="image-20210102114410212" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210102114429857.png" alt="image-20210102114429857" style="zoom:80%;" />



<img src="图解HTTP-随记/image-20210102114649050.png" alt="image-20210102114649050" style="zoom:80%;" />





## 8.4 SSL 客户端认证

<img src="图解HTTP-随记/image-20210102123959683.png" alt="image-20210102123959683" style="zoom:80%;" />



### SSL 客户端认证的认证步骤

<img src="图解HTTP-随记/image-20210102124855654.png" alt="image-20210102124855654" style="zoom:80%;" />

+ **步骤 1**

  <img src="图解HTTP-随记/image-20210102125023480.png" alt="image-20210102125023480" style="zoom:80%;" />

+ **步骤 2**

  <img src="图解HTTP-随记/image-20210102125123126.png" alt="image-20210102125123126" style="zoom:80%;" />

+ **步骤 3**

  <img src="图解HTTP-随记/image-20210102125150064.png" alt="image-20210102125150064" style="zoom:80%;" />



**SSL 客户端认证采用双因素认证：**

<img src="图解HTTP-随记/image-20210102125957821.png" alt="image-20210102125957821" style="zoom:80%;" />



**SSL 客户端认证必要的费用：**

<img src="图解HTTP-随记/image-20210102130030365.png" alt="image-20210102130030365" style="zoom:80%;" />





## 8.5 基于表单认证(使用最多)

<img src="图解HTTP-随记/image-20210102130236069.png" alt="image-20210102130236069" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210102130306936.png" alt="image-20210102130306936" style="zoom: 70%;" />



### 认证多半为基于表单认证

<img src="图解HTTP-随记/image-20210102130612901.png" alt="image-20210102130612901" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20210102130737451.png" alt="image-20210102130737451" style="zoom:80%;" />



### Session 管理及 Cookie 应用

<img src="图解HTTP-随记/image-20210102131057834.png" alt="image-20210102131057834" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20210102131229605.png" alt="image-20210102131229605" style="zoom:80%;" />



#### Session 管理及 Cookie 状态管理步骤

<img src="图解HTTP-随记/image-20210102131318098.png" alt="image-20210102131318098" style="zoom:80%;" />

+ **步骤 1**

  <img src="图解HTTP-随记/image-20210102131414481.png" alt="image-20210102131414481" style="zoom:80%;" />

+ **步骤 2**

  <img src="图解HTTP-随记/image-20210102131858629.png" alt="image-20210102131858629" style="zoom:80%;" />

+ **步骤 3**

  <img src="图解HTTP-随记/image-20210102132021318.png" alt="image-20210102132021318" style="zoom:80%;" />



<img src="图解HTTP-随记/image-20210102132217093.png" alt="image-20210102132217093" style="zoom:80%;" />





# 第 9 章 基于 HTTP 的功能追加协议

## 9.1 基于 HTTP 的协议

<img src="图解HTTP-随记/image-20210105164414653.png" alt="image-20210105164414653" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210105164552681.png" alt="image-20210105164552681" style="zoom:67%;" />



## 9.2 消除 HTTP 瓶颈的 SPDY

###  HTTP 的瓶颈

<img src="图解HTTP-随记/image-20210105164644033.png" alt="image-20210105164644033" style="zoom: 80%;" />

<img src="图解HTTP-随记/image-20210105165432583.png" alt="image-20210105165432583" style="zoom:80%;" />

**以下这些 HTTP 标准就会成为实时显示更新内容的瓶颈：**

<img src="图解HTTP-随记/image-20210105170429309.png" alt="image-20210105170429309" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210105170446240.png" alt="image-20210105170446240" style="zoom:67%;" />



#### Ajax的解决方法

<img src="图解HTTP-随记/image-20210105183325993.png" alt="image-20210105183325993" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210105183834730.png" alt="image-20210105183834730" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20210105183913982.png" alt="image-20210105183913982" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210105184014393.png" alt="image-20210105184014393" style="zoom:67%;" />



#### Comet的解决方法

<img src="图解HTTP-随记/image-20210105184659297.png" alt="image-20210105184659297" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210105184800388.png" alt="image-20210105184800388" style="zoom:67%;" />



#### SPDY的目标

<img src="图解HTTP-随记/image-20210105184837449.png" alt="image-20210105184837449" style="zoom:80%;" />



### SPDY的设计与功能

<img src="图解HTTP-随记/image-20210105185244513.png" alt="image-20210105185244513" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210105185258052.png" alt="image-20210105185258052" style="zoom:67%;" />



#### 获得的额外功能

**使用 SPDY 后，HTTP 协议额外获得以下功能：**

+ **多路复用流**

  <img src="图解HTTP-随记/image-20210105185606511.png" alt="image-20210105185606511" style="zoom:80%;" />

+ **赋予请求优先级**

  <img src="图解HTTP-随记/image-20210105194047139.png" alt="image-20210105194047139" style="zoom:80%;" />

+ **压缩HTTP首部**

  <img src="图解HTTP-随记/image-20210105194458541.png" alt="image-20210105194458541" style="zoom:80%;" />

+ **推送功能**

  <img src="图解HTTP-随记/image-20210105194701442.png" alt="image-20210105194701442" style="zoom:80%;" />

+ **服务器提示功能**

  <img src="图解HTTP-随记/image-20210105194903029.png" alt="image-20210105194903029" style="zoom:80%;" />



<img src="图解HTTP-随记/image-20210105195348282.png" alt="image-20210105195348282" style="zoom:80%;" />



## 9.3 使用浏览器进行全双工通信的

<img src="图解HTTP-随记/image-20210105195852520.png" alt="image-20210105195852520" style="zoom: 80%;" />



### WebSocket 的设计与功能

<img src="图解HTTP-随记/image-20210105195942251.png" alt="image-20210105195942251" style="zoom:80%;" />



### WebSocket 协议

<img src="图解HTTP-随记/image-20210105200148994.png" alt="image-20210105200148994" style="zoom:80%;" />



#### WebSocket协议的主要特点

+ **推送功能**

  <img src="图解HTTP-随记/image-20210105200419987.png" alt="image-20210105200419987" style="zoom:80%;" />

+ **减少通信量**

  <img src="图解HTTP-随记/image-20210105200740361.png" alt="image-20210105200740361" style="zoom:80%;" />

  <img src="图解HTTP-随记/image-20210105200800840.png" alt="image-20210105200800840" style="zoom:80%;" />

  + **握手·请求**

    <img src="图解HTTP-随记/image-20210105201150861.png" alt="image-20210105201150861" style="zoom: 75%;" />

  + **握手·响应**

    <img src="图解HTTP-随记/image-20210105202109593.png" alt="image-20210105202109593" style="zoom:80%;" />

  <img src="图解HTTP-随记/image-20210105202227251.png" alt="image-20210105202227251" style="zoom:80%;" />

+ **WebSocket API**

  <img src="图解HTTP-随记/image-20210105211410604.png" alt="image-20210105211410604" style="zoom:80%;" />

  + **实例**

    <img src="图解HTTP-随记/image-20210105211429730.png" alt="image-20210105211429730" style="zoom:70%;" />



## 9.4 期盼已久的 HTTP/2.0

<img src="图解HTTP-随记/image-20210105211747502.png" alt="image-20210105211747502" style="zoom: 80%;" />

<img src="图解HTTP-随记/image-20210105211943437.png" alt="image-20210105211943437" style="zoom:70%;" />



## 9.5 Web 服务器管理文件的 WebDAV

<img src="图解HTTP-随记/image-20210105212058274.png" alt="image-20210105212058274" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210105212131863.png" alt="image-20210105212131863" style="zoom:67%;" />



### 扩展 HTTP/1.1 的 WebDAV

<img src="图解HTTP-随记/image-20210105212338077.png" alt="image-20210105212338077" style="zoom:70%;" />



### WebDAV 内新增的方法及状态码

<img src="图解HTTP-随记/image-20210105212601153.png" alt="image-20210105212601153" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210105212629547.png" alt="image-20210105212629547" style="zoom:67%;" />

**实例：**

+ **WebDAV的请求实例**

  <img src="图解HTTP-随记/image-20210105212753165.png" alt="image-20210105212753165" style="zoom:70%;" />

+ **WebDAV的响应实例**

  <img src="图解HTTP-随记/image-20210105212844738.png" alt="image-20210105212844738" style="zoom:70%;" />





# 第 10 章 构建 Wetb 内容的技术

## 10.1 HTML

### Web 页面几乎全由 HTML 构建

+ **超文本标记语言：**

  **HTML（HyperText Markup Language，超文本标记语言）是为了发送 Web 上的超文本（Hypertext）而开发的标记语言。**

+ **超文本(超链接文本)：**

  **超文本是一种文档系统，可将文档中任意位置的信息与其他信息（文本或图片等）建立关联，即超链接文本。**

+ **标记语言：**

  **标记语言是指通过在文档的某部分穿插特别的 字符串标签，用来修饰文档的语言。**

+ **标签：**

  **我们把出现在 HTML文档内的 这种特殊字符串叫做 HTML标签（Tag）。**

<img src="图解HTTP-随记/image-20210106100123892.png" alt="image-20210106100123892" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210106100134586.png" alt="image-20210106100134586" style="zoom:67%;" />

<img src="图解HTTP-随记/image-20210106100418366.png" alt="image-20210106100418366" style="zoom: 67%;" />



### HTML 的版本

<img src="图解HTTP-随记/image-20210106100618268.png" alt="image-20210106100618268" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210106100640851.png" alt="image-20210106100640851" style="zoom:67%;" />



### 设计应用 CSS

<img src="图解HTTP-随记/image-20210106100927568.png" alt="image-20210106100927568" style="zoom:67%;" />





## 10.2 动态 HTML

<img src="图解HTTP-随记/image-20210106101128451.png" alt="image-20210106101128451" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210106101207303.png" alt="image-20210106101207303" style="zoom:67%;" />



### 更易控制 HTML 的 DOM

<img src="图解HTTP-随记/image-20210106103149175.png" alt="image-20210106103149175" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20210106103518625.png" alt="image-20210106103518625" style="zoom:67%;" />



## 10.3 Web 应用

<img src="图解HTTP-随记/image-20210106110156232.png" alt="image-20210106110156232" style="zoom:80%;" />



### 动态内容和静态内容

<img src="图解HTTP-随记/image-20210106110318514.png" alt="image-20210106110318514" style="zoom:80%;" />



### 与 Web 服务器及程序协作的 CGI

<img src="图解HTTP-随记/image-20210106110632886.png" alt="image-20210106110632886" style="zoom:67%;" />



### 因 Java 而普及的 Servlet

<img src="图解HTTP-随记/image-20210106110919972.png" alt="image-20210106110919972" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20210106112417255.png" alt="image-20210106112417255" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210106113020240.png" alt="image-20210106113020240" style="zoom:67%;" />





## 10.4 数据发布的格式及语言

### 可扩展标记语言XML

<img src="图解HTTP-随记/image-20210106113307506.png" alt="image-20210106113307506" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20210106113536123.png" alt="image-20210106113536123" style="zoom: 80%;" />

<img src="图解HTTP-随记/image-20210106113701955.png" alt="image-20210106113701955" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210106113835035.png" alt="image-20210106113835035" style="zoom:67%;" />



### 发布更新信息的 RSS/Atom

<img src="图解HTTP-随记/image-20210106114012901.png" alt="image-20210106114012901" style="zoom:80%;" />

+ **RSS 有以下版本，名称和编写方式也不相同：**

  <img src="图解HTTP-随记/image-20210106114125439.png" alt="image-20210106114125439" style="zoom: 67%;" /><img src="图解HTTP-随记/image-20210106114147635.png" alt="image-20210106114147635" style="zoom:67%;" />

+ **Atom 具有以下两种标准：**

  <img src="图解HTTP-随记/image-20210106114249344.png" alt="image-20210106114249344" style="zoom:80%;" />

<img src="图解HTTP-随记/image-20210106114311277.png" alt="image-20210106114311277" style="zoom:80%;" />



### JavaScript 衍生的轻量级易用 JSON

<img src="图解HTTP-随记/image-20210106114459761.png" alt="image-20210106114459761" style="zoom:80%;" />





# 第 11 章 Web 的攻击技术

**互联网上的攻击大都将 Web 站点作为目标**

## 11.1 针对 Web 的攻击技术

<img src="图解HTTP-随记/image-20210107125939142.png" alt="image-20210107125939142" style="zoom:67%;" /><img src="图解HTTP-随记/image-20210107125946959.png" alt="image-20210107125946959" style="zoom:67%;" />



### HTTP 不具备必要的安全功能