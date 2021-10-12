# SDK简介<a name="sis_05_0001"></a>

## 语音交互概述<a name="section1582503120018"></a>

语音交互服务（Speech Interaction Service，简称SIS）是一种人机交互方式，用户通过实时访问和调用API获取语音交互结果。支持用户通过语音识别功能，将口述音频、普通话或者带有一定方言的语音文件识别成可编辑的文本，同时也支持通过语音合成功能将文本转换成逼真的语音等提升用户体验。适用场景如语音客服质检、会议记录、语音短消息、有声读物、电话回访等。

## SDK概述<a name="section191232404117"></a>

语音交互目前支持Java SDK、Python SDK。

通过对语音交互提供的REST API进行的封装，以简化用户的开发工作。用户直接调用语音交互SDK提供的接口函数即可实现使用语音交互业务能力的目的。

## Java接口与API对应关系<a name="section121947299416"></a>

Java接口与API对应关系请参见[表 Java接口与API对应关系表](#table1449262611219)。

**表 1**  Java接口与API对应关系表

<a name="table1449262611219"></a>
<table><thead align="left"><tr id="row14493202614219"><th class="cellrowborder" valign="top" width="16.48%" id="mcps1.2.5.1.1"><p id="p4493102610215"><a name="p4493102610215"></a><a name="p4493102610215"></a>Class</p>
</th>
<th class="cellrowborder" valign="top" width="37.75%" id="mcps1.2.5.1.2"><p id="p1249318269217"><a name="p1249318269217"></a><a name="p1249318269217"></a>Method</p>
</th>
<th class="cellrowborder" valign="top" width="25.35%" id="mcps1.2.5.1.3"><p id="p174938261923"><a name="p174938261923"></a><a name="p174938261923"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="20.419999999999998%" id="mcps1.2.5.1.4"><p id="p1874773613279"><a name="p1874773613279"></a><a name="p1874773613279"></a>功能名称</p>
</th>
</tr>
</thead>
<tbody><tr id="row796411276149"><td class="cellrowborder" rowspan="3" valign="top" width="16.48%" headers="mcps1.2.5.1.1 "><p id="p20721745201414"><a name="p20721745201414"></a><a name="p20721745201414"></a>RasrClient</p>
</td>
<td class="cellrowborder" valign="top" width="37.75%" headers="mcps1.2.5.1.2 "><p id="p480341181516"><a name="p480341181516"></a><a name="p480341181516"></a>void continueStreamConnect(RasrRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="25.35%" headers="mcps1.2.5.1.3 "><p id="p158032112157"><a name="p158032112157"></a><a name="p158032112157"></a>wss://{endpoint}/v1/{project_id}/rasr/continue-stream</p>
</td>
<td class="cellrowborder" valign="top" width="20.419999999999998%" headers="mcps1.2.5.1.4 "><p id="p3747103672713"><a name="p3747103672713"></a><a name="p3747103672713"></a>实时流连续模式</p>
</td>
</tr>
<tr id="row14145134917131"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p84091812111518"><a name="p84091812111518"></a><a name="p84091812111518"></a>void shortStreamConnect(RasrRequest request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p24099126155"><a name="p24099126155"></a><a name="p24099126155"></a>wss://{endpoint}/v1/{project_id}/rasr/short-stream</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p6747936102715"><a name="p6747936102715"></a><a name="p6747936102715"></a>实时流一句话模式</p>
</td>
</tr>
<tr id="row473992417142"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p741712205151"><a name="p741712205151"></a><a name="p741712205151"></a>void sentenceStreamConnect(RasrRequest request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p14417192011156"><a name="p14417192011156"></a><a name="p14417192011156"></a>wss://{endpoint}/v1/{project_id}/rasr/sentence-stream</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p87471236192718"><a name="p87471236192718"></a><a name="p87471236192718"></a>实时流单句模式</p>
</td>
</tr>
<tr id="row566032911527"><td class="cellrowborder" rowspan="3" valign="top" width="16.48%" headers="mcps1.2.5.1.1 "><p id="p199671934175213"><a name="p199671934175213"></a><a name="p199671934175213"></a>AsrCustomizationClient</p>
<p id="p125998725215"><a name="p125998725215"></a><a name="p125998725215"></a></p>
<p id="p156006712524"><a name="p156006712524"></a><a name="p156006712524"></a></p>
</td>
<td class="cellrowborder" valign="top" width="37.75%" headers="mcps1.2.5.1.2 "><p id="p696743435215"><a name="p696743435215"></a><a name="p696743435215"></a>AsrCustomShortResponse getAsrShortResponse(AsrCustomShortRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="25.35%" headers="mcps1.2.5.1.3 "><p id="p1967734185214"><a name="p1967734185214"></a><a name="p1967734185214"></a>POST /v1/{project_id}/asr/short-audio</p>
</td>
<td class="cellrowborder" valign="top" width="20.419999999999998%" headers="mcps1.2.5.1.4 "><p id="p1296783495215"><a name="p1296783495215"></a><a name="p1296783495215"></a>一句话识别</p>
</td>
</tr>
<tr id="row12557315192014"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1355731562010"><a name="p1355731562010"></a><a name="p1355731562010"></a>String submitJob(AsrCustomLongRequest request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p757716489270"><a name="p757716489270"></a><a name="p757716489270"></a>POST /v1/{project_id}/asr/transcriber/jobs</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p7747113692710"><a name="p7747113692710"></a><a name="p7747113692710"></a>录音文件识别-提交请求</p>
</td>
</tr>
<tr id="row1518153214216"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1551843212216"><a name="p1551843212216"></a><a name="p1551843212216"></a>AsrCustomLongResponse getAsrLongResponse(String jobId)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p17688728102819"><a name="p17688728102819"></a><a name="p17688728102819"></a>GET /v1/{project_id}/asr/transcriber/jobs/{job_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p674753617279"><a name="p674753617279"></a><a name="p674753617279"></a>录音文件识别-状态查询</p>
</td>
</tr>
<tr id="row437945315137"><td class="cellrowborder" valign="top" width="16.48%" headers="mcps1.2.5.1.1 "><p id="p1037975315133"><a name="p1037975315133"></a><a name="p1037975315133"></a>TtsCustomizationClient</p>
</td>
<td class="cellrowborder" valign="top" width="37.75%" headers="mcps1.2.5.1.2 "><p id="p937965311131"><a name="p937965311131"></a><a name="p937965311131"></a>TtsCustomResponse getTtsResponse(TtsCustomRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="25.35%" headers="mcps1.2.5.1.3 "><p id="p12380453161318"><a name="p12380453161318"></a><a name="p12380453161318"></a>POST <span> /v1/{project_id}/tts</span></p>
</td>
<td class="cellrowborder" valign="top" width="20.419999999999998%" headers="mcps1.2.5.1.4 "><p id="p8747163615272"><a name="p8747163615272"></a><a name="p8747163615272"></a>语音合成</p>
</td>
</tr>
<tr id="row112511814112"><td class="cellrowborder" rowspan="5" valign="top" width="16.48%" headers="mcps1.2.5.1.1 "><p id="p412531810111"><a name="p412531810111"></a><a name="p412531810111"></a>HotWordClient</p>
</td>
<td class="cellrowborder" valign="top" width="37.75%" headers="mcps1.2.5.1.2 "><p id="p171251618101111"><a name="p171251618101111"></a><a name="p171251618101111"></a>String create(HotWordRequest request)</p>
</td>
<td class="cellrowborder" valign="top" width="25.35%" headers="mcps1.2.5.1.3 "><p id="p1263211521159"><a name="p1263211521159"></a><a name="p1263211521159"></a>POST /v1/{project_id}/asr/vocabularies</p>
</td>
<td class="cellrowborder" valign="top" width="20.419999999999998%" headers="mcps1.2.5.1.4 "><p id="p812581814117"><a name="p812581814117"></a><a name="p812581814117"></a>创建热词表</p>
</td>
</tr>
<tr id="row1113717517119"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p0137251151112"><a name="p0137251151112"></a><a name="p0137251151112"></a>String update(HotWordRequest request, String vocabularyId)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p108931324167"><a name="p108931324167"></a><a name="p108931324167"></a>PUT /v1/{project_id}/asr/vocabularies/{vocabulary_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p17137125151113"><a name="p17137125151113"></a><a name="p17137125151113"></a>更新热词表</p>
</td>
</tr>
<tr id="row22991056171114"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p629915651118"><a name="p629915651118"></a><a name="p629915651118"></a>HotWordResponse query(String vocabularyId)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p188434571611"><a name="p188434571611"></a><a name="p188434571611"></a>GET /v1/{project_id}/asr/vocabularies/{vocabulary_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p6299656101118"><a name="p6299656101118"></a><a name="p6299656101118"></a>查询热词表信息</p>
</td>
</tr>
<tr id="row1222722151219"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p022812271216"><a name="p022812271216"></a><a name="p022812271216"></a>HotWordsResponse query()</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p14885654161620"><a name="p14885654161620"></a><a name="p14885654161620"></a>GET /v1/{project_id}/asr/vocabularies</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p1922818213128"><a name="p1922818213128"></a><a name="p1922818213128"></a>查询热词表列表</p>
</td>
</tr>
<tr id="row15299138131211"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p13299884122"><a name="p13299884122"></a><a name="p13299884122"></a>void delete(String vocabularyId)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p1016310413178"><a name="p1016310413178"></a><a name="p1016310413178"></a>DELETE /v1/{project_id}/asr/vocabularies/{vocabulary_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p3299138181214"><a name="p3299138181214"></a><a name="p3299138181214"></a>删除热词表</p>
</td>
</tr>
</tbody>
</table>

## Python接口与API对应关系<a name="section129019441941"></a>

Python接口与API对应关系请参见[表 Python接口与API对应关系表](#table67851461051)。

**表 2**  Python接口与API对应关系表

<a name="table67851461051"></a>
<table><thead align="left"><tr id="row57862461753"><th class="cellrowborder" valign="top" width="21.85781421857814%" id="mcps1.2.5.1.1"><p id="p167863466514"><a name="p167863466514"></a><a name="p167863466514"></a>Class</p>
</th>
<th class="cellrowborder" valign="top" width="28.32716728327167%" id="mcps1.2.5.1.2"><p id="p978664618513"><a name="p978664618513"></a><a name="p978664618513"></a>Method</p>
</th>
<th class="cellrowborder" valign="top" width="34.95650434956505%" id="mcps1.2.5.1.3"><p id="p1978616461859"><a name="p1978616461859"></a><a name="p1978616461859"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="14.858514148585142%" id="mcps1.2.5.1.4"><p id="p115182012102017"><a name="p115182012102017"></a><a name="p115182012102017"></a>功能名称</p>
</th>
</tr>
</thead>
<tbody><tr id="row87865461453"><td class="cellrowborder" rowspan="3" valign="top" width="21.85781421857814%" headers="mcps1.2.5.1.1 "><p id="p6786124612518"><a name="p6786124612518"></a><a name="p6786124612518"></a>RasrClient</p>
</td>
<td class="cellrowborder" valign="top" width="28.32716728327167%" headers="mcps1.2.5.1.2 "><p id="p1178614462050"><a name="p1178614462050"></a><a name="p1178614462050"></a>continue_stream_connect(request)</p>
</td>
<td class="cellrowborder" valign="top" width="34.95650434956505%" headers="mcps1.2.5.1.3 "><p id="p197868468517"><a name="p197868468517"></a><a name="p197868468517"></a>wss://{endpoint}/v1/{project_id}/rasr/continue-stream</p>
</td>
<td class="cellrowborder" valign="top" width="14.858514148585142%" headers="mcps1.2.5.1.4 "><p id="p18519201232012"><a name="p18519201232012"></a><a name="p18519201232012"></a>实时流连续模式</p>
</td>
</tr>
<tr id="row97861146854"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1578616466512"><a name="p1578616466512"></a><a name="p1578616466512"></a>short_stream_connect(request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p18786446554"><a name="p18786446554"></a><a name="p18786446554"></a>wss://{endpoint}/v1/{project_id}/rasr/short-stream</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p851921292011"><a name="p851921292011"></a><a name="p851921292011"></a>实时流一句话模式</p>
</td>
</tr>
<tr id="row9786046256"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p137864461457"><a name="p137864461457"></a><a name="p137864461457"></a>sentence_stream_connect(request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p13786164611518"><a name="p13786164611518"></a><a name="p13786164611518"></a>wss://{endpoint}/v1/{project_id}/rasr/sentence-stream</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p11519171211203"><a name="p11519171211203"></a><a name="p11519171211203"></a>实时流单句模式</p>
</td>
</tr>
<tr id="row167861846558"><td class="cellrowborder" rowspan="3" valign="top" width="21.85781421857814%" headers="mcps1.2.5.1.1 "><p id="p107872046258"><a name="p107872046258"></a><a name="p107872046258"></a>AsrCustomizationClient</p>
</td>
<td class="cellrowborder" valign="top" width="28.32716728327167%" headers="mcps1.2.5.1.2 "><p id="p3787246850"><a name="p3787246850"></a><a name="p3787246850"></a>get_short_response(request)</p>
</td>
<td class="cellrowborder" valign="top" width="34.95650434956505%" headers="mcps1.2.5.1.3 "><p id="p77879469512"><a name="p77879469512"></a><a name="p77879469512"></a>POST /v1/{project_id}/asr/short-audio</p>
</td>
<td class="cellrowborder" valign="top" width="14.858514148585142%" headers="mcps1.2.5.1.4 "><p id="p175191112102014"><a name="p175191112102014"></a><a name="p175191112102014"></a>一句话识别</p>
</td>
</tr>
<tr id="row878774615517"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p14787046059"><a name="p14787046059"></a><a name="p14787046059"></a>submit_job(request)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p778713461153"><a name="p778713461153"></a><a name="p778713461153"></a>POST /v1/{project_id}/asr/transcriber/jobs</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p1351961214205"><a name="p1351961214205"></a><a name="p1351961214205"></a>录音文件识别-提交请求</p>
</td>
</tr>
<tr id="row157871046956"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p6787164618512"><a name="p6787164618512"></a><a name="p6787164618512"></a>get_long_response(job_id)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p1478716461851"><a name="p1478716461851"></a><a name="p1478716461851"></a>GET /v1/{project_id}/asr/transcriber/jobs/{job_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p145195122200"><a name="p145195122200"></a><a name="p145195122200"></a>录音文件识别-状态查询</p>
</td>
</tr>
<tr id="row47872461956"><td class="cellrowborder" valign="top" width="21.85781421857814%" headers="mcps1.2.5.1.1 "><p id="p978715461253"><a name="p978715461253"></a><a name="p978715461253"></a>TtsCustomizationClient</p>
</td>
<td class="cellrowborder" valign="top" width="28.32716728327167%" headers="mcps1.2.5.1.2 "><p id="p8787194613515"><a name="p8787194613515"></a><a name="p8787194613515"></a>get_tts_response(request)</p>
</td>
<td class="cellrowborder" valign="top" width="34.95650434956505%" headers="mcps1.2.5.1.3 "><p id="p378718465511"><a name="p378718465511"></a><a name="p378718465511"></a>POST <span> /v1/{project_id}/tts</span></p>
</td>
<td class="cellrowborder" valign="top" width="14.858514148585142%" headers="mcps1.2.5.1.4 "><p id="p0519151210204"><a name="p0519151210204"></a><a name="p0519151210204"></a>语音合成</p>
</td>
</tr>
<tr id="row157787831819"><td class="cellrowborder" rowspan="5" valign="top" width="21.85781421857814%" headers="mcps1.2.5.1.1 "><p id="p10666153181816"><a name="p10666153181816"></a><a name="p10666153181816"></a>HotWordClient</p>
<p id="p6669231101810"><a name="p6669231101810"></a><a name="p6669231101810"></a></p>
<p id="p16669831101816"><a name="p16669831101816"></a><a name="p16669831101816"></a></p>
<p id="p1866953118188"><a name="p1866953118188"></a><a name="p1866953118188"></a></p>
<p id="p126692031151818"><a name="p126692031151818"></a><a name="p126692031151818"></a></p>
</td>
<td class="cellrowborder" valign="top" width="28.32716728327167%" headers="mcps1.2.5.1.2 "><p id="p176661931111816"><a name="p176661931111816"></a><a name="p176661931111816"></a>create(request)</p>
</td>
<td class="cellrowborder" valign="top" width="34.95650434956505%" headers="mcps1.2.5.1.3 "><p id="p20666153115186"><a name="p20666153115186"></a><a name="p20666153115186"></a>POST /v1/{project_id}/asr/vocabularies</p>
</td>
<td class="cellrowborder" valign="top" width="14.858514148585142%" headers="mcps1.2.5.1.4 "><p id="p16661031131810"><a name="p16661031131810"></a><a name="p16661031131810"></a>创建热词表</p>
</td>
</tr>
<tr id="row1418022301810"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1366683117182"><a name="p1366683117182"></a><a name="p1366683117182"></a>update(request, vocabulary_id)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p0666173191820"><a name="p0666173191820"></a><a name="p0666173191820"></a>PUT /v1/{project_id}/asr/vocabularies/{vocabulary_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p566643111811"><a name="p566643111811"></a><a name="p566643111811"></a>更新热词表</p>
</td>
</tr>
<tr id="row5240266188"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p56667316185"><a name="p56667316185"></a><a name="p56667316185"></a>query_by_vocabulary_id(vocabularyId)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p56661311181"><a name="p56661311181"></a><a name="p56661311181"></a>GET /v1/{project_id}/asr/vocabularies/{vocabulary_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p96661331131812"><a name="p96661331131812"></a><a name="p96661331131812"></a>查询热词表信息</p>
</td>
</tr>
<tr id="row83891829141810"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p2666431101810"><a name="p2666431101810"></a><a name="p2666431101810"></a>query()</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p666663181817"><a name="p666663181817"></a><a name="p666663181817"></a>GET /v1/{project_id}/asr/vocabularies</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p466620316188"><a name="p466620316188"></a><a name="p466620316188"></a>查询热词表列表</p>
</td>
</tr>
<tr id="row16417121815187"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1466612311181"><a name="p1466612311181"></a><a name="p1466612311181"></a>delete(vocabulary_id)</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p66661131161815"><a name="p66661131161815"></a><a name="p66661131161815"></a>DELETE /v1/{project_id}/asr/vocabularies/{vocabulary_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p176661531161819"><a name="p176661531161819"></a><a name="p176661531161819"></a>删除热词表</p>
</td>
</tr>
</tbody>
</table>

