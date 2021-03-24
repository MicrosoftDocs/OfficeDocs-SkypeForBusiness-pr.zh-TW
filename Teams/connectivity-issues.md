---
title: 針對 Teams 用戶端的連接問題進行疑難排解
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
ms.openlocfilehash: 25a4fc51e0bb8dec810ce921e3678a529ee7a4cf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101159"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="17d9d-103">針對 Microsoft Teams 用戶端的連線問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="17d9d-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="17d9d-104">Microsoft Teams 用戶端所發現的問題大多可以追溯到防火牆或 Proxy 連線。</span><span class="sxs-lookup"><span data-stu-id="17d9d-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="17d9d-105">確認防火牆或 Proxy 中已開啟必要的 URL、IP 位址和連接埠，將會讓不必要的疑難排解工作降到最低。</span><span class="sxs-lookup"><span data-stu-id="17d9d-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="17d9d-106">如需 Microsoft Teams 所需的 URL 和 IP 的特定資訊，請參閱 [Microsoft 365 和 Office 365 URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 和 IP 位址支援文章。</span><span class="sxs-lookup"><span data-stu-id="17d9d-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="17d9d-107">下列案例需要在防火牆中開啟特定的 URL 和連接埠。</span><span class="sxs-lookup"><span data-stu-id="17d9d-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="17d9d-108">驗證</span><span class="sxs-lookup"><span data-stu-id="17d9d-108">Authentication</span></span>

- <span data-ttu-id="17d9d-109">Microsoft Teams 用戶端連線</span><span class="sxs-lookup"><span data-stu-id="17d9d-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="17d9d-110">共同作業</span><span class="sxs-lookup"><span data-stu-id="17d9d-110">Collaboration</span></span>

- <span data-ttu-id="17d9d-111">媒體</span><span class="sxs-lookup"><span data-stu-id="17d9d-111">Media</span></span>

- <span data-ttu-id="17d9d-112">共用服務</span><span class="sxs-lookup"><span data-stu-id="17d9d-112">Shared Services</span></span>

- <span data-ttu-id="17d9d-113">第三方整合</span><span class="sxs-lookup"><span data-stu-id="17d9d-113">Third Party Integration</span></span>

- <span data-ttu-id="17d9d-114">商務用 Skype 互通性</span><span class="sxs-lookup"><span data-stu-id="17d9d-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="17d9d-115">商務用 Skype 用戶端互通性</span><span class="sxs-lookup"><span data-stu-id="17d9d-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="17d9d-116">當 Teams 離線或處於低頻寬條件時</span><span class="sxs-lookup"><span data-stu-id="17d9d-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="17d9d-117">好消息是，即使您離線或是在低頻寬情況下執行，Teams 仍持續執行。</span><span class="sxs-lookup"><span data-stu-id="17d9d-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="17d9d-118">Teams 會將您所有未傳送的郵件 (聊天) 24 小時，並一回到線上就傳送。</span><span class="sxs-lookup"><span data-stu-id="17d9d-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="17d9d-119">如果您離線超過 24 小時，Teams 可讓您選擇重新發送或刪除未接收的郵件。</span><span class="sxs-lookup"><span data-stu-id="17d9d-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="17d9d-120">我們正在努力將這項功能新增到新的聊天中，並將于提供這項功能時更新此檔。</span><span class="sxs-lookup"><span data-stu-id="17d9d-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="17d9d-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="17d9d-121">Related topics</span></span>

[<span data-ttu-id="17d9d-122">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="17d9d-122">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)