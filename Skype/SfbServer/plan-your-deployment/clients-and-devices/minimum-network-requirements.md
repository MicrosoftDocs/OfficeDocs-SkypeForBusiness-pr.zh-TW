---
title: Skype 會議 App 最低網路需求
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
description: 摘要：針對未使用 Microsoft 365 或 Office 365 的組織提供的資訊，並且需要存取由此組織所主控的會議。
ms.openlocfilehash: bcb8cfa74067ec6aa3e895f757c71d075888f447
ms.sourcegitcommit: bf6521f0bc91a55dcf849506bb757ebfae54fcb1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529186"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="cdb20-103">Skype 會議 App 最低網路需求</span><span class="sxs-lookup"><span data-stu-id="cdb20-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="cdb20-104">**摘要：** 未使用 Microsoft 365 或 Office 365 的組織資訊，而且需要存取組織所主持的會議。</span><span class="sxs-lookup"><span data-stu-id="cdb20-104">**Summary:**  Information for organizations who don't use Microsoft 365 or Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="cdb20-105">本文並非適用于這些應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="cdb20-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="cdb20-106">若要讓使用者可以使用 Skype 會議應用程式來參加在商務用 Skype Online 中主控的會議，未使用 Microsoft 365 或 Office 365 之組織的網路系統管理員應該允許或以其他方式使用下列所述的 Fqdn、IPs 及埠。</span><span class="sxs-lookup"><span data-stu-id="cdb20-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Microsoft 365 or Office 365 should allow or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="cdb20-107">Skype 會議應用程式連線的需求</span><span class="sxs-lookup"><span data-stu-id="cdb20-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="cdb20-108">此處所列的資訊是[Office 365 URLs 及 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)的子集，其提供更深入的深度，且一定會為最新。</span><span class="sxs-lookup"><span data-stu-id="cdb20-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="cdb20-109">應用程式</span><span class="sxs-lookup"><span data-stu-id="cdb20-109">App</span></span> |<span data-ttu-id="cdb20-110">目的地 Fqdn</span><span class="sxs-lookup"><span data-stu-id="cdb20-110">Destination FQDNs</span></span>  |<span data-ttu-id="cdb20-111">IP 位址</span><span class="sxs-lookup"><span data-stu-id="cdb20-111">IP Addresses</span></span>  |<span data-ttu-id="cdb20-112">連接埠</span><span class="sxs-lookup"><span data-stu-id="cdb20-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="cdb20-113">**Skype 會議 App**</span><span class="sxs-lookup"><span data-stu-id="cdb20-113">**Skype Meetings App**</span></span> | <span data-ttu-id="cdb20-114">\*。 lync.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-114">\*.lync.com</span></span> <br/><span data-ttu-id="cdb20-115">\*。 infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="cdb20-116">\*。 pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="cdb20-117">\*。 sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="cdb20-118">\*。 msecnd.net</span><span class="sxs-lookup"><span data-stu-id="cdb20-118">\*.msecnd.net</span></span><br/><span data-ttu-id="cdb20-119">\*<span></span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="cdb20-120">\*<span></span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="cdb20-121">\*。 office.live.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-121">\*.office.live.com</span></span><br/><span data-ttu-id="cdb20-122">\*。 cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="cdb20-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="cdb20-123">s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="cdb20-124">這兩個 IP 位址經常更新。</span><span class="sxs-lookup"><span data-stu-id="cdb20-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="cdb20-125">請參閱[商務用 SKYPE ip 範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)和[Office ip 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="cdb20-125">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="cdb20-126">TCP： 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="cdb20-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="cdb20-127">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="cdb20-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="cdb20-128">**Teams**</span><span class="sxs-lookup"><span data-stu-id="cdb20-128">**Teams**</span></span>    | <span data-ttu-id="cdb20-129">\*<span></span>。 microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="cdb20-130">\*<span></span>。 skype.com</span><span class="sxs-lookup"><span data-stu-id="cdb20-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="cdb20-131">這兩個 IP 位址經常更新。</span><span class="sxs-lookup"><span data-stu-id="cdb20-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="cdb20-132">請參閱[商務用 SKYPE ip 範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)和[Office ip 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="cdb20-132">See [Skype for Business IP ranges](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="cdb20-133">TCP：443</span><span class="sxs-lookup"><span data-stu-id="cdb20-133">TCP:  443</span></span> <br/> <span data-ttu-id="cdb20-134">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="cdb20-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="cdb20-135">請參閱</span><span class="sxs-lookup"><span data-stu-id="cdb20-135">See also</span></span>
<span data-ttu-id="cdb20-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="cdb20-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="cdb20-137">規劃會議用戶端（Web 應用程式和會議應用程式）</span><span class="sxs-lookup"><span data-stu-id="cdb20-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="cdb20-138">在商務用 Skype Server 中部署 Web 可下載的用戶端</span><span class="sxs-lookup"><span data-stu-id="cdb20-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="cdb20-139">支援的 Skype 會議應用程式平臺</span><span class="sxs-lookup"><span data-stu-id="cdb20-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
