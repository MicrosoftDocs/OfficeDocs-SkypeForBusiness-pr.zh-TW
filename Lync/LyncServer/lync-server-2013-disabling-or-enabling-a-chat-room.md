---
title: Lync Server 2013：停用或啟用聊天室
description: Lync Server 2013：停用或啟用聊天室。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b81ce2614cebcf554c0390369068d8fd8b8f932
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568149"
---
# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>在 Lync Server 2013 中停用或啟用聊天室

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

如果已不再相關的持久聊天室主題，您可以停用聊天室，讓使用者無法使用它。 停用聊天室時，所有成員都會立即中斷與聊天室的連線。 停用聊天室之後，使用者就無法在聊天室搜尋中重新加入或尋找。

停用聊天室可以在稍後由 Persistent Chat administrator 啟用。 停用聊天室時，其中的成員資格清單與其他設定仍會保留。 如果您重新啟用聊天室，您不需要手動重新建立設定。

如果聊天室的記錄保持不變 (聊天室記錄存留功能是套用至類別內所有聊天室的類別上的選擇性設定。預設值為保留，但可透過將類別的 [ **啟用聊天記錄** ] 設定為 false) ，在停用聊天室時保留內容。 不過，在聊天室保持停用狀態時，搜尋中不會顯示該內容。 如果您稍後啟用聊天室，使用者可以搜尋停用聊天室之前所張貼的郵件。

如需使用 Windows PowerShell 命令列介面來停用或啟用聊天室的詳細資訊，請參閱 [使用 windows PowerShell Cmdlet 設定 Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。 若要停用聊天室，請使用類似下列的命令：

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

若要啟用聊天室，請將 Disabled 屬性設定為 False：

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

請注意，您無法使用 Lync Server 控制台來啟用或停用聊天室。

如需有關設定聊天室的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定聊天室](lync-server-2013-configure-rooms.md) 。

</div>

<span> </span>

</div>

</div>

</div>

