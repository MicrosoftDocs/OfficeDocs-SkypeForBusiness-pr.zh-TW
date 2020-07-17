---
title: 移除舊版封存和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d77292fe478fa95deec50df84a78907af4290e3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="39056-102">移除舊版封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="39056-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39056-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="39056-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="39056-104">如果舊版部署包含封存伺服器或監控伺服器，則在遷移至 Lync Server 2013 後，只要所有使用者都已從其餘的舊版集區中移除，這些伺服器便可以從舊版環境中移除。</span><span class="sxs-lookup"><span data-stu-id="39056-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="39056-105">您可以依任何順序移除封存伺服器或監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="39056-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="39056-106">重要的一點是，所有的使用者都已經從其他的舊版集區中移除。</span><span class="sxs-lookup"><span data-stu-id="39056-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="39056-107">您可以遵循[階段4：將測試使用者移至試驗集](phase-4-move-test-users-to-the-pilot-pool.md)區中所述的程式，將使用者從 Lync server 2010 移至 lync server 2013。</span><span class="sxs-lookup"><span data-stu-id="39056-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="39056-108">在您確認所有使用者都已從任何剩餘的集區中移除之後，請遵循「卸載 Microsoft Lync Server 2010 和移除伺服器角色」中的程式，其可于下載 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) 。</span><span class="sxs-lookup"><span data-stu-id="39056-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

