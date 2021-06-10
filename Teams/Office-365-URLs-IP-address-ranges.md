---
title: Microsoft 365和Office 365 URL 和 IP 位址範圍
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 瞭解如何正確設定Microsoft 365或Office 365 URL 和 IP 位址範圍，並盡可能針對與服務Microsoft Teams Proxy。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094515"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="e0d95-103">Microsoft 365和Office 365 URL 和 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="e0d95-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="e0d95-104">請Microsoft 365 URL Office 365 URL 和[IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)位址範圍，以查看必須為 Teams 正確配置的 URL、IP 位址、埠和通訊協定的詳細且最新的清單。</span><span class="sxs-lookup"><span data-stu-id="e0d95-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="e0d95-105">Microsoft 會持續改善 Microsoft 365 及 Office 365 服務並加入新的功能，這表示必要的連接埠、URL 和 IP 位址可能會隨著時間變更。</span><span class="sxs-lookup"><span data-stu-id="e0d95-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="e0d95-106">我們建議您透過 [RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 訂閱，以在更新或變更此資訊時收到通知。</span><span class="sxs-lookup"><span data-stu-id="e0d95-106">We recommend that you [subscribe via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="e0d95-107">Teams通話和會議體驗建立在新一代雲端式基礎結構上，也是Skype商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e0d95-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="e0d95-108">這些技術投資包括媒體處理和訊號的 Azure 雲端服務、H.264 視訊編解碼器、SILK 和 Opus 音訊編解碼器、網路復原能力、遙測和品質診斷。</span><span class="sxs-lookup"><span data-stu-id="e0d95-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="e0d95-109">因此，有一些 URL 和 IP 可能需要與 Skype 和 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e0d95-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="e0d95-110">針對所有Microsoft 365 Office 365工作負載，建議Teams連接方法會盡可能忽略轉轉 Proxy。</span><span class="sxs-lookup"><span data-stu-id="e0d95-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="e0d95-111">當 Proxy 伺服器位於用戶端Office 365資料中心之間時，媒體可能會強制超過 TCP 而非 UDP，這會影響媒體質量。</span><span class="sxs-lookup"><span data-stu-id="e0d95-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="e0d95-112">下載範例 Proxy PAC 檔案，可用來從管理Microsoft 365端點Office 365[流量](/office365/enterprise/managing-office-365-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="e0d95-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="e0d95-113">如果您的網路和安全性原則需要Microsoft 365或Office 365流量才能透過 Proxy 伺服器，請務必先滿足上述需求，再將Teams部署到生產。</span><span class="sxs-lookup"><span data-stu-id="e0d95-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="e0d95-114">如要詳細資訊，請參閱[適用于](proxy-servers-for-skype-for-business-online.md)Teams 或 商務用 Skype 的 Proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e0d95-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>