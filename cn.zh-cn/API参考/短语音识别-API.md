# 短语音识别<a name="sis_03_0140"></a>

## 功能介绍<a name="zh-cn_topic_0092677182_sc853cdcbb0c440809e92e8a721604107"></a>

短语音识别服务可以针对用户上传的1分钟以内、不超过4MB的完整音频，识别出对应文字内容。

## URI<a name="zh-cn_topic_0092677182_s74e8a2cc17d0445ca0a9b5e8f9ab5a87"></a>

URI格式

POST /v1.0/voice/asr/sentence

## 请求消息<a name="zh-cn_topic_0092677182_sf6f2e23507d14d44bc22f2325c4ae8e6"></a>

请求参数说明请参见[表 请求参数说明](#zh-cn_topic_0092677182_table23692658184839)。

**表 1**  请求参数说明

<a name="zh-cn_topic_0092677182_table23692658184839"></a>
<table><thead align="left"><tr id="zh-cn_topic_0092677182_row34838322184839"><th class="cellrowborder" valign="top" width="18.7%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0092677182_p20300290184839"><a name="zh-cn_topic_0092677182_p20300290184839"></a><a name="zh-cn_topic_0092677182_p20300290184839"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="21.02%" id="mcps1.2.5.1.2"><p id="zh-cn_topic_0092677182_p33710765184839"><a name="zh-cn_topic_0092677182_p33710765184839"></a><a name="zh-cn_topic_0092677182_p33710765184839"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.840000000000002%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0092677182_p46217449184839"><a name="zh-cn_topic_0092677182_p46217449184839"></a><a name="zh-cn_topic_0092677182_p46217449184839"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.440000000000005%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0092677182_p52625885184839"><a name="zh-cn_topic_0092677182_p52625885184839"></a><a name="zh-cn_topic_0092677182_p52625885184839"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0092677182_row16332922184839"><td class="cellrowborder" valign="top" width="18.7%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0092677182_p3331856184839"><a name="zh-cn_topic_0092677182_p3331856184839"></a><a name="zh-cn_topic_0092677182_p3331856184839"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="21.02%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0092677182_p1444894184839"><a name="zh-cn_topic_0092677182_p1444894184839"></a><a name="zh-cn_topic_0092677182_p1444894184839"></a>与url二选一</p>
</td>
<td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0092677182_p49927556184839"><a name="zh-cn_topic_0092677182_p49927556184839"></a><a name="zh-cn_topic_0092677182_p49927556184839"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.440000000000005%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0092677182_p17600235184839"><a name="zh-cn_topic_0092677182_p17600235184839"></a><a name="zh-cn_topic_0092677182_p17600235184839"></a>语音数据，音频数据转化为base64编码，要求base64编码后大小不超过4M，音频时长不超过1分钟。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092677182_row58099800184839"><td class="cellrowborder" valign="top" width="18.7%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0092677182_p12778577184839"><a name="zh-cn_topic_0092677182_p12778577184839"></a><a name="zh-cn_topic_0092677182_p12778577184839"></a>url</p>
</td>
<td class="cellrowborder" valign="top" width="21.02%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0092677182_p28431792184839"><a name="zh-cn_topic_0092677182_p28431792184839"></a><a name="zh-cn_topic_0092677182_p28431792184839"></a>与data二选一</p>
</td>
<td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0092677182_p21273804184839"><a name="zh-cn_topic_0092677182_p21273804184839"></a><a name="zh-cn_topic_0092677182_p21273804184839"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.440000000000005%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0092677182_p1373284134519"><a name="zh-cn_topic_0092677182_p1373284134519"></a><a name="zh-cn_topic_0092677182_p1373284134519"></a>语音的URL路径，目前支持华为云上OBS提供的公共读URL或者已授权访问URL。OBS服务配置请参见<a href="配置OBS服务.md">配置OBS服务</a>。OBS的region要和请求服务的region保持一致，region不一致则OBS不可用，即使OBS是公开访问权限。</p>
<p id="zh-cn_topic_0092677182_p45456524184839"><a name="zh-cn_topic_0092677182_p45456524184839"></a><a name="zh-cn_topic_0092677182_p45456524184839"></a>出于安全的考虑，当前服务不支持从公网上任意URL读取数据。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092677182_row45968107184839"><td class="cellrowborder" valign="top" width="18.7%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0092677182_p53136159184839"><a name="zh-cn_topic_0092677182_p53136159184839"></a><a name="zh-cn_topic_0092677182_p53136159184839"></a>encode_type</p>
</td>
<td class="cellrowborder" valign="top" width="21.02%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0092677182_p9061609184839"><a name="zh-cn_topic_0092677182_p9061609184839"></a><a name="zh-cn_topic_0092677182_p9061609184839"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0092677182_p62901748184839"><a name="zh-cn_topic_0092677182_p62901748184839"></a><a name="zh-cn_topic_0092677182_p62901748184839"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.440000000000005%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0092677182_p37229860191533"><a name="zh-cn_topic_0092677182_p37229860191533"></a><a name="zh-cn_topic_0092677182_p37229860191533"></a>支持语音的格式为wav、mp3、wma、amr、ac3、ogg、aac等格式。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092677182_row62757445184839"><td class="cellrowborder" valign="top" width="18.7%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0092677182_p11059787184839"><a name="zh-cn_topic_0092677182_p11059787184839"></a><a name="zh-cn_topic_0092677182_p11059787184839"></a>sample_rate</p>
</td>
<td class="cellrowborder" valign="top" width="21.02%" headers="mcps1.2.5.1.2 "><p id="zh-cn_topic_0092677182_p23427563184839"><a name="zh-cn_topic_0092677182_p23427563184839"></a><a name="zh-cn_topic_0092677182_p23427563184839"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.840000000000002%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0092677182_p18584431184839"><a name="zh-cn_topic_0092677182_p18584431184839"></a><a name="zh-cn_topic_0092677182_p18584431184839"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.440000000000005%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0092677182_p12943151193514"><a name="zh-cn_topic_0092677182_p12943151193514"></a><a name="zh-cn_topic_0092677182_p12943151193514"></a>语音的采样率。除wav之外的其它语音格式无须该参数。</p>
<p id="zh-cn_topic_0092677182_p75001646624"><a name="zh-cn_topic_0092677182_p75001646624"></a><a name="zh-cn_topic_0092677182_p75001646624"></a>对于wav优先支持如下采样率：</p>
<a name="zh-cn_topic_0092677182_ul1816971513311"></a><a name="zh-cn_topic_0092677182_ul1816971513311"></a><ul id="zh-cn_topic_0092677182_ul1816971513311"><li>8k：代表8KHz，默认为8KHz。</li><li>16k：代表16KHz。</li></ul>
</td>
</tr>
</tbody>
</table>

## 响应消息<a name="zh-cn_topic_0092677182_s29178f76a01d4a548d9dbabfac7e28d5"></a>

响应参数说明请参见[表 响应参数说明](#zh-cn_topic_0092677182_t8e502a083db5405898a82a44a49d25ec)。

**表 2**  响应参数说明

<a name="zh-cn_topic_0092677182_t8e502a083db5405898a82a44a49d25ec"></a>
<table><thead align="left"><tr id="zh-cn_topic_0092677182_r4e9743131010456a8ea55bfa0696b4bc"><th class="cellrowborder" valign="top" width="20.549999999999997%" id="mcps1.2.5.1.1"><p id="zh-cn_topic_0092677182_af25b5162d355432ca1e1858524349d7c"><a name="zh-cn_topic_0092677182_af25b5162d355432ca1e1858524349d7c"></a><a name="zh-cn_topic_0092677182_af25b5162d355432ca1e1858524349d7c"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="7.5200000000000005%" id="mcps1.2.5.1.2"><p id="p135561852161619"><a name="p135561852161619"></a><a name="p135561852161619"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.95%" id="mcps1.2.5.1.3"><p id="zh-cn_topic_0092677182_aa09c864dfa2f4def9c0288179c55e08e"><a name="zh-cn_topic_0092677182_aa09c864dfa2f4def9c0288179c55e08e"></a><a name="zh-cn_topic_0092677182_aa09c864dfa2f4def9c0288179c55e08e"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="52.980000000000004%" id="mcps1.2.5.1.4"><p id="zh-cn_topic_0092677182_a13a080ffac1a4cd1bd2d6543398f7b46"><a name="zh-cn_topic_0092677182_a13a080ffac1a4cd1bd2d6543398f7b46"></a><a name="zh-cn_topic_0092677182_a13a080ffac1a4cd1bd2d6543398f7b46"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0092677182_r600fd27821ac4517abd52e4342e55383"><td class="cellrowborder" valign="top" width="20.549999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0092677182_a0417d08c87c548309f0a2e6ef7885f64"><a name="zh-cn_topic_0092677182_a0417d08c87c548309f0a2e6ef7885f64"></a><a name="zh-cn_topic_0092677182_a0417d08c87c548309f0a2e6ef7885f64"></a>result</p>
</td>
<td class="cellrowborder" valign="top" width="7.5200000000000005%" headers="mcps1.2.5.1.2 "><p id="p4556752161614"><a name="p4556752161614"></a><a name="p4556752161614"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.95%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p784395517545"><a name="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p784395517545"></a><a name="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p784395517545"></a>Object</p>
</td>
<td class="cellrowborder" valign="top" width="52.980000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p984385515416"><a name="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p984385515416"></a><a name="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p984385515416"></a>调用成功时表示调用结果，请参考<a href="#table15126431151618">表 result数据结构说明</a>。</p>
<p id="zh-cn_topic_0092677182_ad86b3abaf3014f43bf348ca78debef02"><a name="zh-cn_topic_0092677182_ad86b3abaf3014f43bf348ca78debef02"></a><a name="zh-cn_topic_0092677182_ad86b3abaf3014f43bf348ca78debef02"></a>调用失败时无此字段。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092677182_r0b3635c29062414a8f25daa5776ff0b4"><td class="cellrowborder" valign="top" width="20.549999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0092677182_a9b879241c7874ed78d27d3b8dc6d6834"><a name="zh-cn_topic_0092677182_a9b879241c7874ed78d27d3b8dc6d6834"></a><a name="zh-cn_topic_0092677182_a9b879241c7874ed78d27d3b8dc6d6834"></a>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="7.5200000000000005%" headers="mcps1.2.5.1.2 "><p id="p1855612522160"><a name="p1855612522160"></a><a name="p1855612522160"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.95%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0092677182_a5f7eb1bbc9854a1fb29cc78cfb848589"><a name="zh-cn_topic_0092677182_a5f7eb1bbc9854a1fb29cc78cfb848589"></a><a name="zh-cn_topic_0092677182_a5f7eb1bbc9854a1fb29cc78cfb848589"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="52.980000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0092677182_p1765688919540"><a name="zh-cn_topic_0092677182_p1765688919540"></a><a name="zh-cn_topic_0092677182_p1765688919540"></a>调用失败时的错误码，具体请参见<a href="错误码.md">错误码</a>。</p>
<p id="zh-cn_topic_0092677182_p2092187919540"><a name="zh-cn_topic_0092677182_p2092187919540"></a><a name="zh-cn_topic_0092677182_p2092187919540"></a>调用成功时无此字段。</p>
</td>
</tr>
<tr id="zh-cn_topic_0092677182_rcfa3fb30dc8044aa84943fa7605471bf"><td class="cellrowborder" valign="top" width="20.549999999999997%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0092677182_a63756edeaf914bb6a76bf251a59f1b6a"><a name="zh-cn_topic_0092677182_a63756edeaf914bb6a76bf251a59f1b6a"></a><a name="zh-cn_topic_0092677182_a63756edeaf914bb6a76bf251a59f1b6a"></a>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="7.5200000000000005%" headers="mcps1.2.5.1.2 "><p id="p2556125231619"><a name="p2556125231619"></a><a name="p2556125231619"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.95%" headers="mcps1.2.5.1.3 "><p id="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p188443551548"><a name="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p188443551548"></a><a name="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p188443551548"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="52.980000000000004%" headers="mcps1.2.5.1.4 "><p id="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p684415559546"><a name="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p684415559546"></a><a name="zh-cn_topic_0092677182_zh-cn_topic_0072646061_p684415559546"></a>调用失败时的错误信息。</p>
<p id="zh-cn_topic_0092677182_ac82fbd70c5bc4bbd996fdee0e81ad640"><a name="zh-cn_topic_0092677182_ac82fbd70c5bc4bbd996fdee0e81ad640"></a><a name="zh-cn_topic_0092677182_ac82fbd70c5bc4bbd996fdee0e81ad640"></a>调用成功时无此字段。</p>
</td>
</tr>
</tbody>
</table>

**表 3**  result数据结构说明

<a name="table15126431151618"></a>
<table><thead align="left"><tr id="row1712703121614"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p15963110111813"><a name="p15963110111813"></a><a name="p15963110111813"></a>参数名</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.2"><p id="p996314015188"><a name="p996314015188"></a><a name="p996314015188"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="p179630041813"><a name="p179630041813"></a><a name="p179630041813"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="p17963190191811"><a name="p17963190191811"></a><a name="p17963190191811"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row212713161616"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1025163717172"><a name="p1025163717172"></a><a name="p1025163717172"></a>words</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p19251937131715"><a name="p19251937131715"></a><a name="p19251937131715"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p325143713174"><a name="p325143713174"></a><a name="p325143713174"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p102512372179"><a name="p102512372179"></a><a name="p102512372179"></a>ASR识别的文字内容，编码格式为UTF-8。</p>
</td>
</tr>
</tbody>
</table>

## 示例<a name="zh-cn_topic_0092677182_section1485471461114"></a>

-   请求示例\(方式一，使用语音的BASE64编码\)

    ```
    POST https://{endpoint}/v1.0/voice/asr/sentence
       
    Request Header:  
    Content-Type:application/json
    X-Auth-Token: MIINRwYJKoZIhvcNAQcCoIINODCCDTQCAQExDTALBglghkgBZQMEAgEwgguVBgkqhkiG...   
    
    Request Body:
    {
     "data":"/+MgxAAUeHpMAUkQAANhuRACAIAgKHKQmRisVo0aNAgQIIQyCgGBiwfB8H4IAgCAJg+D4Ph+IAQBBywfB8HwQDGAwfB8HwfBA5gM/L...",
      "encode_type": "wav",
      "sample_rate": "8k"
    }  
    ```

-   请求示例\(方式二，使用语音片段的URL\)

    ```
    POST https://{endpoint}/v1.0/voice/asr/sentence
       
    Request Header:  
    Content-Type:application/json
    X-Auth-Token: MIINRwYJKoZIhvcNAQcCoIINODCCDTQCAQExDTALBglghkgBZQMEAgEwgguVBgkqhkiG...   
    
    Request Body:
    {
      "url":"https://BucketName.obs.myhwclouds.com/ObjectName",
      "encode_type": "wav",
      "sample_rate": "8k"
    } 
    ```

-   成功响应示例

    ```
    {
      "result":{
       "words":"欢迎使用华为云。"
      }
    }
    ```

-   失败响应示例

    ```
    {
        "error_code": "SIS.0005",
        "error_msg": "The service does not exist."
    }
    ```


## 状态码<a name="section102191633184410"></a>

状态码请参见[状态码](状态码.md)。

## 错误码<a name="section040463810442"></a>

错误码请参见[错误码](错误码.md)。

