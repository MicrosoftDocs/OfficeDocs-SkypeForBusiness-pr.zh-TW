---
title: Lync Server 2013：服務層級協定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b7189d7f13f1b854bfb4bd921251c319f87ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="f17ce-102">Lync Server 2013 中的服務等級協定</span><span class="sxs-lookup"><span data-stu-id="f17ce-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f17ce-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="f17ce-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="f17ce-104">SLA 是定義客戶預期的服務的檔。</span><span class="sxs-lookup"><span data-stu-id="f17ce-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="f17ce-105">此檔的複雜性和內容，主要取決於客戶是內部的客戶（在您的環境中）還是外部的客戶。</span><span class="sxs-lookup"><span data-stu-id="f17ce-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="f17ce-106">外部客戶</span><span class="sxs-lookup"><span data-stu-id="f17ce-106">External Customers</span></span>

<span data-ttu-id="f17ce-107">如果您的客戶是外部客戶，SLA 可能是法定合約的一部分，其中包含財務獎勵，以及超出或超出已定義服務層級之效能的處罰。</span><span class="sxs-lookup"><span data-stu-id="f17ce-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="f17ce-108">定義這些等級的服務必須是整個合約協商的一部分。</span><span class="sxs-lookup"><span data-stu-id="f17ce-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="f17ce-109">與所有合約一樣，雙方都必須瞭解預期。</span><span class="sxs-lookup"><span data-stu-id="f17ce-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="f17ce-110">SLA 定義這些預期。</span><span class="sxs-lookup"><span data-stu-id="f17ce-110">The SLA defines these expectations.</span></span> <span data-ttu-id="f17ce-111">檔的內容不會經常變更，只是因為與客戶協商。</span><span class="sxs-lookup"><span data-stu-id="f17ce-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="f17ce-112">內部客戶</span><span class="sxs-lookup"><span data-stu-id="f17ce-112">Internal Customers</span></span>

<span data-ttu-id="f17ce-113">如果您的客戶是內部客戶，您可能仍想要定義運營團隊和 IT 系統預期的服務。</span><span class="sxs-lookup"><span data-stu-id="f17ce-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="f17ce-114">SLA 可能是由操作人員所建立，且是您組織中 IT 服務可用性的一組目標。</span><span class="sxs-lookup"><span data-stu-id="f17ce-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="f17ce-115">或者，效能等級可以由管理進行設定，並在評估員工效能時做為基準。</span><span class="sxs-lookup"><span data-stu-id="f17ce-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="f17ce-116">典型準則</span><span class="sxs-lookup"><span data-stu-id="f17ce-116">Typical Criteria</span></span>

<span data-ttu-id="f17ce-117">Sla 包含定義最低可用性、支援及容量之準則的章節。</span><span class="sxs-lookup"><span data-stu-id="f17ce-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="f17ce-118">**可用性**   定義可使用網站和其他 Lync 服務的時間與作業系統。</span><span class="sxs-lookup"><span data-stu-id="f17ce-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="f17ce-119">您應該定義任何會影響服務可用性的例行維護作業。</span><span class="sxs-lookup"><span data-stu-id="f17ce-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="f17ce-120">定義影響服務的外部因素，例如，失去網際網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="f17ce-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="f17ce-121">**支援**   定義將提供系統支援的時間。</span><span class="sxs-lookup"><span data-stu-id="f17ce-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="f17ce-122">指定客戶聯繫支援人員的方法、將事件分組的方式，以及以回應與解決事件的時間為目標。</span><span class="sxs-lookup"><span data-stu-id="f17ce-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="f17ce-123">定義向客戶提供意見反應的頻率與內容。</span><span class="sxs-lookup"><span data-stu-id="f17ce-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="f17ce-124">**[產能**   ] 定義 [Lync 網站] 的啟用大小上限，以及超過限制時所需採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="f17ce-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="f17ce-125">定義要執行標準任務的最大啟用時間，例如從文件庫中檢索檔的時間。</span><span class="sxs-lookup"><span data-stu-id="f17ce-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="f17ce-126">定義每個 Lync 文件庫的使用者數目上限，並同意在新增其他使用者的情況下增加容量的進程。</span><span class="sxs-lookup"><span data-stu-id="f17ce-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

