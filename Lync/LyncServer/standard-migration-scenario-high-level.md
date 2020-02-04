---
title: 標準移轉案例 - 高層級
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
ms.openlocfilehash: 68ff7110cc7e14ccc76ab7d0c0125e723477934a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="93ad8-102">標準移轉案例 - 高層級</span><span class="sxs-lookup"><span data-stu-id="93ad8-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93ad8-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="93ad8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="93ad8-104">當您將 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天遷移至 Lync Server 2013、持續聊天伺服器時，請使用下列專案作為起點。</span><span class="sxs-lookup"><span data-stu-id="93ad8-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="93ad8-105">標準的 Lync Server 2013 遷移路徑如下所示：</span><span class="sxs-lookup"><span data-stu-id="93ad8-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="93ad8-106">貴組織先前已部署 Lync Server 2010、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天，而且您想要部署 Lync Server 2013、持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="93ad8-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="93ad8-107">部署 Lync Server 2013，然後部署持續聊天伺服器池（s）。</span><span class="sxs-lookup"><span data-stu-id="93ad8-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="93ad8-108">準備並規劃持久聊天室的遷移，並判斷適當的時間來關閉系統以進行遷移。</span><span class="sxs-lookup"><span data-stu-id="93ad8-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="93ad8-109">執行適用于遷移的 Windows PowerShell Cmdlet （**Export-CsPersistentChatData**和**Import-CsPersistentChatData**），將內容移至持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="93ad8-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="93ad8-110">確認遷移已成功完成。</span><span class="sxs-lookup"><span data-stu-id="93ad8-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="93ad8-111">停止舊版部署。</span><span class="sxs-lookup"><span data-stu-id="93ad8-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="93ad8-112">[設定持久聊天伺服器]，讓舊版用戶端可以連線到 Lync Server 2013、持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="93ad8-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="93ad8-113">這是必要的，因為部署新的用戶端需要一些時間，而且您想要讓擁有舊版用戶端的現有使用者能儘快存取其聊天室。</span><span class="sxs-lookup"><span data-stu-id="93ad8-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="93ad8-114">部署新的用戶端，同時繼續協助確保擁有舊版群組聊天（用戶端）的工人可以存取其聊天室。</span><span class="sxs-lookup"><span data-stu-id="93ad8-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

