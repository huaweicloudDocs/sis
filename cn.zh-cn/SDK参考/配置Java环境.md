# 配置Java环境<a name="sis_05_0041"></a>

1.  配置环境。

    在使用语音交互SDK时，需要准备的环境请参见[表 开发环境](#table330912111514)。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >目前Java SDK不支持在android中使用。

    **表 1**  开发环境

    <a name="table330912111514"></a>
    <table><thead align="left"><tr id="row8310119153"><th class="cellrowborder" valign="top" width="28.939999999999998%" id="mcps1.2.3.1.1"><p id="p72712122154"><a name="p72712122154"></a><a name="p72712122154"></a>准备项</p>
    </th>
    <th class="cellrowborder" valign="top" width="71.06%" id="mcps1.2.3.1.2"><p id="p227141241514"><a name="p227141241514"></a><a name="p227141241514"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row23100114150"><td class="cellrowborder" valign="top" width="28.939999999999998%" headers="mcps1.2.3.1.1 "><p id="p12271412101518"><a name="p12271412101518"></a><a name="p12271412101518"></a>操作系统</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.06%" headers="mcps1.2.3.1.2 "><p id="p1227212141512"><a name="p1227212141512"></a><a name="p1227212141512"></a>Windows系统，推荐Windows 7及以上版本。</p>
    </td>
    </tr>
    <tr id="row3310111153"><td class="cellrowborder" valign="top" width="28.939999999999998%" headers="mcps1.2.3.1.1 "><p id="p9336163271520"><a name="p9336163271520"></a><a name="p9336163271520"></a>JDK</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.06%" headers="mcps1.2.3.1.2 "><p id="p1027121251512"><a name="p1027121251512"></a><a name="p1027121251512"></a>Java开发环境的基本配置。版本要求：强烈推荐使用1.8版本。</p>
    </td>
    </tr>
    <tr id="row63104116153"><td class="cellrowborder" valign="top" width="28.939999999999998%" headers="mcps1.2.3.1.1 "><p id="p231013131512"><a name="p231013131512"></a><a name="p231013131512"></a>Eclipse</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.06%" headers="mcps1.2.3.1.2 "><p id="p20537144115167"><a name="p20537144115167"></a><a name="p20537144115167"></a>在<a href="https://www.eclipse.org/downloads/packages/" target="_blank" rel="noopener noreferrer">Eclipse官网</a>下载对应平台的Eclipse版本，比如：eclipse-jee-mars-R-win32-x86_64.zip。</p>
    </td>
    </tr>
    </tbody>
    </table>

2.  Eclipse导入SDK。
    1.  解压eclipse后，直接打开。同时[下载SDK](获取SDK.md)。
    2.  选择“Window -\> Preferences -\> Java -\> installed JREs“配置正确的JRE路径。
    3.  新建工程，在工程下建立一个文件（New -\> Folder），命名为lib。将下载的jar包拷贝至lib中。

        如果您是更新SDK，请检查与旧版本依赖的jar包有无版本冲突，否则会影响使用。

        例如：旧版本的SDK日志支持log4j 1xx版本，依赖jar包为log4j-1.2.17.jar、slf4j-api-1.7.21.jar、slf4j-log4j12-1.7.5.jar。新版本需要将其替换成log4j-api-2.12.0.jar、log4j-core-2.12.0.jar、log4j-slf4j-impl-2.12.0.jar、slf4j-api-1.7.30.jar。旧版本依赖java-sdk-core-2.0.1.jar，新版本依赖java-sdk-core-3.0.12.jar。

    4.  选中新建的工程，单击右键，下拉选择“Build Path -\> Configure Build Path“，在“ Java Build Path“  对话框中，单击“Libraries “页签，选择“Add JARs“。在打开的窗口中，选择刚放进lib的jar包。单击“OK“，导入完成。

        ![](figures/zh-cn_image_0205454864.png)



