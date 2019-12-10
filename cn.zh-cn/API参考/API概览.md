# API概览<a name="sis_03_0005"></a>

SIS提供的接口为符合RESTful API设计规范的自研接口。通过SIS的自研接口，您可以使用SIS的如[表 接口功能](#zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_table6550431105030)所示的功能。

**表 1**  接口功能

<a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_table6550431105030"></a>
<table><thead align="left"><tr id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_row1547110105030"><th class="cellrowborder" valign="top" width="22.222222222222225%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p54101492105030"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p54101492105030"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p54101492105030"></a>接口</p>
</th>
<th class="cellrowborder" valign="top" width="28.282828282828287%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p20144750105030"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p20144750105030"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p20144750105030"></a>功能</p>
</th>
<th class="cellrowborder" valign="top" width="49.494949494949495%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p21112044105030"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p21112044105030"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p21112044105030"></a>API URI</p>
</th>
</tr>
</thead>
<tbody><tr id="row12803578395"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.4.1.1 "><p id="p19895172120209"><a name="p19895172120209"></a><a name="p19895172120209"></a>定制语音识别接口（一句话识别）</p>
</td>
<td class="cellrowborder" valign="top" width="28.282828282828287%" headers="mcps1.2.4.1.2 "><p id="p19132173215202"><a name="p19132173215202"></a><a name="p19132173215202"></a><a href="一句话识别.md">一句话识别</a></p>
</td>
<td class="cellrowborder" valign="top" width="49.494949494949495%" headers="mcps1.2.4.1.3 "><p id="p18737204415208"><a name="p18737204415208"></a><a name="p18737204415208"></a>POST /v1/{project_id}/asr/short-audio</p>
</td>
</tr>
<tr id="row1934564712917"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.4.1.1 "><p id="p83461647798"><a name="p83461647798"></a><a name="p83461647798"></a>定制语音识别接口（录音文件识别）</p>
</td>
<td class="cellrowborder" valign="top" width="28.282828282828287%" headers="mcps1.2.4.1.2 "><p id="p1834614711917"><a name="p1834614711917"></a><a name="p1834614711917"></a><a href="录音文件识别接口.md">录音文件识别接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="49.494949494949495%" headers="mcps1.2.4.1.3 "><p id="p1834610471091"><a name="p1834610471091"></a><a name="p1834610471091"></a>识别接口：POST /v1/{project_id}/asr/transcriber/jobs</p>
<p id="p14393155741015"><a name="p14393155741015"></a><a name="p14393155741015"></a>状态查询：GET /v1/{project_id}/asr/transcriber/jobs/{job_id}</p>
</td>
</tr>
<tr id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_row55790672105030"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p19630156303"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p19630156303"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p19630156303"></a>短语音识别接口</p>
</td>
<td class="cellrowborder" valign="top" width="28.282828282828287%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p30859977105030"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p30859977105030"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p30859977105030"></a><a href="短语音识别-父.md">短语音识别接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="49.494949494949495%" headers="mcps1.2.4.1.3 "><p id="p072981420219"><a name="p072981420219"></a><a name="p072981420219"></a>POST /v1.0/voice/asr/sentence</p>
</td>
</tr>
<tr id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_row3325121711183"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p1632551711184"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p1632551711184"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p1632551711184"></a>语音合成接口</p>
</td>
<td class="cellrowborder" valign="top" width="28.282828282828287%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p13325417181816"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p13325417181816"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p13325417181816"></a><a href="语音合成.md">语音合成</a></p>
</td>
<td class="cellrowborder" valign="top" width="49.494949494949495%" headers="mcps1.2.4.1.3 "><p id="p380712817228"><a name="p380712817228"></a><a name="p380712817228"></a>POST /v1.0/voice/tts</p>
</td>
</tr>
<tr id="row1623938145618"><td class="cellrowborder" valign="top" width="22.222222222222225%" headers="mcps1.2.4.1.1 "><p id="p163601747105510"><a name="p163601747105510"></a><a name="p163601747105510"></a>定制语音合成接口</p>
</td>
<td class="cellrowborder" valign="top" width="28.282828282828287%" headers="mcps1.2.4.1.2 "><p id="p1036004745512"><a name="p1036004745512"></a><a name="p1036004745512"></a><a href="定制语音合成接口.md">定制语音合成接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="49.494949494949495%" headers="mcps1.2.4.1.3 "><p id="p193601347135511"><a name="p193601347135511"></a><a name="p193601347135511"></a>POST /v1/{project_id}/tts</p>
</td>
</tr>
<tr id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_row7746927402"><td class="cellrowborder" rowspan="3" valign="top" width="22.222222222222225%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p81010371807"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p81010371807"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p81010371807"></a>实时语音转写接口（请求）</p>
</td>
<td class="cellrowborder" valign="top" width="28.282828282828287%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p774752714011"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p774752714011"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p774752714011"></a><a href="开始识别.md">开始识别</a></p>
</td>
<td class="cellrowborder" rowspan="3" valign="top" width="49.494949494949495%" headers="mcps1.2.4.1.3 "><p id="p1527373117157"><a name="p1527373117157"></a><a name="p1527373117157"></a>支持三种模式的请求消息：</p>
<a name="ul1642125455817"></a><a name="ul1642125455817"></a><ul id="ul1642125455817"><li><strong id="b758318315585"><a name="b758318315585"></a><a name="b758318315585"></a>流式一句话</strong><p id="p129314551279"><a name="p129314551279"></a><a name="p129314551279"></a><strong id="b95813319586"><a name="b95813319586"></a><a name="b95813319586"></a></strong>WSS /v1/{project_id}/rasr/short-stream</p>
</li><li><strong id="b728594013586"><a name="b728594013586"></a><a name="b728594013586"></a>实时语音转写连续模式</strong><p id="p42932551175"><a name="p42932551175"></a><a name="p42932551175"></a>WSS /v1/{project_id}/rasr/continue-stream</p>
</li><li><strong id="b42301946165812"><a name="b42301946165812"></a><a name="b42301946165812"></a>实时语音转写单句模式</strong><p id="p18293155871"><a name="p18293155871"></a><a name="p18293155871"></a>WSS /v1/{project_id}/rasr/sentence-stream</p>
</li></ul>
</td>
</tr>
<tr id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_row177472271011"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p6747227807"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p6747227807"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p6747227807"></a><a href="发送音频数据.md">发送音频数据</a></p>
</td>
</tr>
<tr id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_row1774715273011"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p177478271014"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p177478271014"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_p177478271014"></a><a href="结束识别.md">结束识别</a></p>
</td>
</tr>
<tr id="row22724315154"><td class="cellrowborder" rowspan="6" valign="top" width="22.222222222222225%" headers="mcps1.2.4.1.1 "><p id="p17272931101518"><a name="p17272931101518"></a><a name="p17272931101518"></a>实时语音转写接口（响应）</p>
</td>
<td class="cellrowborder" valign="top" width="28.282828282828287%" headers="mcps1.2.4.1.2 "><p id="p1273631171512"><a name="p1273631171512"></a><a name="p1273631171512"></a><a href="开始识别请求响应.md">开始识别请求响应</a></p>
</td>
<td class="cellrowborder" rowspan="6" valign="top" width="49.494949494949495%" headers="mcps1.2.4.1.3 "><p id="p6231839112712"><a name="p6231839112712"></a><a name="p6231839112712"></a>-</p>
</td>
</tr>
<tr id="row327353116155"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1827312314151"><a name="p1827312314151"></a><a name="p1827312314151"></a><a href="事件响应.md">事件响应</a></p>
</td>
</tr>
<tr id="row62731431181519"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12273173171511"><a name="p12273173171511"></a><a name="p12273173171511"></a><a href="识别结果响应.md">识别结果响应</a></p>
</td>
</tr>
<tr id="row106572821716"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1465748151713"><a name="p1465748151713"></a><a name="p1465748151713"></a><a href="错误响应.md">错误响应</a></p>
</td>
</tr>
<tr id="row166570881717"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p166570881716"><a name="p166570881716"></a><a name="p166570881716"></a><a href="严重错误响应.md">严重错误响应</a></p>
</td>
</tr>
<tr id="row1040410323184"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1440412329189"><a name="p1440412329189"></a><a name="p1440412329189"></a><a href="结束识别请求响应.md">结束识别请求响应</a></p>
</td>
</tr>
</tbody>
</table>

