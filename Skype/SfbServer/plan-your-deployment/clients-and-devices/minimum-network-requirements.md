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
description: 摘要：適用于不使用 Office 365 的組織，且需要存取由此組織託管的會議的資訊。
ms.openlocfilehash: e158d93b68df761b59535f4e9239d14194c10443
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816022"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a><span data-ttu-id="ffcd7-103">Skype 會議 App 最低網路需求</span><span class="sxs-lookup"><span data-stu-id="ffcd7-103">Skype Meetings App minimum network requirements</span></span>
 
<span data-ttu-id="ffcd7-104">**摘要：** 針對沒有使用 Office 365 且需要存取組織所託管之會議的組織的資訊。</span><span class="sxs-lookup"><span data-stu-id="ffcd7-104">**Summary:**  Information for organizations who don't use Office 365 and need to access meetings hosted by organizations that do.</span></span> <span data-ttu-id="ffcd7-105">本文不適用於這些 app 的使用者。</span><span class="sxs-lookup"><span data-stu-id="ffcd7-105">This article is not intended for the users of these apps.</span></span>
  
<span data-ttu-id="ffcd7-106">若要允許使用者使用 Skype 會議應用程式來出席在商務用 Skype Online 中託管的會議，不使用 Office 365 之組織的網路系統管理員應該白名單，或以其他方式提供 Fqdn、Ip 及下列埠（如下所述）。</span><span class="sxs-lookup"><span data-stu-id="ffcd7-106">To allow users to use Skype Meetings App to  attend meetings hosted in Skype for Business Online, network administrators of organizations who don't use Office 365 should whitelist or otherwise make available the FQDNs, IPs, and ports mentioned below.</span></span>

## <a name="requirements-for-skype-meetings-app-connectivity"></a><span data-ttu-id="ffcd7-107">Skype 會議應用程式連線的需求</span><span class="sxs-lookup"><span data-stu-id="ffcd7-107">Requirements for Skype Meetings App connectivity</span></span>

<span data-ttu-id="ffcd7-108">此處所列的資訊是[Office 365 url 和 IP 位址範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)的子集，提供更多的深度，且總保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="ffcd7-108">The information listed here is a subset of [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), which provides more depth and will always be the most up to date.</span></span>
                    
 
|<span data-ttu-id="ffcd7-109">適用</span><span class="sxs-lookup"><span data-stu-id="ffcd7-109">App</span></span> |<span data-ttu-id="ffcd7-110">目的地 Fqdn</span><span class="sxs-lookup"><span data-stu-id="ffcd7-110">Destination FQDNs</span></span>  |<span data-ttu-id="ffcd7-111">IP 位址</span><span class="sxs-lookup"><span data-stu-id="ffcd7-111">IP Addresses</span></span>  |<span data-ttu-id="ffcd7-112">埠</span><span class="sxs-lookup"><span data-stu-id="ffcd7-112">Ports</span></span>  |
|---|---------|---------|---------|
|<span data-ttu-id="ffcd7-113">**Skype 會議應用程式**</span><span class="sxs-lookup"><span data-stu-id="ffcd7-113">**Skype Meetings App**</span></span> | <span data-ttu-id="ffcd7-114">\*. lync.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-114">\*.lync.com</span></span> <br/><span data-ttu-id="ffcd7-115">\*. infra.lync.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-115">\*.infra.lync.com</span></span><br/><span data-ttu-id="ffcd7-116">\*. pipe.aria.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-116">\*.pipe.aria.microsoft.com</span></span><br/><span data-ttu-id="ffcd7-117">\*. sfbassets.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-117">\*.sfbassets.com</span></span><br/><span data-ttu-id="ffcd7-118">\*. msecnd.net</span><span class="sxs-lookup"><span data-stu-id="ffcd7-118">\*.msecnd.net</span></span><br/><span data-ttu-id="ffcd7-119">\*<span> </span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-119">\*broadcast<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="ffcd7-120">\*<span> </span>officeapps.live.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-120">\*powerpoint<span></span>.officeapps.live.com</span></span> <br/><span data-ttu-id="ffcd7-121">\*. office.live.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-121">\*.office.live.com</span></span><br/><span data-ttu-id="ffcd7-122">\*. cdn.office.net</span><span class="sxs-lookup"><span data-stu-id="ffcd7-122">\*.cdn.office.net</span></span><br/><span data-ttu-id="ffcd7-123">\*. s-microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-123">\*.s-microsoft.com</span></span><br/>        |   <span data-ttu-id="ffcd7-124">這些 IP 位址會經常更新。</span><span class="sxs-lookup"><span data-stu-id="ffcd7-124">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="ffcd7-125">請參閱[商務用 SKYPE ip 範圍](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)以及[Office IP 範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="ffcd7-125">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>         |<span data-ttu-id="ffcd7-126">TCP： 80 &amp; 443</span><span class="sxs-lookup"><span data-stu-id="ffcd7-126">TCP: 80 &amp; 443</span></span><br/><span data-ttu-id="ffcd7-127">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="ffcd7-127">UDP: 3478-3481</span></span><br/>
|<span data-ttu-id="ffcd7-128">**團隊**</span><span class="sxs-lookup"><span data-stu-id="ffcd7-128">**Teams**</span></span>    | <span data-ttu-id="ffcd7-129">\*<span></span>. microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-129">\*<span></span>.microsoft.com</span></span> <br/><span data-ttu-id="ffcd7-130">\*<span></span>. skype.com</span><span class="sxs-lookup"><span data-stu-id="ffcd7-130">\*<span></span>.skype.com</span></span> | <span data-ttu-id="ffcd7-131">這些 IP 位址會經常更新。</span><span class="sxs-lookup"><span data-stu-id="ffcd7-131">These IP addresses are frequently updated.</span></span>  <span data-ttu-id="ffcd7-132">請參閱[商務用 SKYPE ip 範圍](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)以及[Office IP 範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span><span class="sxs-lookup"><span data-stu-id="ffcd7-132">See [Skype for Business IP ranges](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) as well as [Office IP Ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)</span></span>      |<span data-ttu-id="ffcd7-133">TCP：443</span><span class="sxs-lookup"><span data-stu-id="ffcd7-133">TCP:  443</span></span> <br/> <span data-ttu-id="ffcd7-134">UDP：3478-3481</span><span class="sxs-lookup"><span data-stu-id="ffcd7-134">UDP: 3478-3481</span></span>

## <a name="see-also"></a><span data-ttu-id="ffcd7-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ffcd7-135">See also</span></span>
<span data-ttu-id="ffcd7-136"><a name="BKMK_Conferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="ffcd7-136"><a name="BKMK_Conferencing"> </a></span></span>

[<span data-ttu-id="ffcd7-137">規劃會議用戶端（Web App 與會議應用程式）</span><span class="sxs-lookup"><span data-stu-id="ffcd7-137">Plan for Meetings clients (Web App and Meetings App)</span></span>](meetings-clients.md)

[<span data-ttu-id="ffcd7-138">在商務用 Skype Server 中部署網頁下載用戶端</span><span class="sxs-lookup"><span data-stu-id="ffcd7-138">Deploy Web downloadable clients in Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[<span data-ttu-id="ffcd7-139">Skype 會議應用程式的支援平臺</span><span class="sxs-lookup"><span data-stu-id="ffcd7-139">Supported platforms for Skype Meetings App</span></span>](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
