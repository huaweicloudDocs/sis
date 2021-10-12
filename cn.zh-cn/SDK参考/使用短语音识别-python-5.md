# 热词管理<a name="sis_05_0065"></a>

## 前提条件<a name="section483618911279"></a>

-   确保已按照[配置Python环境](配置Python环境.md)配置完毕，Python SDK仅支持Python3。

## 初始化Client<a name="section590271313272"></a>

初始化HotWordClient，详见[表 HotWordClient初始化参数](#table86254392424)。

**表 1**  HotWordClient初始化参数

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
<td class="cellrowborder" valign="top" width="62.68%" headers="mcps1.2.5.1.4 "><p id="p96261339124216"><a name="p96261339124216"></a><a name="p96261339124216"></a>区域，如：cn-north-4。具体请参考<a href="https://support.huaweicloud.com/api-sis/sis_03_0004.html" target="_blank" rel="noopener noreferrer">终端节点</a>。</p>
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

## 请求参数<a name="section91131147173710"></a>

请求类为HotWordRequest，详见[表3](#table45631337366)。

**表 3**  HotWordRequest

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
<tbody><tr id="row95641038369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p174328142585"><a name="p174328142585"></a><a name="p174328142585"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p0431131415582"><a name="p0431131415582"></a><a name="p0431131415582"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p1430181435815"><a name="p1430181435815"></a><a name="p1430181435815"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1942912148588"><a name="p1942912148588"></a><a name="p1942912148588"></a><span>热词表名，创建时不可重复。内容限制为字母，数字，下中划线和井号，长度不超过32字节。</span></p>
</td>
</tr>
<tr id="row188101130112520"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p13810230162515"><a name="p13810230162515"></a><a name="p13810230162515"></a>language</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p11810183012259"><a name="p11810183012259"></a><a name="p11810183012259"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p281033092518"><a name="p281033092518"></a><a name="p281033092518"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1939951411556"><a name="p1939951411556"></a><a name="p1939951411556"></a>热词表语言类型，目前支持汉语普通话<span class="parmname" id="parmname996733813552"><a name="parmname996733813552"></a><a name="parmname996733813552"></a>“chinese_mandarin”</span>。</p>
</td>
</tr>
<tr id="row923841510270"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p1323891592720"><a name="p1323891592720"></a><a name="p1323891592720"></a>contents</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p7238615162712"><a name="p7238615162712"></a><a name="p7238615162712"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p1723814153275"><a name="p1723814153275"></a><a name="p1723814153275"></a>Array of String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1863034715117"><a name="p1863034715117"></a><a name="p1863034715117"></a>热词库，单词库支持热词数上限1024。单个热词长度上限32字节。</p>
</td>
</tr>
<tr id="row65644313369"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p11536135185115"><a name="p11536135185115"></a><a name="p11536135185115"></a>description</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p1263715398423"><a name="p1263715398423"></a><a name="p1263715398423"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p165351335175117"><a name="p165351335175117"></a><a name="p165351335175117"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p1898164755418"><a name="p1898164755418"></a><a name="p1898164755418"></a><span>热词表描述，长度不超过255字节。</span></p>
</td>
</tr>
</tbody>
</table>

## 响应参数<a name="section82994143818"></a>

创建热词响应参数为Json格式，详见[表4](#table3716134222110)。

**表 4**  创建热词响应

<a name="table3716134222110"></a>
<table><thead align="left"><tr id="row871617429214"><th class="cellrowborder" valign="top" width="13.950000000000001%" id="mcps1.2.5.1.1"><p id="p17716174217213"><a name="p17716174217213"></a><a name="p17716174217213"></a>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="10.16%" id="mcps1.2.5.1.2"><p id="p11716144292113"><a name="p11716144292113"></a><a name="p11716144292113"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="12.9%" id="mcps1.2.5.1.3"><p id="p2716184217216"><a name="p2716184217216"></a><a name="p2716184217216"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="62.99%" id="mcps1.2.5.1.4"><p id="p1671615421213"><a name="p1671615421213"></a><a name="p1671615421213"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row67162428219"><td class="cellrowborder" valign="top" width="13.950000000000001%" headers="mcps1.2.5.1.1 "><p id="p9716842172113"><a name="p9716842172113"></a><a name="p9716842172113"></a>vocabulary_id</p>
</td>
<td class="cellrowborder" valign="top" width="10.16%" headers="mcps1.2.5.1.2 "><p id="p12716134217217"><a name="p12716134217217"></a><a name="p12716134217217"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="12.9%" headers="mcps1.2.5.1.3 "><p id="p2716542112110"><a name="p2716542112110"></a><a name="p2716542112110"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="62.99%" headers="mcps1.2.5.1.4 "><p id="p2716134215210"><a name="p2716134215210"></a><a name="p2716134215210"></a><span>调用成功则返回热词表ID。</span></p>
</td>
</tr>
</tbody>
</table>

## 代码示例<a name="section192369731611"></a>

```
# -*- coding: utf-8 -*-

from huaweicloud_sis.client.hot_word_client import HotWordClient
from huaweicloud_sis.bean.hot_word_request import HotWordRequest
from huaweicloud_sis.exception.exceptions import ClientException
from huaweicloud_sis.exception.exceptions import ServerException
from huaweicloud_sis.bean.sis_config import SisConfig
import json

# 鉴权参数
ak = ''             
sk = ''             
region = ''         # region，如cn-north-4
project_id = ''     # 同region一一对应。登录管理控制台，鼠标移动到右上角的用户名上，在下拉列表中选择我的凭证，在我的凭证页面，在项目列表中查看项目id。多项目时，展开“所属区域”，从“项目ID”列获取子项目ID。


# 热词参数
name = ''           # 创建热词时，需要保证name在此之前没有被创建使用过。如 test1
word_list = list()  # 用于存放热词表。每个热词表最多可以存放1024个热词。如["计算机", "网络"]
vocabulary_id = ''  # 用于更新指定热词表id信息，查询指定热词表id信息，删除指定热词表id信息。使用前要保证热词表id存在，否则就不要使用。


def hot_word_example():
    """
        1. 热词使用包含创建、更新、查询、删除等，一个用户可以创建多个热词表，一个热词表可以包含多个热词。一个vocabulary_id对应一个热词表。
        2. 目前支持一个用户最多创建10个热词表，一个热词表最多包含1024个热词。
        3. 热词可在一句话识别、录音文件识别、实时语音识别使用。例如将地名和人名作为热词，则语音可以准确识别出人名和地名。
    :return: 无
    """
    # 初始化客户端
    config = SisConfig()
    config.set_connect_timeout(10)       # 设置连接超时
    config.set_read_timeout(10)         # 设置读取超时
    # 设置代理，使用代理前一定要确保代理可用。 代理格式可为[host, port] 或 [host, port, username, password]
    # config.set_proxy(proxy)
    hot_word_client = HotWordClient(ak, sk, region, project_id, sis_config=config)

    # option 1 创建热词表
    word_list.append('测试')
    create_request = HotWordRequest(name, word_list)
    # 可选，热词语言，目前仅支持中文 chinese_mandarin。
    create_request.set_language('chinese_mandarin')
    # 可选，热词表描述信息
    create_request.set_description('test')
    create_result = hot_word_client.create(create_request)
    # 返回结果为json格式
    print('成功创建热词表')
    print(json.dumps(create_result, indent=2, ensure_ascii=False))

    # option 2 根据热词表id 更新热词表。新的热词表会替换旧的热词表。使用前需确保热词表id已存在。
    word_list.append('计算机')
    update_request = HotWordRequest('test2', word_list)
    update_result = hot_word_client.update(update_request, vocabulary_id)
    # 返回结果为json格式
    print('成功更新热词表', vocabulary_id)
    print(json.dumps(update_result, indent=2, ensure_ascii=False))

    # option 3 查看热词表列表
    query_list_result = hot_word_client.query_list()
    print(json.dumps(query_list_result, indent=2, ensure_ascii=False))

    # option 4 根据热词表id查询具体热词表信息，使用前需确保热词表id已存在。
    query_result = hot_word_client.query_by_vocabulary_id(vocabulary_id)
    print(json.dumps(query_result, indent=2, ensure_ascii=False))

    # option 5 根据热词表id删除热词表，使用前需确保热词表id已存在。
    delete_result = hot_word_client.delete(vocabulary_id)
    if delete_result is None:
        print('成功删除热词表', vocabulary_id)
    else:
        print(json.dumps(delete_result, indent=2, ensure_ascii=False))


if __name__ == '__main__':
    try:
        hot_word_example()
    except ClientException as e:
        print(e)
    except ServerException as e:
        print(e)
```

