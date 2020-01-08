---
title: Lync Server 2013 可伸縮性測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="19b87-102">Lync Server 2013 中的可伸縮性測試</span><span class="sxs-lookup"><span data-stu-id="19b87-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19b87-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="19b87-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="19b87-104">Lync Server 2013 提供所有 Lync Server 即時通訊的伺服器基礎結構，包括立即訊息（IM）與目前狀態、會議和企業語音。</span><span class="sxs-lookup"><span data-stu-id="19b87-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="19b87-105">這包括使用 Lync Server 2013 池之硬體資源的所有功能，因此會影響效能和縮放比例。</span><span class="sxs-lookup"><span data-stu-id="19b87-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="19b87-106">所有組織都不是同等地使用所有功能。</span><span class="sxs-lookup"><span data-stu-id="19b87-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="19b87-107">例如，某些組織可能會在會議中大量使用影片，而其他人可能只會有很少或沒有影片使用。</span><span class="sxs-lookup"><span data-stu-id="19b87-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="19b87-108">某些組織傾向于將 PowerPoint 投影片共用到應用程式共用，而其他組織則喜歡相反的方式。</span><span class="sxs-lookup"><span data-stu-id="19b87-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="19b87-109">那些部署企業語音的組織可能會或不會大量使用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="19b87-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="19b87-110">大多陣列織會部署監視伺服器，但不是許多人都會部署封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="19b87-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="19b87-111">此外，組織並非全部都有相同的基礎結構，包括硬體容量、網路容量，以及已部署的池數和大小。</span><span class="sxs-lookup"><span data-stu-id="19b87-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="19b87-112">這些功能與基礎結構的多樣性會帶來可伸縮性測試的挑戰，不可能模擬所有可能的功能與基礎結構組合。</span><span class="sxs-lookup"><span data-stu-id="19b87-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="19b87-113">為了判斷 Lync Server 的伸縮性支援，我們會根據平均使用量模型（使用者模型），以並行方式使用所有 Lync Server 功能進行測試。</span><span class="sxs-lookup"><span data-stu-id="19b87-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="19b87-114">若要針對 Lync Server 工作負載判斷適當的使用者模型，我們分析了許多資料點，包括客戶問卷、Microsoft 客戶經驗改進計畫的意見反應，以及來自 Microsoft 內部 IT 部門的 Lync Server 使用資料。以及從我們的 Live Meeting 服務挖掘的資料。</span><span class="sxs-lookup"><span data-stu-id="19b87-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="19b87-115">在許多情況下，使用者模型會有較重的負載來偏向，為組織內的使用提供舒適的邊界。</span><span class="sxs-lookup"><span data-stu-id="19b87-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="19b87-116">在我們的可伸縮性測試中，我們根據建議的硬體和軟體規格設定 Lync Server 2013 池，包括基礎結構元件，例如 Active Directory 網域服務、硬體負載平衡器和防火牆。</span><span class="sxs-lookup"><span data-stu-id="19b87-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="19b87-117">我們將 Lync Server 環境盡可能緊密地設定為一般的實際環境。</span><span class="sxs-lookup"><span data-stu-id="19b87-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="19b87-118">接著，我們使用 Lync Server 2013 的應力和效能工具來模擬 Lync Server 2013 載入（根據我們的使用者模型）。</span><span class="sxs-lookup"><span data-stu-id="19b87-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="19b87-119">.</span><span class="sxs-lookup"><span data-stu-id="19b87-119"></span></span>

<span data-ttu-id="19b87-120">我們會進行多個伸縮性測試的多次小性，包括多個為期三周的測試執行）。</span><span class="sxs-lookup"><span data-stu-id="19b87-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="19b87-121">我們會使用所有測試的結果來協助效能調整，以及驗證使用者模型中的可伸縮性數位支援。</span><span class="sxs-lookup"><span data-stu-id="19b87-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

