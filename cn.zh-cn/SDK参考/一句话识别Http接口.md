# 一句话识别Http接口<a name="sis_05_0044"></a>

## 前提条件<a name="section3443190201812"></a>

-   确保已按照[配置Java环境](配置Java环境.md)配置完毕。
-   确保已存在待识别的音频文件。如果需要请在下载的SDK压缩包中获取示例音频。

## 初始化Client<a name="section159383201336"></a>

初始化AsrCustomizationClient，其参数包括AuthInfo和SisConfig。

**表 1**  AuthInfo

<a name="table275217620616"></a>
<table><thead align="left"><tr id="row127531267616"><th class="cellrowborder" valign="top" width="14.12%" id="mcps1.2.5.1.1"><p id="p157537619610"><a name="p157537619610"></a><a name="p157537619610"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="9.5%" id="mcps1.2.5.1.2"><p id="p6753969615"><a name="p6753969615"></a><a name="p6753969615"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.34%" id="mcps1.2.5.1.3"><p id="p71061015172018"><a name="p71061015172018"></a><a name="p71061015172018"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="63.04%" id="mcps1.2.5.1.4"><p id="p117531161263"><a name="p117531161263"></a><a name="p117531161263"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row12753061963"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p175346569"><a name="p175346569"></a><a name="p175346569"></a>ak</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p167531569610"><a name="p167531569610"></a><a name="p167531569610"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p18106415132016"><a name="p18106415132016"></a><a name="p18106415132016"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.04%" headers="mcps1.2.5.1.4 "><p id="p77531268615"><a name="p77531268615"></a><a name="p77531268615"></a>用户的ak，可参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row5753196864"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p3753863610"><a name="p3753863610"></a><a name="p3753863610"></a>sk</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p553217715211"><a name="p553217715211"></a><a name="p553217715211"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p4106121542011"><a name="p4106121542011"></a><a name="p4106121542011"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.04%" headers="mcps1.2.5.1.4 "><p id="p17531766618"><a name="p17531766618"></a><a name="p17531766618"></a>用户的sk，可参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row107541762067"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p127541061468"><a name="p127541061468"></a><a name="p127541061468"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p9754267611"><a name="p9754267611"></a><a name="p9754267611"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p13106015122013"><a name="p13106015122013"></a><a name="p13106015122013"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.04%" headers="mcps1.2.5.1.4 "><p id="p148991840119"><a name="p148991840119"></a><a name="p148991840119"></a>区域，如cn-north-4，参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0004.html" target="_blank" rel="noopener noreferrer">终端节点</a>。</p>
</td>
</tr>
<tr id="row176430488249"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p164314822417"><a name="p164314822417"></a><a name="p164314822417"></a>projectId</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p864414852411"><a name="p864414852411"></a><a name="p864414852411"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p166441848172411"><a name="p166441848172411"></a><a name="p166441848172411"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.04%" headers="mcps1.2.5.1.4 "><p id="p6644194817249"><a name="p6644194817249"></a><a name="p6644194817249"></a>项目ID，同region一一对应，参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0008.html" target="_blank" rel="noopener noreferrer">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row475416618614"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p1975416964"><a name="p1975416964"></a><a name="p1975416964"></a>endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p157541462615"><a name="p157541462615"></a><a name="p157541462615"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p17106101512205"><a name="p17106101512205"></a><a name="p17106101512205"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.04%" headers="mcps1.2.5.1.4 "><p id="p19754861464"><a name="p19754861464"></a><a name="p19754861464"></a>终端节点，具体请参考<a href="https://developer.huaweicloud.com/endpoint?SIS" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。一般使用默认即可。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  SisConfig

<a name="table1472511119912"></a>
<table><thead align="left"><tr id="row28221511196"><th class="cellrowborder" valign="top" width="13.950000000000001%" id="mcps1.2.5.1.1"><p id="p7822611594"><a name="p7822611594"></a><a name="p7822611594"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.16%" id="mcps1.2.5.1.2"><p id="p782213111916"><a name="p782213111916"></a><a name="p782213111916"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.9%" id="mcps1.2.5.1.3"><p id="p1283016116306"><a name="p1283016116306"></a><a name="p1283016116306"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p188221711898"><a name="p188221711898"></a><a name="p188221711898"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row11822151111916"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p88224114915"><a name="p88224114915"></a><a name="p88224114915"></a>connectionTimeout</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p138226111794"><a name="p138226111794"></a><a name="p138226111794"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p6831141123015"><a name="p6831141123015"></a><a name="p6831141123015"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1882212111895"><a name="p1882212111895"></a><a name="p1882212111895"></a>连接超时，默认10000，单位ms。</p>
</td>
</tr>
<tr id="row10822511395"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p139185435216"><a name="p139185435216"></a><a name="p139185435216"></a>readTimeout</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p1792541527"><a name="p1792541527"></a><a name="p1792541527"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p49954185216"><a name="p49954185216"></a><a name="p49954185216"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p169195465211"><a name="p169195465211"></a><a name="p169195465211"></a>读取超时，默认10000，单位ms。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section54351837143312"></a>

请求类为AsrCustomShortRequest，详见[表3](#table45631337366)。

**表 3**  AsrCustomShortRequest

<a name="table45631337366"></a>
<table><thead align="left"><tr id="row195631236363"><th class="cellrowborder" valign="top" width="15.809999999999999%" id="mcps1.2.5.1.1"><p id="p55640373620"><a name="p55640373620"></a><a name="p55640373620"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="8.3%" id="mcps1.2.5.1.2"><p id="p1456420383614"><a name="p1456420383614"></a><a name="p1456420383614"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.9%" id="mcps1.2.5.1.3"><p id="p1056412313618"><a name="p1056412313618"></a><a name="p1056412313618"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p1856419353613"><a name="p1856419353613"></a><a name="p1856419353613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row95641038369"><td class="cellrowborder" valign="top" width="15.809999999999999%" headers="mcps1.2.5.1.1 "><p id="p11564173163615"><a name="p11564173163615"></a><a name="p11564173163615"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="8.3%" headers="mcps1.2.5.1.2 "><p id="p356419323619"><a name="p356419323619"></a><a name="p356419323619"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p956483123613"><a name="p956483123613"></a><a name="p956483123613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p456415333616"><a name="p456415333616"></a><a name="p456415333616"></a>本地音频文件经过Base64编码后的字符串，音频文件时长不超过1min。</p>
</td>
</tr>
<tr id="row65644313369"><td class="cellrowborder" valign="top" width="15.809999999999999%" headers="mcps1.2.5.1.1 "><p id="p25641933360"><a name="p25641933360"></a><a name="p25641933360"></a>audioFormat</p>
</td>
<td class="cellrowborder" valign="top" width="8.3%" headers="mcps1.2.5.1.2 "><p id="p175641034365"><a name="p175641034365"></a><a name="p175641034365"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p1356463173618"><a name="p1356463173618"></a><a name="p1356463173618"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1599448164011"><a name="p1599448164011"></a><a name="p1599448164011"></a>音频格式，具体信息请参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0040.html" target="_blank" rel="noopener noreferrer">一句话识别</a>章节。</p>
</td>
</tr>
<tr id="row65653319364"><td class="cellrowborder" valign="top" width="15.809999999999999%" headers="mcps1.2.5.1.1 "><p id="p145659343611"><a name="p145659343611"></a><a name="p145659343611"></a>property</p>
</td>
<td class="cellrowborder" valign="top" width="8.3%" headers="mcps1.2.5.1.2 "><p id="p115656333612"><a name="p115656333612"></a><a name="p115656333612"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p105651303613"><a name="p105651303613"></a><a name="p105651303613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1856517313618"><a name="p1856517313618"></a><a name="p1856517313618"></a>属性字符串，语言_采样率_模型，如chinese_8k_common。具体信息请参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0040.html" target="_blank" rel="noopener noreferrer">一句话识别</a>章节。</p>
</td>
</tr>
<tr id="row15558172874017"><td class="cellrowborder" valign="top" width="15.809999999999999%" headers="mcps1.2.5.1.1 "><p id="p8559528154012"><a name="p8559528154012"></a><a name="p8559528154012"></a>addPunc</p>
</td>
<td class="cellrowborder" valign="top" width="8.3%" headers="mcps1.2.5.1.2 "><p id="p755920281403"><a name="p755920281403"></a><a name="p755920281403"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p14559192810408"><a name="p14559192810408"></a><a name="p14559192810408"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p17559102814402"><a name="p17559102814402"></a><a name="p17559102814402"></a>表示是否在识别结果中添加标点，取值为yes 、 no，默认no。</p>
</td>
</tr>
<tr id="row185271782515"><td class="cellrowborder" valign="top" width="15.809999999999999%" headers="mcps1.2.5.1.1 "><p id="p19527178105119"><a name="p19527178105119"></a><a name="p19527178105119"></a>digitNorm</p>
</td>
<td class="cellrowborder" valign="top" width="8.3%" headers="mcps1.2.5.1.2 "><p id="p652719855113"><a name="p652719855113"></a><a name="p652719855113"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p252710818516"><a name="p252710818516"></a><a name="p252710818516"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p64597569556"><a name="p64597569556"></a><a name="p64597569556"></a>表示是否将语音中的数字识别为阿拉伯数字，取值为yes 、 no，默认为yes。</p>
</td>
</tr>
<tr id="row266453364019"><td class="cellrowborder" valign="top" width="15.809999999999999%" headers="mcps1.2.5.1.1 "><p id="p17664143315404"><a name="p17664143315404"></a><a name="p17664143315404"></a>vocabularyId</p>
</td>
<td class="cellrowborder" valign="top" width="8.3%" headers="mcps1.2.5.1.2 "><p id="p126641233134010"><a name="p126641233134010"></a><a name="p126641233134010"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p6664103364017"><a name="p6664103364017"></a><a name="p6664103364017"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1254929112618"><a name="p1254929112618"></a><a name="p1254929112618"></a>热词表id，不使用则不填写。</p>
<p id="p18929185814249"><a name="p18929185814249"></a><a name="p18929185814249"></a>创建热词表请参考《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0071.html" target="_blank" rel="noopener noreferrer">创建热词表</a>章节。</p>
</td>
</tr>
<tr id="row144201784116"><td class="cellrowborder" valign="top" width="15.809999999999999%" headers="mcps1.2.5.1.1 "><p id="p16360737111013"><a name="p16360737111013"></a><a name="p16360737111013"></a><span>needWordInfo</span></p>
</td>
<td class="cellrowborder" valign="top" width="8.3%" headers="mcps1.2.5.1.2 "><p id="p1336073720104"><a name="p1336073720104"></a><a name="p1336073720104"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p536018377109"><a name="p536018377109"></a><a name="p536018377109"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p936117372104"><a name="p936117372104"></a><a name="p936117372104"></a>表示是否在识别结果中输出分词结果信息，取值为<span class="parmvalue" id="parmvalue1490315211594"><a name="parmvalue1490315211594"></a><a name="parmvalue1490315211594"></a>“yes”</span>和<span class="parmvalue" id="parmvalue1812528135912"><a name="parmvalue1812528135912"></a><a name="parmvalue1812528135912"></a>“no”</span>，默认为<span class="parmvalue" id="parmvalue16738171065911"><a name="parmvalue16738171065911"></a><a name="parmvalue16738171065911"></a>“no”</span>。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section2064715487333"></a>

响应类为AsrCustomShortResponse，详见[表4](#zh-cn_topic_0145253487_d0e3729)。

**表 4**  AsrCustomShortResponse

<a name="zh-cn_topic_0145253487_d0e3729"></a>
<table><thead align="left"><tr id="zh-cn_topic_0145253487_row60901406"><th class="cellrowborder" valign="top" width="24.417558244175584%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0145253487_p34066842"><a name="zh-cn_topic_0145253487_p34066842"></a><a name="zh-cn_topic_0145253487_p34066842"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="15.11848815118488%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0145253487_p40033254"><a name="zh-cn_topic_0145253487_p40033254"></a><a name="zh-cn_topic_0145253487_p40033254"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.11848815118488%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0145253487_p21468167"><a name="zh-cn_topic_0145253487_p21468167"></a><a name="zh-cn_topic_0145253487_p21468167"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45.34546545345466%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0145253487_p61200005"><a name="zh-cn_topic_0145253487_p61200005"></a><a name="zh-cn_topic_0145253487_p61200005"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0145253487_row30360312"><td class="cellrowborder" valign="top" width="24.417558244175584%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253487_p43266208"><a name="zh-cn_topic_0145253487_p43266208"></a><a name="zh-cn_topic_0145253487_p43266208"></a>trace_id</p>
</td>
<td class="cellrowborder" valign="top" width="15.11848815118488%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0145253487_p66209150"><a name="zh-cn_topic_0145253487_p66209150"></a><a name="zh-cn_topic_0145253487_p66209150"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.11848815118488%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0145253487_p61340932"><a name="zh-cn_topic_0145253487_p61340932"></a><a name="zh-cn_topic_0145253487_p61340932"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.34546545345466%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253487_p2559566"><a name="zh-cn_topic_0145253487_p2559566"></a><a name="zh-cn_topic_0145253487_p2559566"></a>服务内部的令牌，可用于在日志中追溯具体流程，调用失败无此字段。</p>
<p id="zh-cn_topic_0145253487_p23036096"><a name="zh-cn_topic_0145253487_p23036096"></a><a name="zh-cn_topic_0145253487_p23036096"></a>在某些错误情况下可能没有此令牌字符串。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row5998276"><td class="cellrowborder" valign="top" width="24.417558244175584%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253487_p16098384"><a name="zh-cn_topic_0145253487_p16098384"></a><a name="zh-cn_topic_0145253487_p16098384"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="15.11848815118488%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0145253487_p59254979"><a name="zh-cn_topic_0145253487_p59254979"></a><a name="zh-cn_topic_0145253487_p59254979"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.11848815118488%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0145253487_p34924028"><a name="zh-cn_topic_0145253487_p34924028"></a><a name="zh-cn_topic_0145253487_p34924028"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="45.34546545345466%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253487_p10274025"><a name="zh-cn_topic_0145253487_p10274025"></a><a name="zh-cn_topic_0145253487_p10274025"></a>调用成功表示识别结果，调用失败时无此字段。请参考<a href="#table231812015476">表5</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  Result

<a name="table231812015476"></a>
<table><thead align="left"><tr id="row1731990154716"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p17151167149"><a name="p17151167149"></a><a name="p17151167149"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="13.750000000000002%" id="mcps1.2.5.1.2"><p id="p16151177142"><a name="p16151177142"></a><a name="p16151177142"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.04%" id="mcps1.2.5.1.3"><p id="p0151577416"><a name="p0151577416"></a><a name="p0151577416"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45.21%" id="mcps1.2.5.1.4"><p id="p1715187344"><a name="p1715187344"></a><a name="p1715187344"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row4861951034"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p129801830194920"><a name="p129801830194920"></a><a name="p129801830194920"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="13.750000000000002%" headers="mcps1.2.5.1.2 "><p id="p199808305495"><a name="p199808305495"></a><a name="p199808305495"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p1998043016498"><a name="p1998043016498"></a><a name="p1998043016498"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.21%" headers="mcps1.2.5.1.4 "><p id="p20980130184911"><a name="p20980130184911"></a><a name="p20980130184911"></a>调用成功表示识别出的内容。</p>
</td>
</tr>
<tr id="row4319309473"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p19980143016498"><a name="p19980143016498"></a><a name="p19980143016498"></a>score</p>
</td>
<td class="cellrowborder" valign="top" width="13.750000000000002%" headers="mcps1.2.5.1.2 "><p id="p1098023074919"><a name="p1098023074919"></a><a name="p1098023074919"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p1698113309495"><a name="p1698113309495"></a><a name="p1698113309495"></a>Float</p>
</td>
<td class="cellrowborder" valign="top" width="45.21%" headers="mcps1.2.5.1.4 "><p id="p159811230164917"><a name="p159811230164917"></a><a name="p159811230164917"></a>调用成功表示识别出的置信度，取值范围：0~1。</p>
</td>
</tr>
<tr id="row1515814438319"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p129901831105112"><a name="p129901831105112"></a><a name="p129901831105112"></a>word_info</p>
</td>
<td class="cellrowborder" valign="top" width="13.750000000000002%" headers="mcps1.2.5.1.2 "><p id="p19990931145114"><a name="p19990931145114"></a><a name="p19990931145114"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.04%" headers="mcps1.2.5.1.3 "><p id="p599023115116"><a name="p599023115116"></a><a name="p599023115116"></a>Array of objects</p>
</td>
<td class="cellrowborder" valign="top" width="45.21%" headers="mcps1.2.5.1.4 "><p id="p399023105119"><a name="p399023105119"></a><a name="p399023105119"></a>分词信息列表。</p>
</td>
</tr>
</tbody>
</table>

**表 6**  Word\_info 数据结构

<a name="table154291536145211"></a>
<table><thead align="left"><tr id="row154291236105212"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p7599133785412"><a name="p7599133785412"></a><a name="p7599133785412"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="14.04%" id="mcps1.2.5.1.2"><p id="p642917366527"><a name="p642917366527"></a><a name="p642917366527"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.61%" id="mcps1.2.5.1.3"><p id="p1866554515548"><a name="p1866554515548"></a><a name="p1866554515548"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45.35%" id="mcps1.2.5.1.4"><p id="p8942134765414"><a name="p8942134765414"></a><a name="p8942134765414"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row4429236155211"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p14429173613525"><a name="p14429173613525"></a><a name="p14429173613525"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="14.04%" headers="mcps1.2.5.1.2 "><p id="p164291636195216"><a name="p164291636195216"></a><a name="p164291636195216"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.61%" headers="mcps1.2.5.1.3 "><p id="p1842933617526"><a name="p1842933617526"></a><a name="p1842933617526"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45.35%" headers="mcps1.2.5.1.4 "><p id="p1356222345613"><a name="p1356222345613"></a><a name="p1356222345613"></a>起始时间</p>
</td>
</tr>
<tr id="row13429163685215"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p242963617528"><a name="p242963617528"></a><a name="p242963617528"></a>end_time</p>
</td>
<td class="cellrowborder" valign="top" width="14.04%" headers="mcps1.2.5.1.2 "><p id="p942953695218"><a name="p942953695218"></a><a name="p942953695218"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.61%" headers="mcps1.2.5.1.3 "><p id="p6429193610524"><a name="p6429193610524"></a><a name="p6429193610524"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45.35%" headers="mcps1.2.5.1.4 "><p id="p1819992716561"><a name="p1819992716561"></a><a name="p1819992716561"></a>结束时间</p>
</td>
</tr>
<tr id="row19429936165217"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p134291936135218"><a name="p134291936135218"></a><a name="p134291936135218"></a>word</p>
</td>
<td class="cellrowborder" valign="top" width="14.04%" headers="mcps1.2.5.1.2 "><p id="p1342933625213"><a name="p1342933625213"></a><a name="p1342933625213"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.61%" headers="mcps1.2.5.1.3 "><p id="p6429193617525"><a name="p6429193617525"></a><a name="p6429193617525"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.35%" headers="mcps1.2.5.1.4 "><p id="p173621931145620"><a name="p173621931145620"></a><a name="p173621931145620"></a>分词</p>
</td>
</tr>
</tbody>
</table>

## 代码示例<a name="section207268861814"></a>

```
import com.huawei.sis.bean.SisConfig;
import com.huawei.sis.bean.SisConstant;
import com.huawei.sis.bean.request.AsrCustomShortRequest;
import com.huawei.sis.bean.response.AsrCustomShortResponse;
import com.huawei.sis.bean.AuthInfo;
import com.huawei.sis.client.AsrCustomizationClient;
import com.huawei.sis.exception.SisException;
import com.huawei.sis.util.IOUtils;
import java.util.List;
import com.huawei.sis.util.JsonUtils;


/**
 * 一句话识别
 *
 * Copyright 2021 Huawei Technologies Co.,Ltd.
 */
public class AsrCustomizationDemo {
  private static final int SLEEP_TIME = 500;
  private static final int MAX_POLLING_NUMS = 1000;

  private String ak = "";
  private String sk = "";
  private String region = "";    // 区域，如cn-north-1、cn-north-4
  private String projectId = ""; // 项目id。登录管理控制台，鼠标移动到右上角的用户名上，在下拉列表中选择我的凭证，在项目列表中查看项目id。多项目时，展开“所属区域”，从“项目ID”列获取子项目ID。
  // 一句话识别参数
  private String path = "";             // 音频文件路径，如D:/test.wav等，sdk会将音频文件转化为base64编码
  private String pathAudioFormat = "";  // 文件格式，如wav等
  private String pathProperty = "";     // 属性字符串，language_sampleRate_domain, 如chinese_8k_common


  /**
   * 设置一句话识别参数，所有参数均有默认值，不配置也可使用
   *
   * @param request 一句话识别请求
   */
  private void setShortParameter(AsrCustomShortRequest request) {

    // 设置是否添加标点，默认是no
    request.setAddPunc("yes");
    // 设置是否将语音中的数字转写为阿拉伯数字，yes或no，默认yes
    request.setDigitNorm("no");
  }

  /**
   * 定义config，所有参数可选，设置超时时间等。
   *
   * @return SisConfig
   */
  private SisConfig getConfig() {
    SisConfig config = new SisConfig();
    // 设置连接超时，默认10000ms
    config.setConnectionTimeout(SisConstant.DEFAULT_CONNECTION_TIMEOUT);
    // 设置读取超时，默认10000ms
    config.setReadTimeout(SisConstant.DEFAULT_READ_TIMEOUT);
    // 设置代理, 一定要确保代理可用才启动此设置。 代理初始化也可用不加密的代理，new ProxyHostInfo(host, port);
    // ProxyHostInfo proxy = new ProxyHostInfo(host, port, username, password);
    // config.setProxy(proxy);
    return config;
  }


  /**
   * 一句话识别demo
   */
  private void shortDemo() {
    try {
      // 1. 初始化AsrCustomizationClient
      // 定义authInfo，根据ak，sk，region，projectId
      AuthInfo authInfo = new AuthInfo(ak, sk, region, projectId);
      // 设置config，主要与超时有关
      SisConfig config = getConfig();
      // 根据authInfo和config，构造AsrCustomizationClient
      AsrCustomizationClient asr = new AsrCustomizationClient(authInfo, config);

      // 2. 配置请求
      String data = IOUtils.getEncodeDataByPath(path);
      AsrCustomShortRequest request = new AsrCustomShortRequest(data, pathAudioFormat, pathProperty);
      // 设置请求参数，所有参数均为可选
      setShortParameter(request);

      // 3. 发送请求，获取响应
      AsrCustomShortResponse response = asr.getAsrShortResponse(request);
      // 打印结果
      System.out.println(JsonUtils.obj2Str(response, true));

    } catch (SisException e) {
      e.printStackTrace();
      System.out.println("error_code:" + e.getErrorCode() + "\nerror_msg:" + e.getErrorMsg());
    }
  }

  public static void main(String[] args) {
    AsrCustomizationDemo demo = new AsrCustomizationDemo();
    demo.shortDemo();
  }

}
```

