# 项目介绍<a name="ZH-CN_TOPIC_0000001054438981"></a>

## 全球化子系统<a name="section11516137123416"></a>

OpenHarmony设备上用户可以设置语言和地区，规划中预计会支持68种语言；考虑到OpenHarmony设备间互联时，会涉及从OpenHarmony设备同步语言和地区设置到另一台OpenHarmony设备。因此需要考虑多语言资源回溯和多偏好语言支持的能力。

全球化资源管理模块主要提供语言资源回溯和多偏好语言支持的能力：

-   多语言资源回溯：系统在运行的时候会面临使用不同母语、来至不同地区各种文化背景的用户，如何用有限的翻译语言、最小的冗余来提供匹配该用户文化背景的翻译内容是资源加载中的一项核心功能，是系统支持多语言本地化的基本能力。

-   多偏好语言支持：系统可以根据用户设置的多个偏好语言来选择符合用户习惯的语言来显示，解决多母语用户尤其是像瑞士这样使用多母语用户的需求。

## 涉及仓<a name="section5889165803317"></a>

global\_frameworks\_resmgr\_lite

global\_interfaces\_innerkits\_resmgr\_lite

