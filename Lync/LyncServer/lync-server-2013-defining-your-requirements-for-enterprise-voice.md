---
title: Lync Server 2013：定義您的 Enterprise Voice 需求
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
ms.openlocfilehash: eeadb699c12b3f0ece883484ea8c935bfb795256
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504340"
---
# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="65350-102">在 Lync Server 2013 中定義您的 Enterprise Voice 需求</span><span class="sxs-lookup"><span data-stu-id="65350-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65350-103">_**主題上次修改日期：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="65350-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="65350-104">本主題概述您需要對拓撲中的網站與連結之間的考慮，以及當您部署企業語音時，這些網站的重要性。</span><span class="sxs-lookup"><span data-stu-id="65350-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="65350-105">如需協助您進行這些決策的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的「高級 Enterprise Voice 功能」網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="65350-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="65350-106">網站和地區</span><span class="sxs-lookup"><span data-stu-id="65350-106">Sites and Regions</span></span>

<span data-ttu-id="65350-107">首先，識別您的拓撲中的網站，您將在其中部署企業語音和這些網站所屬的網路地區。</span><span class="sxs-lookup"><span data-stu-id="65350-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="65350-108">明確而言，請考量您要如何為各個網站提供公用交換電話網路 (PSTN) 連線。</span><span class="sxs-lookup"><span data-stu-id="65350-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="65350-109">就管理性與物流的考量而言，這些網站的所屬地區可能會是決定性因素。</span><span class="sxs-lookup"><span data-stu-id="65350-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="65350-110">決定要在本機部署閘道的位置，Survivable 分支裝置 (Sba) 部署所在的位置，以及您可以在本機或在中央網站) 設定 SIP 主幹 ( (ITSP) 。</span><span class="sxs-lookup"><span data-stu-id="65350-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="65350-111">網站間的網路連結</span><span class="sxs-lookup"><span data-stu-id="65350-111">Network Links Between Sites</span></span>

<span data-ttu-id="65350-112">您也需要考慮您期望在中央網站與其分支網站之間之網路連結的頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="65350-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="65350-113">如果您有或想要在網站之間部署彈性的 WAN 連結，建議您在每個分支網站上部署閘道，以提供本機直接向內撥號 (已) 使用者在這些網站上終止。</span><span class="sxs-lookup"><span data-stu-id="65350-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="65350-114">如果您有彈性的 WAN 連結，但 WAN 連結的頻寬可能受限，請為該連結設定通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="65350-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="65350-115">如果您沒有可恢復的 WAN 連結，請在分支網站上裝載低於1000的使用者，而且沒有本機訓練有素的 Lync Server 系統管理員，我們建議您在分支網站上部署 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="65350-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="65350-116">如果您在分支網站上主持1000和5000使用者、缺乏彈性的 WAN 連線，且有訓練有素的 Lync Server 系統管理員，我們建議您在分支網站上部署 Survivable 分支伺服器搭配小型閘道。</span><span class="sxs-lookup"><span data-stu-id="65350-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="65350-117">如果您有支援媒體旁路的閘道對等，也請考慮對受限的連結啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="65350-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65350-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="65350-118">See Also</span></span>


[<span data-ttu-id="65350-119">Lync Server 2013 中的高級 Enterprise Voice 功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="65350-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

