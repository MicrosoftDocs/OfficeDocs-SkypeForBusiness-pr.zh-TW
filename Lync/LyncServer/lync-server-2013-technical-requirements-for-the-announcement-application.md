---
title: Lync Server 2013：宣告應用程式的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54371acb29bcc7d9b6581cbfd26199888dcfe893
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536100"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中宣告應用程式的技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

本節說明宣告應用程式的下列技術需求：

  - 硬體需求

  - 軟體需求

  - 連接埠需求

  - 音訊檔需求

<div>

## <a name="hardware-requirements"></a>硬體需求

宣告應用程式的硬體需求與前端伺服器相同。 如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

宣告應用程式與前端伺服器具有相同的作業系統需求和軟體必要條件。 如需軟體需求的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。

執行宣告應用程式的所有前端伺服器或 Standard Edition 伺服器，都必須為執行 windows Server 2008 R2 的伺服器安裝 Windows Media Format Runtime，或為執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器安裝 Microsoft Media Foundation。 若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。 Windows media Audio ( 的 windows media Format Runtime 或 Microsoft Media Foundation 是 Windows Media Audio 的必要功能。宣告應用程式針對宣告和音樂所播放的 wma) 檔案。

</div>

<div>

## <a name="port-requirements"></a>連接埠需求

宣告應用程式使用下列埠：

  - **埠 5071**    用於 SIP 聆聽要求

<div>


> [!NOTE]  
> 此埠是預設設定，您可以使用 <STRONG>Set-CsApplicationServer</STRONG> Cmdlet 進行變更。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音訊檔案需求

宣告應用程式支援波形 ( .wav) 檔案格式和 Windows Media 音訊)  ( 的音樂和宣告的檔案格式。 宣告應用程式的音訊檔需求與回應群組應用程式相同。 如需詳細資訊，請參閱 [Lync Server 2013 中的回應群組技術需求](lync-server-2013-technical-requirements-for-response-group.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

