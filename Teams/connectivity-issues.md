---
title: 疑難排解團隊用戶端的連線問題
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 針對 Microsoft Teams 用戶端的連線問題進行疑難排解，此問題主要是由防火牆或 Proxy 連線所造成，並了解如何加以修正。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 116ce1afef08a6f1639ed011b799f9ca43ea57f5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085229"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="aa978-103">針對 Microsoft Teams 用戶端的連線問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="aa978-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="aa978-104">Microsoft Teams 用戶端所發現的問題大多可以追溯到防火牆或 Proxy 連線。</span><span class="sxs-lookup"><span data-stu-id="aa978-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="aa978-105">確認防火牆或 Proxy 中已開啟必要的 URL、IP 位址和連接埠，將會讓不必要的疑難排解工作降到最低。</span><span class="sxs-lookup"><span data-stu-id="aa978-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="aa978-106">如需 Microsoft 團隊所需 Url 和 IPs 的特定資訊，請參閱[microsoft 365 和 Office 365 url 和 IP 位址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支援文章。</span><span class="sxs-lookup"><span data-stu-id="aa978-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="aa978-107">下列案例需要在防火牆中開啟特定的 URL 和連接埠。</span><span class="sxs-lookup"><span data-stu-id="aa978-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="aa978-108">驗證</span><span class="sxs-lookup"><span data-stu-id="aa978-108">Authentication</span></span>

-   <span data-ttu-id="aa978-109">Microsoft Teams 用戶端連線</span><span class="sxs-lookup"><span data-stu-id="aa978-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="aa978-110">共同作業</span><span class="sxs-lookup"><span data-stu-id="aa978-110">Collaboration</span></span>

-   <span data-ttu-id="aa978-111">媒體</span><span class="sxs-lookup"><span data-stu-id="aa978-111">Media</span></span>

-   <span data-ttu-id="aa978-112">共用服務</span><span class="sxs-lookup"><span data-stu-id="aa978-112">Shared Services</span></span>

-   <span data-ttu-id="aa978-113">第三方整合</span><span class="sxs-lookup"><span data-stu-id="aa978-113">Third Party Integration</span></span>

-   <span data-ttu-id="aa978-114">商務用 Skype 互通性</span><span class="sxs-lookup"><span data-stu-id="aa978-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="aa978-115">商務用 Skype 用戶端互通性</span><span class="sxs-lookup"><span data-stu-id="aa978-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="aa978-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa978-116">Related topics</span></span>

[<span data-ttu-id="aa978-117">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="aa978-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)