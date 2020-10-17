---
title: Lync Server 2013：回應群組的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b06176a033c90ff915fccb145dac3b3ed6fe87
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536120"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中回應群組的技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

本節說明回應群組應用程式的下列技術需求：

  - 硬體需求

  - 軟體需求

  - 連接埠需求

  - 音訊檔案需求

  - 回應群組設定工具需求

<div>

## <a name="hardware-requirements"></a>硬體需求

回應群組應用程式的硬體需求與前端伺服器相同。 如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

回應群組應用程式與前端伺服器具有相同的作業系統需求和軟體必要條件。 如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。

如果您使用 Windows Media Audio () 的回應群組音樂和宣告的檔案，所有執行回應群組應用程式的前端伺服器或 Standard Edition 伺服器，都必須針對執行 windows server 2008 R2 的伺服器及 Microsoft Media Foundation （執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器）安裝 Windows Media Format Runtime。 若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。

如需有關音訊需求的詳細資訊，請參閱本節稍後的＜音訊檔案需求＞。

</div>

<div>

## <a name="port-requirements"></a>連接埠需求

回應群組應用程式使用下列埠：

  - **埠 5071**    用於 SIP 聆聽要求

  - **埠 8404**    用於伺服器間通訊
    
    <div>
    

    > [!NOTE]  
    > 此埠用於配對服務，且在具有多部前端伺服器的集區中部署回應群組應用程式時是必要的。

    
    </div>

<div>


> [!NOTE]  
> 這些連接埠為預設設定，可使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 予以變更。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音訊檔案需求

回應群組應用程式支援波形 ( wav) 檔案格式和 Windows Media 音訊 ( 回應群組訊息、等候音樂或互動語音回應的檔案格式) 。 (IVR) 問題。

Windows Media 音訊檔案格式要求 Windows Media Format Runtime 已安裝在執行 Windows Server 2008 R2 和 Windows Server 2008 的前端伺服器上。 如需詳細資訊，請參閱本節稍早的＜軟體需求＞。

<div>

## <a name="supported-wave-file-formats"></a>支援的 Wave 檔案格式

所有 Wave 檔案必須符合下列需求：

  - 8 位元或 16 位元檔案

  - 線性脈衝代碼調變 (LPCM)，A-Law 或 mu-Law 格式

  - 單音或立體聲

  - 4MB 以下

為使 Wave 檔案有最佳表現，建議使用 16 kHz 單音的 16 位元 Wave 檔案。

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>支援的 Windows Media 音訊檔案格式

如果您使用 Windows Media 音訊檔案，請考慮使用低位元速率，並驗證系統承受負載時的效能。

您可以使用 Microsoft Expression Encoder 4 將檔案轉換成 Windows Media Audio 格式。 若要下載運算式編碼器4，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) 。

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>回應群組設定工具需求

回應群組設定工具支援下表所述之作業系統和網頁瀏覽器的組合。

<div>


> [!NOTE]  
> 支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>支援的作業系統和網頁瀏覽器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>作業系統</th>
<th>網頁瀏覽器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (原生模式)</p>
<p>Internet Explorer 9 (原生模式)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (原生模式)</p>
<p>Internet Explorer 9 (原生模式)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (原生模式)</p>
<p>Internet Explorer 9 (原生模式)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (原生模式)</p>
<p>Internet Explorer 9 (原生模式)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>回應群組代理程式主控台

代理程式主控台支援下表中所述之作業系統和網頁瀏覽器的組合。

<div>


> [!NOTE]  
> 支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>支援的作業系統和網頁瀏覽器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>作業系統</th>
<th>網頁瀏覽器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (原生模式)</p>
<p>Internet Explorer 9 (原生模式)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (原生模式)</p>
<p>Internet Explorer 9 (原生模式)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (原生模式)</p>
<p>Internet Explorer 9 (原生模式)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (原生模式)</p>
<p>Internet Explorer 9 (原生模式)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

