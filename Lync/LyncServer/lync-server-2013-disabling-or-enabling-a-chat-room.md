---
title: Lync Server 2013： 停用或啟用聊天室
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
ms.openlocfilehash: 96ad55bd6396cdac9b30441eb8b41bebaba834ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>停用或啟用 Lync Server 2013 中的聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-05_

如果不再相關主題的常設聊天室，您可以讓聊天室使用者無法使用藉由停用它。 停用聊天室時，所有成員會立即都中斷連線會議室。 停用聊天室之後，使用者無法將其重新加入或聊天室搜尋中尋找。

常設聊天室管理員可以稍後再啟用已停用的聊天室。 停用聊天室時，其中的成員資格清單與其他設定仍會保留。 如果您重新啟用會議室，您不需要以手動方式重新建立設定。

如果仍然存在該聊天室的歷程記錄 （聊天室歷程記錄保存性是選擇性的設定套用至該類別內的所有聊天室類別上; 預設值是它保存，但可以藉由將類別的**啟用聊天歷程記錄**設定為 false 關閉），此內容會保留時已停用聊天室。 不過，該內容不會出現在搜尋期間聊天室仍會保留在停用狀態的時間。 如果您稍後啟用該聊天室，使用者可以搜尋聊天室被停用之前已張貼的訊息。

如需停用，並使用 Windows PowerShell 命令列介面來啟用聊天室的詳細資訊，請參閱[使用 Windows PowerShell cmdlet 的 Configuring Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 「 聊天室管理 」。 若要停用聊天室，請使用類似如下的命令：

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

若要啟用聊天室，請停用屬性設為 False:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

請注意，無法啟用或停用使用 Lync Server Control Panel 聊天室。

如需設定聊天室的詳細資訊，請參閱部署文件中的[Lync Server 2013 中的 Configure rooms](lync-server-2013-configure-rooms.md) 。

</div>

<span> </span>

</div>

</div>

</div>

