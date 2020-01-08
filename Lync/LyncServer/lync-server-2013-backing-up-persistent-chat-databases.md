---
title: Lync Server 2013：備份持久聊天資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ffb99effcf0a42bbddefd7151aa40a8d691d9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="21d3f-102">在 Lync Server 2013 中備份持續聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="21d3f-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d3f-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="21d3f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="21d3f-104">持續聊天室內容會儲存在持久性聊天資料庫（Mgc）。</span><span class="sxs-lookup"><span data-stu-id="21d3f-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="21d3f-105">這是應定期備份的業務關鍵型資料。</span><span class="sxs-lookup"><span data-stu-id="21d3f-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="21d3f-106">除了聊天室內容之外，持續性聊天資料庫也會儲存主體的相關資訊（例如使用者和使用者群組），以及他們必須在聊天室和聊天室中聊天的角色和存取權。</span><span class="sxs-lookup"><span data-stu-id="21d3f-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="21d3f-107">備份持續聊天資料的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="21d3f-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="21d3f-108">SQL Server 備份</span><span class="sxs-lookup"><span data-stu-id="21d3f-108">SQL Server Backup</span></span>

  - <span data-ttu-id="21d3f-109">將`Export-CsPersistentChatData`永久性聊天資料匯出為檔案的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="21d3f-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="21d3f-110">使用 SQL Server 備份所建立的資料所需的磁碟空間可能會比所建立的20倍`Export-CsPersistentChatData`，但 SQL Server 備份更可能是系統管理員熟悉的程式。</span><span class="sxs-lookup"><span data-stu-id="21d3f-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

