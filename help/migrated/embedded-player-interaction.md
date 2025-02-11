---
jcr-language: en_us
title: 嵌入式播放器的交互 API 文档
description: 了解用于在嵌入式播放器中侦听事件和触发操作的各种API
contentowner: chandrum
exl-id: 4734ecc1-cc8a-40b0-8997-32a31ec661ec
source-git-commit: 3d183dc40e4d1962d25160b74d8cf6cfa26e3171
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 69%

---

# 嵌入式播放器的交互 API 文档

Adobe Learning Manager 提供一个可集成至应用程序的库。 该库提供多种 API 来收听嵌入式播放器中的事件并触发操作。

通过使用提供的 API，您可以在播放器上执行播放、暂停和其他操作。

## 加载库

可在此[位置](https://cpcontents.adobe.com/public/publiccdn/playerInteractionLib.min.js)获取该库。

要加载该库，请按以下步骤操作：

1. 加载使用者应用程序中的 js 文件。
2. 加载该库时，系统会填充 window.cpPlayerLib。

>[!NOTE]
>
>如果您没有使用prod US，请根据您的环境设置参数cpPlayerLib.env和cpPlayerLib.sourceOrigin。

默认值为：

* window.cpPlayerLib.env = [https://learningmanager.adobe.com/app/player](https://learningmanager.adobe.com/app/player)；
* window.cpPlayerLib.sourceOrigin = &quot;[https://cpcontents.adobe.com](https://cpcontents.adobe.com/)&quot;；

### 可用方法

cpPlayerLib 库包含以下函数：

**startPlayer**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>startPlayer</td>
</tr>
<tr>
<td>描述</td>
<td>在应用程序中加载播放器。</td>
</tr>
<tr>
<td>参数</td>
<td><li>loId：学习对象 ID。</li><li>accountId：ALM 帐户的帐户 ID。</li><li>userId：用户 ID。</li><li>accessToken：访问令牌。</li><li>domRefId：div 容器 ID，必须在容器中渲染播放器。</li><li>onModuleLoaded：加载含有以下详细信息的模块时，系统将调用此函数。</li><br><li>contentType</li><li>loId</li><li>moduleId</li><li>completed</li><li>currentLanguage</li><li>availableLanguages</li><li>isCCAvailable</li><li>ccEnabled</li></br></td>
</tr>
<tr>
<td>返回</td>
<td>返回一个 promise 对象。 如果履行承诺，将通过播放器对象。</td>
</tr>
<tr>
<td>异常</td>
<td>这个承诺会导致例外。</td>
</tr>
<tr>
<td>示例代码</td>
<td>cpPlayerLib.startPlayer(loId， accountId， userId， accessToken， domRefId， onModuleLoaded)。then((playerObj) =&gt; {//playerObj具有与播放器交互的api}) &gt;</td>
</tr>
</tbody>
</table>

**getAllPlayers**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>getAllPlayers</td>
</tr>
<tr>
<td>描述</td>
<td>返回当前页面上的所有播放器对象。</td>
</tr>
<tr>
<td>参数</td>
<td>无</td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>cpPlayerLib.getAllPlayers()</td>
</tr>
</tbody>
</table>

**getPlayer**


<table>
<tbody>
<tr>
<td>方法名称</td>
<td>getPlayer</td>
</tr>
<tr>
<td>描述</td>
<td>返回具有指定学习对象ID的播放器对象。</td>
</tr>
<tr>
<td>参数</td>
<td><li>loId：学习对象 ID。</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>cpPlayerLib.getPlayer(loId)</td>
</tr>
</tbody>
</table>

**navigateToModule**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>navigateToModule</td>
</tr>
<tr>
<td>描述</td>
<td>导航至下一个模块。</td>
</tr>
<tr>
<td>参数</td>
<td><li>moduleId：模块ID。</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.navigateToModule(moduleID)</td>
</tr>
</tbody>
</table>

**下一个**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>next</td>
</tr>
<tr>
<td>描述</td>
<td>导航至下一个模块。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.next()</td>
</tr>
</tbody>
</table>

**上一个**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>previous</td>
</tr>
<tr>
<td>描述</td>
<td>导航至上一个模块。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.previous()</td>
</tr>
</tbody>
</table>

**切换目录**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>toggleTOC</td>
</tr>
<tr>
<td>描述</td>
<td>切换播放器上的目录面板。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.toggleTOC()</td>
</tr>
</tbody>
</table>

**toggleNotes**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>toggleNotes</td>
</tr>
<tr>
<td>描述</td>
<td>切换播放器上的备注面板。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.toggleNotes()</td>
</tr>
</tbody>
</table>

**toggleClosedCaption**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>toggleClosedCaption</td>
</tr>
<tr>
<td>描述</td>
<td>在播放器上切换隐藏字幕的显示。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.toggleClosedCaption()</td>
</tr>
</tbody>
</table>

**更改语言**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>changeLanguage</td>
</tr>
<tr>
<td>描述</td>
<td>更改播放器上的内容语言。</td>
</tr>
<tr>
<td>参数</td>
<td><li>language：要指定的语言代码。</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.changeLanguage("es")</td>
</tr>
</tbody>
</table>

**closePlayer**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>closePlayer</td>
</tr>
<tr>
<td>描述</td>
<td>关闭播放器并从页面中删除播放器。 </td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.closePlayer()</td>
</tr>
</tbody>
</table>

**togglePlayPause**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>togglePlayPause</td>
</tr>
<tr>
<td>描述</td>
<td>在播放器和暂停播放器上的内容之间切换。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.togglePlayPause()</td>
</tr>
</tbody>
</table>

**setVolume**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>setVolume</td>
</tr>
<tr>
<td>描述</td>
<td>设置播放器的音量。 该值必须介于 0 和 1 之间。</td>
</tr>
<tr>
<td>参数</td>
<td><li>volume：音量值。 有效范围为0-1。 </li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.setVolume(0.5)</td>
</tr>
</tbody>
</table>

**setPlayBackSpeed**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>setPlayBackSpeed</td>
</tr>
<tr>
<td>描述</td>
<td>在播放器中设置回放速度。</td>
</tr>
<tr>
<td>参数</td>
<td><li>speed：要指定的倍速值。 有效值为。25、.5、.75、1、1.25、1.5、1.75、2。</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.setPlayBackSpeed(1.25)</td>
</tr>
</tbody>
</table>

**查找**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>seek</td>
</tr>
<tr>
<td>描述</td>
<td>跳转至视频的任何时间点。</td>
</tr>
<tr>
<td>参数</td>
<td><li>time：要跳转的时间点。 时间点以秒为单位。</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.seek(50)</td>
</tr>
</tbody>
</table>

**转发**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>forward</td>
</tr>
<tr>
<td>描述</td>
<td>将视频快进 10 秒。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.forward()</td>
</tr>
</tbody>
</table>

**向后**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>backward</td>
</tr>
<tr>
<td>描述</td>
<td>将视频后退 10 秒。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.backward()</td>
</tr>
</tbody>
</table>

**navigateToPage**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>navigateToPage</td>
</tr>
<tr>
<td>描述</td>
<td>跳转至 PPT/PDF 的指定页面。</td>
</tr>
<tr>
<td>参数</td>
<td><li>pageNumber：要跳转到达的页码。</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.navigateToPage (5)</td>
</tr>
</tbody>
</table>

**下一页**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>nextPage</td>
</tr>
<tr>
<td>描述</td>
<td>跳转至 PPT/PDF 的下一页。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.nextPage()</td>
</tr>
</tbody>
</table>

**previousPage**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>previousPage</td>
</tr>
<tr>
<td>描述</td>
<td>跳转至 PPT/PDF 的上一页。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.previousPage()</td>
</tr>
</tbody>
</table>

**放大**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>zoomIn</td>
</tr>
<tr>
<td>描述</td>
<td>放大 PPT/PDF 中的内容。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.zoomIn()</td>
</tr>
</tbody>
</table>

**缩小**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>zoomOut</td>
</tr>
<tr>
<td>描述</td>
<td>缩小 PPT/PDF 中的内容。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.zoomOut()</td>
</tr>
</tbody>
</table>

**downloadJobAid**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>downloadjobaid</td>
</tr>
<tr>
<td>描述</td>
<td>从课程中下载工作辅助。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.downloadJobAid()</td>
</tr>
</tbody>
</table>

**toggleJobAidPullout**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>toggleJobAidPullout</td>
</tr>
<tr>
<td>描述</td>
<td>是否下载工作辅助。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.toggleJobAidPullout()</td>
</tr>
</tbody>
</table>

**全屏**

<table>
<tbody>
<tr>
<td>方法名称</td>
<td>全屏</td>
</tr>
<tr>
<td>描述</td>
<td>将播放器设置为全屏模式。</td>
</tr>
<tr>
<td>参数</td>
<td><li>无</li></td>
</tr>
</tr>
<tr>
<td>示例代码</td>
<td>playerObj.fullScreen()</td>
</tr>
</tbody>
</table>

## 事件列表

**onPlayerEvents(callBack)**

注册回调函数时，系统将在所有播放器事件中调用该函数。 事件名称如下：

* PLAY（视频/音频/CP）
* PAUSE（视频/音频/CP）
* TIMEUPDATE（视频/音频/CP）
* PAGECHANGE（PPT/PDF）
* NOTEADDED（所有内容）
* LAUNCHED（所有内容）
* STARTED（所有内容）
* COMPLETED（所有内容）
* PASSED（所有内容）
* FAILED（所有内容）

**onStreamingEvents(callBack)**

注册回调函数后，系统将在为跟踪用户活动而发送的所有播放器语句中调用该函数。
