# 项目介绍<a name="ZH-CN_TOPIC_0000001054063255"></a>

## HiChain<a name="section19390142934814"></a>

**设备互联安全**

为了实现用户数据在设备互联场景下在各个设备之间的安全流转，需要保证设备之间相互正确可信，即设备和设备之间建立信任关系，并能够在验证信任关系后，搭建安全的连接通道，实现用户数据的安全传输。设备之间的信任关系在本文档中涉及IoT主控设备和IoT设备之间建立的可信关系。

![](http://tools.harmonyos.com/mirrors/hpm-image/hichainsdk_README/figures/zh-cn_image_0000001054308773.png)

-   **IoT设备互联安全**


设备互联支持基于系统的IoT设备（如AI音箱、智能家居、智能穿戴等设备）与IoT主控设备（手机、平板等）间建立点对点的信任关系，并在具备信任关系的设备间，搭建安全的连接通道，实现用户数据端到端加密传输。

-   **IoT主控设备的IoT业务身份标识**


IoT主控设备为不同的IoT设备管理业务生成不同的身份标识，形成不同IoT管理业务间的隔离，该标识用于IoT主控设备与IoT设备之间的认证以及通信。IoT业务身份标识为椭圆曲线公私钥对（Ed25519公私钥对）；

-   **IoT设备身份标识**


IoT设备会生成各自的设备身份标识，用来与IoT主控设备通信。该身份标识同样为椭圆曲线公私钥对（Ed25519公私钥对）；IoT设备私钥不出IoT设备，设备每次恢复出厂设置，会重置这个公私钥对。

上述身份标识可用于IoT主控设备与IoT设备间的安全通信：当IoT主控设备与IoT设备通过信任绑定流程交换业务身份标识或设备标识后，可以进行密钥协商并建立安全通信通道。

-   **设备间点对点的信任绑定**


IoT主控设备和IoT设备建立点对点信任关系的过程，实际上是相互交换IoT设备的身份标识的过程。

在点对点建立信任关系的过程中，用户需要在IoT主控设备上，输入IoT设备上提供的PIN码：对于有屏幕的设备，该PIN码动态生成；对于没有屏幕的设备，该PIN码由设备生产厂家预置；PIN码的展示形式，可以是一个用户可读的数字，也可以是一个二维码。随后，IoT主控设备和IoT设备间使用PAKE协议完成认证和会话密钥协商过程，并在此基础上，通过协商出的会话密钥加密传输通道用于交换双方设备的身份标识公钥。

**IoT主控设备与IoT设备间的通信安全**

当建立过信任关系的IoT主控设备与IoT设备间进行通信时，双方在完成上述信任关系绑定后，基于本地存储的对端身份公钥相互进行认证；在每次通信时基于STS协议完成双向身份认证以及会话密钥协商，之后设备使用此会话密钥加密双方设备间的传输通道。

