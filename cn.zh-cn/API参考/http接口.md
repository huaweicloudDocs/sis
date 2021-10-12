# http接口<a name="sis_03_0094"></a>

## 功能介绍<a name="zh-cn_topic_0145253487_section39529998"></a>

一句话识别接口，用于短语音的同步识别。一次性上传1min以内音频，能快速返回识别结果。该接口的使用限制请参见[约束与限制](https://support.huaweicloud.com/productdesc-sis/sis_01_0011.html)，详细使用指导请参见[SIS服务使用简介](https://support.huaweicloud.com/qs-sis/sis_07_0001.html)章节。

## 调试<a name="section165001857505"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?product=SIS&api=PostShortAudio)中调试该接口。

## URI<a name="zh-cn_topic_0145253487_section20225667"></a>

POST /v1/\{project\_id\}/asr/short-audio

**表 1**  路径参数

<a name="table1676532793611"></a>
<table><thead align="left"><tr id="row1766112723620"><th class="cellrowborder" valign="top" width="16.55%" id="mcps1.2.5.1.1"><p id="p8766227163619"><a name="p8766227163619"></a><a name="p8766227163619"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p117661027173615"><a name="p117661027173615"></a><a name="p117661027173615"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.5.1.3"><p id="p0766527103614"><a name="p0766527103614"></a><a name="p0766527103614"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.73%" id="mcps1.2.5.1.4"><p id="p11766182714369"><a name="p11766182714369"></a><a name="p11766182714369"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1766227103616"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p12766112713614"><a name="p12766112713614"></a><a name="p12766112713614"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p176652714361"><a name="p176652714361"></a><a name="p176652714361"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p1876622712367"><a name="p1876622712367"></a><a name="p1876622712367"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p1766122710362"><a name="p1766122710362"></a><a name="p1766122710362"></a>项目编号。获取方法，请参见<a href="获取项目ID.md">获取项目ID</a>。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数<a name="zh-cn_topic_0145253487_section47813280"></a>

**表 2**  请求Header参数

<a name="HeaderParameter"></a>
<table><thead align="left"><tr id="row3169164363015"><th class="cellrowborder" valign="top" width="16.55%" id="mcps1.2.5.1.1"><p id="p9170154353019"><a name="p9170154353019"></a><a name="p9170154353019"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p1817013434305"><a name="p1817013434305"></a><a name="p1817013434305"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.5.1.3"><p id="p4170104313010"><a name="p4170104313010"></a><a name="p4170104313010"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.73%" id="mcps1.2.5.1.4"><p id="p8170043193013"><a name="p8170043193013"></a><a name="p8170043193013"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row1516904383019"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p1717014310303"><a name="p1717014310303"></a><a name="p1717014310303"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1517018431303"><a name="p1517018431303"></a><a name="p1517018431303"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p1017119432306"><a name="p1017119432306"></a><a name="p1017119432306"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p91911023114116"><a name="p91911023114116"></a><a name="p91911023114116"></a>用户Token。</p>
<p id="p419112316411"><a name="p419112316411"></a><a name="p419112316411"></a>Token认证就是在调用API的时候将Token加到请求消息头，从而通过身份认证，获得操作API的权限，响应消息头中X-Subject-Token的值即为Token。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  请求Body参数

<a name="zh-cn_topic_0145253487_table23614537"></a>
<table><thead align="left"><tr id="zh-cn_topic_0145253487_row37888824"><th class="cellrowborder" valign="top" width="16.55%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0145253487_p49095903"><a name="zh-cn_topic_0145253487_p49095903"></a><a name="zh-cn_topic_0145253487_p49095903"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0145253487_p62783822"><a name="zh-cn_topic_0145253487_p62783822"></a><a name="zh-cn_topic_0145253487_p62783822"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0145253487_p52324839"><a name="zh-cn_topic_0145253487_p52324839"></a><a name="zh-cn_topic_0145253487_p52324839"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.73%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0145253487_p10453536"><a name="zh-cn_topic_0145253487_p10453536"></a><a name="zh-cn_topic_0145253487_p10453536"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0145253487_row41430049"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253487_p390803"><a name="zh-cn_topic_0145253487_p390803"></a><a name="zh-cn_topic_0145253487_p390803"></a>config</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0145253487_p13923816"><a name="zh-cn_topic_0145253487_p13923816"></a><a name="zh-cn_topic_0145253487_p13923816"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0145253487_p54087324"><a name="zh-cn_topic_0145253487_p54087324"></a><a name="zh-cn_topic_0145253487_p54087324"></a><a href="#table1053303517210">Config</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253487_p18997087"><a name="zh-cn_topic_0145253487_p18997087"></a><a name="zh-cn_topic_0145253487_p18997087"></a>配置信息。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row65201318"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253487_p46815435"><a name="zh-cn_topic_0145253487_p46815435"></a><a name="zh-cn_topic_0145253487_p46815435"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0145253487_p65912407"><a name="zh-cn_topic_0145253487_p65912407"></a><a name="zh-cn_topic_0145253487_p65912407"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0145253487_p37304717"><a name="zh-cn_topic_0145253487_p37304717"></a><a name="zh-cn_topic_0145253487_p37304717"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253487_p1783236"><a name="zh-cn_topic_0145253487_p1783236"></a><a name="zh-cn_topic_0145253487_p1783236"></a>语音数据，Base64编码，要求Base64编码后大小不超过4M，音频时长不超过1分钟。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  Config

<a name="table1053303517210"></a>
<table><thead align="left"><tr id="row1053453513211"><th class="cellrowborder" valign="top" width="16.55%" id="mcps1.2.5.1.1"><p id="p12956164610211"><a name="p12956164610211"></a><a name="p12956164610211"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p895654618210"><a name="p895654618210"></a><a name="p895654618210"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.5.1.3"><p id="p49562461227"><a name="p49562461227"></a><a name="p49562461227"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.73%" id="mcps1.2.5.1.4"><p id="p1395684616213"><a name="p1395684616213"></a><a name="p1395684616213"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row105342351323"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p727175714220"><a name="p727175714220"></a><a name="p727175714220"></a>audio_format</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p132715579212"><a name="p132715579212"></a><a name="p132715579212"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p02705716211"><a name="p02705716211"></a><a name="p02705716211"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p62717577213"><a name="p62717577213"></a><a name="p62717577213"></a>支持语音的格式，请参考<a href="#zh-cn_topic_0145253487_table10224419">表 audio_format取值范围</a>。</p>
</td>
</tr>
<tr id="row1253420356214"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p72725711211"><a name="p72725711211"></a><a name="p72725711211"></a>property</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p152717571212"><a name="p152717571212"></a><a name="p152717571212"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p11272576214"><a name="p11272576214"></a><a name="p11272576214"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p159495118583"><a name="p159495118583"></a><a name="p159495118583"></a>所使用的模型特征串，通常是 “语种_采样率_领域”的形式，采样率需要与音频采样率保持一致，取值范围请参考<a href="#table149231753161917">表 property取值范围</a>。</p>
</td>
</tr>
<tr id="row853410351723"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p42805710213"><a name="p42805710213"></a><a name="p42805710213"></a>add_punc</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1428195713218"><a name="p1428195713218"></a><a name="p1428195713218"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p10289571823"><a name="p10289571823"></a><a name="p10289571823"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p17559102814402"><a name="p17559102814402"></a><a name="p17559102814402"></a>表示是否在识别结果中添加标点，取值为<span class="parmvalue" id="parmvalue181493410598"><a name="parmvalue181493410598"></a><a name="parmvalue181493410598"></a>“yes”</span>和<span class="parmvalue" id="parmvalue8826112645917"><a name="parmvalue8826112645917"></a><a name="parmvalue8826112645917"></a>“no”</span>，默认为<span class="parmvalue" id="parmvalue2191202311590"><a name="parmvalue2191202311590"></a><a name="parmvalue2191202311590"></a>“no”</span>。</p>
</td>
</tr>
<tr id="row1895416113716"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p5459115619553"><a name="p5459115619553"></a><a name="p5459115619553"></a>digit_norm</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p845935619556"><a name="p845935619556"></a><a name="p845935619556"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p184591056165517"><a name="p184591056165517"></a><a name="p184591056165517"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p64597569556"><a name="p64597569556"></a><a name="p64597569556"></a>表示是否将语音中的数字识别为阿拉伯数字，取值为<span class="parmvalue" id="parmvalue5348171795914"><a name="parmvalue5348171795914"></a><a name="parmvalue5348171795914"></a>“yes”</span> 和 <span class="parmvalue" id="parmvalue119831414125919"><a name="parmvalue119831414125919"></a><a name="parmvalue119831414125919"></a>“no”</span>，默认为<span class="parmvalue" id="parmvalue105101051115913"><a name="parmvalue105101051115913"></a><a name="parmvalue105101051115913"></a>“yes”</span>。</p>
</td>
</tr>
<tr id="row19534123519218"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p1528195718213"><a name="p1528195718213"></a><a name="p1528195718213"></a>vocabulary_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p92820571622"><a name="p92820571622"></a><a name="p92820571622"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p92816571216"><a name="p92816571216"></a><a name="p92816571216"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p828155718220"><a name="p828155718220"></a><a name="p828155718220"></a>热词表id，不使用则不填写。</p>
<p id="p142810571628"><a name="p142810571628"></a><a name="p142810571628"></a>创建热词表信息请参考<a href="创建热词表.md">创建热词表</a>。</p>
</td>
</tr>
<tr id="row14360103721015"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p16360737111013"><a name="p16360737111013"></a><a name="p16360737111013"></a><span>need_word_info</span></p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1336073720104"><a name="p1336073720104"></a><a name="p1336073720104"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p536018377109"><a name="p536018377109"></a><a name="p536018377109"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p936117372104"><a name="p936117372104"></a><a name="p936117372104"></a>表示是否在识别结果中输出分词结果信息，取值为<span class="parmvalue" id="parmvalue1490315211594"><a name="parmvalue1490315211594"></a><a name="parmvalue1490315211594"></a>“yes”</span>和<span class="parmvalue" id="parmvalue1812528135912"><a name="parmvalue1812528135912"></a><a name="parmvalue1812528135912"></a>“no”</span>，默认为<span class="parmvalue" id="parmvalue16738171065911"><a name="parmvalue16738171065911"></a><a name="parmvalue16738171065911"></a>“no”</span>。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  audio\_format取值范围

<a name="zh-cn_topic_0145253487_table10224419"></a>
<table><thead align="left"><tr id="zh-cn_topic_0145253487_row5381957"><th class="cellrowborder" valign="top" width="30.3%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0145253487_p33285334"><a name="zh-cn_topic_0145253487_p33285334"></a><a name="zh-cn_topic_0145253487_p33285334"></a>audio_format取值</p>
</th>
<th class="cellrowborder" valign="top" width="69.69999999999999%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0145253487_p12835698"><a name="zh-cn_topic_0145253487_p12835698"></a><a name="zh-cn_topic_0145253487_p12835698"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0145253487_row33058637"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p60503953"><a name="zh-cn_topic_0145253487_p60503953"></a><a name="zh-cn_topic_0145253487_p60503953"></a>pcm16k16bit</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p1873124"><a name="zh-cn_topic_0145253487_p1873124"></a><a name="zh-cn_topic_0145253487_p1873124"></a>16k16bit单通道录音数据。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row16858124"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p23330812"><a name="zh-cn_topic_0145253487_p23330812"></a><a name="zh-cn_topic_0145253487_p23330812"></a>pcm8k16bit</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p10747600"><a name="zh-cn_topic_0145253487_p10747600"></a><a name="zh-cn_topic_0145253487_p10747600"></a>8k16bit单通道录音数据。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row29619539"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p50372473"><a name="zh-cn_topic_0145253487_p50372473"></a><a name="zh-cn_topic_0145253487_p50372473"></a>ulaw16k8bit</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p53638519"><a name="zh-cn_topic_0145253487_p53638519"></a><a name="zh-cn_topic_0145253487_p53638519"></a>16k8bit ulaw单通道录音数据。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row12984631"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p45122222"><a name="zh-cn_topic_0145253487_p45122222"></a><a name="zh-cn_topic_0145253487_p45122222"></a>ulaw8k8bit</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p31021328"><a name="zh-cn_topic_0145253487_p31021328"></a><a name="zh-cn_topic_0145253487_p31021328"></a>8k8bit ulaw单通道录音数据。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row10756502"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p65970310"><a name="zh-cn_topic_0145253487_p65970310"></a><a name="zh-cn_topic_0145253487_p65970310"></a>alaw16k8bit</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p41994903"><a name="zh-cn_topic_0145253487_p41994903"></a><a name="zh-cn_topic_0145253487_p41994903"></a>16k8bit alaw单通道录音数据。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row42409811"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p12642680"><a name="zh-cn_topic_0145253487_p12642680"></a><a name="zh-cn_topic_0145253487_p12642680"></a>alaw8k8bit</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p17424145"><a name="zh-cn_topic_0145253487_p17424145"></a><a name="zh-cn_topic_0145253487_p17424145"></a>8k8bit alaw单通道录音数据。</p>
</td>
</tr>
<tr id="row17435841192215"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="p643564122214"><a name="p643564122214"></a><a name="p643564122214"></a>mp3</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="p1843594172215"><a name="p1843594172215"></a><a name="p1843594172215"></a>mp3格式音频。目前仅支持单通道的音频。</p>
</td>
</tr>
<tr id="row16538104117257"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="p1853824120254"><a name="p1853824120254"></a><a name="p1853824120254"></a>aac</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="p135389414256"><a name="p135389414256"></a><a name="p135389414256"></a>aac格式音频。目前仅支持单通道的音频。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row168068541489"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p178061754687"><a name="zh-cn_topic_0145253487_p178061754687"></a><a name="zh-cn_topic_0145253487_p178061754687"></a>wav</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p14806165417810"><a name="zh-cn_topic_0145253487_p14806165417810"></a><a name="zh-cn_topic_0145253487_p14806165417810"></a>带wav封装头的格式，从封装头中自动确定格式，目前仅支持8k/16k采样率、单通道、pcm, alaw, ulaw三种编码格式。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row22599581"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p18626752"><a name="zh-cn_topic_0145253487_p18626752"></a><a name="zh-cn_topic_0145253487_p18626752"></a>amr</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p32371915"><a name="zh-cn_topic_0145253487_p32371915"></a><a name="zh-cn_topic_0145253487_p32371915"></a>AMR窄带(8k) 压缩录音数据。目前仅支持单通道的音频。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row22911783"><td class="cellrowborder" valign="top" width="30.3%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0145253487_p43915171"><a name="zh-cn_topic_0145253487_p43915171"></a><a name="zh-cn_topic_0145253487_p43915171"></a>amrwb</p>
</td>
<td class="cellrowborder" valign="top" width="69.69999999999999%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0145253487_p359066"><a name="zh-cn_topic_0145253487_p359066"></a><a name="zh-cn_topic_0145253487_p359066"></a>AMR 宽带(16k) 压缩录音数据。目前仅支持单通道的音频。</p>
</td>
</tr>
</tbody>
</table>

**表 6**  property取值范围

<a name="table149231753161917"></a>
<table><thead align="left"><tr id="row14924175311912"><th class="cellrowborder" valign="top" width="30.34%" id="mcps1.2.3.1.1"><p id="p0924653191918"><a name="p0924653191918"></a><a name="p0924653191918"></a>property取值</p>
</th>
<th class="cellrowborder" valign="top" width="69.66%" id="mcps1.2.3.1.2"><p id="p19924155311911"><a name="p19924155311911"></a><a name="p19924155311911"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row169241953151913"><td class="cellrowborder" valign="top" width="30.34%" headers="mcps1.2.3.1.1 "><p id="p513842372112"><a name="p513842372112"></a><a name="p513842372112"></a>chinese_8k_common</p>
</td>
<td class="cellrowborder" valign="top" width="69.66%" headers="mcps1.2.3.1.2 "><p id="p17924125331914"><a name="p17924125331914"></a><a name="p17924125331914"></a>支持采样率为8k的中文普通话语音识别。</p>
</td>
</tr>
<tr id="row19245537199"><td class="cellrowborder" valign="top" width="30.34%" headers="mcps1.2.3.1.1 "><p id="p20931629102110"><a name="p20931629102110"></a><a name="p20931629102110"></a>chinese_16k_common</p>
</td>
<td class="cellrowborder" valign="top" width="69.66%" headers="mcps1.2.3.1.2 "><p id="p17924853111912"><a name="p17924853111912"></a><a name="p17924853111912"></a>支持采样率为16k的中文普通话语音识别。</p>
</td>
</tr>
<tr id="row1792495315195"><td class="cellrowborder" valign="top" width="30.34%" headers="mcps1.2.3.1.1 "><p id="p192412539195"><a name="p192412539195"></a><a name="p192412539195"></a>chinese_16k_general</p>
</td>
<td class="cellrowborder" valign="top" width="69.66%" headers="mcps1.2.3.1.2 "><p id="p1221418368239"><a name="p1221418368239"></a><a name="p1221418368239"></a>支持采样率为16k的中文普通话语音识别，同时可识别一些简单的方言。</p>
<p id="p107771919122312"><a name="p107771919122312"></a><a name="p107771919122312"></a>格式仅支持pcm16k16bit、mp3、wav，区域仅支持cn-north-4。</p>
</td>
</tr>
<tr id="row147821030193720"><td class="cellrowborder" valign="top" width="30.34%" headers="mcps1.2.3.1.1 "><p id="p578316307376"><a name="p578316307376"></a><a name="p578316307376"></a>sichuan_16k_common</p>
</td>
<td class="cellrowborder" valign="top" width="69.66%" headers="mcps1.2.3.1.2 "><p id="p4783230163714"><a name="p4783230163714"></a><a name="p4783230163714"></a>支持采样率为16k的中文普通话与四川话方言识别。区域仅支持cn-north-4。</p>
</td>
</tr>
<tr id="row1341212444383"><td class="cellrowborder" valign="top" width="30.34%" headers="mcps1.2.3.1.1 "><p id="p9412174413384"><a name="p9412174413384"></a><a name="p9412174413384"></a>cantonese_16k_common</p>
</td>
<td class="cellrowborder" valign="top" width="69.66%" headers="mcps1.2.3.1.2 "><p id="p54121443388"><a name="p54121443388"></a><a name="p54121443388"></a>支持采样率为16k的粤语方言识别。区域仅支持cn-north-4。</p>
</td>
</tr>
<tr id="row1629412151019"><td class="cellrowborder" valign="top" width="30.34%" headers="mcps1.2.3.1.1 "><p id="p152947150114"><a name="p152947150114"></a><a name="p152947150114"></a>shanghai_16k_common</p>
</td>
<td class="cellrowborder" valign="top" width="69.66%" headers="mcps1.2.3.1.2 "><p id="p7294815217"><a name="p7294815217"></a><a name="p7294815217"></a>支持采样率为16k的上海话方言识别，区域仅支持cn-north-4。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="zh-cn_topic_0145253487_section27666343"></a>

**状态码： 200**

**表 7**  响应Body参数

<a name="zh-cn_topic_0145253487_d0e3729"></a>
<table><thead align="left"><tr id="zh-cn_topic_0145253487_row60901406"><th class="cellrowborder" valign="top" width="16.55%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0145253487_p34066842"><a name="zh-cn_topic_0145253487_p34066842"></a><a name="zh-cn_topic_0145253487_p34066842"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0145253487_p40033254"><a name="zh-cn_topic_0145253487_p40033254"></a><a name="zh-cn_topic_0145253487_p40033254"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0145253487_p21468167"><a name="zh-cn_topic_0145253487_p21468167"></a><a name="zh-cn_topic_0145253487_p21468167"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.73%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0145253487_p61200005"><a name="zh-cn_topic_0145253487_p61200005"></a><a name="zh-cn_topic_0145253487_p61200005"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0145253487_row30360312"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253487_p43266208"><a name="zh-cn_topic_0145253487_p43266208"></a><a name="zh-cn_topic_0145253487_p43266208"></a>trace_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0145253487_p66209150"><a name="zh-cn_topic_0145253487_p66209150"></a><a name="zh-cn_topic_0145253487_p66209150"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0145253487_p61340932"><a name="zh-cn_topic_0145253487_p61340932"></a><a name="zh-cn_topic_0145253487_p61340932"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253487_p2559566"><a name="zh-cn_topic_0145253487_p2559566"></a><a name="zh-cn_topic_0145253487_p2559566"></a>服务内部的令牌，可用于在日志中追溯具体流程，调用失败无此字段。</p>
<p id="zh-cn_topic_0145253487_p23036096"><a name="zh-cn_topic_0145253487_p23036096"></a><a name="zh-cn_topic_0145253487_p23036096"></a>在某些错误情况下可能没有此令牌字符串。</p>
</td>
</tr>
<tr id="zh-cn_topic_0145253487_row5998276"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0145253487_p16098384"><a name="zh-cn_topic_0145253487_p16098384"></a><a name="zh-cn_topic_0145253487_p16098384"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0145253487_p59254979"><a name="zh-cn_topic_0145253487_p59254979"></a><a name="zh-cn_topic_0145253487_p59254979"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p1518854315309"><a name="p1518854315309"></a><a name="p1518854315309"></a><a href="#table231812015476">Result</a> object</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0145253487_p10274025"><a name="zh-cn_topic_0145253487_p10274025"></a><a name="zh-cn_topic_0145253487_p10274025"></a>调用成功表示识别结果，调用失败时无此字段。</p>
</td>
</tr>
</tbody>
</table>

**表 8**  Result

<a name="table231812015476"></a>
<table><thead align="left"><tr id="row1731990154716"><th class="cellrowborder" valign="top" width="16.55%" id="mcps1.2.5.1.1"><p id="p17151167149"><a name="p17151167149"></a><a name="p17151167149"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p16151177142"><a name="p16151177142"></a><a name="p16151177142"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.5.1.3"><p id="p0151577416"><a name="p0151577416"></a><a name="p0151577416"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.73%" id="mcps1.2.5.1.4"><p id="p1715187344"><a name="p1715187344"></a><a name="p1715187344"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row4861951034"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p129801830194920"><a name="p129801830194920"></a><a name="p129801830194920"></a>text</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p199808305495"><a name="p199808305495"></a><a name="p199808305495"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p1998043016498"><a name="p1998043016498"></a><a name="p1998043016498"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p20980130184911"><a name="p20980130184911"></a><a name="p20980130184911"></a>调用成功表示识别出的内容。</p>
</td>
</tr>
<tr id="row4319309473"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p19980143016498"><a name="p19980143016498"></a><a name="p19980143016498"></a>score</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1098023074919"><a name="p1098023074919"></a><a name="p1098023074919"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p1698113309495"><a name="p1698113309495"></a><a name="p1698113309495"></a>Float</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p159811230164917"><a name="p159811230164917"></a><a name="p159811230164917"></a>调用成功表示识别出的置信度，取值范围：0~1。</p>
</td>
</tr>
<tr id="row39902316516"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p129901831105112"><a name="p129901831105112"></a><a name="p129901831105112"></a>word_info</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p19990931145114"><a name="p19990931145114"></a><a name="p19990931145114"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p599023115116"><a name="p599023115116"></a><a name="p599023115116"></a>Array of <a href="#table154291536145211">WordInfo</a> objects</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p399023105119"><a name="p399023105119"></a><a name="p399023105119"></a>分词信息列表。</p>
</td>
</tr>
</tbody>
</table>

**表 9**  WordInfo

<a name="table154291536145211"></a>
<table><thead align="left"><tr id="row154291236105212"><th class="cellrowborder" valign="top" width="16.55%" id="mcps1.2.5.1.1"><p id="p7599133785412"><a name="p7599133785412"></a><a name="p7599133785412"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p642917366527"><a name="p642917366527"></a><a name="p642917366527"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.72%" id="mcps1.2.5.1.3"><p id="p1866554515548"><a name="p1866554515548"></a><a name="p1866554515548"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50.73%" id="mcps1.2.5.1.4"><p id="p8942134765414"><a name="p8942134765414"></a><a name="p8942134765414"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row4429236155211"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p14429173613525"><a name="p14429173613525"></a><a name="p14429173613525"></a>start_time</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p164291636195216"><a name="p164291636195216"></a><a name="p164291636195216"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p1842933617526"><a name="p1842933617526"></a><a name="p1842933617526"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p1356222345613"><a name="p1356222345613"></a><a name="p1356222345613"></a>起始时间</p>
</td>
</tr>
<tr id="row13429163685215"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p242963617528"><a name="p242963617528"></a><a name="p242963617528"></a>end_time</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p942953695218"><a name="p942953695218"></a><a name="p942953695218"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p6429193610524"><a name="p6429193610524"></a><a name="p6429193610524"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p1819992716561"><a name="p1819992716561"></a><a name="p1819992716561"></a>结束时间</p>
</td>
</tr>
<tr id="row19429936165217"><td class="cellrowborder" valign="top" width="16.55%" headers="mcps1.2.5.1.1 "><p id="p134291936135218"><a name="p134291936135218"></a><a name="p134291936135218"></a>word</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p1342933625213"><a name="p1342933625213"></a><a name="p1342933625213"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="17.72%" headers="mcps1.2.5.1.3 "><p id="p6429193617525"><a name="p6429193617525"></a><a name="p6429193617525"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50.73%" headers="mcps1.2.5.1.4 "><p id="p173621931145620"><a name="p173621931145620"></a><a name="p173621931145620"></a>分词</p>
</td>
</tr>
</tbody>
</table>

**状态码： 400**

**表 10**  响应Body参数

<a name="table1086517495118"></a>
<table><thead align="left"><tr id="row1686624911119"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p486619498113"><a name="p486619498113"></a><a name="p486619498113"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p id="p12866349817"><a name="p12866349817"></a><a name="p12866349817"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p id="p1886624916116"><a name="p1886624916116"></a><a name="p1886624916116"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row586617491011"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p086610495117"><a name="p086610495117"></a><a name="p086610495117"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p108662497120"><a name="p108662497120"></a><a name="p108662497120"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p148676491117"><a name="p148676491117"></a><a name="p148676491117"></a>调用失败时的错误码。 调用成功时无此字段。</p>
</td>
</tr>
<tr id="row9866104920116"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p148683491212"><a name="p148683491212"></a><a name="p148683491212"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p id="p148682496112"><a name="p148682496112"></a><a name="p148682496112"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p id="p1486817494116"><a name="p1486817494116"></a><a name="p1486817494116"></a>调用失败时的错误信息。 调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

## 请求示例<a name="zh-cn_topic_0145253487_section47670495"></a>

>![](public_sys-resources/icon-note.gif) **说明：** 
>“endpoint“即调用API的请求地址，不同服务不同区域的“endpoint“不同，具体请参见[终端节点](终端节点.md)。

-   请求示例（伪码）

    ```
    POST https://{endpoint}/v1/{project_id}/asr/short-audio
    
    Request Header:
    Content-Type: application/json
    X-Auth-Token: MIINRwYJKoZIhvcNAQcCoIINODCCDTQCAQExDTALBglghkgBZQMEAgEwgguVBgkqhkiG...   
    
    Request body: 
    {
      "config":
      {
        "audio_format": "ulaw8k8bit",
        "property": "chinese_8k_common",
        "add_punc": "yes",
        "need_word_info": "yes"
      },
      "data": "/+MgxAAUeHpMAUkQAANhuRAC..."
    }
    ```

-   Python3语言请求代码示例

    ```
    # -*- coding: utf-8 -*-
    # 此demo仅供测试使用，强烈建议使用sdk。需提前安装requests，执行pip install requests
    import requests
    import base64
    import json
    
    def sasr_demo():
        url = 'https://{{endpoint}}/v1/{{project_id}}/asr/short-audio'  # endpoint和project_id需替换
        token = '用户对应region的token'
        file_path = '将要识别音频的路径'
        with open(file_path, 'rb') as f:
            data = f.read()
            base64_data = str(base64.b64encode(data), 'utf-8')
        header = {
            'Content-Type': 'application/json',
            'X-Auth-Token': token
        }
        body = {
            'data': base64_data,
            'config': {
                'property': 'chinese_8k_common',
                'audio_format': 'pcm8k16bit'
            }
        }
        resp = requests.post(url, data=json.dumps(body), headers=header)
        print(resp.text)
    
    if __name__ == '__main__':
        sasr_demo()
    
    ```

-   Java语言请求代码示例

    ```
    import java.io.BufferedReader;
    import java.io.InputStream;
    import java.io.InputStreamReader;
    import java.io.OutputStreamWriter;
    import java.net.HttpURLConnection;
    import java.net.URL;
    
    /**
     * 此demo仅供测试使用，强烈建议使用SDK
     */
    public class SasrDemo {
      public void sasrDemo() {
        try {
          // endpoint和projectId需要替换成实际信息。
          URL url = new URL("https://{{endpoint}}/v1/{{project_id}}/asr/short-audio");
          String token = "对应region的token";
          String audioBody = "8k wav格式audio对应base64编码";
          HttpURLConnection connection = (HttpURLConnection)url.openConnection();
          connection.setRequestMethod("POST");
          connection.setDoInput(true);
          connection.setDoOutput(true);
          connection.addRequestProperty("Content-Type", "application/json");
          connection.addRequestProperty("X-Auth-Token", token);
    
    
          OutputStreamWriter osw = new OutputStreamWriter(connection.getOutputStream(), "UTF-8");
          String body = "{\"data\":\"" +  audioBody + "\", \"config\": { \"audio_format\": \"wav\", "
            + "\"property\":\"chinese_8k_common\"}}";
          osw.append(body);
          osw.flush();
          InputStream is = connection.getInputStream();
          BufferedReader br = new BufferedReader(new InputStreamReader(is, "UTF-8"));
          while (br.ready()) {
            System.out.println(br.readLine());
          }
        } catch (Exception e) {
          e.printStackTrace();
        }
      }
      public static void main(String[] args) {
        SasrDemo sasrDemo = new SasrDemo();
        sasrDemo.sasrDemo();
      }
    }
    ```


## 响应示例<a name="section844195144916"></a>

**状态码：200**

成功响应示例

```
{
  "trace_id": "567e8537-a89c-13c3-a882-826321939651",
  "result":{
    "text": "欢迎使用语音云服务。",
    "score": 0.9,
    "word_info": [
            {
                "start_time": 150,
                "end_time": 570,
                "word": "欢迎"
            },
            {
                "start_time": 570,
                "end_time": 990,
                "word": "使用"
            },
            {
                "start_time": 990,
                "end_time": 1380,
                "word": "语音"
            },
            {
                "start_time": 1380,
                "end_time": 1590,
                "word": "云"
            },
            {
                "start_time": 1590,
                "end_time": 2070,
                "word": "服务"
            }
        ]
  }
}
```

**状态码：400**

失败响应示例

```
{ 
    "error_code":"SIS.0001", 
    "error_msg":"***" 
}
```

## 状态码<a name="section102191633184410"></a>

状态码请参见[状态码](状态码.md)。

## 错误码<a name="section040463810442"></a>

错误码请参见[错误码](错误码.md)。

