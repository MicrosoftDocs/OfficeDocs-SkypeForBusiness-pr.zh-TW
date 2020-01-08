---
title: Lync Server 2013：建立或編輯新聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1442454b2afb129fda50d98ed17ccdc2c7ba35c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>在 Lync Server 2013 中建立或編輯新聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-03-19_

設定持久聊天室通常是由使用者處理;持續聊天管理員通常不會設定或管理聊天室。 管理聊天室的 Windows PowerShell Cmdlet 只提供給**CsPersistentChatAdministrator**管理員使用。

在任何指定類別中，擁有**者**的使用者都可以使用 Lync 用戶端來建立及管理會議室。 指定為特定聊天室之管理員的使用者也可以執行會議室的持續管理，例如編輯聊天室屬性或成員資格。

<div>


> [!TIP]  
> 持續性聊天管理員也可以是創意者，而且不受限於創意者所施加的限制。



</div>

或者，如果您是永久性聊天管理員，您可以使用使用者介面來建立和管理聊天室，而不是使用 Windows PowerShell Cmdlet。 若要執行這項作業，請使用 SIP 啟用持久聊天伺服器的管理員，然後使用 Lync 用戶端來建立及管理聊天室。

如果您想要為使用者建立自訂會議室管理工作流程，您可以在持續聊天伺服器設定上設定**RoomManagementUrl**屬性，將使用者從 Lync 用戶端重新導向至您的自訂方案。

如需使用 Windows PowerShell 命令列介面來設定聊天室的詳細資料，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。

如需有關設定聊天室的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定會議室](lync-server-2013-configure-rooms.md)。

<div>


> [!NOTE]  
> 持續聊天伺服器可讓使用者建立及管理特定網站的聊天室。 不過，使用者無法在同一拓朴中建立或管理其他網站上的聊天室。 請務必為貴組織中的所有網站指定聊天室製作者和管理員。



</div>

<div>


> [!NOTE]  
> 駐留在 Lync Server Survivable 分支裝置上的使用者無法建立新的聊天室，或無法查看現有聊天室的聊天室卡片。



</div>

</div>

<span> </span>

</div>

</div>

</div>

