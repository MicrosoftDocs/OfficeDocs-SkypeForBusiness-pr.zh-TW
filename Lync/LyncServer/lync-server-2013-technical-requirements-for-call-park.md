---
title: Lync Server 2013：通話駐留的技術需求
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
ms.openlocfilehash: 8b5fb5f86dd575daf603bd0a21235184346bca05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533950"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話駐留的技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

本節說明通話駐留的下列技術需求：

  - 硬體需求

  - 軟體需求

  - 連接埠需求

  - 音訊檔需求

<div>

## <a name="hardware-requirements"></a>硬體需求

通話駐留應用程式的硬體需求與前端伺服器相同。 如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

通話駐留應用程式與前端伺服器具有相同的作業系統需求和軟體必要條件。 如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。

部署通話駐留應用程式的所有前端伺服器和 Standard Edition 伺服器，都必須為執行 windows Server 2008 R2 的伺服器安裝 Windows Media Format Runtime，或為執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器安裝 Microsoft Media Foundation。 若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。 Windows media Audio ( 的 windows Media Format Runtime 或 Microsoft Media Foundation 是必要的功能。) 通話駐留的檔案會對等候音樂播放。

</div>

<div>

## <a name="port-requirements"></a>連接埠需求

通話駐留應用程式使用下列埠：

  - **埠 5075**    用於 SIP 聆聽要求。

<div>


> [!NOTE]  
> 此連接埠為預設設定，可使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 予以變更。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音訊檔案需求

通話駐留應用程式僅支援 Windows Media Audio ( 的 wma) 檔案用於等候音樂。 您可以使用 Microsoft Expression Encoder 4 自訂等候音樂的檔案。 若要下載運算式編碼器4，請參閱的「運算式編碼器4」 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) 。 使用此工具可將檔案轉換成 .wma 格式。 通話駐留等候音樂檔案的建議格式為 Media Audio 9、44 kHz、16 位元、Mono、CBR、32 kbps。

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

