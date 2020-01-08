---
title: 移轉程序
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="2ef7f-102">移轉程序</span><span class="sxs-lookup"><span data-stu-id="2ef7f-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ef7f-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="2ef7f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="2ef7f-104">Lync Server 2013 的建議和支援的遷移程式是並行遷移程式。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="2ef7f-105">本主題描述為什麼您應該使用並列移植，同時還包含有關共存的資訊。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="2ef7f-106">並行遷移</span><span class="sxs-lookup"><span data-stu-id="2ef7f-106">Side-by-Side Migration</span></span>

<span data-ttu-id="2ef7f-107">在幾乎所有的遷移中，您都應該使用並行遷移路徑。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="2ef7f-108">在並列式遷移中，您可以在執行 Office 通訊伺服器 2007 R2 的對應伺服器旁，使用 Lync Server 2013 部署新的伺服器，然後將作業轉移到新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="2ef7f-109">如果需要回滾到 Office 通訊伺服器 2007 R2，您只需要將操作移回原始伺服器。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="2ef7f-110">請注意，在這種情況下，使用升級後的用戶端排程的新會議將無法運作，而且用戶端也必須降級。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="2ef7f-111">共存測試</span><span class="sxs-lookup"><span data-stu-id="2ef7f-111">Coexistence Testing</span></span>

<span data-ttu-id="2ef7f-112">在與 Office 通訊伺服器 2007 R2 並行部署 Lync Server 2013 之後，拓朴代表 Lync Server 2013 與 Office 通訊伺服器 2007 R2 的共存測試狀態。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="2ef7f-113">當處於這個狀態時，請務必先測試並確定服務已啟動、可管理每個網站，而且用戶端可以與目前與舊版使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="2ef7f-114">在遷移所有使用者之前，請務必瞭解每個部署的狀態，並確保每個部署都能正常運作且正常運作。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="2ef7f-115">通常，共存測試階段會在整個 Lync Server 2013 的試驗測試中存在。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="2ef7f-116">在一段時間內，舊版使用者會移至 Lync Server 2013，以確保應用程式相容性及功能及功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="2ef7f-117">先導測試之後，使用者和應用程式會移至 Lync Server 2013 的產品版本，而舊版池與 Office 通訊伺服器 2007 R2 的應用程式就會停用。</span><span class="sxs-lookup"><span data-stu-id="2ef7f-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

