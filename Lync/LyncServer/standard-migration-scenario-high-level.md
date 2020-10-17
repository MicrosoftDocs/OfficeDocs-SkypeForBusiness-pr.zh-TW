---
title: 標準遷移案例-高層級
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62a557d8b5a0f2a3e1e0f248b01795e75c02b3a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529800"
---
# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="f515b-102">標準遷移案例-高層級</span><span class="sxs-lookup"><span data-stu-id="f515b-102">Standard migration scenario - high-level</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f515b-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f515b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f515b-104">將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、Persistent Chat Server 時，請使用下列專案做為開始點。</span><span class="sxs-lookup"><span data-stu-id="f515b-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="f515b-105">標準 Lync Server 2013 遷移路徑如下：</span><span class="sxs-lookup"><span data-stu-id="f515b-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="f515b-106">您的組織先前已部署 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天，且您想要部署 Lync Server 2013、Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="f515b-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="f515b-107">部署 Lync Server 2013，然後將 Persistent Chat Server 集區 (s) 中部署。</span><span class="sxs-lookup"><span data-stu-id="f515b-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="f515b-108">準備並規劃您的持續聊天室的遷移，並決定適當的時間來關閉系統進行遷移。</span><span class="sxs-lookup"><span data-stu-id="f515b-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="f515b-109">執行 Windows PowerShell Cmdlet 以進行遷移 (**Export-CsPersistentChatData** 及 **Import-CsPersistentChatData**) 將內容移至 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="f515b-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="f515b-110">確認遷移已成功。</span><span class="sxs-lookup"><span data-stu-id="f515b-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="f515b-111">解除委任舊版部署。</span><span class="sxs-lookup"><span data-stu-id="f515b-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="f515b-112">設定 Persistent Chat Server，使舊版用戶端可以連線至 Lync Server 2013，Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="f515b-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="f515b-113">這是必要的，因為部署新的用戶端需要一些時間，而且您想要讓具有舊版用戶端的現有使用者可以儘快存取其聊天室。</span><span class="sxs-lookup"><span data-stu-id="f515b-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="f515b-114">部署新的用戶端，同時繼續協助確保具有傳統群組聊天 (用戶端的工作人員) 可以到達其聊天室。</span><span class="sxs-lookup"><span data-stu-id="f515b-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

