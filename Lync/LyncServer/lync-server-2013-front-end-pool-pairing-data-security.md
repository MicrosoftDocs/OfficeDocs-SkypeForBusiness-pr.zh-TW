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
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="f267c-102">Lync Server 2013 中前端集區配對資料安全性</span><span class="sxs-lookup"><span data-stu-id="f267c-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f267c-103">_**主題上次修改日期：** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="f267c-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="f267c-104">備份服務是在 Lync Server 2013 中引入的資料複製機制，可在兩個資料中心之間連續傳送使用者資料和會議內容，以進行災害復原。</span><span class="sxs-lookup"><span data-stu-id="f267c-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="f267c-105">使用者資料包含使用者 SIP Uri 以及連絡人清單和設定。</span><span class="sxs-lookup"><span data-stu-id="f267c-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="f267c-106">會議內容包括 Microsoft PowerPoint 2010 上傳，以及在會議中使用的白板。</span><span class="sxs-lookup"><span data-stu-id="f267c-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="f267c-107">從來源池中，使用者資料和會議內容是從本機存儲區（zipped）匯出到目標池，並將其解壓縮並匯入到本機儲存區。</span><span class="sxs-lookup"><span data-stu-id="f267c-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="f267c-108">備份服務假設兩個資料中心之間的通訊連結位於從網際網路保護的公司網路內。</span><span class="sxs-lookup"><span data-stu-id="f267c-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="f267c-109">它不會對兩個資料中心之間的傳輸資料進行加密，也不會將它本身封裝在安全通訊協定（例如 HTTPS）中。</span><span class="sxs-lookup"><span data-stu-id="f267c-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="f267c-110">因此，來自公司網路內部人員的中間人攻擊是可能的。</span><span class="sxs-lookup"><span data-stu-id="f267c-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="f267c-111">評估安全風險</span><span class="sxs-lookup"><span data-stu-id="f267c-111">Evaluating Security Risks</span></span>

<span data-ttu-id="f267c-112">跨多個資料中心部署 Lync Server 2013 並使用災害復原功能的任何企業，都必須確保跨資料中心流量受到其公司內部網路的保護。</span><span class="sxs-lookup"><span data-stu-id="f267c-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="f267c-113">考慮內部攻擊防護的企業必須保護資料中心間的通訊連結。</span><span class="sxs-lookup"><span data-stu-id="f267c-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="f267c-114">假設企業的資料中心受保護在公司內部網路的後面是標準的。</span><span class="sxs-lookup"><span data-stu-id="f267c-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="f267c-115">在這些資料中心中傳送了許多其他類型的公司機密資料。</span><span class="sxs-lookup"><span data-stu-id="f267c-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="f267c-116">如果這些跨資料中心連結未受到保護，企業的 IT 基礎結構就會 dire 風險。</span><span class="sxs-lookup"><span data-stu-id="f267c-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="f267c-117">雖然在商業網路中存在中間人攻擊的風險，但與公開網路流量相比，它相對包含。</span><span class="sxs-lookup"><span data-stu-id="f267c-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="f267c-118">具體來說，由備份服務所公開的使用者資料（例如 SIP Uri），通常可透過其他方法（例如 Exchange 或其他目錄軟體的全域通訊錄）來提供給公司內的所有員工。</span><span class="sxs-lookup"><span data-stu-id="f267c-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="f267c-119">因此，當您使用備份服務在兩個配對的池中複製資料時，重點應該是保護兩個資料中心之間的 WAN。</span><span class="sxs-lookup"><span data-stu-id="f267c-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="f267c-120">減輕安全性風險</span><span class="sxs-lookup"><span data-stu-id="f267c-120">Mitigating Security Risks</span></span>

<span data-ttu-id="f267c-121">您可以透過多種方式來加強備份服務流量的安全性保護，包括限制存取資料中心，以保護兩個資料中心之間的 WAN 傳輸。</span><span class="sxs-lookup"><span data-stu-id="f267c-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="f267c-122">在大多數情況下，部署 Lync Server 2013 的企業可能已經有必要的安全性基礎結構。</span><span class="sxs-lookup"><span data-stu-id="f267c-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="f267c-123">針對尋求指導方針的企業，Microsoft 提供的解決方案就是建立安全 IT 基礎結構的範例。</span><span class="sxs-lookup"><span data-stu-id="f267c-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="f267c-124">不過，這並不表示它是唯一的解決方案，也不會暗示它是 Lync Server 的首選方案。</span><span class="sxs-lookup"><span data-stu-id="f267c-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="f267c-125">我們建議企業客戶根據其 IT 安全基礎結構和需求，選擇適合其特定需求的方案。Microsoft 解決方案範例使用 IPSec 和群組原則進行伺服器與網域隔離。</span><span class="sxs-lookup"><span data-stu-id="f267c-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="f267c-126">如需詳細資訊[http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="f267c-126">For details, see [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="f267c-127">如需問題和批註，請與 secwish@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="f267c-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="f267c-128">另一種可能的解決方法是使用 IPSec 來協助保護備份服務本身所傳送的資料。</span><span class="sxs-lookup"><span data-stu-id="f267c-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="f267c-129">如果您選擇這個方法，您應該針對下列伺服器設定 SMB 通訊協定的 IPSec 規則，其中池 A 和池 B 都是兩個配對的前端池。</span><span class="sxs-lookup"><span data-stu-id="f267c-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="f267c-130">從 Pool A 中的每個前端伺服器到池 B 所使用之檔案存放區的 SMB 服務（TCP/445）。</span><span class="sxs-lookup"><span data-stu-id="f267c-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="f267c-131">從 Pool B 中的每個前端伺服器到 Pool A 所使用之檔案存放區的 SMB 服務（TCP/445）。</span><span class="sxs-lookup"><span data-stu-id="f267c-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f267c-132">IPsec 不是用來取代應用程式層級安全性，例如 SSL/TLS。</span><span class="sxs-lookup"><span data-stu-id="f267c-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="f267c-133">使用 IPsec 的其中一個優點是，它可以提供現有應用程式的網路流量安全性，而不需變更它們。</span><span class="sxs-lookup"><span data-stu-id="f267c-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="f267c-134">只要想要保護兩個資料中心間傳輸的企業，就應該諮詢其各自的網路硬體廠商，瞭解如何使用供應商的裝置來設定安全的 WAN 連線。</span><span class="sxs-lookup"><span data-stu-id="f267c-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

