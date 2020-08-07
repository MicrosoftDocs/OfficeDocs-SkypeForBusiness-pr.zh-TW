---
title: Microsoft 365 和 Office 365 Url 與 IP 位址範圍
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 瞭解如何正確地設定 Microsoft 365 或 Office 365 Url 與 IP 位址範圍，以及如何在 Microsoft 團隊服務連線時略過轉寄 proxy。
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
ms.openlocfilehash: 94fd32cb4f68d636a6ff49ecf3b9c19689542142
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582120"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="25667-103">Microsoft 365 和 Office 365 Url 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="25667-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="25667-104">移至[Microsoft 365 和 Office 365 url 與 ip 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)，以取得必須針對團隊正確設定的 URL、IP 位址、埠和通訊協定的詳細資訊和最新清單。</span><span class="sxs-lookup"><span data-stu-id="25667-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="25667-105">Microsoft 會持續改善 Microsoft 365 及 Office 365 服務並加入新的功能，這表示必要的連接埠、URL 和 IP 位址可能會隨著時間變更。</span><span class="sxs-lookup"><span data-stu-id="25667-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="25667-106">我們建議您透過[RSS 進行訂閱](https://go.microsoft.com/fwlink/p/?linkid=236301)，以便在更新或變更此資訊時接收通知。</span><span class="sxs-lookup"><span data-stu-id="25667-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="25667-107">團隊通話和會議體驗是在由 Skype 與商務用 Skype 同時使用的下一代雲端基礎結構上建立。</span><span class="sxs-lookup"><span data-stu-id="25667-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="25667-108">這些技術投資包括適用于媒體處理的 Azure 雲端服務和信號、.H 視頻編解碼器、絞絲及 Opus 音訊編解碼器、網路復原、遙測及品質診斷。</span><span class="sxs-lookup"><span data-stu-id="25667-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="25667-109">如此一來，可能會有與 Skype 和商務用 Skype 相關聯所需的 Url 和 Ip。</span><span class="sxs-lookup"><span data-stu-id="25667-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="25667-110">針對所有 Microsoft 365 和 Office 365 的工作負載，建議的 [團隊服務] 連線方法是在可能的情況下略過轉寄 proxy。</span><span class="sxs-lookup"><span data-stu-id="25667-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="25667-111">當 proxy 伺服器位於用戶端與 Office 365 資料中心時，媒體可能會受到 TCP （而不是 UDP）的影響，而不會影響媒體質量。</span><span class="sxs-lookup"><span data-stu-id="25667-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="25667-112">下載範例 proxy PAC 檔案，這些檔案可以用來設定從[管理 Microsoft 365 和 Office 365 端點](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)繞過的流量旁路。</span><span class="sxs-lookup"><span data-stu-id="25667-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="25667-113">如果您的網路和安全性原則需要 Microsoft 365 或 Office 365 流量，才能透過 proxy 伺服器進行流動，請務必先滿足上述需求，然後才能將團隊部署到生產中。</span><span class="sxs-lookup"><span data-stu-id="25667-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="25667-114">如需詳細資訊，請參閱[小組或商務用 Skype Online 的 Proxy 伺服器](proxy-servers-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="25667-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
