---
title: Lync Server 2013：決定如何部署 Microsoft Lync
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
ms.openlocfilehash: d5f4e622d71175ec393706af39ce470c5030216a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="883ff-102">決定如何部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="883ff-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="883ff-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="883ff-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="883ff-104">在規劃 Lync 時，第一個主要決定是如何部署 Microsoft Lync：在內部部署上使用 Lync Server 2013，或在雲端使用 Microsoft 365 或 Office 365 的 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="883ff-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft 365 or Office 365 in the cloud.</span></span>

  - <span data-ttu-id="883ff-105">**Lync Server 2013 內部部署**：此選擇提供完整的 Lync 功能集，並提供設定、自訂及作業部署的最佳靈活性。</span><span class="sxs-lookup"><span data-stu-id="883ff-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="883ff-106">所有伺服器皆安裝於現場，且由您的組織來維護。</span><span class="sxs-lookup"><span data-stu-id="883ff-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="883ff-107">內部部署部署提供 Lync Server 功能的完整範圍。</span><span class="sxs-lookup"><span data-stu-id="883ff-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="883ff-108">**雲端中的 Lync Online**Lync Online 是專為需要雲端式立即訊息、目前狀態和會議的成本和靈活性優勢所設計的組織，而不會犧牲 Lync Server 的商務類別功能。</span><span class="sxs-lookup"><span data-stu-id="883ff-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="883ff-109">在 Lync Online 中，Microsoft 會部署及維護必要的伺服器基礎結構，並處理即時維護、修補程式和升級。</span><span class="sxs-lookup"><span data-stu-id="883ff-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="883ff-110">Lync Online 中無法使用內部部署中所提供的部分功能。</span><span class="sxs-lookup"><span data-stu-id="883ff-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="883ff-111">您最適合的部署類型取決於您想要部署的工作負載，及組織的地理位置和業務狀態。</span><span class="sxs-lookup"><span data-stu-id="883ff-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="883ff-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="883ff-112">Lync Server</span></span>

<span data-ttu-id="883ff-113">內部部署的 Lync Server 部署最適合下列案例：</span><span class="sxs-lookup"><span data-stu-id="883ff-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="883ff-114">**完整的 Enterprise Voice 功能**    如果您計畫部署完整的企業語音解決方案以取代 PBX 或使用高級通話功能，則需要內部部署 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="883ff-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="883ff-115">內部部署支援與 PBX 系統和主幹的直接連線能力，以及高級電話功能（如回應群組和通話駐留）。</span><span class="sxs-lookup"><span data-stu-id="883ff-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="883ff-116">Lync Online 目前不支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="883ff-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="883ff-117">**媒體質量控制**    如果您想要完整範圍的媒體品質保證功能（例如通話許可控制（CAC）和服務品質（QoS）功能），您將需要內部部署。</span><span class="sxs-lookup"><span data-stu-id="883ff-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="883ff-118">**Persistent 聊天**    如果您需要為組織部署持續性聊天，您必須選擇內部部署。</span><span class="sxs-lookup"><span data-stu-id="883ff-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="883ff-119">**協力廠商伺服器應用程式**    只有內部部署才能與使用 Microsoft 整合通訊 Managed API （UCMA）的受信任協力廠商應用程式搭配使用。</span><span class="sxs-lookup"><span data-stu-id="883ff-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="883ff-120">**需要區域支援的多國/多地區性公司**    如果您有多個國家或地區的資料中心，且需要以地區性為基礎部署和管理伺服器，則內部部署的部署最佳，因為它會提供這種類型的區域管理功能。</span><span class="sxs-lookup"><span data-stu-id="883ff-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="883ff-121">**完全控制原則、報告和升級**    使用內部部署 Lync Server 部署，您可以存取完整的伺服器和用戶端原則集合、監控和其他報告，以及升級的時間。</span><span class="sxs-lookup"><span data-stu-id="883ff-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="883ff-122">Lync Online 提供原則設定與報告的子集，並提供有限但有意義的視窗，可接受升級。</span><span class="sxs-lookup"><span data-stu-id="883ff-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="883ff-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="883ff-123">Lync Online</span></span>

<span data-ttu-id="883ff-124">如果對您而言，前述清單中沒有任何重要因素，則您可能會想要選擇 Lync Online 以擁有部署和管理上的簡易性。</span><span class="sxs-lookup"><span data-stu-id="883ff-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="883ff-125">Lync Online 可提供強健的 IM、顯示狀態和會議功能集，也可讓您組織中使用者間的語音和影片通話。</span><span class="sxs-lookup"><span data-stu-id="883ff-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
