---
title: Lync Server 2013：前端集區配對資料安全性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d86f60e81e053a1ba07878728dd9c7273bd7feeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500720"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="583b1-102">Lync Server 2013 中的前端集區配對資料安全性</span><span class="sxs-lookup"><span data-stu-id="583b1-102">Front End pool pairing data security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="583b1-103">_**主題上次修改日期：** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="583b1-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="583b1-104">備份服務是 Lync Server 2013 中引入的資料複寫機制，可持續跨兩個資料中心，將兩個配對前端集區間的使用者資料和會議內容傳輸到兩個資料中心，以進行嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="583b1-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="583b1-105">使用者資料包含使用者 SIP URIs 以及連絡人清單和設定。</span><span class="sxs-lookup"><span data-stu-id="583b1-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="583b1-106">會議內容包括 Microsoft PowerPoint 2010 上傳，以及在會議中使用的白板。</span><span class="sxs-lookup"><span data-stu-id="583b1-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="583b1-107">從來源集區中，使用者資料和會議內容會從本機儲存區（已壓縮）匯出至目標集區，並將其解壓縮並匯入至本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="583b1-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="583b1-108">備份服務假定兩個資料中心之間的通訊連結，都位於從網際網路保護的公司網路內。</span><span class="sxs-lookup"><span data-stu-id="583b1-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="583b1-109">它不會加密兩個資料中心之間已傳輸的資料，也不會在本機封裝在安全通訊協定（例如 HTTPS）內。</span><span class="sxs-lookup"><span data-stu-id="583b1-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="583b1-110">因此，來自公司網路內部的內部人員可以進行中間人攻擊。</span><span class="sxs-lookup"><span data-stu-id="583b1-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="583b1-111">評估安全性風險</span><span class="sxs-lookup"><span data-stu-id="583b1-111">Evaluating Security Risks</span></span>

<span data-ttu-id="583b1-112">任何可跨多個資料中心部署 Lync Server 2013 並使用嚴重損壞修復功能的企業，都必須確保跨資料中心的流量受到公司內部網路的保護。</span><span class="sxs-lookup"><span data-stu-id="583b1-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="583b1-113">關心內部攻擊防護的企業必須保護資料中心之間的通訊連結。</span><span class="sxs-lookup"><span data-stu-id="583b1-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="583b1-114">假設企業的資料中心受保護在公司內部網路的背後是標準的。</span><span class="sxs-lookup"><span data-stu-id="583b1-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="583b1-115">在這些資料中心內，有許多其他類型的公司機密資料會傳輸。</span><span class="sxs-lookup"><span data-stu-id="583b1-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="583b1-116">如果這些跨資料中心連結未受到保護，企業的 IT 基礎結構便會 dire 風險。</span><span class="sxs-lookup"><span data-stu-id="583b1-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="583b1-117">雖然公司網路記憶體在中間人攻擊的風險存在，但是它相對於公開網際網路的流量，其相對包含。</span><span class="sxs-lookup"><span data-stu-id="583b1-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="583b1-118">尤其是備份服務所公開的使用者資料 (例如 SIP URIs) ，通常可透過其他方式（如 Exchange 或其他目錄軟體的全域通訊錄），從公司內的所有員工取得。</span><span class="sxs-lookup"><span data-stu-id="583b1-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="583b1-119">因此，當備份服務用於複製兩個配對集區間的資料時，重點應該是保護兩個資料中心之間的 WAN。</span><span class="sxs-lookup"><span data-stu-id="583b1-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="583b1-120">降低安全性風險</span><span class="sxs-lookup"><span data-stu-id="583b1-120">Mitigating Security Risks</span></span>

<span data-ttu-id="583b1-121">有許多方式可以增強備份服務流量的安全性保護，其範圍包括限制存取資料中心，以保護兩個資料中心之間的 WAN 傳輸。</span><span class="sxs-lookup"><span data-stu-id="583b1-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="583b1-122">在大多數情況下，部署 Lync Server 2013 的企業可能已具備必要的安全性基礎結構。</span><span class="sxs-lookup"><span data-stu-id="583b1-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="583b1-123">針對尋求指導的企業，Microsoft 提供的解決方案是如何建立安全 IT 基礎結構的範例。</span><span class="sxs-lookup"><span data-stu-id="583b1-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="583b1-124">不過，這並不表示這是唯一的解決方案，也不表示它是 Lync Server 的慣用方案。</span><span class="sxs-lookup"><span data-stu-id="583b1-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="583b1-125">我們建議企業客戶根據其 IT 安全性基礎結構和需求，選擇可滿足其特定需求的解決方案。Microsoft 解決方案範例使用 IPSec 和群組原則來進行伺服器和網域隔離。</span><span class="sxs-lookup"><span data-stu-id="583b1-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="583b1-126">如需詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) 。</span><span class="sxs-lookup"><span data-stu-id="583b1-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="583b1-127">如需問題和批註，請與 secwish@microsoft.com 聯繫。</span><span class="sxs-lookup"><span data-stu-id="583b1-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="583b1-128">另一種可能的解決方法是使用 IPSec，協助保護備份服務本身所傳送的資料。</span><span class="sxs-lookup"><span data-stu-id="583b1-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="583b1-129">如果您選擇此方法，則應該為下列伺服器（其中集區 A 與集區 B 是兩個成對的前端集區）設定 SMB 通訊協定的 IPSec 規則。</span><span class="sxs-lookup"><span data-stu-id="583b1-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="583b1-130">SMB 服務 (TCP/445) 從集區 A 中的每一部前端伺服器到集區 B 所使用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="583b1-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="583b1-131">SMB 服務 (TCP/445) 從集區 B 中的每一部前端伺服器到集區 A 所使用的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="583b1-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="583b1-132">IPsec 不會做為應用程式層級安全性的取代，例如 SSL/TLS。</span><span class="sxs-lookup"><span data-stu-id="583b1-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="583b1-133">使用 IPsec 的其中一個優點是，它可以為現有的應用程式提供網路流量安全性，而不需要加以變更。</span><span class="sxs-lookup"><span data-stu-id="583b1-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="583b1-134">只想要將兩個資料中心之間的傳輸安全的企業，應諮詢其各自的網路硬體廠商，以瞭解使用廠商的設備設定安全的 WAN 連線的方式。</span><span class="sxs-lookup"><span data-stu-id="583b1-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

