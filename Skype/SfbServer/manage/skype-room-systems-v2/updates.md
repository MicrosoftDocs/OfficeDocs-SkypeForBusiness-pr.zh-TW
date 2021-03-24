---
title: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103199"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="35427-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="35427-103">Manage Windows Updates</span></span>

<span data-ttu-id="35427-104">Microsoft 團隊聊天室會在 Windows 10 Enterprise IoT 或 Windows 10 Enterprise (VL) 上執行，並以標準的桌面接收相同的 Windows 更新和 OS 組建。</span><span class="sxs-lookup"><span data-stu-id="35427-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="35427-105">Windows 更新可透過幾種不同的方式來管理：</span><span class="sxs-lookup"><span data-stu-id="35427-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="35427-106">不用動手的做法</span><span class="sxs-lookup"><span data-stu-id="35427-106">Hands-off approach</span></span> 
- <span data-ttu-id="35427-107">更新可從 Windows 直接下載，並在下班時間內安裝更新。</span><span class="sxs-lookup"><span data-stu-id="35427-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="35427-108">若未變更設定，此為預設狀態。</span><span class="sxs-lookup"><span data-stu-id="35427-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="35427-109">非可延遲的更新將會自動安裝第一天的版本。</span><span class="sxs-lookup"><span data-stu-id="35427-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="35427-110">品質更新及驅動程式將會自動下載並安裝第一天。</span><span class="sxs-lookup"><span data-stu-id="35427-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="35427-111">功能更新。</span><span class="sxs-lookup"><span data-stu-id="35427-111">Feature Updates.</span></span> <span data-ttu-id="35427-112">請參閱下列其他附注。</span><span class="sxs-lookup"><span data-stu-id="35427-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="35427-113">[Windows 更新](/windows/deployment/update/waas-manage-updates-wufb) (GPO 或 Intune) </span><span class="sxs-lookup"><span data-stu-id="35427-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="35427-114">更新會從 WU 或您的 WSUS 下載，但已設定的延遲超過 KB 的原始發行日期。</span><span class="sxs-lookup"><span data-stu-id="35427-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="35427-115">與多個 OU 或篩選的原則組合在一起，可讓您建立部署 "振鈴"，讓系統管理員可以指定哪些裝置會先安裝品質更新，以及將在稍後安裝哪些裝置。</span><span class="sxs-lookup"><span data-stu-id="35427-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="35427-116">這可讓您在整個部署期間進行可靠性和效能測試，而不需要在 Microsoft 端點設定管理員中管理 Windows 更新（範例）。</span><span class="sxs-lookup"><span data-stu-id="35427-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Microsoft Endpoint Configuration Manager for example.</span></span>
- <span data-ttu-id="35427-117">如果您想要同時進行頻寬管理，以及 Windows 的 Windows 更新所提供的控制，WSUS 和 Windows 更新可在 [同一時間進行設定](/windows/deployment/update/waas-integrate-wufb) 。</span><span class="sxs-lookup"><span data-stu-id="35427-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="35427-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="35427-118">Feature updates.</span></span> <span data-ttu-id="35427-119">請參閱下列其他附注。</span><span class="sxs-lookup"><span data-stu-id="35427-119">See additional notes below.</span></span>

## <a name="wsusconfiguration-manager"></a>[<span data-ttu-id="35427-120">WSUS/設定管理員</span><span class="sxs-lookup"><span data-stu-id="35427-120">WSUS/Configuration Manager</span></span>](/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="35427-121">很像是企業的 Windows 更新，但有其他選項，針對每個「震鈴」或整個部署中的特定 KB。</span><span class="sxs-lookup"><span data-stu-id="35427-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="35427-122">每個更新都可以個別地部署及測試，而不只是僅依賴延遲。</span><span class="sxs-lookup"><span data-stu-id="35427-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="35427-123">功能更新。</span><span class="sxs-lookup"><span data-stu-id="35427-123">Feature updates.</span></span> <span data-ttu-id="35427-124">請參閱下列其他附注。</span><span class="sxs-lookup"><span data-stu-id="35427-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="35427-125">功能更新</span><span class="sxs-lookup"><span data-stu-id="35427-125">Feature updates</span></span>

<span data-ttu-id="35427-126">與品質和非 Deferable 的更新不同的是，Windows 10 「功能更新」會 (主作業系統版本) ，只會在 Microsoft 測試及驗證 Microsoft 團隊會議室的指定更新功能之後安裝。</span><span class="sxs-lookup"><span data-stu-id="35427-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="35427-127">即使將系統設為 Semi-Annual 通道 (或目標，如果您已將系統設為測試) ，甚至是以您自己的嘗試或設定手動推入，它也不會允許安裝，直到我們最後一次刪除該塊為止。</span><span class="sxs-lookup"><span data-stu-id="35427-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="35427-128">Microsoft 團隊會議室「現成」，使用「動手」方法，不會因為 Windows 更新而自動安裝 Windows Update 或重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="35427-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="35427-129">不過，系統可能會下載更新，並等待下一次重新開機進行安裝。</span><span class="sxs-lookup"><span data-stu-id="35427-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="35427-130">除非有人手動重新開機，否則應該會在每次自動重新開機時進行安裝。</span><span class="sxs-lookup"><span data-stu-id="35427-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="35427-131">在會議室中，windows 更新應該是透明的，而使用者介面絕對不應該中斷 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="35427-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="35427-132">如果您加入宣告網域，請使用 Microsoft 端點設定管理員或 WSUS，並特別注意可能導致裝置安裝更新或在上班時間強制重新開機的原則或動作。</span><span class="sxs-lookup"><span data-stu-id="35427-132">If you choose to domain join, use Microsoft Endpoint Configuration Manager or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="35427-133">如果您的部署在使用期間重新開機系統，或透過 UI 的 Windows 更新發出警示，您會想要查看您的設定。</span><span class="sxs-lookup"><span data-stu-id="35427-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>