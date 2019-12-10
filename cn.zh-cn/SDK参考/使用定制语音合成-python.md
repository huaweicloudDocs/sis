# 使用定制语音合成<a name="sis_05_0055"></a>

## 前提条件<a name="section483618911279"></a>

-   确保已按照[配置Python环境](配置Python环境.md)配置完毕，Python SDK仅支持Python3。

## 初始化Client<a name="section590271313272"></a>

初始化TtsCustomizationClient详见[表 TtsCustomizationClient初始化参数](#table86254392424)。

**表 1**  TtsCustomizationClient初始化参数

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
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p96261339124216"><a name="p96261339124216"></a><a name="p96261339124216"></a>区域，如：cn-north-1。具体请参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0004.html" target="_blank" rel="noopener noreferrer">终端节点</a>。</p>
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
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p136264393421"><a name="p136264393421"></a><a name="p136264393421"></a>详见<a href="#table12745429102316">表 SisConfig数据结构</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  SisConfig数据结构

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
<td class="cellrowborder" valign="top" width="12.73%" headers="mcps1.2.5.1.3 "><p id="p874610297239"><a name="p874610297239"></a><a name="p874610297239"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.6%" headers="mcps1.2.5.1.4 "><p id="p17747216152514"><a name="p17747216152514"></a><a name="p17747216152514"></a>连接超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row6746162962312"><td class="cellrowborder" valign="top" width="13.86%" headers="mcps1.2.5.1.1 "><p id="p974652915232"><a name="p974652915232"></a><a name="p974652915232"></a>read_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="10.81%" headers="mcps1.2.5.1.2 "><p id="p274632918233"><a name="p274632918233"></a><a name="p274632918233"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.73%" headers="mcps1.2.5.1.3 "><p id="p674619295239"><a name="p674619295239"></a><a name="p674619295239"></a>String</p>
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

请求类为TtsCustomRequest，详见[表 TtsCustomRequest数据结构](#table45631337366)。

**表 3**  TtsCustomRequest数据结构

<a name="table45631337366"></a>
<table><thead align="left"><tr id="row195631236363"><th class="cellrowborder" valign="top" width="13.950000000000001%" id="mcps1.2.5.1.1"><p id="p55640373620"><a name="p55640373620"></a><a name="p55640373620"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.16%" id="mcps1.2.5.1.2"><p id="p1456420383614"><a name="p1456420383614"></a><a name="p1456420383614"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.9%" id="mcps1.2.5.1.3"><p id="p1056412313618"><a name="p1056412313618"></a><a name="p1056412313618"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p1856419353613"><a name="p1856419353613"></a><a name="p1856419353613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row95641038369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p174328142585"><a name="p174328142585"></a><a name="p174328142585"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p0431131415582"><a name="p0431131415582"></a><a name="p0431131415582"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p1430181435815"><a name="p1430181435815"></a><a name="p1430181435815"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1942912148588"><a name="p1942912148588"></a><a name="p1942912148588"></a>待合成的文本。</p>
</td>
</tr>
<tr id="row65644313369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p11536135185115"><a name="p11536135185115"></a><a name="p11536135185115"></a>audio_format</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p1263715398423"><a name="p1263715398423"></a><a name="p1263715398423"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p165351335175117"><a name="p165351335175117"></a><a name="p165351335175117"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1153412355518"><a name="p1153412355518"></a><a name="p1153412355518"></a>待合成的音频格式，可选mp3，wav等，默认wav。具体信息请参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0111.html" target="_blank" rel="noopener noreferrer">定制语音合成</a>章节。</p>
</td>
</tr>
<tr id="row65653319364"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p199259321542"><a name="p199259321542"></a><a name="p199259321542"></a>pitch</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p1963314399425"><a name="p1963314399425"></a><a name="p1963314399425"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p1153183517514"><a name="p1153183517514"></a><a name="p1153183517514"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p14530123519513"><a name="p14530123519513"></a><a name="p14530123519513"></a>音高，[-500,500] ，默认是0。</p>
</td>
</tr>
<tr id="row15558172874017"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p1523795385511"><a name="p1523795385511"></a><a name="p1523795385511"></a>speed</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p12631133918427"><a name="p12631133918427"></a><a name="p12631133918427"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p142377539558"><a name="p142377539558"></a><a name="p142377539558"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p923745365514"><a name="p923745365514"></a><a name="p923745365514"></a>语速，[-500,500] ，默认是0。</p>
</td>
</tr>
<tr id="row239612152010"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p84871611141511"><a name="p84871611141511"></a><a name="p84871611141511"></a>volume</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p8629339144220"><a name="p8629339144220"></a><a name="p8629339144220"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p348791181517"><a name="p348791181517"></a><a name="p348791181517"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p18487201118151"><a name="p18487201118151"></a><a name="p18487201118151"></a>音量，[0,100]，默认是50。</p>
</td>
</tr>
<tr id="row1090619812016"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p6794613191711"><a name="p6794613191711"></a><a name="p6794613191711"></a>sample_rate</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p15626193920422"><a name="p15626193920422"></a><a name="p15626193920422"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p3794113191717"><a name="p3794113191717"></a><a name="p3794113191717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p679461301710"><a name="p679461301710"></a><a name="p679461301710"></a>采样率，支持“8000”、“16000”，默认“8000”。</p>
</td>
</tr>
<tr id="row146285401"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p17403201921710"><a name="p17403201921710"></a><a name="p17403201921710"></a>model_property</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p4550175317411"><a name="p4550175317411"></a><a name="p4550175317411"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p54031819131718"><a name="p54031819131718"></a><a name="p54031819131718"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1340315192174"><a name="p1340315192174"></a><a name="p1340315192174"></a>特征字符串，{language}_{speaker}_{domain}，默认chinese_xiaoyan_common。具体信息请参见《API参考》中<a href="https://support.huaweicloud.com/api-sis/sis_03_0111.html" target="_blank" rel="noopener noreferrer">定制语音合成</a>章节。</p>
</td>
</tr>
<tr id="row1177211709"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p33920236179"><a name="p33920236179"></a><a name="p33920236179"></a>saved</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p7954175914419"><a name="p7954175914419"></a><a name="p7954175914419"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p176237269197"><a name="p176237269197"></a><a name="p176237269197"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1139102361718"><a name="p1139102361718"></a><a name="p1139102361718"></a>是否选择合成的音频数据保存到本地，默认不保存。</p>
</td>
</tr>
<tr id="row266453364019"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p1980305313192"><a name="p1980305313192"></a><a name="p1980305313192"></a>saved_path</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p481436411"><a name="p481436411"></a><a name="p481436411"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p15803105361912"><a name="p15803105361912"></a><a name="p15803105361912"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p19803753101913"><a name="p19803753101913"></a><a name="p19803753101913"></a>选择保存到本地的路径。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section2581112416279"></a>

Python SDK响应结果为Json格式，详见[表 响应结果数据结构](#zh-cn_topic_0097232662_t8e502a083db5405898a82a44a49d25ec)。

**表 4**  响应结果数据结构

<a name="zh-cn_topic_0097232662_t8e502a083db5405898a82a44a49d25ec"></a>
<table><thead align="left"><tr id="zh-cn_topic_0097232662_r4e9743131010456a8ea55bfa0696b4bc"><th class="cellrowborder" valign="top" width="13.950000000000001%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0097232662_af25b5162d355432ca1e1858524349d7c"><a name="zh-cn_topic_0097232662_af25b5162d355432ca1e1858524349d7c"></a><a name="zh-cn_topic_0097232662_af25b5162d355432ca1e1858524349d7c"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.11%" id="mcps1.2.5.1.2"><p id="p638372052517"><a name="p638372052517"></a><a name="p638372052517"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.25%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0097232662_aa09c864dfa2f4def9c0288179c55e08e"><a name="zh-cn_topic_0097232662_aa09c864dfa2f4def9c0288179c55e08e"></a><a name="zh-cn_topic_0097232662_aa09c864dfa2f4def9c0288179c55e08e"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.69%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0097232662_a13a080ffac1a4cd1bd2d6543398f7b46"><a name="zh-cn_topic_0097232662_a13a080ffac1a4cd1bd2d6543398f7b46"></a><a name="zh-cn_topic_0097232662_a13a080ffac1a4cd1bd2d6543398f7b46"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0097232662_r600fd27821ac4517abd52e4342e55383"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0097232662_a0417d08c87c548309f0a2e6ef7885f64"><a name="zh-cn_topic_0097232662_a0417d08c87c548309f0a2e6ef7885f64"></a><a name="zh-cn_topic_0097232662_a0417d08c87c548309f0a2e6ef7885f64"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p17383520162514"><a name="p17383520162514"></a><a name="p17383520162514"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.25%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p784395517545"><a name="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p784395517545"></a><a name="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p784395517545"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p984385515416"><a name="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p984385515416"></a><a name="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p984385515416"></a>调用成功时为合成语音内容，请参考<a href="#table998164710258">表 result数据结构</a>。</p>
</td>
</tr>
<tr id="row6625238114410"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p7626173844418"><a name="p7626173844418"></a><a name="p7626173844418"></a>trace_id</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p1062613385448"><a name="p1062613385448"></a><a name="p1062613385448"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.25%" headers="mcps1.2.5.1.3 "><p id="p1362653844418"><a name="p1362653844418"></a><a name="p1362653844418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="p14708184215720"><a name="p14708184215720"></a><a name="p14708184215720"></a>用于后台日志问题追溯。</p>
</td>
</tr>
<tr id="zh-cn_topic_0097232662_r0b3635c29062414a8f25daa5776ff0b4"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0097232662_a9b879241c7874ed78d27d3b8dc6d6834"><a name="zh-cn_topic_0097232662_a9b879241c7874ed78d27d3b8dc6d6834"></a><a name="zh-cn_topic_0097232662_a9b879241c7874ed78d27d3b8dc6d6834"></a>is_saved</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p5383132016256"><a name="p5383132016256"></a><a name="p5383132016256"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.25%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0097232662_a5f7eb1bbc9854a1fb29cc78cfb848589"><a name="zh-cn_topic_0097232662_a5f7eb1bbc9854a1fb29cc78cfb848589"></a><a name="zh-cn_topic_0097232662_a5f7eb1bbc9854a1fb29cc78cfb848589"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0097232662_p1765688919540"><a name="zh-cn_topic_0097232662_p1765688919540"></a><a name="zh-cn_topic_0097232662_p1765688919540"></a>是否保存为本地音频。</p>
</td>
</tr>
<tr id="zh-cn_topic_0097232662_rcfa3fb30dc8044aa84943fa7605471bf"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p212419716554"><a name="p212419716554"></a><a name="p212419716554"></a>saved_path</p>
</td>
<td class="cellrowborder" valign="top" width="10.11%" headers="mcps1.2.5.1.2 "><p id="p938312202251"><a name="p938312202251"></a><a name="p938312202251"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="13.25%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p188443551548"><a name="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p188443551548"></a><a name="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p188443551548"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.69%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p684415559546"><a name="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p684415559546"></a><a name="zh-cn_topic_0097232662_zh-cn_topic_0072646061_p684415559546"></a>保存音频的本地路径，只有在请求时saved参数设置为true才生效。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  result数据结构

<a name="table998164710258"></a>
<table><thead align="left"><tr id="row11982174782511"><th class="cellrowborder" valign="top" width="14.12%" id="mcps1.2.5.1.1"><p id="p0223175782511"><a name="p0223175782511"></a><a name="p0223175782511"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.459999999999999%" id="mcps1.2.5.1.2"><p id="p162231573251"><a name="p162231573251"></a><a name="p162231573251"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="13.25%" id="mcps1.2.5.1.3"><p id="p112230573255"><a name="p112230573255"></a><a name="p112230573255"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.17%" id="mcps1.2.5.1.4"><p id="p192231357182517"><a name="p192231357182517"></a><a name="p192231357182517"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row798294720252"><td class="cellrowborder" valign="top" width="14.12%" headers="mcps1.2.5.1.1 "><p id="p2032115502254"><a name="p2032115502254"></a><a name="p2032115502254"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="10.459999999999999%" headers="mcps1.2.5.1.2 "><p id="p23211350112517"><a name="p23211350112517"></a><a name="p23211350112517"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="13.25%" headers="mcps1.2.5.1.3 "><p id="p113211650112514"><a name="p113211650112514"></a><a name="p113211650112514"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.17%" headers="mcps1.2.5.1.4 "><p id="p63211850162511"><a name="p63211850162511"></a><a name="p63211850162511"></a>合成后生成的语音数据，以Base64编码格式返回。</p>
</td>
</tr>
</tbody>
</table>

## 代码示例<a name="section338116313271"></a>

```
# -*- coding: utf-8 -*-

from huaweicloud_sis.client.tts_client import TtsCustomizationClient
from huaweicloud_sis.bean.tts_request import TtsCustomRequest
from huaweicloud_sis.bean.sis_config import SisConfig
from huaweicloud_sis.exception.exceptions import ClientException
from huaweicloud_sis.exception.exceptions import ServerException
import json


def ttsc_example():
    """ 定制语音合成demo """
    ak = ''             # 参考https://support.huaweicloud.com/sdkreference-sis/sis_05_0003.html
    sk = ''             # 参考https://support.huaweicloud.com/sdkreference-sis/sis_05_0003.html
    region = ''         # region，如cn-north-4
    project_id = ''     # 同region一一对应，参考https://support.huaweicloud.com/api-sis/sis_03_0008.html
    text = ''           # 待合成文本，不超过500字
    path = ''           # 保存路径，可在设置中选择不保存本地

    # step1 初始化客户端
    config = SisConfig()
    config.set_connect_timeout(5)       # 设置连接超时，单位s
    config.set_read_timeout(10)         # 设置读取超时，单位s
    # 设置代理，使用代理前一定要确保代理可用。 代理格式可为[host, port] 或 [host, port, username, password]
    # config.set_proxy(proxy)
    ttsc_client = TtsCustomizationClient(ak, sk, region, project_id, sis_config=config)

    # step2 构造请求
    ttsc_request = TtsCustomRequest(text)
    # 设置请求，所有参数均可不设置，使用默认参数
    # 设置属性字符串， language_speaker_domain, 默认chinese_xiaoyan_common, 参考api文档
    ttsc_request.set_property('chinese_xiaoyan_common')
    # 设置音频格式，默认wav，可选mp3和pcm
    ttsc_request.set_audio_format('wav')
    # 设置采样率，8000 or 16000, 默认8000
    ttsc_request.set_sample_rate('8000')
    # 设置音量，[0, 100]，默认50
    ttsc_request.set_volume(50)
    # 设置音高, [-500, 500], 默认0
    ttsc_request.set_pitch(0)
    # 设置音速, [-500, 500], 默认0
    ttsc_request.set_speed(0)
    # 设置是否保存，默认False
    ttsc_request.set_saved(True)
    # 设置保存路径，只有设置保存，此参数才生效
    ttsc_request.set_saved_path(path)

    # step3 发送请求，返回结果。如果设置保存，可在指定路径里查看保存的音频。
    result = ttsc_client.get_ttsc_response(ttsc_request)
    print(json.dumps(result, indent=2, ensure_ascii=False))


if __name__ == '__main__':
    try:
        ttsc_example()
    except ClientException as e:
        print(e)
    except ServerException as e:
        print(e)

```

