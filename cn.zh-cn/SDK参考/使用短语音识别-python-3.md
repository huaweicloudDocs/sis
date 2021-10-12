# 实时语音识别<a name="sis_05_0053"></a>

## 前提条件<a name="section483618911279"></a>

-   确保已按照[配置Python环境](配置Python环境.md)配置完毕，Python SDK仅支持Python3。
-   确保已存在待识别的音频文件。如果需要请在下载的SDK压缩包中获取示例音频。

## 初始化Client<a name="section590271313272"></a>

初始化RasrClient详见[表 RasrClient初始化参数](#table86254392424)。

**表 1**  RasrClient初始化参数

<a name="table86254392424"></a>
<table><thead align="left"><tr id="row136261939144211"><th class="cellrowborder" valign="top" width="12.9%" id="mcps1.2.5.1.1"><p id="p762663917427"><a name="p762663917427"></a><a name="p762663917427"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.940000000000001%" id="mcps1.2.5.1.2"><p id="p9626153994217"><a name="p9626153994217"></a><a name="p9626153994217"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.47%" id="mcps1.2.5.1.3"><p id="p1662683913422"><a name="p1662683913422"></a><a name="p1662683913422"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.69%" id="mcps1.2.5.1.4"><p id="p362633910427"><a name="p362633910427"></a><a name="p362633910427"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16626939104213"><td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.1 "><p id="p1862615393424"><a name="p1862615393424"></a><a name="p1862615393424"></a>ak</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p962673917423"><a name="p962673917423"></a><a name="p962673917423"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p562643924215"><a name="p562643924215"></a><a name="p562643924215"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p15569643185017"><a name="p15569643185017"></a><a name="p15569643185017"></a>用户的ak，请参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row36261639124211"><td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.1 "><p id="p10626113911425"><a name="p10626113911425"></a><a name="p10626113911425"></a>sk</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p106261639204217"><a name="p106261639204217"></a><a name="p106261639204217"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p66262398426"><a name="p66262398426"></a><a name="p66262398426"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p10626183915420"><a name="p10626183915420"></a><a name="p10626183915420"></a></p>
<p id="p13606164545010"><a name="p13606164545010"></a><a name="p13606164545010"></a>用户的sk，请参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row094331303"><td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.1 "><p id="p121020339302"><a name="p121020339302"></a><a name="p121020339302"></a>use_aksk</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p18101833113015"><a name="p18101833113015"></a><a name="p18101833113015"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p1810123316305"><a name="p1810123316305"></a><a name="p1810123316305"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p01013383013"><a name="p01013383013"></a><a name="p01013383013"></a>使用ak、sk要填写true。</p>
</td>
</tr>
<tr id="row6626739134210"><td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.1 "><p id="p186261739124217"><a name="p186261739124217"></a><a name="p186261739124217"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p1462613994215"><a name="p1462613994215"></a><a name="p1462613994215"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p46265394425"><a name="p46265394425"></a><a name="p46265394425"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p96261339124216"><a name="p96261339124216"></a><a name="p96261339124216"></a>区域，如：cn-north-4。具体请参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0004.html" target="_blank" rel="noopener noreferrer">终端节点</a>。</p>
</td>
</tr>
<tr id="row152416178441"><td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.1 "><p id="p6524101716441"><a name="p6524101716441"></a><a name="p6524101716441"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p9524181714441"><a name="p9524181714441"></a><a name="p9524181714441"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p13119133094416"><a name="p13119133094416"></a><a name="p13119133094416"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p152411734416"><a name="p152411734416"></a><a name="p152411734416"></a>项目ID，同region一一对应，参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0008.html" target="_blank" rel="noopener noreferrer">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row177771133321"><td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.1 "><p id="p37772353214"><a name="p37772353214"></a><a name="p37772353214"></a>callback</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p1177718318323"><a name="p1177718318323"></a><a name="p1177718318323"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p17778238327"><a name="p17778238327"></a><a name="p17778238327"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p19778163113218"><a name="p19778163113218"></a><a name="p19778163113218"></a>回调类RasrCallBack，用于监听Websocket连接、响应、断开、错误等。参考<a href="#section338116313271">代码示例</a>。</p>
</td>
</tr>
<tr id="row10150151575413"><td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.1 "><p id="p215151514544"><a name="p215151514544"></a><a name="p215151514544"></a>config</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p51511315195415"><a name="p51511315195415"></a><a name="p51511315195415"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p13151161555414"><a name="p13151161555414"></a><a name="p13151161555414"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p1151115125415"><a name="p1151115125415"></a><a name="p1151115125415"></a>详见<a href="#table12745429102316">表2</a>。</p>
</td>
</tr>
<tr id="row839453719473"><td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.1 "><p id="p3395193784714"><a name="p3395193784714"></a><a name="p3395193784714"></a>service_endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p9395133716472"><a name="p9395133716472"></a><a name="p9395133716472"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p8395163754712"><a name="p8395163754712"></a><a name="p8395163754712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p53955376474"><a name="p53955376474"></a><a name="p53955376474"></a>终端节点，一般使用默认即可。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  SisConfig

<a name="table12745429102316"></a>
<table><thead align="left"><tr id="row1974652917235"><th class="cellrowborder" valign="top" width="16.56%" id="mcps1.2.5.1.1"><p id="p2746182992315"><a name="p2746182992315"></a><a name="p2746182992315"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="7.9399999999999995%" id="mcps1.2.5.1.2"><p id="p774615294231"><a name="p774615294231"></a><a name="p774615294231"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.34%" id="mcps1.2.5.1.3"><p id="p9746172912312"><a name="p9746172912312"></a><a name="p9746172912312"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.160000000000004%" id="mcps1.2.5.1.4"><p id="p1774672932312"><a name="p1774672932312"></a><a name="p1774672932312"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row174632962316"><td class="cellrowborder" valign="top" width="16.56%" headers="mcps1.2.5.1.1 "><p id="p15746162917234"><a name="p15746162917234"></a><a name="p15746162917234"></a>connect_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="7.9399999999999995%" headers="mcps1.2.5.1.2 "><p id="p10746112962320"><a name="p10746112962320"></a><a name="p10746112962320"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p874610297239"><a name="p874610297239"></a><a name="p874610297239"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="p17747216152514"><a name="p17747216152514"></a><a name="p17747216152514"></a>连接超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row6746162962312"><td class="cellrowborder" valign="top" width="16.56%" headers="mcps1.2.5.1.1 "><p id="p974652915232"><a name="p974652915232"></a><a name="p974652915232"></a>read_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="7.9399999999999995%" headers="mcps1.2.5.1.2 "><p id="p274632918233"><a name="p274632918233"></a><a name="p274632918233"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p674619295239"><a name="p674619295239"></a><a name="p674619295239"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="p874652912315"><a name="p874652912315"></a><a name="p874652912315"></a>读取超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row1174616298233"><td class="cellrowborder" valign="top" width="16.56%" headers="mcps1.2.5.1.1 "><p id="p574611293230"><a name="p574611293230"></a><a name="p574611293230"></a>connect_lost_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="7.9399999999999995%" headers="mcps1.2.5.1.2 "><p id="p10746829162316"><a name="p10746829162316"></a><a name="p10746829162316"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p2014519695912"><a name="p2014519695912"></a><a name="p2014519695912"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="p8103171119599"><a name="p8103171119599"></a><a name="p8103171119599"></a>连接失效超时，默认4，单位s。一般不要修改这个参数。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section143008206277"></a>

请求类为RasrRequest，详见[表3](#table89615681013)。

**表 3**  RasrRequest

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
<tbody><tr id="row19972681020"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p9273360259"><a name="p9273360259"></a><a name="p9273360259"></a>audio_format</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p397106161019"><a name="p397106161019"></a><a name="p397106161019"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p129811612104"><a name="p129811612104"></a><a name="p129811612104"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p76172993511"><a name="p76172993511"></a><a name="p76172993511"></a>音频格式，支持pcm，alaw，ulaw等，如pcm8k16bit，参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0030.html" target="_blank" rel="noopener noreferrer">开始识别</a>章节。</p>
</td>
</tr>
<tr id="row6981063105"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p1597821114351"><a name="p1597821114351"></a><a name="p1597821114351"></a>model_property</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p5729163011115"><a name="p5729163011115"></a><a name="p5729163011115"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p8983612108"><a name="p8983612108"></a><a name="p8983612108"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p29781311193515"><a name="p29781311193515"></a><a name="p29781311193515"></a>属性字符串，language_sampleRate_domain， 如chinese_8k_common，参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0030.html" target="_blank" rel="noopener noreferrer">开始识别</a>章节。</p>
</td>
</tr>
<tr id="row12986661013"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p67201334112615"><a name="p67201334112615"></a><a name="p67201334112615"></a>add_punc</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p14682123391117"><a name="p14682123391117"></a><a name="p14682123391117"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p1372043422610"><a name="p1372043422610"></a><a name="p1372043422610"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p17559102814402"><a name="p17559102814402"></a><a name="p17559102814402"></a>表示是否在识别结果中添加标点，取值为yes 、 no，默认no。</p>
</td>
</tr>
<tr id="row16321145718"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p5459115619553"><a name="p5459115619553"></a><a name="p5459115619553"></a>digit_norm</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p845935619556"><a name="p845935619556"></a><a name="p845935619556"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p184591056165517"><a name="p184591056165517"></a><a name="p184591056165517"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p64597569556"><a name="p64597569556"></a><a name="p64597569556"></a>表示是否将语音中的数字识别为阿拉伯数字，取值为yes 、 no，默认为yes。</p>
</td>
</tr>
<tr id="row9982614105"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p5720134152612"><a name="p5720134152612"></a><a name="p5720134152612"></a>vad_head</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p0142123931114"><a name="p0142123931114"></a><a name="p0142123931114"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p11720173422614"><a name="p11720173422614"></a><a name="p11720173422614"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p14167132212382"><a name="p14167132212382"></a><a name="p14167132212382"></a>头部最大静音时间，[0, 60000]，默认10000ms。</p>
</td>
</tr>
<tr id="row17988614102"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p5840175211381"><a name="p5840175211381"></a><a name="p5840175211381"></a>vad_tail</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p108451139181116"><a name="p108451139181116"></a><a name="p108451139181116"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p15720103413267"><a name="p15720103413267"></a><a name="p15720103413267"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p9610191117391"><a name="p9610191117391"></a><a name="p9610191117391"></a>尾部最大静音时间，[0, 3000]，默认500ms。</p>
</td>
</tr>
<tr id="row16981761104"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p27219345269"><a name="p27219345269"></a><a name="p27219345269"></a>max_seconds</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p1357864015117"><a name="p1357864015117"></a><a name="p1357864015117"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p16721103432615"><a name="p16721103432615"></a><a name="p16721103432615"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p189071652203919"><a name="p189071652203919"></a><a name="p189071652203919"></a>音频最长持续时间， [0, 60]，默认30s。</p>
</td>
</tr>
<tr id="row19986619104"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p16497121824012"><a name="p16497121824012"></a><a name="p16497121824012"></a>interim_results</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p3155041101112"><a name="p3155041101112"></a><a name="p3155041101112"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p198431027194010"><a name="p198431027194010"></a><a name="p198431027194010"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p14333313402"><a name="p14333313402"></a><a name="p14333313402"></a>是否显示中间结果，yes 或 no，默认no。</p>
</td>
</tr>
<tr id="row149122114146"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p99132119142"><a name="p99132119142"></a><a name="p99132119142"></a>vocabulary_id</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p129134121415"><a name="p129134121415"></a><a name="p129134121415"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p14913215140"><a name="p14913215140"></a><a name="p14913215140"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p189131116147"><a name="p189131116147"></a><a name="p189131116147"></a>热词表id，若没有则不填。</p>
</td>
</tr>
<tr id="row13639155518147"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p1675322713273"><a name="p1675322713273"></a><a name="p1675322713273"></a>need_word_info</p>
</td>
<td class="cellrowborder" valign="top" width="9.76%" headers="mcps1.2.5.1.2 "><p id="p10753627182719"><a name="p10753627182719"></a><a name="p10753627182719"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="p187531027172719"><a name="p187531027172719"></a><a name="p187531027172719"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="63.129999999999995%" headers="mcps1.2.5.1.4 "><p id="p175317276278"><a name="p175317276278"></a><a name="p175317276278"></a>表示是否在识别结果中输出分词结果信息，取值为<span class="parmvalue" id="parmvalue1466819217161"><a name="parmvalue1466819217161"></a><a name="parmvalue1466819217161"></a>“yes”</span>和<span class="parmvalue" id="parmvalue55206515164"><a name="parmvalue55206515164"></a><a name="parmvalue55206515164"></a>“no”</span>，默认为<span class="parmvalue" id="parmvalue76273117169"><a name="parmvalue76273117169"></a><a name="parmvalue76273117169"></a>“no”</span>。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section2581112416279"></a>

Python SDK响应结果为Json格式，详见[表4](#zh-cn_topic_0145253482_table28472439)。

**表 4**  响应结果

<a name="zh-cn_topic_0145253482_table28472439"></a>
<table><thead align="left"><tr id="zh-cn_topic_0145253482_row65770485"><th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0145253482_p25809055"><a name="zh-cn_topic_0145253482_p25809055"></a><a name="zh-cn_topic_0145253482_p25809055"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.549999999999999%" id="mcps1.2.5.1.2"><p id="p17596184117418"><a name="p17596184117418"></a><a name="p17596184117418"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.29%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0145253482_p12329793"><a name="zh-cn_topic_0145253482_p12329793"></a><a name="zh-cn_topic_0145253482_p12329793"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.160000000000004%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0145253482_p59189214"><a name="zh-cn_topic_0145253482_p59189214"></a><a name="zh-cn_topic_0145253482_p59189214"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0145253482_row29597019"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253482_p48548320"><a name="zh-cn_topic_0145253482_p48548320"></a><a name="zh-cn_topic_0145253482_p48548320"></a>resp_type</p>
</td>
<td class="cellrowborder" valign="top" width="10.549999999999999%" headers="mcps1.2.5.1.2 "><p id="p155966418413"><a name="p155966418413"></a><a name="p155966418413"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0145253482_p28451507"><a name="zh-cn_topic_0145253482_p28451507"></a><a name="zh-cn_topic_0145253482_p28451507"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253482_p22870763"><a name="zh-cn_topic_0145253482_p22870763"></a><a name="zh-cn_topic_0145253482_p22870763"></a>参数值为RESULT，表示识别结果响应。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253482_row4510277"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253482_p29788172"><a name="zh-cn_topic_0145253482_p29788172"></a><a name="zh-cn_topic_0145253482_p29788172"></a>trace_id</p>
</td>
<td class="cellrowborder" valign="top" width="10.549999999999999%" headers="mcps1.2.5.1.2 "><p id="p16121334124210"><a name="p16121334124210"></a><a name="p16121334124210"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0145253482_p10892013"><a name="zh-cn_topic_0145253482_p10892013"></a><a name="zh-cn_topic_0145253482_p10892013"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253482_p9837846"><a name="zh-cn_topic_0145253482_p9837846"></a><a name="zh-cn_topic_0145253482_p9837846"></a>服务内部的令牌，可用于在日志中追溯具体流程。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253482_row21431754"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253482_p58250493"><a name="zh-cn_topic_0145253482_p58250493"></a><a name="zh-cn_topic_0145253482_p58250493"></a>segments</p>
</td>
<td class="cellrowborder" valign="top" width="10.549999999999999%" headers="mcps1.2.5.1.2 "><p id="p29201136104216"><a name="p29201136104216"></a><a name="p29201136104216"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.29%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0145253482_p52451624"><a name="zh-cn_topic_0145253482_p52451624"></a><a name="zh-cn_topic_0145253482_p52451624"></a>Array of objects</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253482_p20723181"><a name="zh-cn_topic_0145253482_p20723181"></a><a name="zh-cn_topic_0145253482_p20723181"></a>多句结果。详见<a href="#table14679111433818">表5</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  Segment

<a name="table14679111433818"></a>
<table><thead align="left"><tr id="row96791414203814"><th class="cellrowborder" valign="top" width="14.82%" id="mcps1.2.5.1.1"><p id="p329362612408"><a name="p329362612408"></a><a name="p329362612408"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.99%" id="mcps1.2.5.1.2"><p id="p111761146144218"><a name="p111761146144218"></a><a name="p111761146144218"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.120000000000001%" id="mcps1.2.5.1.3"><p id="p3293182644014"><a name="p3293182644014"></a><a name="p3293182644014"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.07%" id="mcps1.2.5.1.4"><p id="p18293162644011"><a name="p18293162644011"></a><a name="p18293162644011"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row867971419383"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p8119181717402"><a name="p8119181717402"></a><a name="p8119181717402"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="10.99%" headers="mcps1.2.5.1.2 "><p id="p6176246184213"><a name="p6176246184213"></a><a name="p6176246184213"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p411913172403"><a name="p411913172403"></a><a name="p411913172403"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.07%" headers="mcps1.2.5.1.4 "><p id="p13119171719409"><a name="p13119171719409"></a><a name="p13119171719409"></a>一句的起始时间戳，单位为ms。</p>
</td>
</tr>
<tr id="row1367901410382"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p01191173401"><a name="p01191173401"></a><a name="p01191173401"></a>end_time</p>
</td>
<td class="cellrowborder" valign="top" width="10.99%" headers="mcps1.2.5.1.2 "><p id="p8176104612429"><a name="p8176104612429"></a><a name="p8176104612429"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p1212061784014"><a name="p1212061784014"></a><a name="p1212061784014"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.07%" headers="mcps1.2.5.1.4 "><p id="p1120141716402"><a name="p1120141716402"></a><a name="p1120141716402"></a>一句的结束时间戳，单位为ms。</p>
</td>
</tr>
<tr id="row1767991473810"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p31201171407"><a name="p31201171407"></a><a name="p31201171407"></a>is_final</p>
</td>
<td class="cellrowborder" valign="top" width="10.99%" headers="mcps1.2.5.1.2 "><p id="p9176104611421"><a name="p9176104611421"></a><a name="p9176104611421"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p4120117114013"><a name="p4120117114013"></a><a name="p4120117114013"></a>Boolen</p>
</td>
<td class="cellrowborder" valign="top" width="62.07%" headers="mcps1.2.5.1.4 "><p id="p1412014176403"><a name="p1412014176403"></a><a name="p1412014176403"></a>true表示是最终结果， false表示为中间临时结果。</p>
</td>
</tr>
<tr id="row17680171417389"><td class="cellrowborder" valign="top" width="14.82%" headers="mcps1.2.5.1.1 "><p id="p12120101754017"><a name="p12120101754017"></a><a name="p12120101754017"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="10.99%" headers="mcps1.2.5.1.2 "><p id="p1417610461425"><a name="p1417610461425"></a><a name="p1417610461425"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p1812021774010"><a name="p1812021774010"></a><a name="p1812021774010"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.07%" headers="mcps1.2.5.1.4 "><p id="p1120217114016"><a name="p1120217114016"></a><a name="p1120217114016"></a>调用成功表示识别结果，详见<a href="#table151211923164115">表6</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 6**  Result

<a name="table151211923164115"></a>
<table><thead align="left"><tr id="row612122384115"><th class="cellrowborder" valign="top" width="15.079999999999998%" id="mcps1.2.5.1.1"><p id="p489123415418"><a name="p489123415418"></a><a name="p489123415418"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.07%" id="mcps1.2.5.1.2"><p id="p11344114194314"><a name="p11344114194314"></a><a name="p11344114194314"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="14.38%" id="mcps1.2.5.1.3"><p id="p88903414419"><a name="p88903414419"></a><a name="p88903414419"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="59.47%" id="mcps1.2.5.1.4"><p id="p128993414113"><a name="p128993414113"></a><a name="p128993414113"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row8121323194116"><td class="cellrowborder" valign="top" width="15.079999999999998%" headers="mcps1.2.5.1.1 "><p id="p0740165204217"><a name="p0740165204217"></a><a name="p0740165204217"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="11.07%" headers="mcps1.2.5.1.2 "><p id="p9344141174316"><a name="p9344141174316"></a><a name="p9344141174316"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.38%" headers="mcps1.2.5.1.3 "><p id="p17740145134213"><a name="p17740145134213"></a><a name="p17740145134213"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="59.47%" headers="mcps1.2.5.1.4 "><p id="p97407574219"><a name="p97407574219"></a><a name="p97407574219"></a>识别结果。</p>
</td>
</tr>
<tr id="row2012118237415"><td class="cellrowborder" valign="top" width="15.079999999999998%" headers="mcps1.2.5.1.1 "><p id="p1274075184213"><a name="p1274075184213"></a><a name="p1274075184213"></a>score</p>
</td>
<td class="cellrowborder" valign="top" width="11.07%" headers="mcps1.2.5.1.2 "><p id="p2034515416439"><a name="p2034515416439"></a><a name="p2034515416439"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="14.38%" headers="mcps1.2.5.1.3 "><p id="p57411551424"><a name="p57411551424"></a><a name="p57411551424"></a>Float</p>
</td>
<td class="cellrowborder" valign="top" width="59.47%" headers="mcps1.2.5.1.4 "><p id="p17741455428"><a name="p17741455428"></a><a name="p17741455428"></a>识别结果的置信度（0-1之间）。此值仅会在最终结果时被赋值，在中间结果时统一置为<span class="parmvalue" id="parmvalue57412059421"><a name="parmvalue57412059421"></a><a name="parmvalue57412059421"></a>“0.0”</span>。</p>
</td>
</tr>
<tr id="row876771112329"><td class="cellrowborder" valign="top" width="15.079999999999998%" headers="mcps1.2.5.1.1 "><p id="p129901831105112"><a name="p129901831105112"></a><a name="p129901831105112"></a>word_info</p>
</td>
<td class="cellrowborder" valign="top" width="11.07%" headers="mcps1.2.5.1.2 "><p id="p19990931145114"><a name="p19990931145114"></a><a name="p19990931145114"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="14.38%" headers="mcps1.2.5.1.3 "><p id="p599023115116"><a name="p599023115116"></a><a name="p599023115116"></a>Array of objects</p>
</td>
<td class="cellrowborder" valign="top" width="59.47%" headers="mcps1.2.5.1.4 "><p id="p399023105119"><a name="p399023105119"></a><a name="p399023105119"></a>分词信息列表。</p>
</td>
</tr>
</tbody>
</table>

**表 7**  Word\_info

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

## 代码示例<a name="section338116313271"></a>

```
# -*- coding: utf-8 -*-

from huaweicloud_sis.client.rasr_client import RasrClient
from huaweicloud_sis.bean.rasr_request import RasrRequest
from huaweicloud_sis.bean.callback import RasrCallBack
from huaweicloud_sis.bean.sis_config import SisConfig
import json

# 鉴权信息
ak = ''             # 用户的ak
sk = ''             # 用户的sk
region = ''         # region，如cn-north-4
project_id = ''     # 同region一一对应

"""
    todo 请正确填写音频格式和模型属性字符串
    1. 音频格式一定要相匹配.
         例如音频是pcm格式，并且采样率为8k，则格式填写pcm8k16bit
         如果返回audio_format is invalid 说明该文件格式不支持

    2. 音频采样率要与属性字符串的采样率要匹配
         例如格式选择pcm16k16bit，属性字符串却选择chinese_8k_common, 则会返回'audio_format' is not match model
"""

# 实时语音识别参数
path = ''           # 需要发送音频路径，如D:/test.pcm, 同时sdk也支持byte流发送数据
audio_format = ''   # 音频支持格式，如pcm8k16bit
property = ''       # 属性字符串，language_sampleRate_domain, 如chinese_8k_common, 采样率要和音频一致

class MyCallback(RasrCallBack):
    """ 回调类，用户需要在对应方法中实现自己的逻辑，其中on_response必须重写 """
    def on_open(self):
        """ websocket连接成功会回调此函数 """
        print('websocket connect success')

    def on_start(self, message):
        """
            websocket 开始识别回调此函数
        :param message: 传入信息
        :return: -
        """
        print('webscoket start to recognize, %s' % message)

    def on_response(self, message):
        """
            websockert返回响应结果会回调此函数
        :param message: json格式
        :return: -
        """
        print(json.dumps(message, indent=2, ensure_ascii=False))

    def on_end(self, message):
        """
            websocket 结束识别回调此函数
        :param message: 传入信息
        :return: -
        """
        print('websocket is ended, %s' % message)

    def on_close(self):
        """ websocket关闭会回调此函数 """
        print('websocket is closed')

    def on_error(self, error):
        """
            websocket出错回调此函数
        :param error: 错误信息
        :return: -
        """
        print('websocket meets error, the error is %s' % error)

    def on_event(self, event):
        """
            出现事件的回调
        :param event: 事件名称
        :return: -
        """
        print('receive event %s' % event)


def rasr_example():
    """ 实时语音识别demo """
    # step1 初始化RasrClient, 暂不支持使用代理
    my_callback = MyCallback()
    config = SisConfig()
    # 设置连接超时,默认是10
    config.set_connect_timeout(10)
    # 设置读取超时, 默认是10
    config.set_read_timeout(10)
    # 设置connect lost超时，一般在普通并发下，不需要设置此值。默认是4
    config.set_connect_lost_timeout(4)
    # websocket暂时不支持使用代理
    rasr_client = RasrClient(ak=ak, sk=sk, use_aksk=True, region=region, project_id=project_id, callback=my_callback,
                             config=config)

    # step2 构造请求
    request = RasrRequest(audio_format, property)
    # 所有参数均可不设置，使用默认值
    request.set_add_punc('yes')         # 设置是否添加标点， yes or no， 默认no
    request.set_vad_head(10000)         # 设置有效头部， [0, 60000], 默认10000
    request.set_vad_tail(500)           # 设置有效尾部，[0, 3000]， 默认500
    request.set_max_seconds(30)         # 设置一句话最大长度，[0, 60], 默认30
    request.set_interim_results('no')   # 设置是否返回中间结果，yes or no，默认no
    request.set_digit_norm('no')        # 设置是否将语音中数字转写为阿拉伯数字，yes or no，默认yes
    # request.set_vocabulary_id('')     # 设置热词表id，若不存在则不填写，否则会报错

    # step3 选择连接模式
    # rasr_client.short_stream_connect(request)       # 流式一句话模式
    # rasr_client.sentence_stream_connect(request)    # 实时语音识别单句模式
    rasr_client.continue_stream_connect(request)    # 实时语音识别连续模式

    # step4 发送音频
    rasr_client.send_start()
    # 连续模式下，可多次发送音频，发送格式为byte数组
    with open(path, 'rb') as f:
        data = f.read()
        rasr_client.send_audio(data)    # 可选byte_len和sleep_time参数，建议使用默认值
    rasr_client.send_end()

    # step5 关闭客户端，使用完毕后一定要关闭，否则服务端20s内没收到数据会报错并主动断开。
    rasr_client.close()


if __name__ == '__main__':
    rasr_example()
```

