---
title: Lync Server 2013： 決定如何部署 Microsoft Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a731b4385dbe46da39fc195e1de6be13057e649d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="5e144-102">決定如何部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e144-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e144-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="5e144-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5e144-104">規劃時 Lync，首要決策在於如何部署 Microsoft Lync： 為 Lync Server 2013 內部部署，或 Lync Online 與 Microsoft Office 365，在雲端上。</span><span class="sxs-lookup"><span data-stu-id="5e144-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="5e144-105">**Lync Server 2013 內部部署**： 此選項提供完整的 Lync 功能集，並提供最大的彈性中設定、 自訂及操作您的部署。</span><span class="sxs-lookup"><span data-stu-id="5e144-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="5e144-106">所有伺服器皆安裝於現場，且由您的組織來維護。</span><span class="sxs-lookup"><span data-stu-id="5e144-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="5e144-107">在內部部署提供的完整範圍 Lync Server 的功能。</span><span class="sxs-lookup"><span data-stu-id="5e144-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="5e144-108">**Lync Online 在雲端中**Lync Online 專為想而無需在 Lync Server 的商務類別功能的成本和靈活性優點基於雲端的立即訊息、 目前狀態和會議的組織。</span><span class="sxs-lookup"><span data-stu-id="5e144-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="5e144-109">透過 Lync Online，Microsoft 部署及維護的所需的伺服器基礎結構，並處理持續維護、 修補和升級。</span><span class="sxs-lookup"><span data-stu-id="5e144-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="5e144-110">在內部部署中提供部分功能不 Lync Online 中提供。</span><span class="sxs-lookup"><span data-stu-id="5e144-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="5e144-111">您最適合的部署類型取決於您想要部署的工作負載，及組織的地理位置和業務狀態。</span><span class="sxs-lookup"><span data-stu-id="5e144-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="5e144-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e144-112">Lync Server</span></span>

<span data-ttu-id="5e144-113">內部部署的 Lync Server 部署最適合下列案例：</span><span class="sxs-lookup"><span data-stu-id="5e144-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="5e144-114">**完整的企業語音功能**   如果您打算部署來取代 PBX 或其使用進階通話功能完整的企業語音解決方案，是必要的內部部署 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="5e144-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="5e144-115">在內部支援與 PBX 系統與主幹，以及進階的電話功能，例如回應群組和通話駐留直接連線。</span><span class="sxs-lookup"><span data-stu-id="5e144-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="5e144-116">Lync Online 目前不支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="5e144-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="5e144-117">**媒體品質控制**   如果您想要完整的媒體品質保證功能，例如通話許可控制 (CAC) 和服務品質 (QoS) 功能，您會想在內部部署。</span><span class="sxs-lookup"><span data-stu-id="5e144-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="5e144-118">**常設聊天室**   如果您需要部署組織的常設聊天室，您必須選擇內部部署。</span><span class="sxs-lookup"><span data-stu-id="5e144-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="5e144-119">**第 3 廠商伺服器應用程式**   僅在內部部署可以搭配信任的第 3 廠商應用程式使用 Microsoft Unified Communications Managed API (UCMA)。</span><span class="sxs-lookup"><span data-stu-id="5e144-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="5e144-120">**多-跨國/跨地區公司需要地區性支援**   如果您有多個國家/地區或區域中的資料中心，且需要部署及管理區域為基礎的伺服器，在內部部署最為適合，因為它可提供這種類型的地區管理功能。</span><span class="sxs-lookup"><span data-stu-id="5e144-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="5e144-121">**完整控制權原則、 報表及升級**   與內部 Lync Server 部署，您可以存取伺服器和用戶端原則、 監視和其他報告，一組完整及升級的時機。</span><span class="sxs-lookup"><span data-stu-id="5e144-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="5e144-122">Lync Online 提供原則設定和報告的子集，並提供有限，雖然重大視窗接受升級。</span><span class="sxs-lookup"><span data-stu-id="5e144-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="5e144-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="5e144-123">Lync Online</span></span>

<span data-ttu-id="5e144-124">如果對您而言，前述清單中沒有任何重要因素，則您可能會想要選擇 Lync Online 以擁有部署和管理上的簡易性。</span><span class="sxs-lookup"><span data-stu-id="5e144-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="5e144-125">Lync Online 提供穩定的 IM、 目前狀態和會議功能設定，而且也可讓語音和視訊通話透過 IP 貴組織中的使用者之間。</span><span class="sxs-lookup"><span data-stu-id="5e144-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

