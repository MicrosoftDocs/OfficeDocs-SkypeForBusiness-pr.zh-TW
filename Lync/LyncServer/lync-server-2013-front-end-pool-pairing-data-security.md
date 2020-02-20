---
title: Lync Server 2013： 前端集區配對資料安全性
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
ms.openlocfilehash: 26759c982723fd656ac3456aad630bc695a7343e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="62964-102">前端配對 Lync Server 2013 中的資料安全性集區</span><span class="sxs-lookup"><span data-stu-id="62964-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62964-103">_**上次修改主題：** 2014年-10-07_</span><span class="sxs-lookup"><span data-stu-id="62964-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="62964-104">備份服務是在兩個配對的前端集區，持續跨兩個資料中心的災害復原用途之間傳輸使用者資料和會議內容的 Lync Server 2013 中引進的資料複寫機制。</span><span class="sxs-lookup"><span data-stu-id="62964-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="62964-105">使用者資料包含使用者的 SIP Uri，以及連絡人清單和設定。</span><span class="sxs-lookup"><span data-stu-id="62964-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="62964-106">會議內容包含 Microsoft PowerPoint 2010 上傳，以及在會議中使用的白板。</span><span class="sxs-lookup"><span data-stu-id="62964-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="62964-107">從來源集區、 使用者資料和會議內容會匯出從本機儲存體、 zipped、 轉接至目標集區，它是在其中顯示解壓縮並匯入至本機儲存體。</span><span class="sxs-lookup"><span data-stu-id="62964-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="62964-108">備份服務假設兩個資料中心之間的通訊連結會受到網際網路從公司網路內。</span><span class="sxs-lookup"><span data-stu-id="62964-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="62964-109">它不會加密的兩個資料中心之間轉送的資料，也不其原生封裝在一個安全的通訊協定，例如 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="62964-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="62964-110">因此，從公司網路內的內部人員攔截攻擊可能會。</span><span class="sxs-lookup"><span data-stu-id="62964-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="62964-111">評估安全性風險</span><span class="sxs-lookup"><span data-stu-id="62964-111">Evaluating Security Risks</span></span>

<span data-ttu-id="62964-112">跨多個資料中心部署 Lync Server 2013，並使用災害復原功能任何企業必須確定該跨資料中心流量受到其公司內部網路。</span><span class="sxs-lookup"><span data-stu-id="62964-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="62964-113">關於內部攻擊保護哪些照護必須保護資料中心之間的通訊連結企業版。</span><span class="sxs-lookup"><span data-stu-id="62964-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="62964-114">企業版的資料中心會受到保護公司內部網路背後的假設是標準。</span><span class="sxs-lookup"><span data-stu-id="62964-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="62964-115">有許多其他類型的公司在這些資料中心間傳輸的機密資料。</span><span class="sxs-lookup"><span data-stu-id="62964-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="62964-116">企業的 IT 基礎結構是可怕風險，如果未受到保護這些跨資料中心的連結。</span><span class="sxs-lookup"><span data-stu-id="62964-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="62964-117">雖然攻擊的風險，攔截位在公司網路內已存在，它是相當包含與公開至網際網路的流量。</span><span class="sxs-lookup"><span data-stu-id="62964-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="62964-118">具體而言，（例如 SIP Uri) 的備份服務所公開的使用者資料是通常可透過其他方式，例如 Exchange 或其他目錄軟體全域通訊錄公司內的所有員工。</span><span class="sxs-lookup"><span data-stu-id="62964-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="62964-119">因此，焦點應該在保護備份服務是用來將兩個配對集區之間的資料複製兩個資料中心間的 WAN。</span><span class="sxs-lookup"><span data-stu-id="62964-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="62964-120">減輕安全性風險</span><span class="sxs-lookup"><span data-stu-id="62964-120">Mitigating Security Risks</span></span>

<span data-ttu-id="62964-121">有許多方法來加強安全性保護備份服務的流量，範圍從限制存取權來保護 WAN 的資料中心兩個資料中心之間傳輸。</span><span class="sxs-lookup"><span data-stu-id="62964-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="62964-122">在大多數情況下，部署 Lync Server 2013 的企業可能中已有必要的安全性基礎結構的地方。</span><span class="sxs-lookup"><span data-stu-id="62964-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="62964-123">尋找下列項目的指引企業版，Microsoft 會提供如何建立安全的 IT 基礎結構的範例方案。</span><span class="sxs-lookup"><span data-stu-id="62964-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="62964-124">不過，這並不表示它是唯一的解決方案，也不表示它是 Lync Server 的較佳的解決方案。</span><span class="sxs-lookup"><span data-stu-id="62964-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="62964-125">建議企業客戶選擇解決方案符合其特定需求，根據其 IT 安全性基礎結構與需求。範例 Microsoft solution 採用 IPSec 」 和 「 群組原則的伺服器和為了隔離網域。</span><span class="sxs-lookup"><span data-stu-id="62964-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="62964-126">如需詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544)。</span><span class="sxs-lookup"><span data-stu-id="62964-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="62964-127">問題和註解，請連絡 secwish@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="62964-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="62964-128">其他可能的解決方案是使用 IPSec 目的只是為了協助確保備份服務傳送本身的資料安全。</span><span class="sxs-lookup"><span data-stu-id="62964-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="62964-129">如果您選擇此方法時，您應該設定為下列的伺服器，其中的集區和集區 B 是兩個配對的前端集區的 SMB 通訊協定的 IPSec 規則。</span><span class="sxs-lookup"><span data-stu-id="62964-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="62964-130">SMB (TCP/445) 從服務每個前端伺服器集區的檔案存放區使用的集區 b。</span><span class="sxs-lookup"><span data-stu-id="62964-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="62964-131">SMB (TCP/445) 從服務每個前端伺服器集區 B 至集區 a 所使用檔案存放區</span><span class="sxs-lookup"><span data-stu-id="62964-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="62964-132">IPsec，不得為應用程式層級安全性，例如 SSL/TLS 的替代文字。</span><span class="sxs-lookup"><span data-stu-id="62964-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="62964-133">使用 IPsec 的一項優點是可以提供網路流量安全之現有應用程式而不必將它們變更。</span><span class="sxs-lookup"><span data-stu-id="62964-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="62964-134">想要只之間安全傳輸兩個資料中心的企業應諮詢其各自的網路硬體廠商有關使用供應商的設備來設定安全的 WAN 連線的方式。</span><span class="sxs-lookup"><span data-stu-id="62964-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

