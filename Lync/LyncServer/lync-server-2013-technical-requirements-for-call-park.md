---
title: Lync Server 2013： 通話駐留的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff91e6b458d4c86f2246cff19e72e5221728e774
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中的通話駐留的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-07_

本節說明通話駐留的技術需求如下：

  - 硬體需求

  - 軟體需求

  - 連接埠需求

  - 音訊檔需求

<div>

## <a name="hardware-requirements"></a>硬體需求

通話駐留應用程式都有相同的硬體需求，作為前端伺服器。 如需硬體需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 的伺服器硬體平台](lync-server-2013-server-hardware-platforms.md)。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

通話駐留應用程式具有與前端伺服器相同的作業系統需求及軟體先決條件。 如需軟體需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。

部署通話駐留應用程式，其中的所有前端伺服器和 Standard Edition 伺服器必須執行 Windows Server 2008 R2 或 Microsoft 媒體 Foundation 執行 Windows Server 2012 的伺服器的伺服器已安裝 Windows Media Format Runtime 或Windows Server 2012 R2。 Windows Server 2008 R2、 Windows Media Format Runtime 被安裝 Windows 桌面體驗的一部分。 Windows Media Format Runtime] 或 [Microsoft 媒體 Foundation 才所需的 Windows Media Audio (.wma) 檔案的通話駐留播放音樂保留。

</div>

<div>

## <a name="port-requirements"></a>連接埠需求

通話駐留應用程式使用下列連接埠：

  - **連接埠 5075**   用於 SIP 聆聽要求。

<div>


> [!NOTE]  
> 此連接埠為預設設定，可使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 予以變更。 如需此 cmdlet 的詳細資訊，請參閱 < Lync Server 管理命令介面文件。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音訊檔案需求

通話駐留應用程式只支援 Windows Media Audio (.wma) 檔案的等候音樂保留。 您可以使用 Microsoft Expression Encoder 4 自訂等候音樂的檔案。 若要下載運算式編碼器 4，請參閱 「 運算式編碼器 4" [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)。 使用此工具可將檔案轉換成 .wma 格式。 通話駐留等候音樂檔案的建議格式為 Media Audio 9、44 kHz、16 位元、Mono、CBR、32 kbps。

<div>


> [!NOTE]  
> 轉換後的檔案只能以 16 kHz 音頻在電話中播放，即使檔案是以 44 kHz 音頻錄製也一樣。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

