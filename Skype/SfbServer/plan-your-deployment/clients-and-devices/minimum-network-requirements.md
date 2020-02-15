---
title: Skype 會議 App 的基本網路需求
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 摘要： 的組織不使用 Office 365 且需要存取執行動作的組織所主控的會議資訊。
ms.openlocfilehash: 162d05f9786f02258afa080e630c85d4b513db4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033187"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="4e3cd-103">Skype 會議 App 的基本網路需求</span><span class="sxs-lookup"><span data-stu-id="4e3cd-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="4e3cd-104">**摘要：** 組織不使用 Office 365 且需要存取執行動作的組織所主控的會議資訊。</span><span class="sxs-lookup"><span data-stu-id="4e3cd-104">**Summary:**  Information for organizations who don't use Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="4e3cd-105">本文不是這些應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="4e3cd-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="4e3cd-106">若要允許使用者使用 Skype 會議 App 參加會議的商務用 Skype 中裝載，不使用 Office 365 的組織的網路系統管理員應該 whitelist 或以其他方式提供以下提及的 Fqdn、 IPs 及連接埠。</span><span class="sxs-lookup"><span data-stu-id="4e3cd-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Office 365 should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="4e3cd-107">Skype 會議 App 連線的需求</span><span class="sxs-lookup"><span data-stu-id="4e3cd-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="4e3cd-108">此處所列的資訊是[Office 365 Url 和 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)，可提供更多的深度，並會永遠是最新的子集。</span><span class="sxs-lookup"><span data-stu-id="4e3cd-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="4e3cd-109">應用程式</span><span class="sxs-lookup"><span data-stu-id="4e3cd-109">App</span></span> |<span data-ttu-id="4e3cd-110">目的地 Fqdn</span><span class="sxs-lookup"><span data-stu-id="4e3cd-110">Destination FQDNs</span></span>  |<span data-ttu-id="4e3cd-111">IP 位址</span><span class="sxs-lookup"><span data-stu-id="4e3cd-111">IP Addresses</span></span>  |<span data-ttu-id="4e3cd-112">連接埠</span><span class="sxs-lookup"><span data-stu-id="4e3cd-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="4e3cd-113">**Skype 會議 App**</span><span class="sxs-lookup"><span data-stu-id="4e3cd-113">**Skype Meetings App**</span></span> | <span data-ttu-id="4e3cd-114">\*。 lync.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-114">\*.lync.com</span></span> <br/><span data-ttu-id="4e3cd-115">\*。 infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="4e3cd-116">\*。 pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="4e3cd-117">\*。 sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="4e3cd-118">\*。 msecnd.net</span><span class="sxs-lookup"><span data-stu-id="4e3cd-118">\*.msecnd.net</span></span><br/><span data-ttu-id="4e3cd-119">\*廣播<span></span>。 officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="4e3cd-120">\*powerpoint<span></span>。 officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="4e3cd-121">\*。 office.live.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-121">\*.office.live.com</span></span><br/><span data-ttu-id="4e3cd-122">\*。 cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="4e3cd-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="4e3cd-123">\*.s microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="4e3cd-124">經常更新這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4e3cd-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="4e3cd-125">請參閱[Skype for Business IP 範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)，以及[Office IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="4e3cd-125">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="4e3cd-126">TCP: 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="4e3cd-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="4e3cd-127">UDP: 3478 3481</span><span class="sxs-lookup"><span data-stu-id="4e3cd-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="4e3cd-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="4e3cd-128">**Teams**</span></span>    | <span data-ttu-id="4e3cd-129">\*<span></span>。 microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="4e3cd-130">\*<span></span>。 skype.com</span><span class="sxs-lookup"><span data-stu-id="4e3cd-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="4e3cd-131">經常更新這些 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4e3cd-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="4e3cd-132">請參閱[Skype for Business IP 範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)，以及[Office IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="4e3cd-132">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="4e3cd-133">TCP: 443</span><span class="sxs-lookup"><span data-stu-id="4e3cd-133">TCP:  443</span></span> <br/> <span data-ttu-id="4e3cd-134">UDP: 3478 3481</span><span class="sxs-lookup"><span data-stu-id="4e3cd-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="4e3cd-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4e3cd-135">See also</span></span>
<span data-ttu-id="4e3cd-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="4e3cd-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="4e3cd-137">規劃會議用戶端 （Web 應用程式和會議應用程式）</span><span class="sxs-lookup"><span data-stu-id="4e3cd-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="4e3cd-138">為商務伺服器部署中用 Skype Web 可下載的用戶端</span><span class="sxs-lookup"><span data-stu-id="4e3cd-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="4e3cd-139">支援的平台的 Skype 會議 App</span><span class="sxs-lookup"><span data-stu-id="4e3cd-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
