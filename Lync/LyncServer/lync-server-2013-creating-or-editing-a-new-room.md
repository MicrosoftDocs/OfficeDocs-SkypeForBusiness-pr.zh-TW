---
title: Lync Server 2013：建立或編輯新聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f0abaf45034918873a17adc8a0f396ddc5d6fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516840"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>在 Lync Server 2013 中建立或編輯新聊天室

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-03-19_

設定 Persistent 聊天室通常是由使用者處理;Persistent Chat 系統管理員通常不會設定或管理聊天室。 管理聊天室的 Windows PowerShell Cmdlet 僅可供 **CsPersistentChatAdministrator** 系統管理員使用。

屬於任何特定類別之建立 **者** 的使用者可以使用 Lync 用戶端來建立及管理聊天室。 指定為特定聊天室管理員的使用者也可以執行會議室的持續管理，例如編輯會議室屬性或成員資格。

<div>


> [!TIP]  
> Persistent Chat 系統管理員也可以是建立者，且不受限於建立者的限制。



</div>

（選用）如果您是 Persistent Chat 系統管理員，可以使用使用者介面來建立及管理聊天室，而不是使用 Windows PowerShell Cmdlet。 若要這麼做，SIP 會為持久聊天伺服器啟用系統管理員，然後使用 Lync 用戶端來建立及管理聊天室。

如果您想要為使用者建立自訂聊天室管理工作流程，您可以設定 Persistent Chat Server 設定上的 **RoomManagementUrl** 屬性，將使用者重新導向至您在 Lync 用戶端的自訂解決方案。

如需使用 Windows PowerShell 命令列介面設定聊天室的詳細資訊，請參閱 [使用 windows PowerShell Cmdlet 設定 Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。

如需有關設定聊天室的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定聊天室](lync-server-2013-configure-rooms.md) 。

<div>


> [!NOTE]  
> Persistent Chat Server 可讓使用者為特定網站建立及管理聊天室。 不過，使用者無法在相同的拓撲中建立或管理其他網站上的聊天室。 請務必為您組織中的所有網站指定聊天室建立者和主管。



</div>

<div>


> [!NOTE]  
> 在 Lync Server Survivable Branch 裝置上的使用者無法建立新聊天室或查看現有聊天室的會議室卡片。



</div>

</div>

<span> </span>

</div>

</div>

</div>

