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
ms.openlocfilehash: b7ab381a70a8a6d69170959fbaf488982887d765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中回應群組的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

本節說明回應群組應用程式的下列技術需求：

  - 硬體需求

  - 軟體需求

  - 埠需求

  - 音訊檔需求

  - 回應群組設定工具需求

<div>

## <a name="hardware-requirements"></a>硬體需求

回應群組應用程式具有與前端伺服器相同的硬體需求。 如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

回應群組應用程式具有與前端伺服器相同的作業系統需求和軟體先決條件。 如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。

如果您使用 Windows Media Audio （.wma）檔案來取得回應群組的音樂與宣告，所有前端伺服器或執行回應群組應用程式的標準版伺服器，都必須針對執行 Windows 的伺服器安裝 Windows Media 格式執行時間伺服器 2008 R2 或適用于執行 Windows Server 2012 或 Windows Server 2012 R2 之伺服器的 Microsoft 媒體基礎。 針對 Windows Server 2008 R2，Windows Media 格式執行時間已安裝為 Windows 桌面體驗的一部分。

如需音訊需求的詳細資訊，請參閱本節稍後的「音訊檔案需求」。

</div>

<div>

## <a name="port-requirements"></a>埠需求

回應群組應用程式使用下列埠：

  - ****    用於 SIP 偵聽要求的埠5071

  - ****    用於 interserver 通訊的埠8404
    
    <div>
    

    > [!NOTE]  
    > 這個埠是用於相符的服務，而且當回應群組應用程式部署在擁有多個前端伺服器的池中時，就是必要的。

    
    </div>

<div>


> [!NOTE]  
> 這些埠是預設的設定，您可以使用<STRONG>CsApplicationServer</STRONG> Cmdlet 變更這些設定。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音訊檔需求

回應群組應用程式支援波形（.wav）檔案格式和 Windows Media 音訊（.wma）檔案格式，以取得回應群組訊息、等候音樂或互動式語音回應（IVR）問題。

Windows Media 音訊檔案格式要求 Windows Media 格式執行時間已安裝在執行 Windows Server 2008 R2 和 Windows Server 2008 的前端伺服器上。 如需詳細資訊，請參閱本節前面的「軟體需求」。

<div>

## <a name="supported-wave-file-formats"></a>支援的 Wave 檔案格式

所有的 wave 檔案必須符合下列需求：

  - 8位或16位檔案

  - 線性脈衝程式碼調製（LPCM）、法律或 mu-定律格式

  - 單聲道或身歷聲

  - 4MB 或更低

為了獲得波形檔案的最佳效能，建議使用 16 kHz、單聲道、16位波檔案。

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>支援的 Windows Media 音訊檔案格式

如果您使用的是 Windows Media 音訊檔，請考慮使用低傳輸率，並在 [載入] 底下驗證系統的效能。

您可以使用 Microsoft Expression 編碼器4將檔案轉換成 Windows Media 音訊格式。 若要下載運算式編碼器4， [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)請參閱。

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>回應群組設定工具需求

[回應群組設定] 工具支援下表所述的作業系統與網頁瀏覽器混合。

<div>


> [!NOTE]  
> 支援32位或64位版本的作業系統。 僅支援32位版本的 Internet Explorer。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>支援的作業系統與網頁瀏覽器

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
<td><p>Windows Vista （含 Service Pack （SP）2）</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 （原生模式）</p>
<p>Internet Explorer 9 （原生模式）</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 Service Pack 1</p></td>
<td><p>Internet Explorer 8 （原生模式）</p>
<p>Internet Explorer 9 （原生模式）</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 （原生模式）</p>
<p>Internet Explorer 9 （原生模式）</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8 （原生模式）</p>
<p>Internet Explorer 9 （原生模式）</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>回應群組代理程式主控台

[代理程式主控台] 支援下表所述的作業系統與網頁瀏覽器混合。

<div>


> [!NOTE]  
> 支援32位或64位版本的作業系統。 僅支援32位版本的 Internet Explorer。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>支援的作業系統與網頁瀏覽器

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
<td><p>Windows Vista （含 Service Pack （SP）2）</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 （原生模式）</p>
<p>Internet Explorer 9 （原生模式）</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 Service Pack 1</p></td>
<td><p>Internet Explorer 8 （原生模式）</p>
<p>Internet Explorer 9 （原生模式）</p>
<p>Firefox 10。0</p>
<p>Chrome 18。0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 （原生模式）</p>
<p>Internet Explorer 9 （原生模式）</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8 （原生模式）</p>
<p>Internet Explorer 9 （原生模式）</p>
<p>Firefox 10。0</p>
<p>Chrome 18。0</p></td>
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

