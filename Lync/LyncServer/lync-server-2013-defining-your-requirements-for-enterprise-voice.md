---
title: Lync Server 2013：定義 Enterprise Voice 的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0ce05c39e3433ff949d82f583207aebfba871fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="fbcbe-102">在 Lync Server 2013 中定義 Enterprise Voice 的需求</span><span class="sxs-lookup"><span data-stu-id="fbcbe-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbcbe-103">_**主題上次修改日期：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="fbcbe-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="fbcbe-104">本主題概述您需要的考慮，包括您在拓撲中的區域、網站和連結，以及當您部署企業語音時這些專案的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fbcbe-105">如需協助您做出這些決定的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 [網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)]。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="fbcbe-106">網站和區域</span><span class="sxs-lookup"><span data-stu-id="fbcbe-106">Sites and Regions</span></span>

<span data-ttu-id="fbcbe-107">首先，請在您的拓撲中找出您要部署企業語音的網站，以及這些網站所屬的網路區域。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="fbcbe-108">具體來說，請考慮您將如何提供公用的交換電話網絡（PSTN）連線至每個網站。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="fbcbe-109">出於易管理性和後勤原因，這些網站所屬的區域可以是決定因素。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="fbcbe-110">決定要在本機部署閘道的位置，將部署 Survivable 分支裝置（SBAs），以及您可以將 SIP trunks （本機或在中央網站）設定為網際網路電話服務提供者（ITSP）。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="fbcbe-111">網站之間的網路連結</span><span class="sxs-lookup"><span data-stu-id="fbcbe-111">Network Links Between Sites</span></span>

<span data-ttu-id="fbcbe-112">您也需要考慮您在中央網站與其分支網站之間的網路連結上預期的頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="fbcbe-113">如果您有或想要在網站之間部署彈性 WAN 連結，建議您在每個分支網站部署一個閘道，以針對這些網站上的使用者提供本機直向內撥打電話（已結束）。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="fbcbe-114">如果您有彈性 WAN 連結，但 WAN 連結上的頻寬可能受到限制，請設定該連結的 [呼叫許可控制]。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="fbcbe-115">如果您沒有可復原的 WAN 連結，請在分支網站中主持少於1000個使用者，而且沒有當地訓練有素的 Lync Server 管理員可用，我們建議您在分支網站上部署 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="fbcbe-116">如果您是在分支網站上的1000和5000使用者之間主持、缺乏強健的 WAN 連線，且已提供訓練有素的 Lync Server 管理員，我們建議您在分支網站上部署 Survivable 分支伺服器與小型閘道。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="fbcbe-117">如果您有支援媒體旁路的閘道對等，也可以考慮在受限制的連結上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="fbcbe-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbcbe-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="fbcbe-118">See Also</span></span>


<span data-ttu-id="fbcbe-119">[Lync Server 2013 中的 [高級企業語音功能] 的網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="fbcbe-119">[Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

