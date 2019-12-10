# 使用短语音识别<a name="sis_05_0050"></a>

## 前提条件<a name="section483618911279"></a>

-   确保已按照[配置Python环境](配置Python环境.md)配置完毕，Python SDK仅支持Python3。
-   确保已存在待识别的音频文件。如果需要请在下载的SDK压缩包中获取示例音频。
-   如果使用URL传入音频，需要将待识别的音频文件上传OBS，并获取URL，同时确保服务已授权访问OBS，可参考[配置OBS服务](https://support.huaweicloud.com/api-sis/sis_03_0047.html)。

## 初始化Client<a name="section590271313272"></a>

初始化AsrClient详见[表 AsrClient初始化参数](#table86254392424)。

**表 1**  AsrClient初始化参数

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

请求类为AsrRequest，详见[表 AsrRequest数据结构](#table45631337366)。

**表 3**  AsrRequest数据结构

<a name="table45631337366"></a>
<table><thead align="left"><tr id="row195631236363"><th class="cellrowborder" valign="top" width="12.82%" id="mcps1.2.5.1.1"><p id="p55640373620"><a name="p55640373620"></a><a name="p55640373620"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.940000000000001%" id="mcps1.2.5.1.2"><p id="p1456420383614"><a name="p1456420383614"></a><a name="p1456420383614"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.25%" id="mcps1.2.5.1.3"><p id="p1056412313618"><a name="p1056412313618"></a><a name="p1056412313618"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p1856419353613"><a name="p1856419353613"></a><a name="p1856419353613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row356384610110"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p13501183101819"><a name="p13501183101819"></a><a name="p13501183101819"></a>data</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p150110381818"><a name="p150110381818"></a><a name="p150110381818"></a>与url二选一</p>
</td>
<td class="cellrowborder" valign="top" width="12.25%" headers="mcps1.2.5.1.3 "><p id="p12500123131817"><a name="p12500123131817"></a><a name="p12500123131817"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p749933151815"><a name="p749933151815"></a><a name="p749933151815"></a>音频的Base64编码。</p>
</td>
</tr>
<tr id="row95641038369"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p114982361816"><a name="p114982361816"></a><a name="p114982361816"></a>url</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p1749711310187"><a name="p1749711310187"></a><a name="p1749711310187"></a>与data二选一</p>
</td>
<td class="cellrowborder" valign="top" width="12.25%" headers="mcps1.2.5.1.3 "><p id="p124967341818"><a name="p124967341818"></a><a name="p124967341818"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1691714229298"><a name="p1691714229298"></a><a name="p1691714229298"></a>音频的OBS链接，必须和data二选一。若两者都设置，则默认选择data作为传入音频。</p>
</td>
</tr>
<tr id="row65644313369"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p114924318181"><a name="p114924318181"></a><a name="p114924318181"></a>sample_rate</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p11491113151819"><a name="p11491113151819"></a><a name="p11491113151819"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.25%" headers="mcps1.2.5.1.3 "><p id="p17490113111810"><a name="p17490113111810"></a><a name="p17490113111810"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p124891636181"><a name="p124891636181"></a><a name="p124891636181"></a>采样率，8k或16k，默认8k。</p>
</td>
</tr>
<tr id="row65653319364"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p184891231183"><a name="p184891231183"></a><a name="p184891231183"></a>encode_type</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p18487232187"><a name="p18487232187"></a><a name="p18487232187"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.25%" headers="mcps1.2.5.1.3 "><p id="p1548612319184"><a name="p1548612319184"></a><a name="p1548612319184"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p104851732187"><a name="p104851732187"></a><a name="p104851732187"></a>音频格式，支持wav、mp3、wma，默认为空。</p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section2581112416279"></a>

Python SDK响应结果为Json格式，[表 响应结果数据结构](#table1917456103719)。

**表 4**  响应结果数据结构

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
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p91764613714"><a name="p91764613714"></a><a name="p91764613714"></a>详见<a href="#table14271914380">表 result数据结构</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 5**  result数据结构

<a name="table14271914380"></a>
<table><thead align="left"><tr id="row14279193812"><th class="cellrowborder" valign="top" width="12.82%" id="mcps1.2.5.1.1"><p id="p82817114384"><a name="p82817114384"></a><a name="p82817114384"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.940000000000001%" id="mcps1.2.5.1.2"><p id="p8287103811"><a name="p8287103811"></a><a name="p8287103811"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.25%" id="mcps1.2.5.1.3"><p id="p3287123816"><a name="p3287123816"></a><a name="p3287123816"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p728711386"><a name="p728711386"></a><a name="p728711386"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row728151133817"><td class="cellrowborder" valign="top" width="12.82%" headers="mcps1.2.5.1.1 "><p id="p328171113813"><a name="p328171113813"></a><a name="p328171113813"></a>words</p>
</td>
<td class="cellrowborder" valign="top" width="11.940000000000001%" headers="mcps1.2.5.1.2 "><p id="p1128171173814"><a name="p1128171173814"></a><a name="p1128171173814"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.25%" headers="mcps1.2.5.1.3 "><p id="p1528141143815"><a name="p1528141143815"></a><a name="p1528141143815"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1597344514384"><a name="p1597344514384"></a><a name="p1597344514384"></a>识别结果。</p>
</td>
</tr>
</tbody>
</table>

## 代码示例<a name="section338116313271"></a>

```
# -*- coding: utf-8 -*-

from huaweicloud_sis.client.asr_client import AsrClient
from huaweicloud_sis.bean.asr_request import AsrRequest
from huaweicloud_sis.bean.sis_config import SisConfig
from huaweicloud_sis.utils import io_utils
from huaweicloud_sis.exception.exceptions import ClientException
from huaweicloud_sis.exception.exceptions import ServerException
import json


def asr_short_example():
    """ 短语音识别demo """
    ak = ''         # 参考https://support.huaweicloud.com/sdkreference-sis/sis_05_0003.html
    sk = ''         # 参考https://support.huaweicloud.com/sdkreference-sis/sis_05_0003.html
    region = ''     # region，如cn-north-1
    path = ''       # 待识别音频的本地路径

    # step1 初始化客户端
    config = SisConfig()
    config.set_connect_timeout(5)       # 设置连接超时
    config.set_read_timeout(10)         # 设置读取超时
    # 设置代理，使用代理前一定要确保代理可用。 代理格式可为[host, port] 或 [host, port, username, password]
    # config.set_proxy(proxy)
    asr_client = AsrClient(ak, sk, region, sis_config=config)

    # step2 构造请求
    asr_request = AsrRequest()
    # 通过data传递音频或者obs url传递音频，二选一。
    data_str = io_utils.encode_file(path)
    asr_request.set_data(data_str)
    # 或者可以通过obs url传入连接, 当两者都设置，仅data会生效。
    # asr_request.set_url(obs_url)
    # 设置采样率, 8k or 16k，默认8k
    asr_request.set_sample_rate('8k')
    # 设置音频格式，可自动识别，支持格式详见api文档
    # asr_request.set_encode_type('')

    # step3 发送请求，返回结果，为json格式
    result = asr_client.get_asr_response(asr_request)
    print(json.dumps(result, indent=2, ensure_ascii=False))


if __name__ == '__main__':
    try:
        asr_short_example()
    except ClientException as e:
        print(e)
    except ServerException as e:
        print(e)

```

