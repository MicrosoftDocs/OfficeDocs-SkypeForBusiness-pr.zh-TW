---
title: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.openlocfilehash: be3555507b0c9a8967b444b96e8c6e4af8f35fbf
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628559"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="4229a-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="4229a-103">Manage Windows Updates</span></span>

<span data-ttu-id="4229a-104">Microsoft 團隊聊天室會在 Windows 10 企業版 IoT 或 Windows 10 企業版（VL）上執行，並以標準桌上型電腦的形式接收相同的 Windows 更新與 OS 組建。</span><span class="sxs-lookup"><span data-stu-id="4229a-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="4229a-105">您可以依照下列各節中的討論來管理 Windows 更新：</span><span class="sxs-lookup"><span data-stu-id="4229a-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="4229a-106">動手做法</span><span class="sxs-lookup"><span data-stu-id="4229a-106">Hands-off approach</span></span> 

- <span data-ttu-id="4229a-107">根據預設，自動從 Windows 更新下載更新，並在下班期間安裝。</span><span class="sxs-lookup"><span data-stu-id="4229a-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="4229a-108">非推遲更新安裝 day-自動發行一次。</span><span class="sxs-lookup"><span data-stu-id="4229a-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="4229a-109">品質更新及驅動程式會自動下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="4229a-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="4229a-110">功能更新。</span><span class="sxs-lookup"><span data-stu-id="4229a-110">Feature Updates.</span></span> <span data-ttu-id="4229a-111">請參閱後面的筆記。</span><span class="sxs-lookup"><span data-stu-id="4229a-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="4229a-112">商務用 Windows 更新（GPO 或 Intune）</span><span class="sxs-lookup"><span data-stu-id="4229a-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="4229a-113">[商務用 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)下載</span><span class="sxs-lookup"><span data-stu-id="4229a-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="4229a-114">更新是從 Windows Update 或您的 WSUS 下載，但在原始發行日期之後已設定延遲時間。</span><span class="sxs-lookup"><span data-stu-id="4229a-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="4229a-115">您可以使用多個 Ou 或篩選原則來建立「振鈴」，管理員可以在其中指定哪些裝置會先安裝品質更新，且稍後會進行安裝。</span><span class="sxs-lookup"><span data-stu-id="4229a-115">You can use multiple OUs or filtered policies to create deployment “rings” where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="4229a-116">您可以在系統子集上測試可靠性和效能，而不需要在 Configuration Manager 中管理 Windows 更新的額外負荷，就能在整個部署中推出更新。</span><span class="sxs-lookup"><span data-stu-id="4229a-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="4229a-117">如果您想要頻寬管理和商務用 Windows 更新提供的控制，您可以同時[設定](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 windows 更新。</span><span class="sxs-lookup"><span data-stu-id="4229a-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="4229a-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="4229a-118">Feature updates.</span></span> <span data-ttu-id="4229a-119">請參閱後面的筆記。</span><span class="sxs-lookup"><span data-stu-id="4229a-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="4229a-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4229a-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="4229a-121">[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)下載</span><span class="sxs-lookup"><span data-stu-id="4229a-121">[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="4229a-122">就像是商務用 Windows 更新，但在每個 "震鈴" 或整個部署中都有以特定的 KB 為目標的額外選項。</span><span class="sxs-lookup"><span data-stu-id="4229a-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="4229a-123">每個更新都可以個別部署和測試，而不是只依賴延遲。</span><span class="sxs-lookup"><span data-stu-id="4229a-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="4229a-124">功能更新。</span><span class="sxs-lookup"><span data-stu-id="4229a-124">Feature updates.</span></span> <span data-ttu-id="4229a-125">請參閱後面的筆記。</span><span class="sxs-lookup"><span data-stu-id="4229a-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="4229a-126">功能更新</span><span class="sxs-lookup"><span data-stu-id="4229a-126">Feature updates</span></span>

<span data-ttu-id="4229a-127">與品質和不間斷更新不同，Windows 10 的「功能更新」（主要 OS 版本）只會在 Microsoft 測試並驗證 Microsoft 團隊會議室的特定更新功能之後安裝。</span><span class="sxs-lookup"><span data-stu-id="4229a-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="4229a-128">即使更新已發行至半年通道（如果您已將系統設定至該通道進行測試）或手動推送，Microsoft 房間系統裝置也不會允許安裝未經測試的更新。</span><span class="sxs-lookup"><span data-stu-id="4229a-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="4229a-129">Microsoft 團隊聊天室的功能是「不在使用中」的功能，且不會在 Windows 更新中安裝 Windows 更新或自動重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="4229a-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="4229a-130">系統會下載更新，並等待下一次重新開機來進行安裝。</span><span class="sxs-lookup"><span data-stu-id="4229a-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="4229a-131">除非有人手動重新開機，否則只會在每次自動重新開機時進行安裝。</span><span class="sxs-lookup"><span data-stu-id="4229a-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="4229a-132">Windows 更新在聊天室中應該是透明的，而且一般的操作應該不會被 Windows 更新中斷。</span><span class="sxs-lookup"><span data-stu-id="4229a-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="4229a-133">如果您選擇 [網域加入裝置]，請使用 Microsoft 端點建構管理員或 WSUS。</span><span class="sxs-lookup"><span data-stu-id="4229a-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="4229a-134">特別注意在上班時間內導致裝置更新或強制重新開機的原則或動作。</span><span class="sxs-lookup"><span data-stu-id="4229a-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="4229a-135">您部署中的系統不應在使用期間重新開機，或在使用時間期間透過 UI 發出有關 Windows 更新的警示，請檢查您的設定（如果發生此行為）。</span><span class="sxs-lookup"><span data-stu-id="4229a-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>