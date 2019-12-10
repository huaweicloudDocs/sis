# SDK简介<a name="sis_05_0001"></a>

## 语音交互概述<a name="section1582503120018"></a>

语音交互是一种人机交互方式，以开放API（Application Programming Interface，应用程序编程接口）的方式提供给用户，用户通过实时访问和调用API获取语音交互结果。

## SDK概述<a name="section191232404117"></a>

语音交互目前支持Java SDK、Python SDK。

通过对语音交互提供的REST API进行的封装，以简化用户的开发工作。用户直接调用语音交互SDK提供的接口函数即可实现使用语音交互业务能力的目的。

## Java接口与API对应关系<a name="section121947299416"></a>

Java接口与API对应关系请参见[表 Java接口与API对应关系表](#table1449262611219)。

**表 1**  Java接口与API对应关系表

<a name="table1449262611219"></a>
<table><thead align="left"><tr id="row14493202614219"><th class="cellrowborder" valign="top" width="26.332633263326333%" id="mcps1.2.4.1.1"><p id="p4493102610215"><a name="p4493102610215"></a><a name="p4493102610215"></a>Class</p>
</th>
<th class="cellrowborder" valign="top" width="40.33403340334033%" id="mcps1.2.4.1.2"><p id="p1249318269217"><a name="p1249318269217"></a><a name="p1249318269217"></a>Method</p>
</th>
<th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p174938261923"><a name="p174938261923"></a><a name="p174938261923"></a>API</p>
</th>
</tr>
</thead>
<tbody><tr id="row1949372610219"><td class="cellrowborder" valign="top" width="26.332633263326333%" headers="mcps1.2.4.1.1 "><p id="p184931261227"><a name="p184931261227"></a><a name="p184931261227"></a>AsrClient</p>
</td>
<td class="cellrowborder" valign="top" width="40.33403340334033%" headers="mcps1.2.4.1.2 "><p id="p8493192617216"><a name="p8493192617216"></a><a name="p8493192617216"></a>AsrResponse getAsrShortResponse(AsrShortRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p104931226521"><a name="p104931226521"></a><a name="p104931226521"></a>POST /v1.0/voice/asr/sentence</p>
</td>
</tr>
<tr id="row049411268212"><td class="cellrowborder" valign="top" width="26.332633263326333%" headers="mcps1.2.4.1.1 "><p id="p154947261022"><a name="p154947261022"></a><a name="p154947261022"></a>TtsClient</p>
</td>
<td class="cellrowborder" valign="top" width="40.33403340334033%" headers="mcps1.2.4.1.2 "><p id="p114941260215"><a name="p114941260215"></a><a name="p114941260215"></a>TtsResponse getTtsResponse(TtsRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p549416266219"><a name="p549416266219"></a><a name="p549416266219"></a>POST /v1.0/voice/tts</p>
</td>
</tr>
<tr id="row796411276149"><td class="cellrowborder" rowspan="3" valign="top" width="26.332633263326333%" headers="mcps1.2.4.1.1 "><p id="p20721745201414"><a name="p20721745201414"></a><a name="p20721745201414"></a>RasrClient</p>
</td>
<td class="cellrowborder" valign="top" width="40.33403340334033%" headers="mcps1.2.4.1.2 "><p id="p480341181516"><a name="p480341181516"></a><a name="p480341181516"></a>void continueStreamConnect(RasrRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p158032112157"><a name="p158032112157"></a><a name="p158032112157"></a>wss://{endpoint}/v1/{project_id}/rasr/continue-stream</p>
</td>
</tr>
<tr id="row14145134917131"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p84091812111518"><a name="p84091812111518"></a><a name="p84091812111518"></a>void shortStreamConnect(RasrRequest request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p24099126155"><a name="p24099126155"></a><a name="p24099126155"></a>wss://{endpoint}/v1/{project_id}/rasr/short-stream</p>
</td>
</tr>
<tr id="row473992417142"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p741712205151"><a name="p741712205151"></a><a name="p741712205151"></a>void sentenceStreamConnect(RasrRequest request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p14417192011156"><a name="p14417192011156"></a><a name="p14417192011156"></a>wss://{endpoint}/v1/{project_id}/rasr/sentence-stream</p>
</td>
</tr>
<tr id="row824474171718"><td class="cellrowborder" rowspan="3" valign="top" width="26.332633263326333%" headers="mcps1.2.4.1.1 "><p id="p142445419174"><a name="p142445419174"></a><a name="p142445419174"></a>AsrCustomizationClient</p>
</td>
<td class="cellrowborder" valign="top" width="40.33403340334033%" headers="mcps1.2.4.1.2 "><p id="p32441643170"><a name="p32441643170"></a><a name="p32441643170"></a>AsrCustomShortResponse getAsrShortResponse(AsrCustomShortRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p84761113191812"><a name="p84761113191812"></a><a name="p84761113191812"></a>POST /v1/{project_id}/asr/short-audio</p>
</td>
</tr>
<tr id="row12557315192014"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1355731562010"><a name="p1355731562010"></a><a name="p1355731562010"></a>String submitJob(AsrCustomLongRequest request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p757716489270"><a name="p757716489270"></a><a name="p757716489270"></a>POST /v1/{project_id}/asr/transcriber/jobs</p>
</td>
</tr>
<tr id="row1518153214216"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1551843212216"><a name="p1551843212216"></a><a name="p1551843212216"></a>AsrCustomLongResponse getAsrLongResponse(String jobId)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p17688728102819"><a name="p17688728102819"></a><a name="p17688728102819"></a>GET /v1/{project_id}/asr/transcriber/jobs/{job_id}</p>
</td>
</tr>
<tr id="row437945315137"><td class="cellrowborder" valign="top" width="26.332633263326333%" headers="mcps1.2.4.1.1 "><p id="p1037975315133"><a name="p1037975315133"></a><a name="p1037975315133"></a>TtsCustomizationClient</p>
</td>
<td class="cellrowborder" valign="top" width="40.33403340334033%" headers="mcps1.2.4.1.2 "><p id="p937965311131"><a name="p937965311131"></a><a name="p937965311131"></a>TtsCustomResponse getTtsResponse(TtsCustomRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p12380453161318"><a name="p12380453161318"></a><a name="p12380453161318"></a>POST  /v1/{project_id}/tts</p>
</td>
</tr>
</tbody>
</table>

## Python接口与API对应关系<a name="section129019441941"></a>

Python接口与API对应关系请参见[表 Python接口与API对应关系表](#table67851461051)。

**表 2**  Python接口与API对应关系表

<a name="table67851461051"></a>
<table><thead align="left"><tr id="row57862461753"><th class="cellrowborder" valign="top" width="23.632363236323634%" id="mcps1.2.4.1.1"><p id="p167863466514"><a name="p167863466514"></a><a name="p167863466514"></a>Class</p>
</th>
<th class="cellrowborder" valign="top" width="34.26342634263426%" id="mcps1.2.4.1.2"><p id="p978664618513"><a name="p978664618513"></a><a name="p978664618513"></a>Method</p>
</th>
<th class="cellrowborder" valign="top" width="42.104210421042104%" id="mcps1.2.4.1.3"><p id="p1978616461859"><a name="p1978616461859"></a><a name="p1978616461859"></a>API</p>
</th>
</tr>
</thead>
<tbody><tr id="row1878664610518"><td class="cellrowborder" valign="top" width="23.632363236323634%" headers="mcps1.2.4.1.1 "><p id="p278617462518"><a name="p278617462518"></a><a name="p278617462518"></a>AsrClient</p>
</td>
<td class="cellrowborder" valign="top" width="34.26342634263426%" headers="mcps1.2.4.1.2 "><p id="p1378634617510"><a name="p1378634617510"></a><a name="p1378634617510"></a>get_asr_response(request)</p>
</td>
<td class="cellrowborder" valign="top" width="42.104210421042104%" headers="mcps1.2.4.1.3 "><p id="p1378618469518"><a name="p1378618469518"></a><a name="p1378618469518"></a>POST /v1.0/voice/asr/sentence</p>
</td>
</tr>
<tr id="row8786104612514"><td class="cellrowborder" valign="top" width="23.632363236323634%" headers="mcps1.2.4.1.1 "><p id="p19786846354"><a name="p19786846354"></a><a name="p19786846354"></a>TtsClient</p>
</td>
<td class="cellrowborder" valign="top" width="34.26342634263426%" headers="mcps1.2.4.1.2 "><p id="p67861746557"><a name="p67861746557"></a><a name="p67861746557"></a>get_tts_response(request)</p>
</td>
<td class="cellrowborder" valign="top" width="42.104210421042104%" headers="mcps1.2.4.1.3 "><p id="p167863461150"><a name="p167863461150"></a><a name="p167863461150"></a>POST /v1.0/voice/tts</p>
</td>
</tr>
<tr id="row87865461453"><td class="cellrowborder" rowspan="3" valign="top" width="23.632363236323634%" headers="mcps1.2.4.1.1 "><p id="p6786124612518"><a name="p6786124612518"></a><a name="p6786124612518"></a>RasrClient</p>
</td>
<td class="cellrowborder" valign="top" width="34.26342634263426%" headers="mcps1.2.4.1.2 "><p id="p1178614462050"><a name="p1178614462050"></a><a name="p1178614462050"></a>continue_stream_connect(request)</p>
</td>
<td class="cellrowborder" valign="top" width="42.104210421042104%" headers="mcps1.2.4.1.3 "><p id="p197868468517"><a name="p197868468517"></a><a name="p197868468517"></a>wss://{endpoint}/v1/{project_id}/rasr/continue-stream</p>
</td>
</tr>
<tr id="row97861146854"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1578616466512"><a name="p1578616466512"></a><a name="p1578616466512"></a>short_stream_connect(request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18786446554"><a name="p18786446554"></a><a name="p18786446554"></a>wss://{endpoint}/v1/{project_id}/rasr/short-stream</p>
</td>
</tr>
<tr id="row9786046256"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p137864461457"><a name="p137864461457"></a><a name="p137864461457"></a>sentence_stream_connect(request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p13786164611518"><a name="p13786164611518"></a><a name="p13786164611518"></a>wss://{endpoint}/v1/{project_id}/rasr/sentence-stream</p>
</td>
</tr>
<tr id="row167861846558"><td class="cellrowborder" rowspan="3" valign="top" width="23.632363236323634%" headers="mcps1.2.4.1.1 "><p id="p107872046258"><a name="p107872046258"></a><a name="p107872046258"></a>AsrCustomizationClient</p>
</td>
<td class="cellrowborder" valign="top" width="34.26342634263426%" headers="mcps1.2.4.1.2 "><p id="p3787246850"><a name="p3787246850"></a><a name="p3787246850"></a>get_short_response(request)</p>
</td>
<td class="cellrowborder" valign="top" width="42.104210421042104%" headers="mcps1.2.4.1.3 "><p id="p77879469512"><a name="p77879469512"></a><a name="p77879469512"></a>POST /v1/{project_id}/asr/short-audio</p>
</td>
</tr>
<tr id="row878774615517"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p14787046059"><a name="p14787046059"></a><a name="p14787046059"></a>submit_job(request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p778713461153"><a name="p778713461153"></a><a name="p778713461153"></a>POST /v1/{project_id}/asr/transcriber/jobs</p>
</td>
</tr>
<tr id="row157871046956"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6787164618512"><a name="p6787164618512"></a><a name="p6787164618512"></a>get_long_response(job_id)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1478716461851"><a name="p1478716461851"></a><a name="p1478716461851"></a>GET /v1/{project_id}/asr/transcriber/jobs/{job_id}</p>
</td>
</tr>
<tr id="row47872461956"><td class="cellrowborder" valign="top" width="23.632363236323634%" headers="mcps1.2.4.1.1 "><p id="p978715461253"><a name="p978715461253"></a><a name="p978715461253"></a>TtsCustomizationClient</p>
</td>
<td class="cellrowborder" valign="top" width="34.26342634263426%" headers="mcps1.2.4.1.2 "><p id="p8787194613515"><a name="p8787194613515"></a><a name="p8787194613515"></a>get_tts_response(request)</p>
</td>
<td class="cellrowborder" valign="top" width="42.104210421042104%" headers="mcps1.2.4.1.3 "><p id="p378718465511"><a name="p378718465511"></a><a name="p378718465511"></a>POST  /v1/{project_id}/tts</p>
</td>
</tr>
</tbody>
</table>

