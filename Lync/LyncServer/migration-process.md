---
title: 移轉程序
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53021b37baca7a859c79a6c47bfbf3d587a3466d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="1f58d-102">移轉程序</span><span class="sxs-lookup"><span data-stu-id="1f58d-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f58d-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1f58d-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1f58d-104">Lync Server 2013 的建議和支援的遷移程式是並排遷移。</span><span class="sxs-lookup"><span data-stu-id="1f58d-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="1f58d-105">本主題描述為什麼您應該使用並列移植，同時還包含共存測試的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1f58d-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="1f58d-106">並行遷移</span><span class="sxs-lookup"><span data-stu-id="1f58d-106">Side-By-Side Migration</span></span>

<span data-ttu-id="1f58d-107">在幾乎所有的遷移中，您都應該使用並行遷移路徑。</span><span class="sxs-lookup"><span data-stu-id="1f58d-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="1f58d-108">在並列式遷移中，您會使用 Lync Server 2013 與執行 Lync Server 2010 的對應伺服器一起部署新的伺服器，然後將作業轉移到新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f58d-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="1f58d-109">如果需要回滾至 Lync Server 2010，您只需要將操作移回原始伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f58d-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="1f58d-110">請注意，在這種情況下，使用升級後的用戶端排程的新會議將無法運作，而且用戶端也必須降級。</span><span class="sxs-lookup"><span data-stu-id="1f58d-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="1f58d-111">共存測試</span><span class="sxs-lookup"><span data-stu-id="1f58d-111">Coexistence Testing</span></span>

<span data-ttu-id="1f58d-112">在您以 Lync Server 2010 並行部署 Lync Server 2013 之後，該部署代表 Lync Server 2013 和 Lync Server 2010 的共存測試狀態。</span><span class="sxs-lookup"><span data-stu-id="1f58d-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="1f58d-113">當處於這個狀態時，請務必測試並確定服務已啟動、可管理每個網站，而且用戶端可以與目前與舊版使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="1f58d-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="1f58d-114">在遷移所有使用者之前，請務必瞭解每個部署的狀態，並確保每個部署都能正常運作且正常運作。</span><span class="sxs-lookup"><span data-stu-id="1f58d-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="1f58d-115">通常，共存測試階段會在整個 Lync Server 2013 的試驗測試中存在。</span><span class="sxs-lookup"><span data-stu-id="1f58d-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="1f58d-116">在一段時間內，舊版使用者會移至 Lync Server 2013，以確保應用程式相容性及功能及功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="1f58d-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="1f58d-117">先導測試之後，使用者和應用程式會移至 Lync Server 2013 的產品版本，而舊版池和 Lync Server 2010 的應用程式就會停用。</span><span class="sxs-lookup"><span data-stu-id="1f58d-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

