---
title: Lync Server 2013：通話駐留的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c03c3b99e911766d2c60eec2a5515b3750d29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話駐留的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

本節說明通話駐留的下列技術需求：

  - 硬體需求

  - 軟體需求

  - 埠需求

  - 音訊檔需求

<div>

## <a name="hardware-requirements"></a>硬體需求

通話駐留應用程式具有與前端伺服器相同的硬體需求。 如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

通話駐留應用程式具有與前端伺服器相同的作業系統需求和軟體先決條件。 如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。

已部署通話駐留應用程式的所有前端伺服器和標準版伺服器，都必須針對執行 Windows Server 2008 R2 的伺服器安裝 Windows Media 格式執行時間，或是執行 Windows Server 2012 的伺服器的 Microsoft Media Foundation，或Windows Server 2012 R2。 針對 Windows Server 2008 R2，Windows Media 格式執行時間已安裝為 Windows 桌面體驗的一部分。 Windows media 音訊（.wma）檔案需要 windows Media Format 執行時間或 Microsoft 媒體基礎，這些檔案會通話駐留的暫停播放。

</div>

<div>

## <a name="port-requirements"></a>埠需求

通話駐留應用程式使用下列埠：

  - ****    用於 SIP 偵聽要求的埠5075。

<div>


> [!NOTE]  
> 此埠是預設設定，您可以使用<STRONG>CsApplicationServer</STRONG> Cmdlet 進行變更。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音訊檔需求

通話駐留應用程式只支援 Windows Media 音訊（.wma）檔案，以供等候音樂。 您可以使用 Microsoft Expression 編碼器4來自訂等候音樂的檔案。 若要下載 Expression 編碼器4，請參閱「運算式編碼器 4 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)」。 使用工具將檔案轉換為 .wma 格式。 通話駐留音樂保留盤案的建議格式是媒體音訊9、44 kHz、16位、單聲道、CBR、32 kbps。

<div>


> [!NOTE]  
> 已轉換的檔案只能在 16 kHz 的電話上播放，即使該檔案是在 44 kHz 錄製。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

