---
title: 疑難排解 Microsoft 團隊用戶端的連線問題
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: 疑難排解 Microsoft 團隊用戶端的連線問題, 主要是由防火牆或 proxy 連線所致, 並瞭解如何修正。
appliesto:
- Microsoft Teams
ms.openlocfilehash: d208671415e44ca5ec83313d0d8af666534f2b20
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180484"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="cbbb5-103">疑難排解 Microsoft 團隊用戶端的連線問題</span><span class="sxs-lookup"><span data-stu-id="cbbb5-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="cbbb5-104">使用 Microsoft 團隊用戶端發現的大多數問題, 都可以追溯到防火牆或 proxy 連線。</span><span class="sxs-lookup"><span data-stu-id="cbbb5-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="cbbb5-105">驗證在您的防火牆或 proxy 中開啟必要的 Url、IP 位址和埠, 將會將不必要的疑難排解減到最少。</span><span class="sxs-lookup"><span data-stu-id="cbbb5-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="cbbb5-106">如需 Microsoft 團隊所需 Url 和 IPs 的特定資訊, 請參閱[Office 365 url 和 IP 位址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支援文章。</span><span class="sxs-lookup"><span data-stu-id="cbbb5-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="cbbb5-107">下列案例需要在防火牆中開啟特定的 Url 和埠。</span><span class="sxs-lookup"><span data-stu-id="cbbb5-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="cbbb5-108">Authentication</span><span class="sxs-lookup"><span data-stu-id="cbbb5-108">Authentication</span></span>

-   <span data-ttu-id="cbbb5-109">Microsoft 團隊用戶端連線能力</span><span class="sxs-lookup"><span data-stu-id="cbbb5-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="cbbb5-110">共同作業</span><span class="sxs-lookup"><span data-stu-id="cbbb5-110">Collaboration</span></span>

-   <span data-ttu-id="cbbb5-111">媒體</span><span class="sxs-lookup"><span data-stu-id="cbbb5-111">Media</span></span>

-   <span data-ttu-id="cbbb5-112">共用服務</span><span class="sxs-lookup"><span data-stu-id="cbbb5-112">Shared Services</span></span>

-   <span data-ttu-id="cbbb5-113">協力廠商整合</span><span class="sxs-lookup"><span data-stu-id="cbbb5-113">Third Party Integration</span></span>

-   <span data-ttu-id="cbbb5-114">商務用 Skype 互通性</span><span class="sxs-lookup"><span data-stu-id="cbbb5-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="cbbb5-115">商務用 Skype 用戶端互通性</span><span class="sxs-lookup"><span data-stu-id="cbbb5-115">Skype for Business Client Interoperability</span></span>
