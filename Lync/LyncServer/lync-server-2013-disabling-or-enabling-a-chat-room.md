---
title: Lync Server 2013：停用或啟用聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>在 Lync Server 2013 中停用或啟用聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

如果永久聊天室的主題已不再相關，您可以停用聊天室，讓使用者無法使用該聊天室。 停用聊天室時，所有成員都會立即中斷與聊天室的連線。 停用聊天室之後，使用者就無法在聊天室搜尋中重新加入或尋找。

停用聊天室可在稍後由持續聊天管理員啟用。 如果聊天室停用，則會保留其成員資格清單及其他設定。 如果您再次啟用聊天室，就不需要手動重新建立設定。

如果聊天室的歷程記錄持續存在（聊天室記錄暫留是在類別中套用至所有聊天室的選擇性設定，預設值是它會保留，但若要將類別的 [**啟用聊天記錄**] 設定為 false，則會在停用聊天室時保留該內容。 不過，在聊天室保持在停用狀態時，搜尋中不會顯示該內容。 如果您稍後啟用聊天室，使用者就可以搜尋在停用聊天室之前所張貼的訊息。

如需使用 Windows PowerShell 命令列介面來停用或啟用聊天室的詳細資料，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。 若要停用聊天室，請使用類似以下的命令：

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

若要啟用聊天室，請將 Disabled 屬性設定為 False：

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

請注意，您無法使用 Lync Server [控制台] 來啟用或停用聊天室。

如需有關設定聊天室的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定會議室](lync-server-2013-configure-rooms.md)。

</div>

<span> </span>

</div>

</div>

</div>

