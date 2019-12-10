# 使用语音合成<a name="sis_05_0054"></a>

## 前提条件<a name="section483618911279"></a>

-   确保已按照[配置Python环境](配置Python环境.md)配置完毕，Python SDK仅支持Python3。

## 初始化Client<a name="section35142363486"></a>

初始化TtsClient详见[表 TtsClient初始化参数](#table86254392424)。

**表 1**  TtsClient初始化参数

<a name="table86254392424"></a>
<table><thead align="left"><tr id="row136261939144211"><th class="cellrowborder" valign="top" width="13.08%" id="mcps1.2.5.1.1"><p id="p762663917427"><a name="p762663917427"></a><a name="p762663917427"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="12.21%" id="mcps1.2.5.1.2"><p id="p9626153994217"><a name="p9626153994217"></a><a name="p9626153994217"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.47%" id="mcps1.2.5.1.3"><p id="p1662683913422"><a name="p1662683913422"></a><a name="p1662683913422"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.239999999999995%" id="mcps1.2.5.1.4"><p id="p362633910427"><a name="p362633910427"></a><a name="p362633910427"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row16626939104213"><td class="cellrowborder" valign="top" width="13.08%" headers="mcps1.2.5.1.1 "><p id="p1862615393424"><a name="p1862615393424"></a><a name="p1862615393424"></a>ak</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p962673917423"><a name="p962673917423"></a><a name="p962673917423"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p562643924215"><a name="p562643924215"></a><a name="p562643924215"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.239999999999995%" headers="mcps1.2.5.1.4 "><p id="p96261239104212"><a name="p96261239104212"></a><a name="p96261239104212"></a>用户的ak，可参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row36261639124211"><td class="cellrowborder" valign="top" width="13.08%" headers="mcps1.2.5.1.1 "><p id="p10626113911425"><a name="p10626113911425"></a><a name="p10626113911425"></a>sk</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p106261639204217"><a name="p106261639204217"></a><a name="p106261639204217"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p66262398426"><a name="p66262398426"></a><a name="p66262398426"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.239999999999995%" headers="mcps1.2.5.1.4 "><p id="p10626183915420"><a name="p10626183915420"></a><a name="p10626183915420"></a>用户的sk，可参考<a href="AK-SK认证.md">AK/SK认证</a>。</p>
</td>
</tr>
<tr id="row6626739134210"><td class="cellrowborder" valign="top" width="13.08%" headers="mcps1.2.5.1.1 "><p id="p186261739124217"><a name="p186261739124217"></a><a name="p186261739124217"></a>region</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p1462613994215"><a name="p1462613994215"></a><a name="p1462613994215"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p46265394425"><a name="p46265394425"></a><a name="p46265394425"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.239999999999995%" headers="mcps1.2.5.1.4 "><p id="p96261339124216"><a name="p96261339124216"></a><a name="p96261339124216"></a>区域，如：cn-north-1。具体请参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0004.html" target="_blank" rel="noopener noreferrer">终端节点</a>。</p>
</td>
</tr>
<tr id="row13922135916464"><td class="cellrowborder" valign="top" width="13.08%" headers="mcps1.2.5.1.1 "><p id="p17923155919464"><a name="p17923155919464"></a><a name="p17923155919464"></a>service_endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p29231159194610"><a name="p29231159194610"></a><a name="p29231159194610"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p3923115914616"><a name="p3923115914616"></a><a name="p3923115914616"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.239999999999995%" headers="mcps1.2.5.1.4 "><p id="p169231059124618"><a name="p169231059124618"></a><a name="p169231059124618"></a>终端节点，一般使用默认即可。</p>
</td>
</tr>
<tr id="row18626173974218"><td class="cellrowborder" valign="top" width="13.08%" headers="mcps1.2.5.1.1 "><p id="p1362611392427"><a name="p1362611392427"></a><a name="p1362611392427"></a>sis_config</p>
</td>
<td class="cellrowborder" valign="top" width="12.21%" headers="mcps1.2.5.1.2 "><p id="p66261239174215"><a name="p66261239174215"></a><a name="p66261239174215"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.47%" headers="mcps1.2.5.1.3 "><p id="p562618395429"><a name="p562618395429"></a><a name="p562618395429"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="62.239999999999995%" headers="mcps1.2.5.1.4 "><p id="p136264393421"><a name="p136264393421"></a><a name="p136264393421"></a>详见<a href="#table12745429102316">表 SisConfig数据结构</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 2**  SisConfig数据结构

<a name="table12745429102316"></a>
<table><thead align="left"><tr id="row1974652917235"><th class="cellrowborder" valign="top" width="13.43%" id="mcps1.2.5.1.1"><p id="p2746182992315"><a name="p2746182992315"></a><a name="p2746182992315"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.86%" id="mcps1.2.5.1.2"><p id="p774615294231"><a name="p774615294231"></a><a name="p774615294231"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.120000000000001%" id="mcps1.2.5.1.3"><p id="p9746172912312"><a name="p9746172912312"></a><a name="p9746172912312"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.59%" id="mcps1.2.5.1.4"><p id="p1774672932312"><a name="p1774672932312"></a><a name="p1774672932312"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row174632962316"><td class="cellrowborder" valign="top" width="13.43%" headers="mcps1.2.5.1.1 "><p id="p15746162917234"><a name="p15746162917234"></a><a name="p15746162917234"></a>connect_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="11.86%" headers="mcps1.2.5.1.2 "><p id="p10746112962320"><a name="p10746112962320"></a><a name="p10746112962320"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p874610297239"><a name="p874610297239"></a><a name="p874610297239"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.59%" headers="mcps1.2.5.1.4 "><p id="p17747216152514"><a name="p17747216152514"></a><a name="p17747216152514"></a>连接超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row6746162962312"><td class="cellrowborder" valign="top" width="13.43%" headers="mcps1.2.5.1.1 "><p id="p974652915232"><a name="p974652915232"></a><a name="p974652915232"></a>read_timeout</p>
</td>
<td class="cellrowborder" valign="top" width="11.86%" headers="mcps1.2.5.1.2 "><p id="p274632918233"><a name="p274632918233"></a><a name="p274632918233"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p674619295239"><a name="p674619295239"></a><a name="p674619295239"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.59%" headers="mcps1.2.5.1.4 "><p id="p874652912315"><a name="p874652912315"></a><a name="p874652912315"></a>读取超时，默认10，单位s。</p>
</td>
</tr>
<tr id="row1174616298233"><td class="cellrowborder" valign="top" width="13.43%" headers="mcps1.2.5.1.1 "><p id="p574611293230"><a name="p574611293230"></a><a name="p574611293230"></a>proxy</p>
</td>
<td class="cellrowborder" valign="top" width="11.86%" headers="mcps1.2.5.1.2 "><p id="p10746829162316"><a name="p10746829162316"></a><a name="p10746829162316"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.120000000000001%" headers="mcps1.2.5.1.3 "><p id="p1574613293234"><a name="p1574613293234"></a><a name="p1574613293234"></a>List</p>
</td>
<td class="cellrowborder" valign="top" width="62.59%" headers="mcps1.2.5.1.4 "><p id="p8746529182310"><a name="p8746529182310"></a><a name="p8746529182310"></a>[host, port] 或 [host, port, username, password]。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="section143008206277"></a>

请求类为TtsRequest，详见[表 TtsRequest数据结构](#table45631337366)。

**表 3**  TtsRequest数据结构

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
<tbody><tr id="row356384610110"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p456413461117"><a name="p456413461117"></a><a name="p456413461117"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p1656416461112"><a name="p1656416461112"></a><a name="p1656416461112"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p65645461519"><a name="p65645461519"></a><a name="p65645461519"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p85641646718"><a name="p85641646718"></a><a name="p85641646718"></a>待合成的文本。</p>
</td>
</tr>
<tr id="row95641038369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p67201334112615"><a name="p67201334112615"></a><a name="p67201334112615"></a>sample_rate</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p1263715398423"><a name="p1263715398423"></a><a name="p1263715398423"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p1372043422610"><a name="p1372043422610"></a><a name="p1372043422610"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p5720193412613"><a name="p5720193412613"></a><a name="p5720193412613"></a>采样率，支持8k/16k。 默认8k。</p>
</td>
</tr>
<tr id="row65644313369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p5720134152612"><a name="p5720134152612"></a><a name="p5720134152612"></a>voice_name</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p1963314399425"><a name="p1963314399425"></a><a name="p1963314399425"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p11720173422614"><a name="p11720173422614"></a><a name="p11720173422614"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1972093419268"><a name="p1972093419268"></a><a name="p1972093419268"></a>发声人，支持xiaoyu，xiaoqi，xiaoyan，三个发声人，默认选择xiaoyan。</p>
</td>
</tr>
<tr id="row65653319364"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p3720173432620"><a name="p3720173432620"></a><a name="p3720173432620"></a>pitch_rate</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p12631133918427"><a name="p12631133918427"></a><a name="p12631133918427"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p15720103413267"><a name="p15720103413267"></a><a name="p15720103413267"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p6720163419261"><a name="p6720163419261"></a><a name="p6720163419261"></a>音高，[-500,500]，默认0。</p>
</td>
</tr>
<tr id="row15558172874017"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p27219345269"><a name="p27219345269"></a><a name="p27219345269"></a>speech_speed</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p8629339144220"><a name="p8629339144220"></a><a name="p8629339144220"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p16721103432615"><a name="p16721103432615"></a><a name="p16721103432615"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p3721133410266"><a name="p3721133410266"></a><a name="p3721133410266"></a>语速，[-500,500]，默认0。</p>
</td>
</tr>
<tr id="row266453364019"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p172117347261"><a name="p172117347261"></a><a name="p172117347261"></a>volume</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p15626193920422"><a name="p15626193920422"></a><a name="p15626193920422"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p19721173410263"><a name="p19721173410263"></a><a name="p19721173410263"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1872153412616"><a name="p1872153412616"></a><a name="p1872153412616"></a>音量，[-20,20]，默认0。</p>
</td>
</tr>
<tr id="row1550125319412"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p157211134152618"><a name="p157211134152618"></a><a name="p157211134152618"></a>saved</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p4550175317411"><a name="p4550175317411"></a><a name="p4550175317411"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p6721234192619"><a name="p6721234192619"></a><a name="p6721234192619"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p172123419261"><a name="p172123419261"></a><a name="p172123419261"></a>合成音频是否保存为本地音频文件,目前仅支持合成wav格式音频文件, 默认False。</p>
</td>
</tr>
<tr id="row1095415592413"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p147215349268"><a name="p147215349268"></a><a name="p147215349268"></a>saved_path</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p7954175914419"><a name="p7954175914419"></a><a name="p7954175914419"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p17211234172613"><a name="p17211234172613"></a><a name="p17211234172613"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p4721234102611"><a name="p4721234102611"></a><a name="p4721234102611"></a>设置合成的音频文件保存路径。</p>
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
<td class="cellrowborder" valign="top" width="62.17%" headers="mcps1.2.5.1.4 "><p id="p63211850162511"><a name="p63211850162511"></a><a name="p63211850162511"></a>合成后生成的语音数据，以Base64编码格式返回。用户如需生成音频，需要将Base64编码解码成byte数组，再保存为wav音频。</p>
<div class="note" id="note1732245092519"><a name="note1732245092519"></a><a name="note1732245092519"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p2322135015259"><a name="p2322135015259"></a><a name="p2322135015259"></a>语音数据输出的格式为wav格式。</p>
</div></div>
</td>
</tr>
</tbody>
</table>

## 代码示例<a name="section338116313271"></a>

```
# -*- coding: utf-8 -*-

from huaweicloud_sis.client.tts_client import TtsClient
from huaweicloud_sis.bean.tts_request import TtsRequest
from huaweicloud_sis.bean.sis_config import SisConfig
from huaweicloud_sis.exception.exceptions import ClientException
from huaweicloud_sis.exception.exceptions import ServerException
import json


def tts_example():
    """ 语音合成demo """
    ak = ''         # 参考https://support.huaweicloud.com/sdkreference-sis/sis_05_0003.html
    sk = ''         # 参考https://support.huaweicloud.com/sdkreference-sis/sis_05_0003.html
    region = ''     # region，如cn-north-1
    text = ''       # 待合成文本，不超过500字
    path = ''       # 保存路径，可在设置中选择不保存本地

    # step1 初始化客户端
    config = SisConfig()
    config.set_connect_timeout(5)       # 设置连接超时
    config.set_read_timeout(10)         # 设置读取超时
    # 设置代理，使用代理前一定要确保代理可用。 代理格式可为[host, port] 或 [host, port, username, password]
    # config.set_proxy(proxy)
    tts_client = TtsClient(ak, sk, region, sis_config=config)

    # step2 构造请求
    tts_request = TtsRequest(text)
    # 设置请求，所有参数均可不设置，使用默认参数
    # 设置发声人，默认xiaoyan，可参考api文档
    tts_request.set_voice_name('xiaoyan')
    # 设置采样率，默认8k
    tts_request.set_sample_rate('8k')
    # 设置音量，[-20, 20]，默认0
    tts_request.set_volume(0)
    # 设置音高, [-500, 500], 默认0
    tts_request.set_pitch_rate(0)
    # 设置音速, [-500, 500], 默认0
    tts_request.set_speech_speed(0)
    # 设置是否保存，默认False
    tts_request.set_saved(True)
    # 设置保存路径，只有设置保存，此参数才生效
    tts_request.set_saved_path(path)

    # step3 发送请求，返回结果,格式为json. 如果设置保存，可在指定路径里查看保存的音频
    result = tts_client.get_tts_response(tts_request)
    print(json.dumps(result, indent=2, ensure_ascii=False))


if __name__ == '__main__':
    try:
        tts_example()
    except ClientException as e:
        print(e)
    except ServerException as e:
        print(e)

```

