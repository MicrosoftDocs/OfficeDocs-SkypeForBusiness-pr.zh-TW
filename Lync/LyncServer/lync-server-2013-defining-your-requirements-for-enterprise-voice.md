---
title: Lync Server 2013： 定義 Enterprise Voice 的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0406286f4f9d8251743fe6ff3a4807dff277fe92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="17819-102">定義 Lync Server 2013 中的 Enterprise Voice 的需求</span><span class="sxs-lookup"><span data-stu-id="17819-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17819-103">_**主題上次修改日期：** 2012年-08-07_</span><span class="sxs-lookup"><span data-stu-id="17819-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="17819-104">本主題概要說明您必須先需區域、 網站及您的拓撲中的網站和方式的重要部署 Enterprise Voice 時之間的連結的考量。</span><span class="sxs-lookup"><span data-stu-id="17819-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="17819-105">如需可協助您進行這些決策的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的進階 Enterprise Voice 功能的網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)。</span><span class="sxs-lookup"><span data-stu-id="17819-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="17819-106">網站和地區</span><span class="sxs-lookup"><span data-stu-id="17819-106">Sites and Regions</span></span>

<span data-ttu-id="17819-107">首先，找出您要部署 Enterprise Voice 和這些網站隸屬於網路地區的拓撲中的站台。</span><span class="sxs-lookup"><span data-stu-id="17819-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="17819-108">明確而言，請考量您要如何為各個網站提供公用交換電話網路 (PSTN) 連線。</span><span class="sxs-lookup"><span data-stu-id="17819-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="17819-109">就管理性與物流的考量而言，這些網站的所屬地區可能會是決定性因素。</span><span class="sxs-lookup"><span data-stu-id="17819-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="17819-110">決定其中閘道會部署在本機上，其中將部署 Survivable Branch Appliance (Sba)，其中您可以設定 SIP 主幹 （本機或在中央網站） 網際網路電話語音服務提供者 (ITSP)。</span><span class="sxs-lookup"><span data-stu-id="17819-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="17819-111">網站間的網路連結</span><span class="sxs-lookup"><span data-stu-id="17819-111">Network Links Between Sites</span></span>

<span data-ttu-id="17819-112">您也必須考慮您預期的網路連結您的中央網站和其分支站台之間的頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="17819-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="17819-113">如果您有，或計劃部署，可恢復的 WAN 連結之間的網站，建議您部署的閘道，以提供使用者在這些網站上的本機直接向內撥號 (DID) 終止每個分支網站。</span><span class="sxs-lookup"><span data-stu-id="17819-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="17819-114">如果您有彈性的 WAN 連結，但 WAN 連結的頻寬可能受限，請為該連結設定通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="17819-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="17819-115">如果您不具備可恢復的 WAN 連結，裝載少於 1000 位使用者在您的分支網站，而且不具有本機受過訓練的 Lync Server 系統管理員可以使用，我們建議您將部署 Survivable Branch Appliance 分支網站。</span><span class="sxs-lookup"><span data-stu-id="17819-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="17819-116">如果您主控 1000年到 5000 分支網站的使用者之間，缺少可恢復的 WAN 連線，並有經過訓練的 Lync Server 系統管理員可以使用，我們建議您部署 Survivable Branch Server 小型分支網站閘道。</span><span class="sxs-lookup"><span data-stu-id="17819-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="17819-117">如果您有支援媒體旁路的閘道對等，也請考慮對受限的連結啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="17819-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17819-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17819-118">See Also</span></span>


[<span data-ttu-id="17819-119">Lync Server 2013 中的進階 Enterprise Voice 功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="17819-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

