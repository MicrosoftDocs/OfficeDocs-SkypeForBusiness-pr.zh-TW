---
title: Lync Server 2013：設定自動探索的支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bbb9007562dfecdc4f38b6cf8ac3f1579094ed6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="8057b-102">在 Lync Server 2013 中設定自動探索支援</span><span class="sxs-lookup"><span data-stu-id="8057b-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8057b-103">_**主題上次修改日期：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="8057b-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="8057b-104">Lync Server web services**自動探索服務**會先出現在 lync Server 2010 累計更新：11月2011。</span><span class="sxs-lookup"><span data-stu-id="8057b-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="8057b-105">此更新附帶 Lync Mobile 用戶端的初始版本。</span><span class="sxs-lookup"><span data-stu-id="8057b-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="8057b-106">自動探索服務公開了行動服務，稱為 Mcx 服務。</span><span class="sxs-lookup"><span data-stu-id="8057b-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="8057b-107">自動探索服務充當所有用戶端的單一位置，可要求提供哪些服務和功能的相關資訊，以及如何與 sevices 取得聯繫–不論是完整功能變數名稱或 web 統一資源定位器參照。</span><span class="sxs-lookup"><span data-stu-id="8057b-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="8057b-108">自動探索會公開許多功能，而且每個用戶端都會根據用戶端可以使用的功能來發出要求。</span><span class="sxs-lookup"><span data-stu-id="8057b-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="8057b-109">例如，桌面 Lync 2013 用戶端會使用 autodiscvoer 來判斷外部 web 服務，但不會使用行動性 (Mcx) 服務。</span><span class="sxs-lookup"><span data-stu-id="8057b-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="8057b-110">若要正確定義及啟用您的用戶端以使用其可用的功能，則應定義允許用戶端有效尋找及使用自動探索專案的案例。</span><span class="sxs-lookup"><span data-stu-id="8057b-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="8057b-111">若要使用 autodoscover，您的部署需要反向 proxy 發行 Lync Server web 服務、DNS 記錄已設定為解析 Lync Server 自動探索服務和 Lync Server web 服務的 DNS 查詢，以及已針對您的特定案例正確設定憑證服務。</span><span class="sxs-lookup"><span data-stu-id="8057b-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8057b-112">如需自動探索要求/回應中的元素的技術詳細資料，請參閱<A href="lync-server-2013-understanding-autodiscover.md">瞭解 Lync Server 2013 中的自動</A>探索。</span><span class="sxs-lookup"><span data-stu-id="8057b-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8057b-113">下列資訊和表格會針對每個案例定義哪些設定 (若您需要實施任何) 以提供自動探索服務的完整和有效使用。</span><span class="sxs-lookup"><span data-stu-id="8057b-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="8057b-114">下列主題中的資訊僅適用于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="8057b-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="8057b-115">如果您正在尋找如何規劃 Lync Server 2010 行動的指引，請參閱 [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113) 。</span><span class="sxs-lookup"><span data-stu-id="8057b-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="8057b-116">若要部署 Lync Server 2010 的行動性，請參閱[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="8057b-116">To deploy Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8057b-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="8057b-117">In This Section</span></span>

  - [<span data-ttu-id="8057b-118">在 Lync Server 2013 中設定自動探索的 DNS</span><span class="sxs-lookup"><span data-stu-id="8057b-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="8057b-119">在 Lync Server 2013 中設定自動探索的憑證</span><span class="sxs-lookup"><span data-stu-id="8057b-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="8057b-120">在 Lync Server 2013 中設定自動探索的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="8057b-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="8057b-121">在 Lync Server 2013 中設定自動探索以進行混合部署</span><span class="sxs-lookup"><span data-stu-id="8057b-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

