---
title: Lync Server 2013：刪除訊息或清除過時的訊息
description: Lync Server 2013：刪除訊息或清除過時的郵件。
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
ms.openlocfilehash: 928e34d2ab52b02155568c7da96e4ac1d8154b7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575819"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="2075a-103">在 Lync Server 2013 中刪除訊息或清除過時的訊息</span><span class="sxs-lookup"><span data-stu-id="2075a-103">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2075a-104">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="2075a-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="2075a-105">Persistent Chat 系統管理員可以從 Persistent 聊天室刪除郵件 (，也可以選擇性地將其取代為另一封郵件) 。</span><span class="sxs-lookup"><span data-stu-id="2075a-105">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="2075a-106">管理員也可以清除過時訊息作為持續維護的一部分，以將資料庫的成長最小化。</span><span class="sxs-lookup"><span data-stu-id="2075a-106">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="2075a-107">例如，此 Windows PowerShell 命令會從使用者 kenmyer@litwareinc.com 所張貼的 ITChatRoom 聊天室中移除所有郵件：</span><span class="sxs-lookup"><span data-stu-id="2075a-107">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="2075a-108">這個範例會取代所有已移除的郵件，請注意，該郵件已不再可用：</span><span class="sxs-lookup"><span data-stu-id="2075a-108">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="2075a-109">如需詳細資訊，請參閱 [test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="2075a-109">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

