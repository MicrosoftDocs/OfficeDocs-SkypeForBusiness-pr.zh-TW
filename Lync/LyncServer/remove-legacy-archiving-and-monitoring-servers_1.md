---
title: 移除舊版封存和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4f149db04be75cec961478f4382b3e7a333e0a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="a4363-102">移除舊版封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="a4363-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4363-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="a4363-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="a4363-104">如果您的 Office 通訊伺服器 2007 R2 部署包含封存伺服器或監控伺服器，在遷移至 Lync Server 2013 後，只要所有使用者都已從任何剩餘的 Office 通訊伺服器 2007 R2 集區中移除，這些伺服器便可以從舊版環境中移除。</span><span class="sxs-lookup"><span data-stu-id="a4363-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="a4363-105">您可以依任何順序移除封存伺服器或監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4363-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="a4363-106">重要的一點是，所有使用者已從任何其他的 Office 通訊伺服器 2007 R2 集區中移除。</span><span class="sxs-lookup"><span data-stu-id="a4363-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="a4363-107">您可以遵循[階段6：將使用者移至試驗集](phase-6-move-users-to-the-pilot-pool.md)區中所述的程式，將使用者從 Office 通訊伺服器 2007 R2 移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a4363-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="a4363-108">確認所有使用者都已從任何剩餘的集區中移除之後，請遵循中的「移除伺服器和伺服器角色」中的程式 [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887) 。</span><span class="sxs-lookup"><span data-stu-id="a4363-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

