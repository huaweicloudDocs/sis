# API概览<a name="sis_03_0005"></a>

SIS服务提供了两种接口，包含REST（Representational State Transfer）API，支持您通过HTTPS请求调用，请参见[表1](#zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_table6550431105030)。也包含WebSocket接口，支持Websocket协议，请参见[表2](#table73356454568)。

**表 1**  REST API功能

<a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_table6550431105030"></a>
<table><thead align="left"><tr id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_row1547110105030"><th class="cellrowborder" valign="top" width="22.434343434343436%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p54101492105030"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p54101492105030"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p54101492105030"></a>接口</p>
</th>
<th class="cellrowborder" valign="top" width="20.989898989898993%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p20144750105030"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p20144750105030"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p20144750105030"></a>功能</p>
</th>
<th class="cellrowborder" valign="top" width="56.57575757575758%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p21112044105030"><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p21112044105030"></a><a name="zh-cn_topic_0171541470_zh-cn_topic_0171174227_zh-cn_topic_0111426203_p21112044105030"></a>API URI</p>
</th>
</tr>
</thead>
<tbody><tr id="row12803578395"><td class="cellrowborder" valign="top" width="22.434343434343436%" headers="mcps1.2.4.1.1 "><p id="p19895172120209"><a name="p19895172120209"></a><a name="p19895172120209"></a>一句话识别接口</p>
</td>
<td class="cellrowborder" valign="top" width="20.989898989898993%" headers="mcps1.2.4.1.2 "><p id="p19132173215202"><a name="p19132173215202"></a><a name="p19132173215202"></a><a href="一句话识别.md">一句话识别</a></p>
</td>
<td class="cellrowborder" valign="top" width="56.57575757575758%" headers="mcps1.2.4.1.3 "><p id="p18737204415208"><a name="p18737204415208"></a><a name="p18737204415208"></a>POST /v1/{project_id}/asr/short-audio</p>
</td>
</tr>
<tr id="row1934564712917"><td class="cellrowborder" valign="top" width="22.434343434343436%" headers="mcps1.2.4.1.1 "><p id="p83461647798"><a name="p83461647798"></a><a name="p83461647798"></a>录音文件识别接</p>
</td>
<td class="cellrowborder" valign="top" width="20.989898989898993%" headers="mcps1.2.4.1.2 "><p id="p1834614711917"><a name="p1834614711917"></a><a name="p1834614711917"></a><a href="录音文件识别接口.md">录音文件识别接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="56.57575757575758%" headers="mcps1.2.4.1.3 "><p id="p11929124560"><a name="p11929124560"></a><a name="p11929124560"></a>识别接口：POST /v1/{project_id}/asr/transcriber/jobs</p>
<p id="p53861570618"><a name="p53861570618"></a><a name="p53861570618"></a>状态查询：GET /v1/{project_id}/asr/transcriber/jobs/{job_id}</p>
</td>
</tr>
<tr id="row1623938145618"><td class="cellrowborder" valign="top" width="22.434343434343436%" headers="mcps1.2.4.1.1 "><p id="p163601747105510"><a name="p163601747105510"></a><a name="p163601747105510"></a>语音合成接口</p>
</td>
<td class="cellrowborder" valign="top" width="20.989898989898993%" headers="mcps1.2.4.1.2 "><p id="p1036004745512"><a name="p1036004745512"></a><a name="p1036004745512"></a><a href="语音合成接口.md">语音合成接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="56.57575757575758%" headers="mcps1.2.4.1.3 "><p id="p193601347135511"><a name="p193601347135511"></a><a name="p193601347135511"></a>POST /v1/{project_id}/tts</p>
</td>
</tr>
</tbody>
</table>

**表 2**  WebSocket API功能

<a name="table73356454568"></a>
<table><thead align="left"><tr id="row73361145195614"><th class="cellrowborder" valign="top" width="22.434343434343436%" id="mcps1.2.4.1.1"><p id="p2033664518568"><a name="p2033664518568"></a><a name="p2033664518568"></a>接口</p>
</th>
<th class="cellrowborder" valign="top" width="28.33333333333334%" id="mcps1.2.4.1.2"><p id="p43362045115619"><a name="p43362045115619"></a><a name="p43362045115619"></a>功能</p>
</th>
<th class="cellrowborder" valign="top" width="49.23232323232323%" id="mcps1.2.4.1.3"><p id="p193361345175612"><a name="p193361345175612"></a><a name="p193361345175612"></a>API URI</p>
</th>
</tr>
</thead>
<tbody><tr id="row1133854513564"><td class="cellrowborder" rowspan="3" valign="top" width="22.434343434343436%" headers="mcps1.2.4.1.1 "><p id="p8338245155612"><a name="p8338245155612"></a><a name="p8338245155612"></a>实时语音识别接口（请求）</p>
</td>
<td class="cellrowborder" valign="top" width="28.33333333333334%" headers="mcps1.2.4.1.2 "><p id="p113386457566"><a name="p113386457566"></a><a name="p113386457566"></a><a href="开始识别.md">开始识别</a></p>
</td>
<td class="cellrowborder" rowspan="3" valign="top" width="49.23232323232323%" headers="mcps1.2.4.1.3 "><p id="p1233834545618"><a name="p1233834545618"></a><a name="p1233834545618"></a>支持三种模式的请求消息：</p>
<a name="ul1233810455563"></a><a name="ul1233810455563"></a><ul id="ul1233810455563"><li><strong id="b8338154510567"><a name="b8338154510567"></a><a name="b8338154510567"></a>流式一句话</strong><p id="p133894517565"><a name="p133894517565"></a><a name="p133894517565"></a><strong id="b1733984565613"><a name="b1733984565613"></a><a name="b1733984565613"></a></strong><span>WSS /v1/{project_id}/rasr/short-stream</span></p>
</li><li><strong id="b433944505612"><a name="b433944505612"></a><a name="b433944505612"></a>实时语音识别连续模式</strong><p id="p1633984505619"><a name="p1633984505619"></a><a name="p1633984505619"></a><span>WSS /v1/{project_id}/rasr/continue-stream</span></p>
</li><li><strong id="b63402045135610"><a name="b63402045135610"></a><a name="b63402045135610"></a>实时语音识别单句模式</strong><p id="p1834084545614"><a name="p1834084545614"></a><a name="p1834084545614"></a><span>WSS /v1/{project_id}/rasr/sentence-stream</span></p>
</li></ul>
</td>
</tr>
<tr id="row2340045105617"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p2340945115620"><a name="p2340945115620"></a><a name="p2340945115620"></a><a href="发送音频数据.md">发送音频数据</a></p>
</td>
</tr>
<tr id="row1634015454565"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12340194545614"><a name="p12340194545614"></a><a name="p12340194545614"></a><a href="结束识别.md">结束识别</a></p>
</td>
</tr>
</tbody>
</table>

