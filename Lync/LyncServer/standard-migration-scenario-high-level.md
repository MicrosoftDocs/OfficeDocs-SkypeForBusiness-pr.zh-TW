---
title: 標準移轉案例-高層級
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34084de0af0971018043f230c260adb514f1d460
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="e0b24-102">標準移轉案例-高層級</span><span class="sxs-lookup"><span data-stu-id="e0b24-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0b24-103">_**上次修改主題：** 2013年-01-30_</span><span class="sxs-lookup"><span data-stu-id="e0b24-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e0b24-104">將 Lync Server 2010，Group Chat 或： Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013，Persistent Chat Server 時，請使用下列項目做為起點。</span><span class="sxs-lookup"><span data-stu-id="e0b24-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="e0b24-105">標準的 Lync Server 2013 移轉方式如下：</span><span class="sxs-lookup"><span data-stu-id="e0b24-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="e0b24-106">您的組織已部署 Lync Server 2010，Group Chat 或 Office Communications Server 2007 R2 群組聊天，以及您想要部署 Lync Server 2013，Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="e0b24-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="e0b24-107">部署 Lync Server 2013，然後將部署 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="e0b24-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="e0b24-108">準備並規劃移轉您的常設聊天室，並決定適當時機來關閉系統以進行移轉。</span><span class="sxs-lookup"><span data-stu-id="e0b24-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="e0b24-109">執行移轉 （**Export-cspersistentchatdata**與**Import-cspersistentchatdata**） 將內容移至 Persistent Chat Server 的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0b24-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="e0b24-110">確認移轉已成功。</span><span class="sxs-lookup"><span data-stu-id="e0b24-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="e0b24-111">解除委任舊版部署。</span><span class="sxs-lookup"><span data-stu-id="e0b24-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="e0b24-112">設定常設聊天室伺服器，以便舊版用戶端可以連線至 Lync Server 2013，Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="e0b24-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="e0b24-113">這是必要的因為所花的時間來部署新的用戶端，而且想要啟用現有的使用者使用舊版用戶端儘速可以存取他們的聊天室。</span><span class="sxs-lookup"><span data-stu-id="e0b24-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="e0b24-114">部署新的用戶端，同時繼續以協助確保與舊版群組聊天 （用戶端） 的工作者可以前往他們的聊天室。</span><span class="sxs-lookup"><span data-stu-id="e0b24-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

