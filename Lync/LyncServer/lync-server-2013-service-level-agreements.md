---
title: Lync Server 2013： 服務等級協定
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
ms.openlocfilehash: 8f902a946d272ce3a16db5f032b74ec031c7e3a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="72b5e-102">Lync Server 2013 中的服務等級協定</span><span class="sxs-lookup"><span data-stu-id="72b5e-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72b5e-103">_**上次修改主題：** 2014年-08-18_</span><span class="sxs-lookup"><span data-stu-id="72b5e-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="72b5e-104">SLA 是定義您的客戶預期從您的服務的文件。</span><span class="sxs-lookup"><span data-stu-id="72b5e-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="72b5e-105">這份文件的內容與複雜性主要取決於客戶是 （在您的環境） 內部或外部。</span><span class="sxs-lookup"><span data-stu-id="72b5e-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="72b5e-106">外部的客戶</span><span class="sxs-lookup"><span data-stu-id="72b5e-106">External Customers</span></span>

<span data-ttu-id="72b5e-107">如果您的客戶是服務的外部，SLA 可能是服務的法律與財務獎勵和落內部或外部定義的層級的效能的負面影響合約的一部分。</span><span class="sxs-lookup"><span data-stu-id="72b5e-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="72b5e-108">定義服務的這些層級應是整體合約交涉的一部分。</span><span class="sxs-lookup"><span data-stu-id="72b5e-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="72b5e-109">如同所有合約，請務必雙方了解的期望。</span><span class="sxs-lookup"><span data-stu-id="72b5e-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="72b5e-110">SLA 定義這些的期望。</span><span class="sxs-lookup"><span data-stu-id="72b5e-110">The SLA defines these expectations.</span></span> <span data-ttu-id="72b5e-111">文件的內容應該不常變更，只有因為與客戶的交涉。</span><span class="sxs-lookup"><span data-stu-id="72b5e-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="72b5e-112">內部的客戶</span><span class="sxs-lookup"><span data-stu-id="72b5e-112">Internal Customers</span></span>

<span data-ttu-id="72b5e-113">如果您的客戶是內部，您仍可能要定義和 IT 系統的作業小組所預期的服務。</span><span class="sxs-lookup"><span data-stu-id="72b5e-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="72b5e-114">SLA 可能操作人員所建立，且適合貴組織的 IT 服務的可用性目標的一組。</span><span class="sxs-lookup"><span data-stu-id="72b5e-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="72b5e-115">或者，可能會管理來設定並時做為基準評估人員效能的效能層級。</span><span class="sxs-lookup"><span data-stu-id="72b5e-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="72b5e-116">典型的準則</span><span class="sxs-lookup"><span data-stu-id="72b5e-116">Typical Criteria</span></span>

<span data-ttu-id="72b5e-117">Sla 包括定義的最低層級的可用性、 支援和容量準則的區段。</span><span class="sxs-lookup"><span data-stu-id="72b5e-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="72b5e-118">**可用性**   定義小時和所在的網站和其他 Lync 服務將提供使用的作業系統。</span><span class="sxs-lookup"><span data-stu-id="72b5e-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="72b5e-119">您應該定義會影響服務的可用性任何例行維護。</span><span class="sxs-lookup"><span data-stu-id="72b5e-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="72b5e-120">定義外部因素會影響服務，例如，網際網路連線遺失。</span><span class="sxs-lookup"><span data-stu-id="72b5e-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="72b5e-121">**支援**   定義小時時支援系統將提供使用。</span><span class="sxs-lookup"><span data-stu-id="72b5e-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="72b5e-122">指定的客戶，請連絡支援人員、 事件分組的方式，以及目標時間來回應，並解決事件的方法。</span><span class="sxs-lookup"><span data-stu-id="72b5e-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="72b5e-123">定義頻率及內容意見反應給客戶。</span><span class="sxs-lookup"><span data-stu-id="72b5e-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="72b5e-124">**容量**   定義最多啟用 Lync 網站和如果超過限制時要採取的步驟的大小。</span><span class="sxs-lookup"><span data-stu-id="72b5e-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="72b5e-125">定義已啟用的時間上限執行一般工作，例如擷取文件中的文件庫的時間。</span><span class="sxs-lookup"><span data-stu-id="72b5e-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="72b5e-126">定義每個 Lync 集區的使用者數目上限，並同意提高產能，如果新增更多使用者的程序。</span><span class="sxs-lookup"><span data-stu-id="72b5e-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

