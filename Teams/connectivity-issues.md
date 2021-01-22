---
title: 疑難排解 Teams 用戶端的連接問題
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
ms.openlocfilehash: 59041734887a667eca325a3d2650425d6d336b78
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918539"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="49da3-103">針對 Microsoft Teams 用戶端的連線問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="49da3-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="49da3-104">Microsoft Teams 用戶端所發現的問題大多可以追溯到防火牆或 Proxy 連線。</span><span class="sxs-lookup"><span data-stu-id="49da3-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="49da3-105">確認防火牆或 Proxy 中已開啟必要的 URL、IP 位址和連接埠，將會讓不必要的疑難排解工作降到最低。</span><span class="sxs-lookup"><span data-stu-id="49da3-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="49da3-106">如需 Microsoft Teams 所需 URL 和 IP 的特定資訊，請參閱 [Microsoft 365 和 Office 365 URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 與 IP 位址支援文章。</span><span class="sxs-lookup"><span data-stu-id="49da3-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="49da3-107">下列案例需要在防火牆中開啟特定的 URL 和連接埠。</span><span class="sxs-lookup"><span data-stu-id="49da3-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="49da3-108">驗證</span><span class="sxs-lookup"><span data-stu-id="49da3-108">Authentication</span></span>

- <span data-ttu-id="49da3-109">Microsoft Teams 用戶端連線</span><span class="sxs-lookup"><span data-stu-id="49da3-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="49da3-110">共同作業</span><span class="sxs-lookup"><span data-stu-id="49da3-110">Collaboration</span></span>

- <span data-ttu-id="49da3-111">媒體</span><span class="sxs-lookup"><span data-stu-id="49da3-111">Media</span></span>

- <span data-ttu-id="49da3-112">共用服務</span><span class="sxs-lookup"><span data-stu-id="49da3-112">Shared Services</span></span>

- <span data-ttu-id="49da3-113">第三方整合</span><span class="sxs-lookup"><span data-stu-id="49da3-113">Third Party Integration</span></span>

- <span data-ttu-id="49da3-114">商務用 Skype 互通性</span><span class="sxs-lookup"><span data-stu-id="49da3-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="49da3-115">商務用 Skype 用戶端互通性</span><span class="sxs-lookup"><span data-stu-id="49da3-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="49da3-116">Teams 離線或頻寬不足時</span><span class="sxs-lookup"><span data-stu-id="49da3-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="49da3-117">好消息是，即使您離線或以低頻寬條件執行，Teams 仍持續執行。</span><span class="sxs-lookup"><span data-stu-id="49da3-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="49da3-118">Teams 會將您所有未傳送的訊息 (現有聊天內容) 24 小時，當您恢復連線時，就會立即傳送這些訊息。</span><span class="sxs-lookup"><span data-stu-id="49da3-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="49da3-119">如果您處於離線狀態超過 24 小時，Teams 可讓您選擇重新發送或刪除未接收的訊息。</span><span class="sxs-lookup"><span data-stu-id="49da3-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="49da3-120">我們正致力於將這項功能新增到新聊天中，並且將在提供這項功能時更新檔。</span><span class="sxs-lookup"><span data-stu-id="49da3-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="49da3-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="49da3-121">Related topics</span></span>

[<span data-ttu-id="49da3-122">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="49da3-122">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
