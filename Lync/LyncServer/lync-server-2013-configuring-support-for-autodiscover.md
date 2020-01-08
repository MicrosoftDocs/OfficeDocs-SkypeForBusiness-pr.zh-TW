---
title: Lync Server 2013：設定自動探索的支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb83156d319db96a4c6ed79768193a24e5cc3e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="42b5d-102">在 Lync Server 2013 中設定自動探索的支援</span><span class="sxs-lookup"><span data-stu-id="42b5d-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42b5d-103">_**主題上次修改日期：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="42b5d-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="42b5d-104">Lync Server web services**自動探索服務**會先出現在 lync Server 2010 累計更新：2011年11月。</span><span class="sxs-lookup"><span data-stu-id="42b5d-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="42b5d-105">此更新隨附于 Lync 行動用戶端的初始版本。</span><span class="sxs-lookup"><span data-stu-id="42b5d-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="42b5d-106">自動探索服務公開了行動服務，稱為 Mcx 服務。</span><span class="sxs-lookup"><span data-stu-id="42b5d-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="42b5d-107">自動探索服務會充當單一位置，讓所有用戶端要求提供哪些服務和功能的相關資訊，以及如何與 sevices 取得聯繫，只要是完全合格的功能變數名稱或網頁統一資源定位器參照即可。</span><span class="sxs-lookup"><span data-stu-id="42b5d-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="42b5d-108">自動探索會公開許多功能，而每個用戶端都會根據用戶端可以使用的功能來提出要求。</span><span class="sxs-lookup"><span data-stu-id="42b5d-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="42b5d-109">例如，桌面 Lync 2013 用戶端會使用 autodiscvoer 來判斷外部 web 服務，但不會使用行動（Mcx）服務。</span><span class="sxs-lookup"><span data-stu-id="42b5d-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="42b5d-110">若要正確定義並讓您的用戶端使用提供的功能，您必須定義允許用戶端有效尋找及使用自動探索專案的案例。</span><span class="sxs-lookup"><span data-stu-id="42b5d-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="42b5d-111">若要使用 autodoscover，您的部署需要反向 proxy 發佈 Lync Server web 服務、DNS 記錄已設定為解析 Lync Server 自動探索服務和 Lync Server web 服務的 DNS 查詢，以及該憑證服務針對您的特定案例正確地設定。</span><span class="sxs-lookup"><span data-stu-id="42b5d-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="42b5d-112">如需有關自動探索要求/回應中的元素的技術詳細資料，請參閱<A href="lync-server-2013-understanding-autodiscover.md">瞭解 Lync Server 2013 中的自動</A>探索。</span><span class="sxs-lookup"><span data-stu-id="42b5d-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="42b5d-113">下列資訊與表格會根據案例所定義的設定（如果有的話）來提供自動探索服務的完整和有效使用。</span><span class="sxs-lookup"><span data-stu-id="42b5d-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="42b5d-114">下列主題中的資訊僅適用于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="42b5d-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="42b5d-115">如果您正在尋找如何規劃 Lync Server 2010 行動性的指導方針，請參閱[http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)。</span><span class="sxs-lookup"><span data-stu-id="42b5d-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="42b5d-116">若要部署 Lync Server 2010 的行動性，請參閱[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="42b5d-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42b5d-117">本節內容</span><span class="sxs-lookup"><span data-stu-id="42b5d-117">In This Section</span></span>

  - [<span data-ttu-id="42b5d-118">在 Lync Server 2013 中針對自動探索設定 DNS</span><span class="sxs-lookup"><span data-stu-id="42b5d-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="42b5d-119">在 Lync Server 2013 中設定自動探索的憑證</span><span class="sxs-lookup"><span data-stu-id="42b5d-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="42b5d-120">在 Lync Server 2013 中針對自動探索設定反向 proxy</span><span class="sxs-lookup"><span data-stu-id="42b5d-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="42b5d-121">在 Lync Server 2013 中設定自動探索以進行混合式部署</span><span class="sxs-lookup"><span data-stu-id="42b5d-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

