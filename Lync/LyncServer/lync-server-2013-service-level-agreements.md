---
title: Lync Server 2013：服務等級協定
description: Lync Server 2013：服務等級協定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 817aa8e092d9d368dfd8cb920958553ee32e8600
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576469"
---
# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="8c263-103">Lync Server 2013 中的服務等級協定</span><span class="sxs-lookup"><span data-stu-id="8c263-103">Service level agreements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c263-104">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="8c263-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8c263-105">SLA 是一種檔，可定義客戶期望的服務。</span><span class="sxs-lookup"><span data-stu-id="8c263-105">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="8c263-106">這份檔的複雜性和內容，主要取決於客戶是環境內部 (環境還是) 或外部。</span><span class="sxs-lookup"><span data-stu-id="8c263-106">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="8c263-107">外部客戶</span><span class="sxs-lookup"><span data-stu-id="8c263-107">External Customers</span></span>

<span data-ttu-id="8c263-108">如果您的客戶是外部客戶，SLA 可能是法律訴訟的一部分，其效能是在定義的服務層級之內或之外的效能。</span><span class="sxs-lookup"><span data-stu-id="8c263-108">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="8c263-109">定義這些服務等級應該是整體合約協商的一部分。</span><span class="sxs-lookup"><span data-stu-id="8c263-109">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="8c263-110">就像所有合約一樣，雙方都必須瞭解期望。</span><span class="sxs-lookup"><span data-stu-id="8c263-110">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="8c263-111">SLA 會定義這些預期。</span><span class="sxs-lookup"><span data-stu-id="8c263-111">The SLA defines these expectations.</span></span> <span data-ttu-id="8c263-112">檔內容應該不經常變更，且只能因與客戶談判。</span><span class="sxs-lookup"><span data-stu-id="8c263-112">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="8c263-113">內部客戶</span><span class="sxs-lookup"><span data-stu-id="8c263-113">Internal Customers</span></span>

<span data-ttu-id="8c263-114">如果您的客戶為內部客戶，您可能仍要定義運作小組和 IT 系統所需的服務。</span><span class="sxs-lookup"><span data-stu-id="8c263-114">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="8c263-115">SLA 可由作業人員建立，並預定為組織內 IT 服務可用性的一組目標。</span><span class="sxs-lookup"><span data-stu-id="8c263-115">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="8c263-116">或者，在評估人員效能時，可以使用管理，將效能層級設定為基準。</span><span class="sxs-lookup"><span data-stu-id="8c263-116">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="8c263-117">一般準則</span><span class="sxs-lookup"><span data-stu-id="8c263-117">Typical Criteria</span></span>

<span data-ttu-id="8c263-118">Sla 包括定義最低可用性、支援和容量層級準則的各節。</span><span class="sxs-lookup"><span data-stu-id="8c263-118">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="8c263-119">**可用性**    定義可使用網站和其他 Lync 服務的時段和作業系統。</span><span class="sxs-lookup"><span data-stu-id="8c263-119">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="8c263-120">應定義影響服務可用性的任何例行維護。</span><span class="sxs-lookup"><span data-stu-id="8c263-120">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="8c263-121">定義影響服務的外部因素，例如，失去網際網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="8c263-121">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="8c263-122">**支援**    定義可使用系統支援的時間。</span><span class="sxs-lookup"><span data-stu-id="8c263-122">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="8c263-123">為客戶指定方法，以聯繫支援人員、如何群組事件，以及目標時間以回應及解決事件。</span><span class="sxs-lookup"><span data-stu-id="8c263-123">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="8c263-124">定義對客戶的意見反應頻率和內容。</span><span class="sxs-lookup"><span data-stu-id="8c263-124">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="8c263-125">**容量**    若超出限制，請定義 Lync 網站的已啟用大小上限及所要採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="8c263-125">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="8c263-126">定義要執行標準任務的最大啟用時間，例如從文件庫中取得檔的時間。</span><span class="sxs-lookup"><span data-stu-id="8c263-126">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="8c263-127">定義每個 Lync 集區的使用者數目上限，並在新增更多使用者時，同意增加容量的處理常式。</span><span class="sxs-lookup"><span data-stu-id="8c263-127">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

