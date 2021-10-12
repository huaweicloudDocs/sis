# 获取SDK<a name="sis_05_0004"></a>

## 下载SDK包<a name="section10816155716519"></a>

语音交互SDK软件包获取请参见[表 下载SDK包](#table47650414583)。

示例音频参见[示例音频](示例音频.md)。

当您使用过旧版本的Java SDK时，需要注意旧版本的SDK依赖的jar包与新版本SDK的jar包有无冲突。新版本SDK升级日志为log4j2，同时java-sdk-core升级到3.0.12版本。

**表 1**  下载SDK包

<a name="table47650414583"></a>
<table><thead align="left"><tr id="row77666475813"><th class="cellrowborder" valign="top" width="27.88%" id="mcps1.2.3.1.1"><p id="p95715105588"><a name="p95715105588"></a><a name="p95715105588"></a>SDK语言</p>
</th>
<th class="cellrowborder" valign="top" width="72.11999999999999%" id="mcps1.2.3.1.2"><p id="p142462596274"><a name="p142462596274"></a><a name="p142462596274"></a>下载地址</p>
</th>
</tr>
</thead>
<tbody><tr id="row657924712520"><td class="cellrowborder" valign="top" width="27.88%" headers="mcps1.2.3.1.1 "><p id="p17834457192216"><a name="p17834457192216"></a><a name="p17834457192216"></a>Java</p>
</td>
<td class="cellrowborder" valign="top" width="72.11999999999999%" headers="mcps1.2.3.1.2 "><p id="p117021750810"><a name="p117021750810"></a><a name="p117021750810"></a><a href="https://sis-sdk-repository.obs.cn-north-1.myhuaweicloud.com/java/huaweicloud-java-sdk-sis-1.7.1.zip" target="_blank" rel="noopener noreferrer">https://sis-sdk-repository.obs.cn-north-1.myhuaweicloud.com/java/huaweicloud-java-sdk-sis-1.7.1.zip</a></p>
</td>
</tr>
<tr id="row104394851315"><td class="cellrowborder" valign="top" width="27.88%" headers="mcps1.2.3.1.1 "><p id="p4440986132"><a name="p4440986132"></a><a name="p4440986132"></a>Python</p>
</td>
<td class="cellrowborder" valign="top" width="72.11999999999999%" headers="mcps1.2.3.1.2 "><p id="p79074071417"><a name="p79074071417"></a><a name="p79074071417"></a><a href="https://sis-sdk-repository.obs.cn-north-1.myhuaweicloud.com/python/huaweicloud-python-sdk-sis-1.7.1.zip" target="_blank" rel="noopener noreferrer">https://sis-sdk-repository.obs.cn-north-1.myhuaweicloud.com/python/huaweicloud-python-sdk-sis-1.7.1.zip</a></p>
</td>
</tr>
<tr id="row0224740102017"><td class="cellrowborder" valign="top" width="27.88%" headers="mcps1.2.3.1.1 "><p id="p16224124052018"><a name="p16224124052018"></a><a name="p16224124052018"></a>IOS(OC)</p>
</td>
<td class="cellrowborder" valign="top" width="72.11999999999999%" headers="mcps1.2.3.1.2 "><p id="p142241740192016"><a name="p142241740192016"></a><a name="p142241740192016"></a><a href="https://sis-sdk-repository.obs.cn-north-1.myhuaweicloud.com/ios/huaweicloud-ios-sdk-sis-1.0.0.zip" target="_blank" rel="noopener noreferrer">https://sis-sdk-repository.obs.cn-north-1.myhuaweicloud.com/ios/huaweicloud-ios-sdk-sis-1.0.0.zip</a>(</p>
</td>
</tr>
</tbody>
</table>

## Maven引入SDK<a name="section107149208611"></a>

Java SDK也可以通过Maven引入，Maven引入后需要用户自己配置log4j2.xml，示例文件可参见[下载SDK包](#table47650414583)，操作如下。

1.  在工程的pom.xml文件里添加依赖。

    ```
            <dependency>
                <groupId>com.huawei.sis</groupId>
                <artifactId>huaweicloud-java-sdk-sis</artifactId>
                <version>1.7.1</version>
            </dependency>
    ```

2.  <a name="li113031542111013"></a>在工程的pom.xml文件里添加仓库，这里以仓库ID为“sis-repo“为例。

    仓库地址为：https://mirrors.huaweicloud.com/repository/maven/huaweicloudsdk。

    ```
        <repositories>
            <repository>
                <id>sis-repo</id>
                <name>Sis Release Repository</name>
                <url>https://mirrors.huaweicloud.com/repository/maven/huaweicloudsdk</url>
                <releases>
                    <enabled>true</enabled>
                </releases>
                <snapshots>
                    <enabled>false</enabled>
                </snapshots>
            </repository>
        </repositories>
    ```

3.  在Maven的配置文件setting.xml中，添加镜像。

    setting.xml文件一般存放在用户目录下，例如，Windows系统：“ C:\\Users\\$\{用户名\}\\.m2\\setting.xml“，$\{用户名\}要替换成个人电脑的用户名。

    ```
        <mirror>
            <id>huaweicloud</id>
            <name>Huaweicloud Repository</name>
            <url>https://mirrors.huaweicloud.com/repository/maven/</url>
            <mirrorOf>*,!sis-repo</mirrorOf>
        </mirror>
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >```
    ><mirrorOf>*,!sis-repo</mirrorOf>
    >```
    >配置镜像时，为使步骤[2](#li113031542111013)配置的仓库地址生效。需要在镜像设置中过滤掉这个仓库，从而镜像中的这个ID为“sis-repo“的仓库不会生效。


