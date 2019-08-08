---
title: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft 團隊聊天室的 Windows 更新
ms.openlocfilehash: 434e6d28796662c1cc8904b7ad94f059d7d447b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243275"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="59c14-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="59c14-103">Manage Windows Updates</span></span>

<span data-ttu-id="59c14-104">Microsoft 團隊聊天室會在 Windows 10 企業版 IoT 或 Windows 10 企業版 (VL) 上執行, 並以標準桌面接收相同的 Windows 更新與 OS 組建。</span><span class="sxs-lookup"><span data-stu-id="59c14-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="59c14-105">您可以透過幾種不同的方式來管理 Windows 更新:</span><span class="sxs-lookup"><span data-stu-id="59c14-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="59c14-106">動手做法</span><span class="sxs-lookup"><span data-stu-id="59c14-106">Hands-off approach</span></span> 

- <span data-ttu-id="59c14-107">您可以從 Windows 自動下載更新, 並在下班期間安裝更新。</span><span class="sxs-lookup"><span data-stu-id="59c14-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="59c14-108">這是預設的配置。</span><span class="sxs-lookup"><span data-stu-id="59c14-108">This is the default configuration.</span></span>
- <span data-ttu-id="59c14-109">非推遲更新安裝 day-自動發行一次。</span><span class="sxs-lookup"><span data-stu-id="59c14-109">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="59c14-110">品質更新及驅動程式會自動下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="59c14-110">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="59c14-111">功能更新。</span><span class="sxs-lookup"><span data-stu-id="59c14-111">Feature Updates.</span></span> <span data-ttu-id="59c14-112">請參閱後面的筆記。</span><span class="sxs-lookup"><span data-stu-id="59c14-112">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="59c14-113">商務用 Windows 更新 (GPO 或 Intune)</span><span class="sxs-lookup"><span data-stu-id="59c14-113">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="59c14-114">[商務用 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)下載</span><span class="sxs-lookup"><span data-stu-id="59c14-114">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="59c14-115">更新是從 WU 或您的 WSUS 下載, 但已設定的延遲超過 KB 的原始發行日期。</span><span class="sxs-lookup"><span data-stu-id="59c14-115">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span>
- <span data-ttu-id="59c14-116">與多個 OU 或篩選的原則搭配使用, 您可以建立部署 "鈴響", 管理員可以在這裡指定哪些裝置會先安裝品質更新, 以及稍後要安裝哪些裝置。</span><span class="sxs-lookup"><span data-stu-id="59c14-116">Used with multiple OU’s or filtered policies, you can create deployment “rings” where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="59c14-117">這可讓您在整個部署期間進行可靠性和效能測試, 而不需要在 SCCM 中管理 Windows 更新的額外負荷 (例如)。</span><span class="sxs-lookup"><span data-stu-id="59c14-117">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM for example.</span></span>
- <span data-ttu-id="59c14-118">如果您想要頻寬管理和商務用 Windows 更新提供的控制, 您可以同時[設定](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 windows 更新。</span><span class="sxs-lookup"><span data-stu-id="59c14-118">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="59c14-119">功能更新。</span><span class="sxs-lookup"><span data-stu-id="59c14-119">Feature updates.</span></span> <span data-ttu-id="59c14-120">請參閱後面的筆記。</span><span class="sxs-lookup"><span data-stu-id="59c14-120">See the notes that follow.</span></span>

## <a name="wsussccm"></a><span data-ttu-id="59c14-121">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="59c14-121">WSUS/SCCM</span></span>

- <span data-ttu-id="59c14-122">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)下載</span><span class="sxs-lookup"><span data-stu-id="59c14-122">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="59c14-123">就像是商務用 Windows 更新, 但在每個 "震鈴" 或整個部署中都有以特定的 KB 為目標的額外選項。</span><span class="sxs-lookup"><span data-stu-id="59c14-123">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="59c14-124">每個更新都可以個別部署和測試, 而不是只依賴延遲。</span><span class="sxs-lookup"><span data-stu-id="59c14-124">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="59c14-125">功能更新。</span><span class="sxs-lookup"><span data-stu-id="59c14-125">Feature updates.</span></span> <span data-ttu-id="59c14-126">請參閱後面的筆記。</span><span class="sxs-lookup"><span data-stu-id="59c14-126">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="59c14-127">功能更新</span><span class="sxs-lookup"><span data-stu-id="59c14-127">Feature updates</span></span>

<span data-ttu-id="59c14-128">與品質和不間斷更新不同, Windows 10 的「功能更新」 (主要 OS 版本) 只會在 Microsoft 測試並驗證 Microsoft 團隊會議室的特定更新功能之後安裝。</span><span class="sxs-lookup"><span data-stu-id="59c14-128">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="59c14-129">即使更新已發行至半年通道 (如果您已將系統設定至該通道進行測試) 或手動推送, Microsoft 房間系統裝置也不會允許安裝未經測試的更新。</span><span class="sxs-lookup"><span data-stu-id="59c14-129">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="59c14-130">Microsoft 團隊聊天室是「不在使用中」的「不在使用中」的方式, 不會在 Windows 更新中安裝 Windows 更新或自動重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="59c14-130">Microsoft Teams Rooms "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="59c14-131">系統可能會下載更新, 並等待下一次重新開機來安裝。</span><span class="sxs-lookup"><span data-stu-id="59c14-131">Systems may download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="59c14-132">除非有人手動重新開機, 否則系統會在自動重新開機時進行安裝。</span><span class="sxs-lookup"><span data-stu-id="59c14-132">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="59c14-133">Windows 更新在聊天室中應該是透明的, 而使用者介面不應該被 Windows 更新中斷。</span><span class="sxs-lookup"><span data-stu-id="59c14-133">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="59c14-134">如果您加入宣告網域的裝置, 請使用 SCCM 或 WSUS。</span><span class="sxs-lookup"><span data-stu-id="59c14-134">If you choose to domain joined devices, use SCCM or WSUS.</span></span> <span data-ttu-id="59c14-135">特別注意策略或動作, 可能會導致裝置安裝更新, 或在營業期間強制重新開機。</span><span class="sxs-lookup"><span data-stu-id="59c14-135">Pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="59c14-136">您部署中的系統不應在使用期間重新開機, 或在使用時間期間透過 UI 發出有關 Windows 更新的警示, 請檢查您的設定 (如果發生此行為)。</span><span class="sxs-lookup"><span data-stu-id="59c14-136">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>