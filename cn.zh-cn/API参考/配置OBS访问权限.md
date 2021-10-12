# 配置OBS访问权限<a name="sis_03_0047"></a>

## OBS服务<a name="section1928410143213"></a>

OBS全称Object Stroage Service（对象存储服务），提供海量、安全、高可靠、低成本的数据存储能力，可供用户存储任意类型和大小的数据。

EI企业智能服务对于图片、语音等多媒体文件支持直接使用华为云OBS服务的数据处理方式，以减少服务使用成本，降低服务的响应时长，提升服务使用的体验。如语音交互服务仅支持同一region下OBS的音频链接作为传入音频的URL，不支持互联网任意音频链接作为传入音频的URL。

考虑到数据的安全，语音交互服务无法直接获取到用户数据，需要用户开启公共读授权或者语音交互服务授权。

## 开启公共读授权<a name="section788312305717"></a>

开启公共授权，则数据全网可见，所有用户均可访问。

配置公共读可参考[配置标准桶策略](https://support.huaweicloud.com/usermanual-obs/obs_03_0142.html)，将桶策略设置为“公共读”。一般私密数据不建议用此方法。

目前仅支持访问用户个人OBS下的音频的链接，不支持读取其他用户公共读的链接。

## 开启语音交互服务授权<a name="section55616722819"></a>

开启公共读授权访问，对于敏感信息，如个人私有数据，存在泄漏风险。可考虑开启语音交互服务授权。

进入语音交互服务，单击“服务授权“，选择确认对象存储服务授权。

主帐号或者有Security Administrator权限的子帐号才可以创建委托。

## 上传音频<a name="section7284174493912"></a>

可参考OBS文档[上传对象](https://support.huaweicloud.com/qs-obs/obs_qs_0008.html)。

## 获取音频URL<a name="section83426149217"></a>

可参考OBS文档[获取对象URL](https://support.huaweicloud.com/sdk-java-devg-obs/obs_21_2111.html)。

