---
title: Lync Server 2013：刪除訊息或清除過時的訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8040d52690628b6085727d6a1fdac9288b94d5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="9b9a0-102">在 Lync Server 2013 中刪除訊息或清除過時的訊息</span><span class="sxs-lookup"><span data-stu-id="9b9a0-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b9a0-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="9b9a0-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="9b9a0-104">持續聊天系統管理員可以從持續聊天室刪除郵件（也可以選擇是否要將它取代為其他郵件）。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="9b9a0-105">系統管理員也可以清除過時的訊息做為日常維護的一部分，以將資料庫的增長降至最低。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="9b9a0-106">例如，這個 Windows PowerShell 命令會移除使用者 kenmyer@litwareinc.com 張貼的 ITChatRoom 聊天室中的所有訊息：</span><span class="sxs-lookup"><span data-stu-id="9b9a0-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="9b9a0-107">這個範例會將所有已移除的郵件取代為不能再使用的筆記：</span><span class="sxs-lookup"><span data-stu-id="9b9a0-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="9b9a0-108">如需詳細資訊，請參閱[Remove CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

