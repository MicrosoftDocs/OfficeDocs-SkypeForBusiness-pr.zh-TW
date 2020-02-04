---
title: Lync Server 2013：決定 Microsoft Lync 的部署方式
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
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="c2ab6-102">決定 Lync Server 2013 的部署方式</span><span class="sxs-lookup"><span data-stu-id="c2ab6-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2ab6-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c2ab6-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c2ab6-104">規劃 Lync 時，第一個主要決定是如何部署 Microsoft Lync：在內部部署中使用 Lync Server 2013，或在雲端使用 Microsoft Office 365 的 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="c2ab6-105">**Lync Server 2013 內部部署**：此選項提供完整的 Lync 功能集，並提供設定、自訂及操作您的部署的絕佳靈活性。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="c2ab6-106">所有伺服器都安裝在現場，且由您的組織維護。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="c2ab6-107">內部部署部署提供完整的 Lync 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="c2ab6-108">**雲端中的 Lync Online**Lync Online 是專為想要以雲端為基礎的立即訊息、目前狀態及會議帶來成本與靈活性效益而設計，而不會犧牲 Lync Server 的企業級功能。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="c2ab6-109">在 Lync Online 中，Microsoft 會部署並維護所需的伺服器基礎結構，並處理持續進行的維護、修補程式和升級。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="c2ab6-110">在 Lync Online 中，內部部署中提供的部分功能無法使用。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="c2ab6-111">最適合您的部署類型，取決於您要部署的工作負載，以及貴組織的地理位置與業務狀態。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="c2ab6-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="c2ab6-112">Lync Server</span></span>

<span data-ttu-id="c2ab6-113">內部部署 Lync Server 部署最適合下列案例：</span><span class="sxs-lookup"><span data-stu-id="c2ab6-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="c2ab6-114">**完整的企業語音功能**   如果您打算部署完整的企業語音解決方案來取代 PBX 或使用高級通話功能，則需要內部部署 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="c2ab6-115">內部部署支援與 PBX 系統與 trunks 的直接連線，以及 [回應群組] 和 [通話駐留] 等高級電話功能。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="c2ab6-116">Lync Online 目前不支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="c2ab6-117">**媒體質量控制**   如果您想要完整的多媒體品質保證功能（例如 [呼叫許可控制] （CAC）和 [服務品質（QoS）] 功能），您需要內部部署。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="c2ab6-118">**持續聊天**   如果您需要為貴組織部署持續聊天，您必須選擇內部部署。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="c2ab6-119">**協力廠商伺服器應用程式**   只有內部部署部署才能搭配使用 Microsoft 整合通訊 Managed API （UCMA）的受信任的協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="c2ab6-120">\*\*\*\*    如果您在多個國家或地區中有資料中心，且需要在地區性基礎上部署和管理伺服器，則需要地區支援的多國國家/地區公司（內部部署）最佳，因為它提供了這種類型的地區管理功能。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="c2ab6-121">**使用內部部署 Lync Server 部署來完全控制原則、報告和升級**   ，您可以存取完整的伺服器和用戶端原則、監控及其他報告，以及升級的時間。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="c2ab6-122">Lync Online 提供原則設定和報告的子集，並提供有限但重要的視窗來接受升級。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="c2ab6-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="c2ab6-123">Lync Online</span></span>

<span data-ttu-id="c2ab6-124">如果前面清單中的任何一個要素對您而言都不重要，您可能會想要選擇 Lync Online，以簡化部署和易管理性。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="c2ab6-125">Lync Online 可提供強健的 IM、目前狀態及會議功能集，同時也能在您組織中的使用者之間使用語音和視頻通話。</span><span class="sxs-lookup"><span data-stu-id="c2ab6-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

