---
title: 移除舊版封存和監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 816855b2661b8834264a2ff4b573ecbfe403d9b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="90ef5-102">移除舊版封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="90ef5-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90ef5-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="90ef5-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="90ef5-104">如果您的 Office 通訊伺服器 2007 R2 部署包含封存伺服器或監視伺服器，則遷移至 Lync Server 2013 之後，就可以從舊版環境中移除這些伺服器（前提是所有使用者都已從任何剩餘版本中移除）。Office 通訊伺服器 2007 R2 池。</span><span class="sxs-lookup"><span data-stu-id="90ef5-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="90ef5-105">您可以以任何順序移除封存伺服器或監視伺服器。</span><span class="sxs-lookup"><span data-stu-id="90ef5-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="90ef5-106">主要需求是所有使用者都已從任何剩餘的 Office 通訊伺服器 2007 R2 池中移除。</span><span class="sxs-lookup"><span data-stu-id="90ef5-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="90ef5-107">您可以按照階段6中所述的程式，將 Office 通訊伺服器 2007 R2 的使用者移至 Lync Server 2013 [：將使用者移至試驗](phase-6-move-users-to-the-pilot-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="90ef5-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="90ef5-108">確認所有使用者都已從任何剩餘的池中移除之後，請依照中的 [移除伺服器和伺服器角色] 中的程式[http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)操作。</span><span class="sxs-lookup"><span data-stu-id="90ef5-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

