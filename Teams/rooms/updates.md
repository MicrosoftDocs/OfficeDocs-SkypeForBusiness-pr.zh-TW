---
title: 管理 Microsoft Teams 會議室的 Windows 更新
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 系統管理員可以瞭解如何管理 Microsoft Teams 會議室的 Windows 更新和 Windows 功能更新。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117361"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="9f214-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="9f214-103">Manage Windows Updates</span></span>

<span data-ttu-id="9f214-104">Microsoft Teams 會議室在 Windows 10 企業版 IoT 或 Windows 10 企業版 (VL) 上執行，並接收與標準桌上型電腦相同的 Windows 更新和作業系統建立。</span><span class="sxs-lookup"><span data-stu-id="9f214-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="9f214-105">如下列各節所述，可以管理 Windows 更新：</span><span class="sxs-lookup"><span data-stu-id="9f214-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="9f214-106">離開方法</span><span class="sxs-lookup"><span data-stu-id="9f214-106">Hands-off approach</span></span> 

- <span data-ttu-id="9f214-107">根據預設，更新會直接從 Windows Updates 自動下載，並會在非工作時間安裝。</span><span class="sxs-lookup"><span data-stu-id="9f214-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="9f214-108">不可延遲的更新會自動在發行的第一天安裝。</span><span class="sxs-lookup"><span data-stu-id="9f214-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="9f214-109">品質更新和驅動程式會自動下載並安裝一天。</span><span class="sxs-lookup"><span data-stu-id="9f214-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="9f214-110">功能更新。</span><span class="sxs-lookup"><span data-stu-id="9f214-110">Feature Updates.</span></span> <span data-ttu-id="9f214-111">請參閱下列筆記。</span><span class="sxs-lookup"><span data-stu-id="9f214-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="9f214-112">商務用 Windows 更新 (GPO 或 Intune) </span><span class="sxs-lookup"><span data-stu-id="9f214-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="9f214-113">[下載商務用 Windows](/windows/deployment/update/waas-manage-updates-wufb) 更新</span><span class="sxs-lookup"><span data-stu-id="9f214-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="9f214-114">更新會從 Windows Update 或您的 WSUS 下載，但已配置的延遲會過原始發行日期。</span><span class="sxs-lookup"><span data-stu-id="9f214-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="9f214-115">您可以使用多個 OUs 或篩選後的政策來建立部署「圈」，讓系統管理員可以指定哪些裝置會先安裝品質更新，哪些裝置稍後再安裝。</span><span class="sxs-lookup"><span data-stu-id="9f214-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="9f214-116">在整個部署中推出更新之前，您可以在系統子集上測試可靠性和績效，而不需要在 Configuration Manager 中管理 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="9f214-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="9f214-117">如果您同時想要頻寬管理和商務用 Windows[](/windows/deployment/update/waas-integrate-wufb)更新提供的控制項，可以同時配置 WSUS 和商務用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="9f214-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="9f214-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="9f214-118">Feature updates.</span></span> <span data-ttu-id="9f214-119">請參閱下列筆記。</span><span class="sxs-lookup"><span data-stu-id="9f214-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="9f214-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f214-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="9f214-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下載</span><span class="sxs-lookup"><span data-stu-id="9f214-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="9f214-122">就像商務用 Windows Update 一樣，但在每個「響鈴」或整個部署中，有一個額外的選項是將特定 KB 作為目標。</span><span class="sxs-lookup"><span data-stu-id="9f214-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="9f214-123">每個更新都可以依需要個別部署和測試，而不是只仰賴延遲。</span><span class="sxs-lookup"><span data-stu-id="9f214-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="9f214-124">功能更新。</span><span class="sxs-lookup"><span data-stu-id="9f214-124">Feature updates.</span></span> <span data-ttu-id="9f214-125">請參閱下列筆記。</span><span class="sxs-lookup"><span data-stu-id="9f214-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="9f214-126">功能更新</span><span class="sxs-lookup"><span data-stu-id="9f214-126">Feature updates</span></span>

<span data-ttu-id="9f214-127">與品質與不可延遲更新不同，Windows 10「功能更新」 (主要作業系統版本) 只會在 Microsoft 測試及驗證 Microsoft Teams 會議室的給定更新功能後安裝。</span><span class="sxs-lookup"><span data-stu-id="9f214-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="9f214-128">即使您將更新發行至 Semi-Annual 通道 (或已設定目標，如果您有系統設定至該通道以測試) 或手動推送，Microsoft Room Systems 裝置也不會允許安裝未測試的更新。</span><span class="sxs-lookup"><span data-stu-id="9f214-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="9f214-129">Microsoft Teams 會議室功能「開箱即用」，而且不會安裝 Windows Update 或自動重新開機 Windows Update 的裝置。</span><span class="sxs-lookup"><span data-stu-id="9f214-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="9f214-130">系統會下載更新，並等待下次重新開機以安裝更新。</span><span class="sxs-lookup"><span data-stu-id="9f214-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="9f214-131">除非有人手動重新開機，安裝只會在自動夜間重新開機時執行。</span><span class="sxs-lookup"><span data-stu-id="9f214-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="9f214-132">Windows 更新在聊天室中應該是透明的，Windows 更新不應中斷正常作業。</span><span class="sxs-lookup"><span data-stu-id="9f214-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="9f214-133">如果您選擇將加入裝置網域，請使用 Microsoft 端點組組管理員或 WSUS。</span><span class="sxs-lookup"><span data-stu-id="9f214-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="9f214-134">請特別注意導致裝置更新或工作時間強制重新開機的政策或動作。</span><span class="sxs-lookup"><span data-stu-id="9f214-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="9f214-135">部署中的系統不應在使用期間重新開機，或在使用時間期間提醒您有關 Windows 更新的提醒，如果發生此行為，請檢查您的組配置。</span><span class="sxs-lookup"><span data-stu-id="9f214-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>