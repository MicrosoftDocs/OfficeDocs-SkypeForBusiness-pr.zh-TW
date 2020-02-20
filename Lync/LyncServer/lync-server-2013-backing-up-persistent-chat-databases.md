---
title: Lync Server 2013： 備份常設聊天室資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dc1f448c248f80bfcc636c900b6601fda4aa200
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="292df-102">備份 Lync Server 2013 常設聊天室資料庫</span><span class="sxs-lookup"><span data-stu-id="292df-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="292df-103">_**上次修改主題：** 2013年-02-17_</span><span class="sxs-lookup"><span data-stu-id="292df-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="292df-104">常設聊天室內容儲存在常設聊天室資料庫 (Mgc.mdf)。</span><span class="sxs-lookup"><span data-stu-id="292df-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="292df-105">這是應該定期備份的重要商業資料。</span><span class="sxs-lookup"><span data-stu-id="292df-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="292df-106">除了聊天室內容、 常設聊天室資料庫也會儲存資訊 （例如使用者和使用者群組） 的主體和角色及它們對聊天室和聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="292df-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="292df-107">有兩種備份常設聊天室資料。</span><span class="sxs-lookup"><span data-stu-id="292df-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="292df-108">SQL Server 備份</span><span class="sxs-lookup"><span data-stu-id="292df-108">SQL Server Backup</span></span>

  - <span data-ttu-id="292df-109">`Export-CsPersistentChatData`指令程式，將常設聊天室資料匯出成檔案</span><span class="sxs-lookup"><span data-stu-id="292df-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="292df-110">使用 SQL Server 備份所建立的資料需要更多磁碟空間 — 更可能是 20 次 — 比建立`Export-CsPersistentChatData`，但 SQL Server 備份會很可能是系統管理員所熟悉的程序。</span><span class="sxs-lookup"><span data-stu-id="292df-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

