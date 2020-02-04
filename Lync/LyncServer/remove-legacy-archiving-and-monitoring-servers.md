---
title: 移除舊版封存和監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1df5ed76a0e0518120c9772b515b36c5f23bfd89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="016a8-102">移除舊版封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="016a8-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="016a8-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="016a8-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="016a8-104">如果您的舊版部署包含封存伺服器或監視伺服器，則在遷移至 Lync Server 2013 之後，如果所有使用者都已從任何其餘的舊版池中移除，則可以從舊版環境中移除這些伺服器。</span><span class="sxs-lookup"><span data-stu-id="016a8-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="016a8-105">您可以以任何順序移除封存伺服器或監視伺服器。</span><span class="sxs-lookup"><span data-stu-id="016a8-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="016a8-106">主要需求是所有使用者都已從任何其餘的舊版池中移除。</span><span class="sxs-lookup"><span data-stu-id="016a8-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="016a8-107">您可以按照階段4所述的程式，將 Lync Server 2010 中的使用者移至 Lync Server 2013 [：將測試使用者移至試驗](phase-4-move-test-users-to-the-pilot-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="016a8-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="016a8-108">確認所有使用者都已從任何剩餘的 pool 中移除之後，請依照「卸載 Microsoft Lync Server 2010 及移除伺服器角色」中的程式操作，這些程式可以在[http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)此下載。</span><span class="sxs-lookup"><span data-stu-id="016a8-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

