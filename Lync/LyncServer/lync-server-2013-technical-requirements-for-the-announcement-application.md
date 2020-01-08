---
title: Lync Server 2013：宣告應用程式的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的宣告應用程式的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

本節說明宣告應用程式的下列技術需求：

  - 硬體需求

  - 軟體需求

  - 埠需求

  - 音訊檔需求

<div>

## <a name="hardware-requirements"></a>硬體需求

宣告應用程式的硬體需求與前端伺服器相同。 如需硬體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。

</div>

<div>

## <a name="software-requirements"></a>軟體需求

宣告應用程式的作業系統需求和軟體先決條件與前端伺服器相同。 如需軟體需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)。

執行宣告應用程式的所有前端伺服器或標準版伺服器，都必須針對執行 Windows Server 2008 R2 的伺服器安裝 windows Media 格式執行時間，或是執行 Windows Server 2012 的伺服器的 Microsoft Media Foundation，或Windows Server 2012 R2。 針對 Windows Server 2008 R2，Windows Media 格式執行時間會安裝為 Windows 桌面體驗的一部分。 Windows Media 格式執行時間或 Microsoft 媒體基礎是 Windows Media 音訊（.wma）檔案所必需的，這些檔案是宣告應用程式在公告和音樂中播放的檔。

</div>

<div>

## <a name="port-requirements"></a>埠需求

宣告應用程式會使用下列埠：

  - ****    用於 SIP 偵聽要求的埠5071

<div>


> [!NOTE]  
> 這個埠是預設設定，您可以使用<STRONG>CsApplicationServer</STRONG> Cmdlet 進行變更。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音訊檔需求

宣告應用程式支援 Wave （.wav）檔案格式和 Windows Media 音訊（.wma）檔案格式，以供音樂和公告用。 宣告應用程式的音訊檔需求與回應群組應用程式相同。 如需詳細資訊，請參閱[Lync Server 2013 中的 [回應] 群組技術需求](lync-server-2013-technical-requirements-for-response-group.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

