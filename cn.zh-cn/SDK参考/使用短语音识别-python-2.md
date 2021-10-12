# 录音文件识别<a name="sis_05_0052"></a>

## 前提条件<a name="section483618911279"></a>

-   确保已按照[配置Python环境](配置Python环境.md)配置完毕，Python SDK仅支持Python3。
-   确保已存在待识别的音频文件并上传OBS，示例音频可参考下载SDK压缩包文件，同时确保服务已授权访问OBS，可参考[配置OBS服务](https://support.huaweicloud.com/api-sis/sis_03_0047.html)。

## 初始化Client<a name="section590271313272"></a>

初始化AsrCustomizationClient详见[表 AsrCustomizationClient初始化参数](#table86254392424)。

**表 1**  AsrCustomizationClient初始化参数

<a name="table86254392424"></a>
<table><thead align="left"><tr id="row136261939144211"><th class="cellrowborder" valign="top" width="14.12%" id="mcps1.2.5.1.1"><p id="p762663917427"><a name="p762663917427"></a><a name="p762663917427"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.11%" id="mcps1.2.5.1.2"><p id="p9626153994217"><a name="p9626153994217"></a><a name="p9626153994217"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.600000000000001%" id="mcps1.2.5.1.3"><p id="p1662683913422"><a name="p1662683913422"></a><a name="p1662683913422"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.17%" id="mcps1.2.5.1.4"><p id="p362633910427"><a name="p362633910427"></a><a name="p362633910427"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16626939104213"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p1862615393424"><a name="p1862615393424"></a><a name="p1862615393424"></a>ak</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p962673917423"><a name="p962673917423"></a><a name="p962673917423"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.3 "><p id="p562643924215"><a name="p562643924215"></a><a name="p562643924215"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.17%" headers="mcps1.2.5.1.4 "><p id="p96261239104212"><a name="p96261239104212"></a><a name="p96261239104212"></a>用户的ak，可参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row36261639124211"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p10626113911425"><a name="p10626113911425"></a><a name="p10626113911425"></a>sk</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p106261639204217"><a name="p106261639204217"></a><a name="p106261639204217"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.3 "><p id="p66262398426"><a name="p66262398426"></a><a name="p66262398426"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.17%" headers="mcps1.2.5.1.4 "><p id="p10626183915420"><a name="p10626183915420"></a><a name="p10626183915420"></a>用户的sk，可参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row6626739134210"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p186261739124217"><a name="p186261739124217"></a><a name="p186261739124217"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p1462613994215"><a name="p1462613994215"></a><a name="p1462613994215"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.3 "><p id="p46265394425"><a name="p46265394425"></a><a name="p46265394425"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.17%" headers="mcps1.2.5.1.4 "><p id="p96261339124216"><a name="p96261339124216"></a><a name="p96261339124216"></a>区域，如：cn-north-4。具体请参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0004.html" target="_blank" rel="noopener noreferrer">终端节点</a>。</p>
</td>
</tr>
<tr id="row152416178441"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p6524101716441"><a name="p6524101716441"></a><a name="p6524101716441"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p9524181714441"><a name="p9524181714441"></a><a name="p9524181714441"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.3 "><p id="p13119133094416"><a name="p13119133094416"></a><a name="p13119133094416"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.17%" headers="mcps1.2.5.1.4 "><p id="p152411734416"><a name="p152411734416"></a><a name="p152411734416"></a>项目ID，同region一一对应，参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0008.html" target="_blank" rel="noopener noreferrer">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row839453719473"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p3395193784714"><a name="p3395193784714"></a><a name="p3395193784714"></a>service_endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p9395133716472"><a name="p9395133716472"></a><a name="p9395133716472"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.3 "><p id="p8395163754712"><a name="p8395163754712"></a><a name="p8395163754712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.17%" headers="mcps1.2.5.1.4 "><p id="p53955376474"><a name="p53955376474"></a><a name="p53955376474"></a>终端节点，一般使用默认即可。</p>
</td>
</tr>
<tr id="row18626173974218"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p1362611392427"><a name="p1362611392427"></a><a name="p1362611392427"></a>sis_config</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p66261239174215"><a name="p66261239174215"></a><a name="p66261239174215"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.3 "><p id="p562618395429"><a name="p562618395429"></a><a name="p562618395429"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.17%" headers="mcps1.2.5.1.4 "><p id="p136264393421"><a name="p136264393421"></a><a name="p136264393421"></a>详见<a href="#table12745429102316">表2</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  SisConfig

<a name="table12745429102316"></a>
<table><thead align="left"><tr id="row1974652917235"><th class="cellrowborder" valign="top" width="14.299999999999999%" id="mcps1.2.5.1.1"><p id="p2746182992315"><a name="p2746182992315"></a><a name="p2746182992315"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.2%" id="mcps1.2.5.1.2"><p id="p774615294231"><a name="p774615294231"></a><a name="p774615294231"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.34%" id="mcps1.2.5.1.3"><p id="p9746172912312"><a name="p9746172912312"></a><a name="p9746172912312"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.160000000000004%" id="mcps1.2.5.1.4"><p id="p1774672932312"><a name="p1774672932312"></a><a name="p1774672932312"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row174632962316"><td class="cellrowborder" valign="top" width="14.299999999999999%" headers="mcps1.2.5.1.1 "><p id="p15746162917234"><a name="p15746162917234"></a><a name="p15746162917234"></a>connect_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="10.2%" headers="mcps1.2.5.1.2 "><p id="p10746112962320"><a name="p10746112962320"></a><a name="p10746112962320"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p874610297239"><a name="p874610297239"></a><a name="p874610297239"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="p17747216152514"><a name="p17747216152514"></a><a name="p17747216152514"></a>连接超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row6746162962312"><td class="cellrowborder" valign="top" width="14.299999999999999%" headers="mcps1.2.5.1.1 "><p id="p974652915232"><a name="p974652915232"></a><a name="p974652915232"></a>read_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="10.2%" headers="mcps1.2.5.1.2 "><p id="p274632918233"><a name="p274632918233"></a><a name="p274632918233"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p674619295239"><a name="p674619295239"></a><a name="p674619295239"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="p874652912315"><a name="p874652912315"></a><a name="p874652912315"></a>读取超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row1174616298233"><td class="cellrowborder" valign="top" width="14.299999999999999%" headers="mcps1.2.5.1.1 "><p id="p574611293230"><a name="p574611293230"></a><a name="p574611293230"></a>proxy</p>
</td>
<td class="cellrowborder" valign="top" width="10.2%" headers="mcps1.2.5.1.2 "><p id="p10746829162316"><a name="p10746829162316"></a><a name="p10746829162316"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.34%" headers="mcps1.2.5.1.3 "><p id="p1574613293234"><a name="p1574613293234"></a><a name="p1574613293234"></a>List</p>
</td>
<td class="cellrowborder" valign="top" width="62.160000000000004%" headers="mcps1.2.5.1.4 "><p id="p8746529182310"><a name="p8746529182310"></a><a name="p8746529182310"></a>[host, port] 或 [host, port, username, password]。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section143008206277"></a>

请求类为AsrCustomLongRequest，详见[表3](#table45631337366)。

**表 3**  AsrCustomLongRequest

<a name="table45631337366"></a>
<table><thead align="left"><tr id="row195631236363"><th class="cellrowborder" valign="top" width="13.950000000000001%" id="mcps1.2.5.1.1"><p id="p55640373620"><a name="p55640373620"></a><a name="p55640373620"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.18%" id="mcps1.2.5.1.2"><p id="p1456420383614"><a name="p1456420383614"></a><a name="p1456420383614"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.23%" id="mcps1.2.5.1.3"><p id="p1056412313618"><a name="p1056412313618"></a><a name="p1056412313618"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.63999999999999%" id="mcps1.2.5.1.4"><p id="p1856419353613"><a name="p1856419353613"></a><a name="p1856419353613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row95641038369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p11564173163615"><a name="p11564173163615"></a><a name="p11564173163615"></a>data_url</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p356419323619"><a name="p356419323619"></a><a name="p356419323619"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p956483123613"><a name="p956483123613"></a><a name="p956483123613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p456415333616"><a name="p456415333616"></a><a name="p456415333616"></a>OBS音频链接，目前华为云仅支持来自OBS的链接，注意OBS的region要与AsrCustomizationClient的region保持一致，同时需要确保链接为用户个人的OBS的音频连接，不支持访问其他用户的公共读的OBS音频链接。</p>
</td>
</tr>
<tr id="row65644313369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p25641933360"><a name="p25641933360"></a><a name="p25641933360"></a>audio_format</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p175641034365"><a name="p175641034365"></a><a name="p175641034365"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p1356463173618"><a name="p1356463173618"></a><a name="p1356463173618"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p1599448164011"><a name="p1599448164011"></a><a name="p1599448164011"></a>音频格式，具体信息请参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0092.html" target="_blank" rel="noopener noreferrer">录音文件识别</a>章节。</p>
</td>
</tr>
<tr id="row65653319364"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p145659343611"><a name="p145659343611"></a><a name="p145659343611"></a>model_property</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p115656333612"><a name="p115656333612"></a><a name="p115656333612"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p105651303613"><a name="p105651303613"></a><a name="p105651303613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p1856517313618"><a name="p1856517313618"></a><a name="p1856517313618"></a>属性字符串，语言_采样率_模型，如chinese_8k_common。具体信息请参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0092.html" target="_blank" rel="noopener noreferrer">录音文件识别</a>章节。</p>
</td>
</tr>
<tr id="row15558172874017"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p8559528154012"><a name="p8559528154012"></a><a name="p8559528154012"></a>add_punc</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p755920281403"><a name="p755920281403"></a><a name="p755920281403"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p14559192810408"><a name="p14559192810408"></a><a name="p14559192810408"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p17559102814402"><a name="p17559102814402"></a><a name="p17559102814402"></a>表示是否在识别结果中添加标点，取值为yes 、 no，默认no。</p>
</td>
</tr>
<tr id="row12487449302"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p5459115619553"><a name="p5459115619553"></a><a name="p5459115619553"></a>digit_norm</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p845935619556"><a name="p845935619556"></a><a name="p845935619556"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p184591056165517"><a name="p184591056165517"></a><a name="p184591056165517"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p64597569556"><a name="p64597569556"></a><a name="p64597569556"></a>表示是否将语音中的数字识别为阿拉伯数字，取值为yes 、 no，默认为yes。</p>
</td>
</tr>
<tr id="row316365315528"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p576455914325"><a name="p576455914325"></a><a name="p576455914325"></a>need_analysis_info</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p9164145318522"><a name="p9164145318522"></a><a name="p9164145318522"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p18764659163211"><a name="p18764659163211"></a><a name="p18764659163211"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p341451417364"><a name="p341451417364"></a><a name="p341451417364"></a>是否选择分析信息。</p>
<p id="p177641591321"><a name="p177641591321"></a><a name="p177641591321"></a>如果选择false，则声道、话者分离、情绪检测、速度信息均无效。默认false。</p>
</td>
</tr>
<tr id="row66386593525"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p1976455963219"><a name="p1976455963219"></a><a name="p1976455963219"></a>diarization</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p17639205916524"><a name="p17639205916524"></a><a name="p17639205916524"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p17641659103217"><a name="p17641659103217"></a><a name="p17641659103217"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p176445913322"><a name="p176445913322"></a><a name="p176445913322"></a>是否需要话者分离，表示识别结果会包含role项，默认true。</p>
</td>
</tr>
<tr id="row143729101535"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p197641859123212"><a name="p197641859123212"></a><a name="p197641859123212"></a>channel</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p193721010175315"><a name="p193721010175315"></a><a name="p193721010175315"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p13764145973210"><a name="p13764145973210"></a><a name="p13764145973210"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p11764195915321"><a name="p11764195915321"></a><a name="p11764195915321"></a>语音文件声道信息，可以为MONO（缺省), LEFT_AGENT， RIGHT_AGENT。默认MONO。</p>
</td>
</tr>
<tr id="row52955149531"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p177641559133216"><a name="p177641559133216"></a><a name="p177641559133216"></a>emotion</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p12955142532"><a name="p12955142532"></a><a name="p12955142532"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p1276417597323"><a name="p1276417597323"></a><a name="p1276417597323"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p16764195993215"><a name="p16764195993215"></a><a name="p16764195993215"></a>是否需要做情绪检测，默认true。</p>
</td>
</tr>
<tr id="row1831114616537"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p07641959153212"><a name="p07641959153212"></a><a name="p07641959153212"></a>speed</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p43111164539"><a name="p43111164539"></a><a name="p43111164539"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p15764195993215"><a name="p15764195993215"></a><a name="p15764195993215"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p127641159113214"><a name="p127641159113214"></a><a name="p127641159113214"></a>是否需要输出语速信息，默认true。</p>
</td>
</tr>
<tr id="row266453364019"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p17664143315404"><a name="p17664143315404"></a><a name="p17664143315404"></a>vocabulary_id</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p126641233134010"><a name="p126641233134010"></a><a name="p126641233134010"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p6664103364017"><a name="p6664103364017"></a><a name="p6664103364017"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p1254929112618"><a name="p1254929112618"></a><a name="p1254929112618"></a>热词表id，不使用则不填写。</p>
<p id="p18929185814249"><a name="p18929185814249"></a><a name="p18929185814249"></a>创建热词表请参考《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0071.html" target="_blank" rel="noopener noreferrer">创建热词表</a>章节。</p>
</td>
</tr>
<tr id="row11726105791219"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p129901831105112"><a name="p129901831105112"></a><a name="p129901831105112"></a>word_info</p>
</td>
<td class="cellrowborder" valign="top" width="10.18%" headers="mcps1.2.5.1.2 "><p id="p19990931145114"><a name="p19990931145114"></a><a name="p19990931145114"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.23%" headers="mcps1.2.5.1.3 "><p id="p599023115116"><a name="p599023115116"></a><a name="p599023115116"></a>Array of objects</p>
</td>
<td class="cellrowborder" valign="top" width="62.63999999999999%" headers="mcps1.2.5.1.4 "><p id="p399023105119"><a name="p399023105119"></a><a name="p399023105119"></a>分词信息列表。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section2581112416279"></a>

Python SDK响应结果为Json格式，详见[表4](#table1917456103719)。

**表 4**  响应结果

<a name="table1917456103719"></a>
<table><thead align="left"><tr id="row18174156103716"><th class="cellrowborder" valign="top" width="12.82%" id="mcps1.2.5.1.1"><p id="p917516153711"><a name="p917516153711"></a><a name="p917516153711"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.72%" id="mcps1.2.5.1.2"><p id="p6175176123718"><a name="p6175176123718"></a><a name="p6175176123718"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.47%" id="mcps1.2.5.1.3"><p id="p41758683712"><a name="p41758683712"></a><a name="p41758683712"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p917518613712"><a name="p917518613712"></a><a name="p917518613712"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row6462132101"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p104626318108"><a name="p104626318108"></a><a name="p104626318108"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="11.72%" headers="mcps1.2.5.1.2 "><p id="p446213381020"><a name="p446213381020"></a><a name="p446213381020"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p146283181012"><a name="p146283181012"></a><a name="p146283181012"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p186911528142817"><a name="p186911528142817"></a><a name="p186911528142817"></a>当前识别状态。具体状态如下所示：</p>
<p id="p136912288289"><a name="p136912288289"></a><a name="p136912288289"></a>WAITING 等待识别。</p>
<p id="p19691628192815"><a name="p19691628192815"></a><a name="p19691628192815"></a>FINISHED 识别已经完成。</p>
<p id="p969122822813"><a name="p969122822813"></a><a name="p969122822813"></a>ERROR 识别过程中发生错误。</p>
</td>
</tr>
<tr id="row188818661020"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p8881196141019"><a name="p8881196141019"></a><a name="p8881196141019"></a>create_time</p>
</td>
<td class="cellrowborder" valign="top" width="11.72%" headers="mcps1.2.5.1.2 "><p id="p288114601016"><a name="p288114601016"></a><a name="p288114601016"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p17607339161015"><a name="p17607339161015"></a><a name="p17607339161015"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p3691162818282"><a name="p3691162818282"></a><a name="p3691162818282"></a>任务创建时间, 遵循 RFC 3339格式。</p>
<p id="p2069162815282"><a name="p2069162815282"></a><a name="p2069162815282"></a>格式示例：2018-12-04T13:10:29.310Z。</p>
</td>
</tr>
<tr id="row17286205813919"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p828665819918"><a name="p828665819918"></a><a name="p828665819918"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="11.72%" headers="mcps1.2.5.1.2 "><p id="p18286858594"><a name="p18286858594"></a><a name="p18286858594"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p758715407104"><a name="p758715407104"></a><a name="p758715407104"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p469111280286"><a name="p469111280286"></a><a name="p469111280286"></a>开始识别时间, 遵循 RFC 3339格式。</p>
<p id="p6691152813286"><a name="p6691152813286"></a><a name="p6691152813286"></a>当status为FINISHED或ERROR时存在。</p>
<p id="p15691142822819"><a name="p15691142822819"></a><a name="p15691142822819"></a>格式示例：2018-12-04T13:10:29.310Z。</p>
</td>
</tr>
<tr id="row86822536916"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p176827534918"><a name="p176827534918"></a><a name="p176827534918"></a>finish_time</p>
</td>
<td class="cellrowborder" valign="top" width="11.72%" headers="mcps1.2.5.1.2 "><p id="p1068225310920"><a name="p1068225310920"></a><a name="p1068225310920"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p3519941131016"><a name="p3519941131016"></a><a name="p3519941131016"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p12692528152814"><a name="p12692528152814"></a><a name="p12692528152814"></a>识别完成时间, 遵循 RFC 3339格式。</p>
<p id="p126921728182812"><a name="p126921728182812"></a><a name="p126921728182812"></a>当status为FINISHED或ERROR时存在。</p>
<p id="p469215284287"><a name="p469215284287"></a><a name="p469215284287"></a>格式示例：2018-12-04T13:10:29.310Z。</p>
</td>
</tr>
<tr id="row111751668379"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p111758612376"><a name="p111758612376"></a><a name="p111758612376"></a>segments</p>
</td>
<td class="cellrowborder" valign="top" width="11.72%" headers="mcps1.2.5.1.2 "><p id="p3176961376"><a name="p3176961376"></a><a name="p3176961376"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p1317619620373"><a name="p1317619620373"></a><a name="p1317619620373"></a>Array of objects</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p8692928162817"><a name="p8692928162817"></a><a name="p8692928162817"></a>识别结果, 多句结果的数组。</p>
<p id="p1069215287283"><a name="p1069215287283"></a><a name="p1069215287283"></a>数据结构参见<a href="#table235014283281">表5</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  Segment

<a name="table235014283281"></a>
<table><thead align="left"><tr id="row069242818289"><th class="cellrowborder" valign="top" width="12.989999999999998%" id="mcps1.2.5.1.1"><p id="p8692828112814"><a name="p8692828112814"></a><a name="p8692828112814"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="12.030000000000001%" id="mcps1.2.5.1.2"><p id="p14692328112814"><a name="p14692328112814"></a><a name="p14692328112814"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.120000000000001%" id="mcps1.2.5.1.3"><p id="p186921928192812"><a name="p186921928192812"></a><a name="p186921928192812"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.86000000000001%" id="mcps1.2.5.1.4"><p id="p46921728142819"><a name="p46921728142819"></a><a name="p46921728142819"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row669214289281"><td class="cellrowborder" valign="top" width="12.989999999999998%" headers="mcps1.2.5.1.1 "><p id="p12692112822813"><a name="p12692112822813"></a><a name="p12692112822813"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p13692182811282"><a name="p13692182811282"></a><a name="p13692182811282"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p1669218281281"><a name="p1669218281281"></a><a name="p1669218281281"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.86000000000001%" headers="mcps1.2.5.1.4 "><p id="p1693122852810"><a name="p1693122852810"></a><a name="p1693122852810"></a>一句的起始时间戳，单位ms。</p>
</td>
</tr>
<tr id="row19693182819282"><td class="cellrowborder" valign="top" width="12.989999999999998%" headers="mcps1.2.5.1.1 "><p id="p196933280284"><a name="p196933280284"></a><a name="p196933280284"></a>end_time</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p18693152813282"><a name="p18693152813282"></a><a name="p18693152813282"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p146936288286"><a name="p146936288286"></a><a name="p146936288286"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.86000000000001%" headers="mcps1.2.5.1.4 "><p id="p13693192810281"><a name="p13693192810281"></a><a name="p13693192810281"></a>一句的结束时间戳，单位ms。</p>
</td>
</tr>
<tr id="row1869318283282"><td class="cellrowborder" valign="top" width="12.989999999999998%" headers="mcps1.2.5.1.1 "><p id="p13693112815283"><a name="p13693112815283"></a><a name="p13693112815283"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="12.030000000000001%" headers="mcps1.2.5.1.2 "><p id="p1693028122817"><a name="p1693028122817"></a><a name="p1693028122817"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p96939288288"><a name="p96939288288"></a><a name="p96939288288"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.86000000000001%" headers="mcps1.2.5.1.4 "><p id="p9693192852819"><a name="p9693192852819"></a><a name="p9693192852819"></a>调用成功表示识别结果，调用失败时无此字段。详见<a href="#table736482819285">表6</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 6**  Result

<a name="table736482819285"></a>
<table><thead align="left"><tr id="row1693528132811"><th class="cellrowborder" valign="top" width="13.16%" id="mcps1.2.5.1.1"><p id="p1069318286287"><a name="p1069318286287"></a><a name="p1069318286287"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="11.86%" id="mcps1.2.5.1.2"><p id="p569312817289"><a name="p569312817289"></a><a name="p569312817289"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.840000000000002%" id="mcps1.2.5.1.3"><p id="p46931728152815"><a name="p46931728152815"></a><a name="p46931728152815"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="59.14%" id="mcps1.2.5.1.4"><p id="p369382818289"><a name="p369382818289"></a><a name="p369382818289"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row9693152813281"><td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.1 "><p id="p13693728162811"><a name="p13693728162811"></a><a name="p13693728162811"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="11.86%" headers="mcps1.2.5.1.2 "><p id="p06941828132813"><a name="p06941828132813"></a><a name="p06941828132813"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.5.1.3 "><p id="p206941528162817"><a name="p206941528162817"></a><a name="p206941528162817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="59.14%" headers="mcps1.2.5.1.4 "><p id="p10694028112812"><a name="p10694028112812"></a><a name="p10694028112812"></a>识别结果文本。</p>
</td>
</tr>
<tr id="row13694428182810"><td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.1 "><p id="p1169492816289"><a name="p1169492816289"></a><a name="p1169492816289"></a>analysis_info</p>
</td>
<td class="cellrowborder" valign="top" width="11.86%" headers="mcps1.2.5.1.2 "><p id="p7694142812817"><a name="p7694142812817"></a><a name="p7694142812817"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.5.1.3 "><p id="p769402812812"><a name="p769402812812"></a><a name="p769402812812"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="59.14%" headers="mcps1.2.5.1.4 "><p id="p18694152862813"><a name="p18694152862813"></a><a name="p18694152862813"></a>每一句的质检分析结果对象。</p>
<p id="p1469432832816"><a name="p1469432832816"></a><a name="p1469432832816"></a>仅在识别配置中的need_analysis_info不为null时存在该返回结果。详见<a href="#table1840612815283">表7</a>。</p>
</td>
</tr>
<tr id="row11677173111139"><td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.1 "><p id="p16518261956"><a name="p16518261956"></a><a name="p16518261956"></a><span>word_info</span></p>
</td>
<td class="cellrowborder" valign="top" width="11.86%" headers="mcps1.2.5.1.2 "><p id="p19651132611516"><a name="p19651132611516"></a><a name="p19651132611516"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.5.1.3 "><p id="p13651526855"><a name="p13651526855"></a><a name="p13651526855"></a>Array of Object</p>
</td>
<td class="cellrowborder" valign="top" width="59.14%" headers="mcps1.2.5.1.4 "><p id="p665112620516"><a name="p665112620516"></a><a name="p665112620516"></a>分词输出列表。</p>
</td>
</tr>
</tbody>
</table>

**表 7**  Analysis\_info

<a name="table1840612815283"></a>
<table><thead align="left"><tr id="row369402820284"><th class="cellrowborder" valign="top" width="13.08%" id="mcps1.2.5.1.1"><p id="p2694528182814"><a name="p2694528182814"></a><a name="p2694528182814"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="12.120000000000001%" id="mcps1.2.5.1.2"><p id="p56941828122820"><a name="p56941828122820"></a><a name="p56941828122820"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.21%" id="mcps1.2.5.1.3"><p id="p1569482822813"><a name="p1569482822813"></a><a name="p1569482822813"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.59%" id="mcps1.2.5.1.4"><p id="p10694628152811"><a name="p10694628152811"></a><a name="p10694628152811"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row11694192820283"><td class="cellrowborder" valign="top" width="13.08%" headers="mcps1.2.5.1.1 "><p id="p9694228182820"><a name="p9694228182820"></a><a name="p9694228182820"></a>role</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.2 "><p id="p369402819287"><a name="p369402819287"></a><a name="p369402819287"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.3 "><p id="p2694172842819"><a name="p2694172842819"></a><a name="p2694172842819"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.59%" headers="mcps1.2.5.1.4 "><p id="p106949285287"><a name="p106949285287"></a><a name="p106949285287"></a>角色类型，目前仅支持 AGENT(座席)，USER(用户)。</p>
</td>
</tr>
<tr id="row1569416280283"><td class="cellrowborder" valign="top" width="13.08%" headers="mcps1.2.5.1.1 "><p id="p2069410288283"><a name="p2069410288283"></a><a name="p2069410288283"></a>emotion</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.2 "><p id="p76941228122811"><a name="p76941228122811"></a><a name="p76941228122811"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.3 "><p id="p13694162810289"><a name="p13694162810289"></a><a name="p13694162810289"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.59%" headers="mcps1.2.5.1.4 "><p id="p1269502872817"><a name="p1269502872817"></a><a name="p1269502872817"></a>情绪类型，目前仅支持NORMAL(正常)，ANGRY(愤怒)。</p>
<p id="p2069515287286"><a name="p2069515287286"></a><a name="p2069515287286"></a>在识别配置中emotion为true时存在。</p>
</td>
</tr>
<tr id="row14695152818286"><td class="cellrowborder" valign="top" width="13.08%" headers="mcps1.2.5.1.1 "><p id="p9695162811285"><a name="p9695162811285"></a><a name="p9695162811285"></a>speed</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.2 "><p id="p20695122812282"><a name="p20695122812282"></a><a name="p20695122812282"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.3 "><p id="p13237181344"><a name="p13237181344"></a><a name="p13237181344"></a>Float</p>
</td>
<td class="cellrowborder" valign="top" width="62.59%" headers="mcps1.2.5.1.4 "><p id="p1969572810287"><a name="p1969572810287"></a><a name="p1969572810287"></a>语速信息，单位是"每秒字数"。</p>
<p id="p9695142802819"><a name="p9695142802819"></a><a name="p9695142802819"></a>在识别配置中speed为true时存在。</p>
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

## 代码示例<a name="section338116313271"></a>

```
# -*- coding: utf-8 -*-

from huaweicloud_sis.client.asr_client import AsrCustomizationClient
from huaweicloud_sis.bean.asr_request import AsrCustomShortRequest
from huaweicloud_sis.bean.asr_request import AsrCustomLongRequest
from huaweicloud_sis.exception.exceptions import ClientException
from huaweicloud_sis.exception.exceptions import ServerException
from huaweicloud_sis.utils import io_utils
from huaweicloud_sis.bean.sis_config import SisConfig
import json
import time

# 鉴权参数
ak = ''             
sk = ''             
region = ''         # region，如cn-north-4
project_id = ''     # 同region一一对应。登录管理控制台，鼠标移动到右上角的用户名上，在下拉列表中选择我的凭证，在我的凭证页面，在项目列表中查看项目id。多项目时，展开“所属区域”，从“项目ID”列获取子项目ID。

"""
    todo 请正确填写音频格式和模型属性字符串
    1. 音频格式一定要相匹配.
         例如obs url是xx.wav, 则是auto 格式
         例如音频是pcm格式，并且采样率为8k，则格式填写pcm8k16bit。
         如果返回audio_format is invalid 说明该文件格式不支持

    2. 音频采样率要与属性字符串的采样率要匹配。
         例如格式选择pcm16k16bit，属性字符串却选择chinese_8k_common, 则属于采样率不匹配
         例如wav本身是16k采样率，属性选择chinese_8k_common, 同样属于采样率不匹配

    3. 用户可以通过使用热词，识别专业术语，增加语句识别准确率。
"""

# 录音文件识别参数，音频文件以obs连接方式传入（即先需要将音频传送到华为云的obs）
obs_url = ''                # 音频obs连接
obs_audio_format = ''       # 音频格式，如auto
obs_property = ''           # language_sampleRate_domain, 如chinese_8k_common

def asrc_long_example():
    """ 录音文件识别示例 """
    # step1 初始化客户端
    config = SisConfig()
    config.set_connect_timeout(10)       # 设置连接超时
    config.set_read_timeout(10)         # 设置读取超时
    # 设置代理，使用代理前一定要确保代理可用。 代理格式可为[host, port] 或 [host, port, username, password]
    # config.set_proxy(proxy)
    asr_client = AsrCustomizationClient(ak, sk, region, project_id,  sis_config=config)

    # step2 构造请求
    asrc_request = AsrCustomLongRequest(obs_audio_format, obs_property, obs_url)
    # 所有参数均可不设置，使用默认值
    # 设置是否添加标点，yes or no，默认no
    asrc_request.set_add_punc('yes')
    # 设置 是否需要分析信息，True or False, 默认False。 只有need_analysis_info生效，diarization、channel、emotion、speed才会生效
    # 目前仅支持8k模型
    asrc_request.set_need_analysis_info(True)
    # 设置是否需要话者分离，默认True，需要need_analysis_info设置为True才生效。
    asrc_request.set_diarization(True)
    # 设置声道信息, 一般都是单声道，默认为MONO，需要need_analysis_info设置为True才生效
    asrc_request.set_channel('MONO')
    # 设置是否返回感情信息, 默认True，需要need_analysis_info设置为True才生效。
    asrc_request.set_emotion(True)
    # 设置是否需要返回语速信息，默认True，需要need_analysis_info设置为True才生效。
    asrc_request.set_speed(True)
    # 设置是否添加热词表id，没有则不填
    # asrc_request.set_vocabulary_id(None)
    # 设置回调地址，设置后音频转写结果将直接发送至回调地址。请务必保证地址可联通。目前不支持ip地址，仅支持域名。
    # asrc_request.set_callback_url('')
    # 设置是否将语音中数字转写为阿拉伯数字，yes or no，默认yes
    asrc_request.set_digit_norm('yes')

    # step3 发送请求，获取job_id
    job_id = asr_client.submit_job(asrc_request)

    # step4 根据job_id轮询，获取结果。
    status = 'WAITING'
    count = 0   # 每2s查询一次，最多尝试2000次，即4000s
    while status != 'FINISHED' and count < 2000:
        print(count, ' query')
        result = asr_client.get_long_response(job_id)
        status = result['status']
        if status == 'ERROR':
            print('录音文件识别执行失败, %s' % json.dump(result))
            break
        time.sleep(2)
        count += 1
    if status != 'FINISHED':
        print('录音文件识别未在 %d 内获取结果，job_id 为%s' % (count, job_id))
    print(json.dumps(result, indent=2, ensure_ascii=False))


if __name__ == '__main__':
    try:
        asrc_long_example()         # 录音文件识别
    except ClientException as e:
        print(e)
    except ServerException as e:
        print(e)
```

