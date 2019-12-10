# REST API介绍<a name="sis_03_0010"></a>

公有云API符合RESTful API设计理论。REST从资源的角度观察整个网络，分布在各处的资源由URI（Uniform Resource Identifier）确定，客户端的应用通过URL（Unified Resource Locator）获取资源。URL的一般格式为：https://Endpoint/uri。其中uri为资源路径，也即API访问的路径。

公有云接口采用HTTPS传输协议，请求/响应报文使用JSON报文，媒体类型表示为Application/json。

REST从资源的角度来观察整个网络，提供创建、查询、更新、删掉等方法访问服务的资源。

REST API请求/响应对可以分为几个部分：

-   [请求URI](#zh-cn_topic_0105303312_section1849899574)
-   [请求消息头](#zh-cn_topic_0105303312_section1454211155819)
-   [请求消息体](#zh-cn_topic_0105303312_section14612192315587)
-   [响应消息头](#zh-cn_topic_0105303312_section7804143005810)
-   [响应消息体](#zh-cn_topic_0105303312_section034615592583)
-   [发起请求](#zh-cn_topic_0105303312_section140743661613)

## 请求URI<a name="zh-cn_topic_0105303312_section1849899574"></a>

请求URI由如下部分组成。

**\{URI-scheme\} :// \{**Endpoint**\} / \{resource-path\} ? \{query-string\}**

尽管请求URI包含在请求消息头中，但大多数语言或框架都要求您从请求消息中单独传递它，所有我们在此单独拿出来强调。

**表 1**  URI中的参数说明

<a name="zh-cn_topic_0105303312_t1797260c744a4e1a85d354f259cae55a"></a>
<table><thead align="left"><tr id="zh-cn_topic_0105303312_r6dceed05bcc649d2b032accbb2980a31"><th class="cellrowborder" valign="top" width="24.529999999999998%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0105303312_a3446b6b785cb432bae9f45aef9177041"><a name="zh-cn_topic_0105303312_a3446b6b785cb432bae9f45aef9177041"></a><a name="zh-cn_topic_0105303312_a3446b6b785cb432bae9f45aef9177041"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="75.47%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0105303312_abe71244a12ac45308e99d4bbf975a9f8"><a name="zh-cn_topic_0105303312_abe71244a12ac45308e99d4bbf975a9f8"></a><a name="zh-cn_topic_0105303312_abe71244a12ac45308e99d4bbf975a9f8"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0105303312_row106982018513"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p136991001517"><a name="zh-cn_topic_0105303312_p136991001517"></a><a name="zh-cn_topic_0105303312_p136991001517"></a>URI-scheme</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_p129216817521"><a name="zh-cn_topic_0105303312_p129216817521"></a><a name="zh-cn_topic_0105303312_p129216817521"></a>表示用于传输请求的协议。SIS的API都必须采用https。</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_rb217758afff146a1b40b0dcbb28a4ae1"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_zh-cn_topic_0035614179_p480227019422"><a name="zh-cn_topic_0105303312_zh-cn_topic_0035614179_p480227019422"></a><a name="zh-cn_topic_0105303312_zh-cn_topic_0035614179_p480227019422"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_ad82b3484a1be43ddadf436efbe15285e"><a name="zh-cn_topic_0105303312_ad82b3484a1be43ddadf436efbe15285e"></a><a name="zh-cn_topic_0105303312_ad82b3484a1be43ddadf436efbe15285e"></a>指定承载REST服务端点的服务器域名或IP。</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_refeed61892004ea682639be281a1a707"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p1797614317513"><a name="zh-cn_topic_0105303312_p1797614317513"></a><a name="zh-cn_topic_0105303312_p1797614317513"></a>resource-path</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_a90409cbb8b1c49c4ad4d3cfee16f475e"><a name="zh-cn_topic_0105303312_a90409cbb8b1c49c4ad4d3cfee16f475e"></a><a name="zh-cn_topic_0105303312_a90409cbb8b1c49c4ad4d3cfee16f475e"></a>资源路径，也即API访问路径。从具体接口的URI模块获取，例如“v3/auth/tokens”。</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row19939365518"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p393966455"><a name="zh-cn_topic_0105303312_p393966455"></a><a name="zh-cn_topic_0105303312_p393966455"></a>query-string</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_p159401867517"><a name="zh-cn_topic_0105303312_p159401867517"></a><a name="zh-cn_topic_0105303312_p159401867517"></a>可选参数，例如API版本或资源选择标准。</p>
</td>
</tr>
</tbody>
</table>

## 请求方法<a name="zh-cn_topic_0105303312_section10555351105412"></a>

HTTPS方法（也称为操作或动词），它告诉服务你正在请求什么类型的操作。 

**表 2**  HTTPS方法

<a name="zh-cn_topic_0105303312_table6784213556"></a>
<table><thead align="left"><tr id="zh-cn_topic_0105303312_row158516220552"><th class="cellrowborder" valign="top" width="18%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0105303312_p19871923550"><a name="zh-cn_topic_0105303312_p19871923550"></a><a name="zh-cn_topic_0105303312_p19871923550"></a>方法</p>
</th>
<th class="cellrowborder" valign="top" width="82%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0105303312_p199019211551"><a name="zh-cn_topic_0105303312_p199019211551"></a><a name="zh-cn_topic_0105303312_p199019211551"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0105303312_row893182175513"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p89718219557"><a name="zh-cn_topic_0105303312_p89718219557"></a><a name="zh-cn_topic_0105303312_p89718219557"></a>GET</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_p181009218551"><a name="zh-cn_topic_0105303312_p181009218551"></a><a name="zh-cn_topic_0105303312_p181009218551"></a>请求服务器返回指定资源。</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row710113255515"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p1210618218558"><a name="zh-cn_topic_0105303312_p1210618218558"></a><a name="zh-cn_topic_0105303312_p1210618218558"></a>PUT</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_p810915255511"><a name="zh-cn_topic_0105303312_p810915255511"></a><a name="zh-cn_topic_0105303312_p810915255511"></a>请求服务器更新指定资源。</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row6110226555"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p1911262175512"><a name="zh-cn_topic_0105303312_p1911262175512"></a><a name="zh-cn_topic_0105303312_p1911262175512"></a>POST</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_p711411255514"><a name="zh-cn_topic_0105303312_p711411255514"></a><a name="zh-cn_topic_0105303312_p711411255514"></a>请求服务器新增资源或执行特殊操作。</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row81151920557"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p91178235510"><a name="zh-cn_topic_0105303312_p91178235510"></a><a name="zh-cn_topic_0105303312_p91178235510"></a>DELETE</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_p21203215557"><a name="zh-cn_topic_0105303312_p21203215557"></a><a name="zh-cn_topic_0105303312_p21203215557"></a>请求服务器删除指定资源，如删除对象等。</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row5120725559"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p412212220551"><a name="zh-cn_topic_0105303312_p412212220551"></a><a name="zh-cn_topic_0105303312_p412212220551"></a>HEAD</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_p181242265518"><a name="zh-cn_topic_0105303312_p181242265518"></a><a name="zh-cn_topic_0105303312_p181242265518"></a>请求服务器资源头部。</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row1712672145515"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0105303312_p20127202175518"><a name="zh-cn_topic_0105303312_p20127202175518"></a><a name="zh-cn_topic_0105303312_p20127202175518"></a>PATCH</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0105303312_p71296215510"><a name="zh-cn_topic_0105303312_p71296215510"></a><a name="zh-cn_topic_0105303312_p71296215510"></a>请求服务器更新资源的部分内容。</p>
<p id="zh-cn_topic_0105303312_p2129326557"><a name="zh-cn_topic_0105303312_p2129326557"></a><a name="zh-cn_topic_0105303312_p2129326557"></a>当资源不存在的时候，PATCH可能会去创建一个新的资源。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息头<a name="zh-cn_topic_0105303312_section1454211155819"></a>

可选的附加请求头字段，如指定的URI和HTTPS方法所要求的字段。详细的公共请求消息头字段请参见[表 公共请求消息头](#zh-cn_topic_0105303312_table65872482)，其中请求认证信息请参见[认证鉴权](认证鉴权.md)。

**表 3**  公共请求消息头

<a name="zh-cn_topic_0105303312_table65872482"></a>
<table><thead align="left"><tr id="zh-cn_topic_0105303312_row1383662"><th class="cellrowborder" valign="top" width="12.8%" id="mcps1.2.5.1.1"><p id="p45183856"><a name="p45183856"></a><a name="p45183856"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="29.2%" id="mcps1.2.5.1.2"><p id="p36013683"><a name="p36013683"></a><a name="p36013683"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21.62%" id="mcps1.2.5.1.3"><p id="p31427248"><a name="p31427248"></a><a name="p31427248"></a>说明</p>
</th>
<th class="cellrowborder" valign="top" width="36.38%" id="mcps1.2.5.1.4"><p id="p62579149"><a name="p62579149"></a><a name="p62579149"></a>示例</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0105303312_row27854539"><td class="cellrowborder" valign="top" width="12.8%" headers="mcps1.2.5.1.1 "><p id="p9768392"><a name="p9768392"></a><a name="p9768392"></a>Content-type</p>
</td>
<td class="cellrowborder" valign="top" width="29.2%" headers="mcps1.2.5.1.2 "><p id="p53042294"><a name="p53042294"></a><a name="p53042294"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.62%" headers="mcps1.2.5.1.3 "><p id="p1458597"><a name="p1458597"></a><a name="p1458597"></a>发送的实体的MIME类型。</p>
</td>
<td class="cellrowborder" valign="top" width="36.38%" headers="mcps1.2.5.1.4 "><p id="p51037565"><a name="p51037565"></a><a name="p51037565"></a>application/json</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row9251781"><td class="cellrowborder" valign="top" width="12.8%" headers="mcps1.2.5.1.1 "><p id="p28074446"><a name="p28074446"></a><a name="p28074446"></a>Content-Length</p>
</td>
<td class="cellrowborder" valign="top" width="29.2%" headers="mcps1.2.5.1.2 "><p id="p59437682"><a name="p59437682"></a><a name="p59437682"></a>POST/PUT请求必填。 GET不能包含。</p>
</td>
<td class="cellrowborder" valign="top" width="21.62%" headers="mcps1.2.5.1.3 "><p id="p49722938"><a name="p49722938"></a><a name="p49722938"></a>请求body长度，单位为Byte。</p>
</td>
<td class="cellrowborder" valign="top" width="36.38%" headers="mcps1.2.5.1.4 "><p id="p1026191"><a name="p1026191"></a><a name="p1026191"></a>3495</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row2284258142814"><td class="cellrowborder" valign="top" width="12.8%" headers="mcps1.2.5.1.1 "><p id="p71241014163"><a name="p71241014163"></a><a name="p71241014163"></a>Upgrade</p>
</td>
<td class="cellrowborder" valign="top" width="29.2%" headers="mcps1.2.5.1.2 "><p id="p1912461414613"><a name="p1912461414613"></a><a name="p1912461414613"></a>发送WebSocket握手请求时，包含该头域。</p>
</td>
<td class="cellrowborder" valign="top" width="21.62%" headers="mcps1.2.5.1.3 "><p id="p10124314867"><a name="p10124314867"></a><a name="p10124314867"></a>upgrade是HTTP1.1中用于定义转换协议的header域。</p>
</td>
<td class="cellrowborder" valign="top" width="36.38%" headers="mcps1.2.5.1.4 "><p id="p1712415148611"><a name="p1712415148611"></a><a name="p1712415148611"></a>websocket</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row1468990152914"><td class="cellrowborder" valign="top" width="12.8%" headers="mcps1.2.5.1.1 "><p id="p1312411414611"><a name="p1312411414611"></a><a name="p1312411414611"></a>Connection</p>
</td>
<td class="cellrowborder" valign="top" width="29.2%" headers="mcps1.2.5.1.2 "><p id="p1312461415610"><a name="p1312461415610"></a><a name="p1312461415610"></a>发送WebSocket握手请求时，包含该头域。</p>
</td>
<td class="cellrowborder" valign="top" width="21.62%" headers="mcps1.2.5.1.3 "><p id="p512411418613"><a name="p512411418613"></a><a name="p512411418613"></a>带有Upgrade头的HTTP1.1消息须含有Connection。</p>
</td>
<td class="cellrowborder" valign="top" width="36.38%" headers="mcps1.2.5.1.4 "><p id="p10124151419610"><a name="p10124151419610"></a><a name="p10124151419610"></a>Upgrade</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row1983621652913"><td class="cellrowborder" valign="top" width="12.8%" headers="mcps1.2.5.1.1 "><p id="p9581826181411"><a name="p9581826181411"></a><a name="p9581826181411"></a>Sec-WebSocket-Key</p>
</td>
<td class="cellrowborder" valign="top" width="29.2%" headers="mcps1.2.5.1.2 "><p id="p145811226141410"><a name="p145811226141410"></a><a name="p145811226141410"></a>发送WebSocket握手请求时，包含该头域。</p>
</td>
<td class="cellrowborder" valign="top" width="21.62%" headers="mcps1.2.5.1.3 "><p id="p922632391918"><a name="p922632391918"></a><a name="p922632391918"></a>采用base64编码的随机16字节长的字符序列。用来发送给服务器使用，服务器会使用此字段组装成另一个key值放在握手返回信息里发送客户端。</p>
</td>
<td class="cellrowborder" valign="top" width="36.38%" headers="mcps1.2.5.1.4 "><p id="p165811126121410"><a name="p165811126121410"></a><a name="p165811126121410"></a>x3JJHMbDL1EzLkh9GBhXDw==</p>
</td>
</tr>
<tr id="zh-cn_topic_0105303312_row24684337"><td class="cellrowborder" valign="top" width="12.8%" headers="mcps1.2.5.1.1 "><p id="p358272681415"><a name="p358272681415"></a><a name="p358272681415"></a>Sec-WebSocket-Version</p>
</td>
<td class="cellrowborder" valign="top" width="29.2%" headers="mcps1.2.5.1.2 "><p id="p185821626191413"><a name="p185821626191413"></a><a name="p185821626191413"></a>发送WebSocket握手请求时，包含该头域。</p>
</td>
<td class="cellrowborder" valign="top" width="21.62%" headers="mcps1.2.5.1.3 "><p id="p18582102617147"><a name="p18582102617147"></a><a name="p18582102617147"></a>标识了客户端支持WebSocket协议的版本。</p>
</td>
<td class="cellrowborder" valign="top" width="36.38%" headers="mcps1.2.5.1.4 "><p id="p1858214265147"><a name="p1858214265147"></a><a name="p1858214265147"></a>13</p>
</td>
</tr>
<tr id="row1611119533414"><td class="cellrowborder" valign="top" width="12.8%" headers="mcps1.2.5.1.1 "><p id="p51111753144114"><a name="p51111753144114"></a><a name="p51111753144114"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="29.2%" headers="mcps1.2.5.1.2 "><p id="p1011275313413"><a name="p1011275313413"></a><a name="p1011275313413"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.62%" headers="mcps1.2.5.1.3 "><p id="p13112165313415"><a name="p13112165313415"></a><a name="p13112165313415"></a>用户Token。</p>
</td>
<td class="cellrowborder" valign="top" width="36.38%" headers="mcps1.2.5.1.4 "><p id="p1260413319613"><a name="p1260413319613"></a><a name="p1260413319613"></a>MIINRwYJKoZIhvcNAQcCoIINODCCDTQCAQExDTALBglghkgBZQMEAgEwgguVBgkqhkiG...</p>
</td>
</tr>
<tr id="row101121153134117"><td class="cellrowborder" valign="top" width="12.8%" headers="mcps1.2.5.1.1 "><p id="p0604131864"><a name="p0604131864"></a><a name="p0604131864"></a>X-Language</p>
</td>
<td class="cellrowborder" valign="top" width="29.2%" headers="mcps1.2.5.1.2 "><p id="p14112453124110"><a name="p14112453124110"></a><a name="p14112453124110"></a>请求语言类型。</p>
</td>
<td class="cellrowborder" valign="top" width="21.62%" headers="mcps1.2.5.1.3 "><p id="p1611265324113"><a name="p1611265324113"></a><a name="p1611265324113"></a>否，默认为zh-cn。</p>
</td>
<td class="cellrowborder" valign="top" width="36.38%" headers="mcps1.2.5.1.4 "><p id="p61123538415"><a name="p61123538415"></a><a name="p61123538415"></a>en-us</p>
</td>
</tr>
</tbody>
</table>

## 请求消息体<a name="zh-cn_topic_0105303312_section14612192315587"></a>

请求消息体通常以结构化格式（如JSON或XML）发出，与请求消息头中Content-type对应，传递除请求消息头之外的内容。

若请求消息体中参数支持中文，则中文字符必须为UTF-8编码。

## 响应消息头<a name="zh-cn_topic_0105303312_section7804143005810"></a>

响应消息头包含如下两部分。

-   一个HTTPS状态代码，从2xx成功代码到4xx或5xx错误代码。 或者，可以返回服务定义的状态码，如API文档中所示。
-   附加响应头字段，如支持请求的响应所需，如Content-type响应消息头。详细的公共响应消息头字段请参见[表 公共响应消息头](#zh-cn_topic_0105303312_table62221141)。

    **表 4**  公共响应消息头

    <a name="zh-cn_topic_0105303312_table62221141"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0105303312_row63243638"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p7792486"><a name="p7792486"></a><a name="p7792486"></a>参数名</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p27211647"><a name="p27211647"></a><a name="p27211647"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0105303312_row63139385"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p26038457"><a name="p26038457"></a><a name="p26038457"></a>Content-Length</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p28740267"><a name="p28740267"></a><a name="p28740267"></a>响应消息体的字节长度，单位为Byte。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0105303312_row17507668"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p13689315"><a name="p13689315"></a><a name="p13689315"></a>Date</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p35092741"><a name="p35092741"></a><a name="p35092741"></a>系统响应的时间。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0105303312_row65347713"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p14131575"><a name="p14131575"></a><a name="p14131575"></a>Content-type</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p3806964"><a name="p3806964"></a><a name="p3806964"></a>发送的实体的MIME类型。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0105303312_row093016256309"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p6686394287"><a name="p6686394287"></a><a name="p6686394287"></a>Upgrade</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p166861391285"><a name="p166861391285"></a><a name="p166861391285"></a>发送WebSocket握手请求时，相应消息包含该头域，内容为websocket。</p>
    </td>
    </tr>
    <tr id="row46391148154019"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p2243285610140"><a name="p2243285610140"></a><a name="p2243285610140"></a>Connection</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p512205410140"><a name="p512205410140"></a><a name="p512205410140"></a>发送WebSocket握手请求时，相应消息包含该头域，内容为Upgrade。</p>
    </td>
    </tr>
    <tr id="row13640348104016"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p3664814142818"><a name="p3664814142818"></a><a name="p3664814142818"></a>Sec-WebSocket-Accept</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7664121415283"><a name="p7664121415283"></a><a name="p7664121415283"></a>结合Sec-WebSocket-Key提供基本的防护，比如恶意的连接，或者无意的连接。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 响应消息体<a name="zh-cn_topic_0105303312_section034615592583"></a>

响应消息体通常以结构化格式（如JSON或XML）返回，与响应消息头中Content-type对应，传递除响应消息头之外的内容。

## 发起请求<a name="zh-cn_topic_0105303312_section140743661613"></a>

共有三种方式可以基于已构建好的请求消息发起请求，分别为：

-   cURL

    cURL是一个命令行工具，用来执行各种URL操作和信息传输。cURL充当的是HTTPS客户端，可以发送HTTPS请求给服务端，并接收响应消息。cURL适用于接口调试。关于cURL详细信息请参见[https://curl.haxx.se/](https://curl.haxx.se/)。

-   编码

    通过编码调用接口，组装请求消息，并发送处理请求消息。

-   REST客户端

    Mozilla、Google都为REST提供了图形化的浏览器插件，发送处理请求消息。针对Firefox，请参见[Firefox REST Client](https://addons.mozilla.org/en-US/firefox/addon/restclient/)。针对Chrome，请参见[Chrome REST Client](https://chrome.google.com/webstore/detail/postman-interceptor/aicmkgpgakddgnaphhhpliifpcfhicfo/)。


