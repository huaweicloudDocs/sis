# 配置Python环境<a name="sis_05_0056"></a>

## 前提条件<a name="section730963124"></a>

-   确保已安装Python3，目前Python SDK仅支持Python3。
-   确保已安装setuptools、requests、websocket-client。

## 操作步骤<a name="section225384318120"></a>

1.  下载Python SDK，通过**pip-list**命令查看安装包。若未安装，则执行以下命令：

    ```
    pip install setuptools
    pip install requests
    pip install websocket-client
    ```

2.  进入下载的Python SDK目录，在setup.py所在层目录执行 python setup.py install 命令，完成SDK安装。

