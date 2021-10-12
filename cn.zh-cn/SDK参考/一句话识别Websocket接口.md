# 一句话识别Websocket接口<a name="sis_05_0071"></a>

## 前提条件<a name="section3443190201812"></a>

-   确保已按照[配置Java环境](配置Java环境.md)配置完毕。
-   确保已存在待识别的音频文件。如果需要请在下载的SDK压缩包中获取示例音频。

## 初始化Client<a name="section52701821173516"></a>

初始化SasrWebsocketClient，其参数包括AuthInfo、RasrListener、SisConfig。

**表 1**  AuthInfo

<a name="table275217620616"></a>
<table><thead align="left"><tr id="row127531267616"><th class="cellrowborder" valign="top" width="14.12%" id="mcps1.2.5.1.1"><p id="p17260204316196"><a name="p17260204316196"></a><a name="p17260204316196"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="9.5%" id="mcps1.2.5.1.2"><p id="p426010432193"><a name="p426010432193"></a><a name="p426010432193"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.34%" id="mcps1.2.5.1.3"><p id="p52601443101916"><a name="p52601443101916"></a><a name="p52601443101916"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="63.04%" id="mcps1.2.5.1.4"><p id="p162601643191915"><a name="p162601643191915"></a><a name="p162601643191915"></a>描述</p>
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
<td class="cellrowborder" valign="top" width="63.04%" headers="mcps1.2.5.1.4 "><p id="p1026117431194"><a name="p1026117431194"></a><a name="p1026117431194"></a>区域，如cn-north-4，参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0004.html" target="_blank" rel="noopener noreferrer">终端节点</a>。</p>
</td>
</tr>
<tr id="row176430488249"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p164314822417"><a name="p164314822417"></a><a name="p164314822417"></a>projectId</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p864414852411"><a name="p864414852411"></a><a name="p864414852411"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p166441848172411"><a name="p166441848172411"></a><a name="p166441848172411"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.04%" headers="mcps1.2.5.1.4 "><p id="p72615438192"><a name="p72615438192"></a><a name="p72615438192"></a>项目ID，同region一一对应，参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0008.html" target="_blank" rel="noopener noreferrer">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row475416618614"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p1975416964"><a name="p1975416964"></a><a name="p1975416964"></a>endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p157541462615"><a name="p157541462615"></a><a name="p157541462615"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p17106101512205"><a name="p17106101512205"></a><a name="p17106101512205"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.04%" headers="mcps1.2.5.1.4 "><p id="p19754861464"><a name="p19754861464"></a><a name="p19754861464"></a>终端节点，参考<a href="https://developer.huaweicloud.com/endpoint?SIS" target="_blank" rel="noopener noreferrer">地区和终端节点</a>。一般使用默认即可。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  SisConfig

<a name="table1472511119912"></a>
<table><thead align="left"><tr id="row28221511196"><th class="cellrowborder" valign="top" width="14.82%" id="mcps1.2.5.1.1"><p id="p7822611594"><a name="p7822611594"></a><a name="p7822611594"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="9.29%" id="mcps1.2.5.1.2"><p id="p782213111916"><a name="p782213111916"></a><a name="p782213111916"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.9%" id="mcps1.2.5.1.3"><p id="p1283016116306"><a name="p1283016116306"></a><a name="p1283016116306"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p188221711898"><a name="p188221711898"></a><a name="p188221711898"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row11822151111916"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p88224114915"><a name="p88224114915"></a><a name="p88224114915"></a>connectionTimeout</p>
</td>
<td class="cellrowborder" valign="top" width="9.29%" headers="mcps1.2.5.1.2 "><p id="p138226111794"><a name="p138226111794"></a><a name="p138226111794"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p6831141123015"><a name="p6831141123015"></a><a name="p6831141123015"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1882212111895"><a name="p1882212111895"></a><a name="p1882212111895"></a>连接超时，默认10000，单位ms。</p>
</td>
</tr>
<tr id="row10822511395"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p139185435216"><a name="p139185435216"></a><a name="p139185435216"></a>readTimeout</p>
</td>
<td class="cellrowborder" valign="top" width="9.29%" headers="mcps1.2.5.1.2 "><p id="p1792541527"><a name="p1792541527"></a><a name="p1792541527"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p49954185216"><a name="p49954185216"></a><a name="p49954185216"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p169195465211"><a name="p169195465211"></a><a name="p169195465211"></a>读取超时，默认10000，单位ms。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section16821438355"></a>

请求类为SasrWebsocketRequest，详见[表 SasrWebsocketRequest](#table89615681013)。

**表 3**  SasrWebsocketRequest

<a name="table89615681013"></a>
<table><thead align="left"><tr id="row17977651017"><th class="cellrowborder" valign="top" width="14.82%" id="mcps1.2.5.1.1"><p id="p10138111181020"><a name="p10138111181020"></a><a name="p10138111181020"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="9.76%" id="mcps1.2.5.1.2"><p id="p4138311181014"><a name="p4138311181014"></a><a name="p4138311181014"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.29%" id="mcps1.2.5.1.3"><p id="p113881131012"><a name="p113881131012"></a><a name="p113881131012"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="63.129999999999995%" id="mcps1.2.5.1.4"><p id="p191381211171014"><a name="p191381211171014"></a><a name="p191381211171014"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row19972681020"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p9273360259"><a name="p9273360259"></a><a name="p9273360259"></a>audioFormat</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p397106161019"><a name="p397106161019"></a><a name="p397106161019"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p129811612104"><a name="p129811612104"></a><a name="p129811612104"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p76172993511"><a name="p76172993511"></a><a name="p76172993511"></a>音频格式，支持pcm，alaw，ulaw等，如pcm8k16bit，</p>
</td>
</tr>
<tr id="row6981063105"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p1597821114351"><a name="p1597821114351"></a><a name="p1597821114351"></a>property</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p5729163011115"><a name="p5729163011115"></a><a name="p5729163011115"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p8983612108"><a name="p8983612108"></a><a name="p8983612108"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p29781311193515"><a name="p29781311193515"></a><a name="p29781311193515"></a>属性字符串，language_sampleRate_domain， 如chinese_8k_common。</p>
</td>
</tr>
<tr id="row12986661013"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p67201334112615"><a name="p67201334112615"></a><a name="p67201334112615"></a>punc</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p14682123391117"><a name="p14682123391117"></a><a name="p14682123391117"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p1372043422610"><a name="p1372043422610"></a><a name="p1372043422610"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p17559102814402"><a name="p17559102814402"></a><a name="p17559102814402"></a>表示是否在识别结果中添加标点，取值为yes 、 no，默认no。</p>
</td>
</tr>
<tr id="row1249625205415"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p19527178105119"><a name="p19527178105119"></a><a name="p19527178105119"></a>digitNorm</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p652719855113"><a name="p652719855113"></a><a name="p652719855113"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p252710818516"><a name="p252710818516"></a><a name="p252710818516"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p64597569556"><a name="p64597569556"></a><a name="p64597569556"></a>表示是否将语音中的数字识别为阿拉伯数字，取值为yes 、 no，默认为yes。</p>
</td>
</tr>
<tr id="row19986619104"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p16497121824012"><a name="p16497121824012"></a><a name="p16497121824012"></a>intermediateResult</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p3155041101112"><a name="p3155041101112"></a><a name="p3155041101112"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p198431027194010"><a name="p198431027194010"></a><a name="p198431027194010"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p14333313402"><a name="p14333313402"></a><a name="p14333313402"></a>是否显示中间结果，yes 或 no，默认no。</p>
</td>
</tr>
<tr id="row149122114146"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p99132119142"><a name="p99132119142"></a><a name="p99132119142"></a>vocabularyId</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p129134121415"><a name="p129134121415"></a><a name="p129134121415"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p14913215140"><a name="p14913215140"></a><a name="p14913215140"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p189131116147"><a name="p189131116147"></a><a name="p189131116147"></a>热词表id，若没有则不填。</p>
</td>
</tr>
<tr id="row34301435777"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p17619353162812"><a name="p17619353162812"></a><a name="p17619353162812"></a>needWordInfo</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p76192053192812"><a name="p76192053192812"></a><a name="p76192053192812"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p166191653112816"><a name="p166191653112816"></a><a name="p166191653112816"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p561965310283"><a name="p561965310283"></a><a name="p561965310283"></a>表示是否在识别结果中输出分词结果信息，取值为<span class="parmvalue" id="parmvalue1547034318196"><a name="parmvalue1547034318196"></a><a name="parmvalue1547034318196"></a>“yes”</span>和<span class="parmvalue" id="parmvalue1399912366199"><a name="parmvalue1399912366199"></a><a name="parmvalue1399912366199"></a>“no”</span>，默认为<span class="parmvalue" id="parmvalue945163119198"><a name="parmvalue945163119198"></a><a name="parmvalue945163119198"></a>“no”</span>。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section973485583515"></a>

状态响应类为StateResponse，详见[表4](#table332964451616)。

结果响应类为RasrResponse，详见[表5](#zh-cn_topic_0145253482_table28472439)。

**表 4**  StateResponse

<a name="table332964451616"></a>
<table><thead align="left"><tr id="row18330144418168"><th class="cellrowborder" valign="top" width="15.17%" id="mcps1.2.5.1.1"><p id="p12321991193"><a name="p12321991193"></a><a name="p12321991193"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="9.5%" id="mcps1.2.5.1.2"><p id="p732110971911"><a name="p732110971911"></a><a name="p732110971911"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.55%" id="mcps1.2.5.1.3"><p id="p632114961914"><a name="p632114961914"></a><a name="p632114961914"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.78%" id="mcps1.2.5.1.4"><p id="p123212919199"><a name="p123212919199"></a><a name="p123212919199"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row15330184412167"><td class="cellrowborder" valign="top" width="15.17%" headers="mcps1.2.5.1.1 "><p id="p5330344181612"><a name="p5330344181612"></a><a name="p5330344181612"></a>state</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p3330344131610"><a name="p3330344131610"></a><a name="p3330344131610"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.55%" headers="mcps1.2.5.1.3 "><p id="p1330144171613"><a name="p1330144171613"></a><a name="p1330144171613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.78%" headers="mcps1.2.5.1.4 "><p id="p19330944171610"><a name="p19330944171610"></a><a name="p19330944171610"></a>识别状态，包括start、end、fail。</p>
</td>
</tr>
<tr id="row153305449168"><td class="cellrowborder" valign="top" width="15.17%" headers="mcps1.2.5.1.1 "><p id="p15724494235"><a name="p15724494235"></a><a name="p15724494235"></a>traceId</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p17330134414168"><a name="p17330134414168"></a><a name="p17330134414168"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.55%" headers="mcps1.2.5.1.3 "><p id="p13330204421611"><a name="p13330204421611"></a><a name="p13330204421611"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.78%" headers="mcps1.2.5.1.4 "><p id="p163301644161617"><a name="p163301644161617"></a><a name="p163301644161617"></a>用于日志问题追溯。</p>
</td>
</tr>
<tr id="row433024413166"><td class="cellrowborder" valign="top" width="15.17%" headers="mcps1.2.5.1.1 "><p id="p3648159234"><a name="p3648159234"></a><a name="p3648159234"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="9.5%" headers="mcps1.2.5.1.2 "><p id="p8330194421616"><a name="p8330194421616"></a><a name="p8330194421616"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.55%" headers="mcps1.2.5.1.3 "><p id="p033012440165"><a name="p033012440165"></a><a name="p033012440165"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.78%" headers="mcps1.2.5.1.4 "><p id="p1060312315262"><a name="p1060312315262"></a><a name="p1060312315262"></a>状态描述。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  RasrResponse

<a name="zh-cn_topic_0145253482_table28472439"></a>
<table><thead align="left"><tr id="zh-cn_topic_0145253482_row65770485"><th class="cellrowborder" valign="top" width="21.73%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0145253482_p25809055"><a name="zh-cn_topic_0145253482_p25809055"></a><a name="zh-cn_topic_0145253482_p25809055"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="21.790000000000003%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0145253482_p12329793"><a name="zh-cn_topic_0145253482_p12329793"></a><a name="zh-cn_topic_0145253482_p12329793"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="56.48%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0145253482_p59189214"><a name="zh-cn_topic_0145253482_p59189214"></a><a name="zh-cn_topic_0145253482_p59189214"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0145253482_row29597019"><td class="cellrowborder" valign="top" width="21.73%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0145253482_p48548320"><a name="zh-cn_topic_0145253482_p48548320"></a><a name="zh-cn_topic_0145253482_p48548320"></a>resp_type</p>
</td>
<td class="cellrowborder" valign="top" width="21.790000000000003%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0145253482_p28451507"><a name="zh-cn_topic_0145253482_p28451507"></a><a name="zh-cn_topic_0145253482_p28451507"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="56.48%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0145253482_p22870763"><a name="zh-cn_topic_0145253482_p22870763"></a><a name="zh-cn_topic_0145253482_p22870763"></a>参数值为RESULT，表示识别结果响应。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253482_row4510277"><td class="cellrowborder" valign="top" width="21.73%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0145253482_p29788172"><a name="zh-cn_topic_0145253482_p29788172"></a><a name="zh-cn_topic_0145253482_p29788172"></a>trace_id</p>
</td>
<td class="cellrowborder" valign="top" width="21.790000000000003%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0145253482_p10892013"><a name="zh-cn_topic_0145253482_p10892013"></a><a name="zh-cn_topic_0145253482_p10892013"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="56.48%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0145253482_p9837846"><a name="zh-cn_topic_0145253482_p9837846"></a><a name="zh-cn_topic_0145253482_p9837846"></a>服务内部的令牌，可用于在日志中追溯具体流程。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253482_row21431754"><td class="cellrowborder" valign="top" width="21.73%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0145253482_p58250493"><a name="zh-cn_topic_0145253482_p58250493"></a><a name="zh-cn_topic_0145253482_p58250493"></a>segments</p>
</td>
<td class="cellrowborder" valign="top" width="21.790000000000003%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0145253482_p52451624"><a name="zh-cn_topic_0145253482_p52451624"></a><a name="zh-cn_topic_0145253482_p52451624"></a>Array of objects</p>
</td>
<td class="cellrowborder" valign="top" width="56.48%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0145253482_p20723181"><a name="zh-cn_topic_0145253482_p20723181"></a><a name="zh-cn_topic_0145253482_p20723181"></a>多句结果。</p>
<p id="p314395510233"><a name="p314395510233"></a><a name="p314395510233"></a>请参考<a href="#table14679111433818">表6</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 6**  Segment

<a name="table14679111433818"></a>
<table><thead align="left"><tr id="row96791414203814"><th class="cellrowborder" valign="top" width="27.762776277627765%" id="mcps1.2.4.1.1"><p id="p329362612408"><a name="p329362612408"></a><a name="p329362612408"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="29.652965296529647%" id="mcps1.2.4.1.2"><p id="p3293182644014"><a name="p3293182644014"></a><a name="p3293182644014"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="42.584258425842584%" id="mcps1.2.4.1.3"><p id="p18293162644011"><a name="p18293162644011"></a><a name="p18293162644011"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row867971419383"><td class="cellrowborder" valign="top" width="27.762776277627765%" headers="mcps1.2.4.1.1 "><p id="p8119181717402"><a name="p8119181717402"></a><a name="p8119181717402"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="29.652965296529647%" headers="mcps1.2.4.1.2 "><p id="p411913172403"><a name="p411913172403"></a><a name="p411913172403"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.584258425842584%" headers="mcps1.2.4.1.3 "><p id="p13119171719409"><a name="p13119171719409"></a><a name="p13119171719409"></a>一句的起始时间戳，单位为ms。</p>
</td>
</tr>
<tr id="row1367901410382"><td class="cellrowborder" valign="top" width="27.762776277627765%" headers="mcps1.2.4.1.1 "><p id="p01191173401"><a name="p01191173401"></a><a name="p01191173401"></a>end_time</p>
</td>
<td class="cellrowborder" valign="top" width="29.652965296529647%" headers="mcps1.2.4.1.2 "><p id="p1212061784014"><a name="p1212061784014"></a><a name="p1212061784014"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="42.584258425842584%" headers="mcps1.2.4.1.3 "><p id="p1120141716402"><a name="p1120141716402"></a><a name="p1120141716402"></a>一句的结束时间戳，单位为ms。</p>
</td>
</tr>
<tr id="row1767991473810"><td class="cellrowborder" valign="top" width="27.762776277627765%" headers="mcps1.2.4.1.1 "><p id="p31201171407"><a name="p31201171407"></a><a name="p31201171407"></a>is_final</p>
</td>
<td class="cellrowborder" valign="top" width="29.652965296529647%" headers="mcps1.2.4.1.2 "><p id="p4120117114013"><a name="p4120117114013"></a><a name="p4120117114013"></a>Boolen</p>
</td>
<td class="cellrowborder" valign="top" width="42.584258425842584%" headers="mcps1.2.4.1.3 "><p id="p1412014176403"><a name="p1412014176403"></a><a name="p1412014176403"></a>true表示是最终结果， false表示为中间临时结果。</p>
</td>
</tr>
<tr id="row17680171417389"><td class="cellrowborder" valign="top" width="27.762776277627765%" headers="mcps1.2.4.1.1 "><p id="p12120101754017"><a name="p12120101754017"></a><a name="p12120101754017"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="29.652965296529647%" headers="mcps1.2.4.1.2 "><p id="p1812021774010"><a name="p1812021774010"></a><a name="p1812021774010"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="42.584258425842584%" headers="mcps1.2.4.1.3 "><p id="p1120217114016"><a name="p1120217114016"></a><a name="p1120217114016"></a>调用成功表示识别结果，调用失败时无此字段。</p>
<p id="p92342984212"><a name="p92342984212"></a><a name="p92342984212"></a>请参考<a href="#table151211923164115">表7</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 7**  Result

<a name="table151211923164115"></a>
<table><thead align="left"><tr id="row612122384115"><th class="cellrowborder" valign="top" width="24.26242624262426%" id="mcps1.2.4.1.1"><p id="p489123415418"><a name="p489123415418"></a><a name="p489123415418"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="21.02210221022102%" id="mcps1.2.4.1.2"><p id="p88903414419"><a name="p88903414419"></a><a name="p88903414419"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.71547154715471%" id="mcps1.2.4.1.3"><p id="p128993414113"><a name="p128993414113"></a><a name="p128993414113"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row8121323194116"><td class="cellrowborder" valign="top" width="24.26242624262426%" headers="mcps1.2.4.1.1 "><p id="p0740165204217"><a name="p0740165204217"></a><a name="p0740165204217"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="21.02210221022102%" headers="mcps1.2.4.1.2 "><p id="p17740145134213"><a name="p17740145134213"></a><a name="p17740145134213"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.71547154715471%" headers="mcps1.2.4.1.3 "><p id="p97407574219"><a name="p97407574219"></a><a name="p97407574219"></a>识别结果。</p>
</td>
</tr>
<tr id="row2012118237415"><td class="cellrowborder" valign="top" width="24.26242624262426%" headers="mcps1.2.4.1.1 "><p id="p1274075184213"><a name="p1274075184213"></a><a name="p1274075184213"></a>score</p>
</td>
<td class="cellrowborder" valign="top" width="21.02210221022102%" headers="mcps1.2.4.1.2 "><p id="p57411551424"><a name="p57411551424"></a><a name="p57411551424"></a>Float</p>
</td>
<td class="cellrowborder" valign="top" width="54.71547154715471%" headers="mcps1.2.4.1.3 "><p id="p17741455428"><a name="p17741455428"></a><a name="p17741455428"></a>识别结果的置信度，取值范围：0~1。此值仅会在最终结果时被赋值，在中间结果时统一置为<span class="parmvalue" id="parmvalue57412059421"><a name="parmvalue57412059421"></a><a name="parmvalue57412059421"></a>“0.0”</span>。</p>
<div class="note" id="note47411359422"><a name="note47411359422"></a><a name="note47411359422"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1374115574213"><a name="p1374115574213"></a><a name="p1374115574213"></a>目前置信度作用不是太大，请勿过多依赖此值。</p>
</div></div>
</td>
</tr>
<tr id="row673843415810"><td class="cellrowborder" valign="top" width="24.26242624262426%" headers="mcps1.2.4.1.1 "><p id="p16518261956"><a name="p16518261956"></a><a name="p16518261956"></a><span>word_info</span></p>
</td>
<td class="cellrowborder" valign="top" width="21.02210221022102%" headers="mcps1.2.4.1.2 "><p id="p15742249115"><a name="p15742249115"></a><a name="p15742249115"></a>Array of Object</p>
</td>
<td class="cellrowborder" valign="top" width="54.71547154715471%" headers="mcps1.2.4.1.3 "><p id="p665112620516"><a name="p665112620516"></a><a name="p665112620516"></a>分词输出列表。</p>
</td>
</tr>
</tbody>
</table>

**表 8**  Word\_info 数据结构

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

## 示例代码<a name="section1930645315507"></a>

```
import com.huawei.sis.bean.AuthInfo;
import com.huawei.sis.bean.RasrListener;
import com.huawei.sis.bean.SisConfig;
import com.huawei.sis.bean.SisConstant;
import com.huawei.sis.bean.request.SasrWebsocketRequest;
import com.huawei.sis.bean.response.RasrResponse;
import com.huawei.sis.bean.response.StateResponse;
import com.huawei.sis.client.SasrWebsocketClient;
import com.huawei.sis.util.JsonUtils;

/**
 * 一句话识别 websocket demo
 *
 * Copyright 2021 Huawei Technologies Co.,Ltd.
 */
public class SasrWebsocketDemo {

  private String ak = "";
  private String sk = "";
  private String region = "cn-north-4";         // 区域，如cn-north-1、cn-north-4
  private String projectId = "";                // 项目id，在我的凭证查看。参考https://support.huaweicloud.com/api-sis/sis_03_0008.html

  private String path = "";                     // 本地音频路径，如D:/test.wav, sdk也支持byte数组传送。

  private String audioFormat = "pcm16k16bit";             // 音频格式，如pcm16k16bit，详见api文档或sdk文档
  private String property = "chinese_16k_common";       // 属性字符串，language_sampleRate_domain，如chinese_16k_common, 详见api文档

  /**
   * 一句话识别websocket版本参数设置，所有参数设置均为可选，均有默认值。用户根据需求设置参数。
   *
   * @param request request请求，包含各种参数
   */
  private void setParameters(SasrWebsocketRequest request) {

    // 1. 设置是否添加标点符号，yes 或 no， 默认"no"
    request.setAddPunc("yes");
    // 2. 设置是否显示中间结果，yes或no，默认“no”
    request.setIntermediateResult("no");
    // 3. 设置热词表id, 若没有则设置，否则会报错。
    // request.setVocabularyId("");
    // 4. 设置是否将音频中数字转写为阿拉伯数字，yes or no，默认yes
    request.setDigitNorm("no");
    // 5. 设置是否需要word_info，yes or no, 默认no
    request.setNeedWordInfo("no");
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
   * 获取监听器，监听器的监听函数。
   *
   * @return RasrListener，用于监听websocket
   */
  private RasrListener getRasrListener() {
    RasrListener rasrListener = new RasrListener() {
      @Override
      /**
       * 连接成功回调
       */
      public void onTranscriptionConnect() {
        System.out.println("sasr websocket connected");
      }

      @Override
      /**
       * 断开连接回调
       */
      public void onTranscriptionClose() {
        System.out.println("sasr websocket closed");
      }

      @Override
      /**
       * 响应结果回调
       */
      public void onTranscriptionResponse(RasrResponse response) {
        printResponse(response);
      }

      @Override
      /**
       * 识别开始回调
       */
      public void onTranscriptionBegin(StateResponse response) {
        printResponse(response);
      }

      @Override
      /**
       * 识别结束回调
       */
      public void onSTranscriptionEnd(StateResponse response) {
        printResponse(response);
      }

      @Override
      /**
       * 识别出错回调
       */
      public void onTranscriptionFail(StateResponse response) {
        printResponse(response);
      }

      @Override
      public void onEvent(String event) {
        log.info("receive event {}", event);
      }
    };
    return rasrListener;
  }


  private void printResponse(Object response) {
    try {
      System.out.println(JsonUtils.obj2Str(response, true));
    } catch (Exception e) {
      e.printStackTrace();
    }
  }

  /**
   * 实时语音识别SDK的工作流程
   */
  private void process() {
    try {
      // 1. 实现监听器接口listener，用户自定义收到响应的处理逻辑。
      RasrListener listener = getRasrListener();

      // 2. 初始化SasrWebsocketClient
      AuthInfo authInfo = new AuthInfo(ak, sk, region, projectId);
      SasrWebsocketClient sasrWebsocketClient = new SasrWebsocketClient(authInfo, listener, getConfig());

      // 3. 配置参数
      // audioFormat为支持格式、property为属性字符串，具体填写请详细参考api文档
      SasrWebsocketRequest request = new SasrWebsocketRequest(audioFormat, property);
      setParameters(request);

      // 4 连接websocket
      sasrWebsocketClient.sasrConnect(request);

      // 5. 发送开始请求、发送音频、发送end请求
      // 发送开始请求，即将开始请求连带配置发送至服务端
      sasrWebsocketClient.sendStart();

      // 也可以自己控制发送速率.byteLen为每次发送大小，sleepTime为每次发送后睡眠时间(ms)，一些非持续获取音频场景不需要睡眠，可设置为0.
      sasrWebsocketClient.sendAudio(path);
      // rasrClient.sendAudio(path, byteLen, sleepTime);

      // 可直接发送byte流,即byte数组
      // byte[] data = IOUtils.getFileData(path);
      // rasrClient.sendByte(data);
      // rasrClient.sendByte(data, byteLen, sleepTime);

      // 发送结尾请求
      sasrWebsocketClient.sendEnd();

      // 6. 关闭客户端。发送完毕后，此步一定要实施，否则服务端因为20s没有接受任何消息而报异常。
      sasrWebsocketClient.close();

    } catch (Exception e) {
      e.printStackTrace();
    }

  }

  public static void main(String[] args) {
    SasrWebsocketDemo sasrWebsocketDemo = new SasrWebsocketDemo();
    sasrWebsocketDemo.process();
  }
}
```

