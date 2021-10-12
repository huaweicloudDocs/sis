# 一句话识别Http接口<a name="sis_05_0051"></a>

## 前提条件<a name="section483618911279"></a>

-   确保已按照[配置Python环境](配置Python环境.md)配置完毕，Python SDK仅支持Python3。
-   确保已存在待识别的音频文件。如果需要请在下载的SDK压缩包中获取示例音频。

## 初始化Client<a name="section590271313272"></a>

初始化AsrCustomizationClient详见[表 AsrCustomizationClient初始化参数](#table86254392424)。

**表 1**  AsrCustomizationClient初始化参数

<a name="table86254392424"></a>
<table><thead align="left"><tr id="row136261939144211"><th class="cellrowborder" valign="top" width="13.600000000000001%" id="mcps1.2.5.1.1"><p id="p762663917427"><a name="p762663917427"></a><a name="p762663917427"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.600000000000001%" id="mcps1.2.5.1.2"><p id="p9626153994217"><a name="p9626153994217"></a><a name="p9626153994217"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.120000000000001%" id="mcps1.2.5.1.3"><p id="p1662683913422"><a name="p1662683913422"></a><a name="p1662683913422"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.68%" id="mcps1.2.5.1.4"><p id="p362633910427"><a name="p362633910427"></a><a name="p362633910427"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16626939104213"><td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.1 "><p id="p1862615393424"><a name="p1862615393424"></a><a name="p1862615393424"></a>ak</p>
</td>
<td class="cellrowborder" valign="top" width="11.600000000000001%" headers="mcps1.2.5.1.2 "><p id="p962673917423"><a name="p962673917423"></a><a name="p962673917423"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p562643924215"><a name="p562643924215"></a><a name="p562643924215"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p96261239104212"><a name="p96261239104212"></a><a name="p96261239104212"></a>用户的ak，可参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row36261639124211"><td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.1 "><p id="p10626113911425"><a name="p10626113911425"></a><a name="p10626113911425"></a>sk</p>
</td>
<td class="cellrowborder" valign="top" width="11.600000000000001%" headers="mcps1.2.5.1.2 "><p id="p106261639204217"><a name="p106261639204217"></a><a name="p106261639204217"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p66262398426"><a name="p66262398426"></a><a name="p66262398426"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p10626183915420"><a name="p10626183915420"></a><a name="p10626183915420"></a>用户的sk，可参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row6626739134210"><td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.1 "><p id="p186261739124217"><a name="p186261739124217"></a><a name="p186261739124217"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="11.600000000000001%" headers="mcps1.2.5.1.2 "><p id="p1462613994215"><a name="p1462613994215"></a><a name="p1462613994215"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p46265394425"><a name="p46265394425"></a><a name="p46265394425"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p148991840119"><a name="p148991840119"></a><a name="p148991840119"></a>区域，如cn-north-4，参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0004.html" target="_blank" rel="noopener noreferrer">终端节点</a>。</p>
</td>
</tr>
<tr id="row152416178441"><td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.1 "><p id="p6524101716441"><a name="p6524101716441"></a><a name="p6524101716441"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="11.600000000000001%" headers="mcps1.2.5.1.2 "><p id="p9524181714441"><a name="p9524181714441"></a><a name="p9524181714441"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p13119133094416"><a name="p13119133094416"></a><a name="p13119133094416"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p152411734416"><a name="p152411734416"></a><a name="p152411734416"></a>项目ID，同region一一对应，参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0008.html" target="_blank" rel="noopener noreferrer">获取项目ID</a>。</p>
</td>
</tr>
<tr id="row839453719473"><td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.1 "><p id="p3395193784714"><a name="p3395193784714"></a><a name="p3395193784714"></a>service_endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="11.600000000000001%" headers="mcps1.2.5.1.2 "><p id="p9395133716472"><a name="p9395133716472"></a><a name="p9395133716472"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p8395163754712"><a name="p8395163754712"></a><a name="p8395163754712"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p53955376474"><a name="p53955376474"></a><a name="p53955376474"></a>终端节点，一般使用默认即可。</p>
</td>
</tr>
<tr id="row18626173974218"><td class="cellrowborder" valign="top" width="13.600000000000001%" headers="mcps1.2.5.1.1 "><p id="p1362611392427"><a name="p1362611392427"></a><a name="p1362611392427"></a>sis_config</p>
</td>
<td class="cellrowborder" valign="top" width="11.600000000000001%" headers="mcps1.2.5.1.2 "><p id="p66261239174215"><a name="p66261239174215"></a><a name="p66261239174215"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p562618395429"><a name="p562618395429"></a><a name="p562618395429"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p136264393421"><a name="p136264393421"></a><a name="p136264393421"></a>详见<a href="#table12745429102316">表2</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  SisConfig

<a name="table12745429102316"></a>
<table><thead align="left"><tr id="row1974652917235"><th class="cellrowborder" valign="top" width="13.86%" id="mcps1.2.5.1.1"><p id="p2746182992315"><a name="p2746182992315"></a><a name="p2746182992315"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.81%" id="mcps1.2.5.1.2"><p id="p774615294231"><a name="p774615294231"></a><a name="p774615294231"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.73%" id="mcps1.2.5.1.3"><p id="p9746172912312"><a name="p9746172912312"></a><a name="p9746172912312"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.6%" id="mcps1.2.5.1.4"><p id="p1774672932312"><a name="p1774672932312"></a><a name="p1774672932312"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row174632962316"><td class="cellrowborder" valign="top" width="13.86%" headers="mcps1.2.5.1.1 "><p id="p15746162917234"><a name="p15746162917234"></a><a name="p15746162917234"></a>connect_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="10.81%" headers="mcps1.2.5.1.2 "><p id="p10746112962320"><a name="p10746112962320"></a><a name="p10746112962320"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.73%" headers="mcps1.2.5.1.3 "><p id="p874610297239"><a name="p874610297239"></a><a name="p874610297239"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.6%" headers="mcps1.2.5.1.4 "><p id="p17747216152514"><a name="p17747216152514"></a><a name="p17747216152514"></a>连接超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row6746162962312"><td class="cellrowborder" valign="top" width="13.86%" headers="mcps1.2.5.1.1 "><p id="p974652915232"><a name="p974652915232"></a><a name="p974652915232"></a>read_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="10.81%" headers="mcps1.2.5.1.2 "><p id="p274632918233"><a name="p274632918233"></a><a name="p274632918233"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.73%" headers="mcps1.2.5.1.3 "><p id="p674619295239"><a name="p674619295239"></a><a name="p674619295239"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.6%" headers="mcps1.2.5.1.4 "><p id="p874652912315"><a name="p874652912315"></a><a name="p874652912315"></a>读取超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row1174616298233"><td class="cellrowborder" valign="top" width="13.86%" headers="mcps1.2.5.1.1 "><p id="p574611293230"><a name="p574611293230"></a><a name="p574611293230"></a>proxy</p>
</td>
<td class="cellrowborder" valign="top" width="10.81%" headers="mcps1.2.5.1.2 "><p id="p10746829162316"><a name="p10746829162316"></a><a name="p10746829162316"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.73%" headers="mcps1.2.5.1.3 "><p id="p1574613293234"><a name="p1574613293234"></a><a name="p1574613293234"></a>List</p>
</td>
<td class="cellrowborder" valign="top" width="62.6%" headers="mcps1.2.5.1.4 "><p id="p8746529182310"><a name="p8746529182310"></a><a name="p8746529182310"></a>[host, port] 或 [host, port, username, password]。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section143008206277"></a>

请求类为AsrCustomShortRequest，详见[表3](#table45631337366)。

**表 3**  AsrCustomShortRequest

<a name="table45631337366"></a>
<table><thead align="left"><tr id="row195631236363"><th class="cellrowborder" valign="top" width="13.950000000000001%" id="mcps1.2.5.1.1"><p id="p55640373620"><a name="p55640373620"></a><a name="p55640373620"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.16%" id="mcps1.2.5.1.2"><p id="p1456420383614"><a name="p1456420383614"></a><a name="p1456420383614"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.16%" id="mcps1.2.5.1.3"><p id="p1056412313618"><a name="p1056412313618"></a><a name="p1056412313618"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.73%" id="mcps1.2.5.1.4"><p id="p1856419353613"><a name="p1856419353613"></a><a name="p1856419353613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row95641038369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p11564173163615"><a name="p11564173163615"></a><a name="p11564173163615"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p356419323619"><a name="p356419323619"></a><a name="p356419323619"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.3 "><p id="p956483123613"><a name="p956483123613"></a><a name="p956483123613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.73%" headers="mcps1.2.5.1.4 "><p id="p456415333616"><a name="p456415333616"></a><a name="p456415333616"></a>本地音频文件经过Base64编码后的字符串，音频文件时长不超过1min。</p>
</td>
</tr>
<tr id="row65644313369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p25641933360"><a name="p25641933360"></a><a name="p25641933360"></a>audio_format</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p175641034365"><a name="p175641034365"></a><a name="p175641034365"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.3 "><p id="p1356463173618"><a name="p1356463173618"></a><a name="p1356463173618"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.73%" headers="mcps1.2.5.1.4 "><p id="p1599448164011"><a name="p1599448164011"></a><a name="p1599448164011"></a>音频格式，具体信息请参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0040.html" target="_blank" rel="noopener noreferrer">一句话识别</a>章节。</p>
</td>
</tr>
<tr id="row65653319364"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p145659343611"><a name="p145659343611"></a><a name="p145659343611"></a>model_property</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p115656333612"><a name="p115656333612"></a><a name="p115656333612"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.3 "><p id="p105651303613"><a name="p105651303613"></a><a name="p105651303613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.73%" headers="mcps1.2.5.1.4 "><p id="p1856517313618"><a name="p1856517313618"></a><a name="p1856517313618"></a>属性字符串，语言_采样率_模型，如chinese_8k_common。具体信息请参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0040.html" target="_blank" rel="noopener noreferrer">一句话识别</a>章节。</p>
</td>
</tr>
<tr id="row15558172874017"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p8559528154012"><a name="p8559528154012"></a><a name="p8559528154012"></a>add_punc</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p755920281403"><a name="p755920281403"></a><a name="p755920281403"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.3 "><p id="p14559192810408"><a name="p14559192810408"></a><a name="p14559192810408"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.73%" headers="mcps1.2.5.1.4 "><p id="p17559102814402"><a name="p17559102814402"></a><a name="p17559102814402"></a>表示是否在识别结果中添加标点，取值为yes 、 no，默认no。</p>
</td>
</tr>
<tr id="row5459185665518"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p5459115619553"><a name="p5459115619553"></a><a name="p5459115619553"></a>digit_norm</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p845935619556"><a name="p845935619556"></a><a name="p845935619556"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.3 "><p id="p184591056165517"><a name="p184591056165517"></a><a name="p184591056165517"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.73%" headers="mcps1.2.5.1.4 "><p id="p64597569556"><a name="p64597569556"></a><a name="p64597569556"></a>表示是否将语音中的数字识别为阿拉伯数字，取值为yes 、 no，默认为yes。</p>
</td>
</tr>
<tr id="row266453364019"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p17664143315404"><a name="p17664143315404"></a><a name="p17664143315404"></a>vocabulary_id</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p126641233134010"><a name="p126641233134010"></a><a name="p126641233134010"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.3 "><p id="p6664103364017"><a name="p6664103364017"></a><a name="p6664103364017"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.73%" headers="mcps1.2.5.1.4 "><p id="p1254929112618"><a name="p1254929112618"></a><a name="p1254929112618"></a>热词表id，不使用则不填写。</p>
<p id="p18929185814249"><a name="p18929185814249"></a><a name="p18929185814249"></a>创建热词表请参考《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0071.html" target="_blank" rel="noopener noreferrer">创建热词表</a>章节。</p>
</td>
</tr>
<tr id="row37752238101"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p16360737111013"><a name="p16360737111013"></a><a name="p16360737111013"></a>need_word_info</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p1336073720104"><a name="p1336073720104"></a><a name="p1336073720104"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.16%" headers="mcps1.2.5.1.3 "><p id="p536018377109"><a name="p536018377109"></a><a name="p536018377109"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.73%" headers="mcps1.2.5.1.4 "><p id="p936117372104"><a name="p936117372104"></a><a name="p936117372104"></a>表示是否在识别结果中输出分词结果信息，取值为<span class="parmvalue" id="parmvalue1490315211594"><a name="parmvalue1490315211594"></a><a name="parmvalue1490315211594"></a>“yes”</span>和<span class="parmvalue" id="parmvalue1812528135912"><a name="parmvalue1812528135912"></a><a name="parmvalue1812528135912"></a>“no”</span>，默认为<span class="parmvalue" id="parmvalue16738171065911"><a name="parmvalue16738171065911"></a><a name="parmvalue16738171065911"></a>“no”</span>。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section2581112416279"></a>

Python SDK响应结果为Json格式，[表4](#table1917456103719)。

**表 4**  响应结果

<a name="table1917456103719"></a>
<table><thead align="left"><tr id="row18174156103716"><th class="cellrowborder" valign="top" width="12.82%" id="mcps1.2.5.1.1"><p id="p917516153711"><a name="p917516153711"></a><a name="p917516153711"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.940000000000001%" id="mcps1.2.5.1.2"><p id="p6175176123718"><a name="p6175176123718"></a><a name="p6175176123718"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.25%" id="mcps1.2.5.1.3"><p id="p41758683712"><a name="p41758683712"></a><a name="p41758683712"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p917518613712"><a name="p917518613712"></a><a name="p917518613712"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row111751668379"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p111758612376"><a name="p111758612376"></a><a name="p111758612376"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p3176961376"><a name="p3176961376"></a><a name="p3176961376"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.25%" headers="mcps1.2.5.1.3 "><p id="p1317619620373"><a name="p1317619620373"></a><a name="p1317619620373"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p91764613714"><a name="p91764613714"></a><a name="p91764613714"></a>详见<a href="#table14271914380">表5</a>。</p>
</td>
</tr>
<tr id="row167071842185715"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p67084428579"><a name="p67084428579"></a><a name="p67084428579"></a>trace_id</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p97081742105717"><a name="p97081742105717"></a><a name="p97081742105717"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.25%" headers="mcps1.2.5.1.3 "><p id="p9708842185720"><a name="p9708842185720"></a><a name="p9708842185720"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p14708184215720"><a name="p14708184215720"></a><a name="p14708184215720"></a>用于后台日志问题追溯。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  Result

<a name="table14271914380"></a>
<table><thead align="left"><tr id="row14279193812"><th class="cellrowborder" valign="top" width="12.82%" id="mcps1.2.5.1.1"><p id="p82817114384"><a name="p82817114384"></a><a name="p82817114384"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.940000000000001%" id="mcps1.2.5.1.2"><p id="p8287103811"><a name="p8287103811"></a><a name="p8287103811"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="16.34%" id="mcps1.2.5.1.3"><p id="p3287123816"><a name="p3287123816"></a><a name="p3287123816"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="58.9%" id="mcps1.2.5.1.4"><p id="p728711386"><a name="p728711386"></a><a name="p728711386"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row728151133817"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p328171113813"><a name="p328171113813"></a><a name="p328171113813"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p1128171173814"><a name="p1128171173814"></a><a name="p1128171173814"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.34%" headers="mcps1.2.5.1.3 "><p id="p1528141143815"><a name="p1528141143815"></a><a name="p1528141143815"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="58.9%" headers="mcps1.2.5.1.4 "><p id="p1597344514384"><a name="p1597344514384"></a><a name="p1597344514384"></a>识别结果。</p>
</td>
</tr>
<tr id="row1879992313587"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p1979922314588"><a name="p1979922314588"></a><a name="p1979922314588"></a>score</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p179982315584"><a name="p179982315584"></a><a name="p179982315584"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="16.34%" headers="mcps1.2.5.1.3 "><p id="p8799152316581"><a name="p8799152316581"></a><a name="p8799152316581"></a>Float</p>
</td>
<td class="cellrowborder" valign="top" width="58.9%" headers="mcps1.2.5.1.4 "><p id="p5799723135816"><a name="p5799723135816"></a><a name="p5799723135816"></a>识别结果置信度评分。</p>
</td>
</tr>
<tr id="row22084586105"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p129901831105112"><a name="p129901831105112"></a><a name="p129901831105112"></a>word_info</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p19990931145114"><a name="p19990931145114"></a><a name="p19990931145114"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="16.34%" headers="mcps1.2.5.1.3 "><p id="p599023115116"><a name="p599023115116"></a><a name="p599023115116"></a>Array of objects</p>
</td>
<td class="cellrowborder" valign="top" width="58.9%" headers="mcps1.2.5.1.4 "><p id="p399023105119"><a name="p399023105119"></a><a name="p399023105119"></a>分词信息列表。</p>
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

## 代码示例<a name="section338116313271"></a>

```
# -*- coding: utf-8 -*-

from huaweicloud_sis.client.asr_client import AsrCustomizationClient
from huaweicloud_sis.bean.asr_request import AsrCustomShortRequest

from huaweicloud_sis.exception.exceptions import ClientException
from huaweicloud_sis.exception.exceptions import ServerException
from huaweicloud_sis.utils import io_utils
from huaweicloud_sis.bean.sis_config import SisConfig
import json


# 鉴权参数
ak = ''             
sk = ''             
region = ''         # region，如cn-north-4
project_id = ''     # 同region一一对应。登录管理控制台，鼠标移动到右上角的用户名上，在下拉列表中选择我的凭证，在我的凭证页面，在项目列表中查看项目id。多项目时，展开“所属区域”，从“项目ID”列获取子项目ID。
# 一句话识别参数，音频要求为1min以内
path = ''                   # 文件位置，需要具体到音频文件，如D:/test.wav
path_audio_format = ''      # 音频格式，如wav
path_property = ''          # 所使用的模型特征串，通常是 “语种_采样率_领域”的形式, 如chinese_8k_common


def asrc_short_example():
    """ 一句话识别示例 """
    # step1 初始化客户端
    config = SisConfig()
    config.set_connect_timeout(10)       # 设置连接超时
    config.set_read_timeout(10)         # 设置读取超时
    # 设置代理，使用代理前一定要确保代理可用。 代理格式可为[host, port] 或 [host, port, username, password]
    # config.set_proxy(proxy)
    asr_client = AsrCustomizationClient(ak, sk, region, project_id,  sis_config=config)

    # step2 构造请求
    data = io_utils.encode_file(path)
    asr_request = AsrCustomShortRequest(path_audio_format, path_property, data)
    # 所有参数均可不设置，使用默认值
    # 设置是否添加标点，yes or no，默认no
    asr_request.set_add_punc('yes')
    # 设置是否将语音中数字转写为阿拉伯数字，yes or no，默认yes
    asr_request.set_digit_norm('no')
    # step3 发送请求，返回结果,返回结果为json格式
    result = asr_client.get_short_response(asr_request)
    print(json.dumps(result, indent=2, ensure_ascii=False))


if __name__ == '__main__':
    try:
        asrc_short_example()        # 一句话识别
    except ClientException as e:
        print(e)
    except ServerException as e:
        print(e)
```

