---
title: 管理Windows更新Microsoft Teams 會議室
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
description: 系統管理員可以瞭解如何管理Windows更新Windows更新Microsoft Teams 會議室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117361"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="9203e-103">管理Windows更新</span><span class="sxs-lookup"><span data-stu-id="9203e-103">Manage Windows Updates</span></span>

<span data-ttu-id="9203e-104">Microsoft Teams 會議室于 Windows 10 企業版 IoT 或 VL Windows 10 企業版 (VL) 上執行Windows接收與標準桌上型電腦相同的更新和作業系統建立。</span><span class="sxs-lookup"><span data-stu-id="9203e-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="9203e-105">Windows如下列各節所述，可以管理更新：</span><span class="sxs-lookup"><span data-stu-id="9203e-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="9203e-106">離開方法</span><span class="sxs-lookup"><span data-stu-id="9203e-106">Hands-off approach</span></span> 

- <span data-ttu-id="9203e-107">根據預設，更新會直接從 Windows下載，並會在非工作時間安裝。</span><span class="sxs-lookup"><span data-stu-id="9203e-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="9203e-108">不可延遲的更新會自動在發行的第一天安裝。</span><span class="sxs-lookup"><span data-stu-id="9203e-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="9203e-109">品質更新和驅動程式會自動下載並安裝一天。</span><span class="sxs-lookup"><span data-stu-id="9203e-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="9203e-110">功能更新。</span><span class="sxs-lookup"><span data-stu-id="9203e-110">Feature Updates.</span></span> <span data-ttu-id="9203e-111">請參閱下列筆記。</span><span class="sxs-lookup"><span data-stu-id="9203e-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="9203e-112">Windows商務用更新 (GPO 或 Intune) </span><span class="sxs-lookup"><span data-stu-id="9203e-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="9203e-113">[Windows商務用更新](/windows/deployment/update/waas-manage-updates-wufb)下載</span><span class="sxs-lookup"><span data-stu-id="9203e-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="9203e-114">更新會從更新Windows您的 WSUS 下載，但已配置的延遲會過原始發行日期。</span><span class="sxs-lookup"><span data-stu-id="9203e-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="9203e-115">您可以使用多個 OUs 或篩選後的政策來建立部署「圈」，讓系統管理員可以指定哪些裝置會先安裝品質更新，哪些裝置稍後再安裝。</span><span class="sxs-lookup"><span data-stu-id="9203e-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="9203e-116">在整個部署中推出更新之前，可以在系統子集上測試可靠性和Windows，而不需要在 Configuration Manager 中管理Windows更新。</span><span class="sxs-lookup"><span data-stu-id="9203e-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="9203e-117">如果您想要同時Windows頻寬管理和商務用更新的控制權，可以同時[](/windows/deployment/update/waas-integrate-wufb)Windows商務用更新。</span><span class="sxs-lookup"><span data-stu-id="9203e-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="9203e-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="9203e-118">Feature updates.</span></span> <span data-ttu-id="9203e-119">請參閱下列筆記。</span><span class="sxs-lookup"><span data-stu-id="9203e-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="9203e-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9203e-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="9203e-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下載</span><span class="sxs-lookup"><span data-stu-id="9203e-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="9203e-122">就像商務Windows更新一樣，但在每個「響鈴」或整個部署中，有一個額外的選項是將特定 KB 作為目標。</span><span class="sxs-lookup"><span data-stu-id="9203e-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="9203e-123">每個更新都可以依需要個別部署和測試，而不是只仰賴延遲。</span><span class="sxs-lookup"><span data-stu-id="9203e-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="9203e-124">功能更新。</span><span class="sxs-lookup"><span data-stu-id="9203e-124">Feature updates.</span></span> <span data-ttu-id="9203e-125">請參閱下列筆記。</span><span class="sxs-lookup"><span data-stu-id="9203e-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="9203e-126">功能更新</span><span class="sxs-lookup"><span data-stu-id="9203e-126">Feature updates</span></span>

<span data-ttu-id="9203e-127">與品質與不可延遲更新不同，Windows 10主要作業系統版本 (的) 功能更新只會在 Microsoft 測試並驗證使用 Microsoft Teams 會議室 的給定更新功能之後安裝。</span><span class="sxs-lookup"><span data-stu-id="9203e-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="9203e-128">即使您將更新發行至 Semi-Annual 通道 (或已設定目標，如果您有系統設定至該通道以測試) 或手動推送，Microsoft Room Systems 裝置也不會允許安裝未測試的更新。</span><span class="sxs-lookup"><span data-stu-id="9203e-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="9203e-129">Microsoft Teams 會議室「開箱即用」功能，而且不會針對更新自動安裝 Windows 更新或重新開機Windows裝置。</span><span class="sxs-lookup"><span data-stu-id="9203e-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="9203e-130">系統下載更新，並等待下次重新開機以安裝更新。</span><span class="sxs-lookup"><span data-stu-id="9203e-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="9203e-131">除非有人手動重新開機，安裝只會在自動夜間重新開機時執行。</span><span class="sxs-lookup"><span data-stu-id="9203e-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="9203e-132">Windows更新在聊天室中應該是透明的，而且正常作業不應受到更新Windows干擾。</span><span class="sxs-lookup"><span data-stu-id="9203e-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="9203e-133">如果您選擇將加入裝置網域，請使用 Microsoft Endpoint Configuration Manager WSUS。</span><span class="sxs-lookup"><span data-stu-id="9203e-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="9203e-134">請特別注意導致裝置更新或工作時間強制重新開機的政策或動作。</span><span class="sxs-lookup"><span data-stu-id="9203e-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="9203e-135">部署中的系統不應在使用期間重新開機，或提醒Windows使用時間期間，在 UI 上更新更新，如果發生此行為，請檢查您的組組。</span><span class="sxs-lookup"><span data-stu-id="9203e-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>