---
title: 疑難排解 Microsoft 團隊用戶端的連線問題
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
description: 疑難排解 Microsoft 團隊用戶端的連線問題，主要是由防火牆或 proxy 連線所致，並瞭解如何修正。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a12be097d0609f3631b6761f31350603b283faa2
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825351"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="77431-103">疑難排解 Microsoft 團隊用戶端的連線問題</span><span class="sxs-lookup"><span data-stu-id="77431-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="77431-104">使用 Microsoft 團隊用戶端發現的大多數問題，都可以追溯到防火牆或 proxy 連線。</span><span class="sxs-lookup"><span data-stu-id="77431-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="77431-105">驗證在您的防火牆或 proxy 中開啟必要的 Url、IP 位址和埠，將會將不必要的疑難排解減到最少。</span><span class="sxs-lookup"><span data-stu-id="77431-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="77431-106">如需 Microsoft 團隊所需 Url 和 IPs 的特定資訊，請參閱[Office 365 url 和 IP 位址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支援文章。</span><span class="sxs-lookup"><span data-stu-id="77431-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="77431-107">下列案例需要在防火牆中開啟特定的 Url 和埠。</span><span class="sxs-lookup"><span data-stu-id="77431-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="77431-108">驗證</span><span class="sxs-lookup"><span data-stu-id="77431-108">Authentication</span></span>

-   <span data-ttu-id="77431-109">Microsoft 團隊用戶端連線能力</span><span class="sxs-lookup"><span data-stu-id="77431-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="77431-110">共同作業</span><span class="sxs-lookup"><span data-stu-id="77431-110">Collaboration</span></span>

-   <span data-ttu-id="77431-111">媒體</span><span class="sxs-lookup"><span data-stu-id="77431-111">Media</span></span>

-   <span data-ttu-id="77431-112">共用服務</span><span class="sxs-lookup"><span data-stu-id="77431-112">Shared Services</span></span>

-   <span data-ttu-id="77431-113">協力廠商整合</span><span class="sxs-lookup"><span data-stu-id="77431-113">Third Party Integration</span></span>

-   <span data-ttu-id="77431-114">商務用 Skype 互通性</span><span class="sxs-lookup"><span data-stu-id="77431-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="77431-115">商務用 Skype 用戶端互通性</span><span class="sxs-lookup"><span data-stu-id="77431-115">Skype for Business Client Interoperability</span></span>
