---
title: 音訊會議的疑難排解與已知問題
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '取得使用 Microsoft 作為電話撥入式會議提供者時已知問題的清單、狀態，以及一些因應措施。 '
ms.openlocfilehash: 71d363ff98fc4590fb6d96cc3e8a8cb77b1fa24c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237189"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a><span data-ttu-id="c5f76-103">音訊會議的疑難排解與已知問題</span><span class="sxs-lookup"><span data-stu-id="c5f76-103">Audio Conferencing troubleshooting and known issues</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 <span data-ttu-id="c5f76-104">**本文適用于使用 microsoft 商務用 Skype音訊會議提供者的使用者。不適用於使用協力廠商音訊會議提供者 (ACP) 。**</span><span class="sxs-lookup"><span data-stu-id="c5f76-104">**This article is for Skype for Business users using Microsoft as their audio conferencing provider. It does not apply to customers who are using a third-party audio conferencing provider (ACP).**</span></span>
  
## <a name="troubleshooting-and-known-issues"></a><span data-ttu-id="c5f76-105">疑難排解和已知問題</span><span class="sxs-lookup"><span data-stu-id="c5f76-105">Troubleshooting and known issues</span></span>

<span data-ttu-id="c5f76-106">使用 Microsoft 做為音訊會議提供者的音訊會議目前發生正在追蹤並積極調查的問題，且日後更新功能後，Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c5f76-106">Audio Conferencing that uses Microsoft as the audio conferencing provider has current issues that are being tracked and actively investigated and will be potentially resolved when the feature is updated in future releases of Microsoft 365.</span></span>
  
<span data-ttu-id="c5f76-107">目前，當您針對在組織中使用音訊會議進行音訊會議設定及商務用 Skype疑難排解時，請使用此功能做為參考。</span><span class="sxs-lookup"><span data-stu-id="c5f76-107">For now, use this as a reference when you are troubleshooting potential issues with getting Audio Conferencing set up and working for the people using Skype for Business in your organization.</span></span>

|<span data-ttu-id="c5f76-108">**問題**</span><span class="sxs-lookup"><span data-stu-id="c5f76-108">**Issue**</span></span>|<span data-ttu-id="c5f76-109">**行為/徵狀**</span><span class="sxs-lookup"><span data-stu-id="c5f76-109">**Behavior/Symptoms**</span></span>|<span data-ttu-id="c5f76-110">**已知的因應措施**</span><span class="sxs-lookup"><span data-stu-id="c5f76-110">**Known workaround**</span></span>|<span data-ttu-id="c5f76-111">**發現日期**</span><span class="sxs-lookup"><span data-stu-id="c5f76-111">**Discovery date**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c5f76-112">進入和離開通知在會議開始時會開啟，但在會議開始後會關閉。</span><span class="sxs-lookup"><span data-stu-id="c5f76-112">Entry and exit notifications are turned on when a meeting starts, but they're turned off shortly after the meeting starts.</span></span>  <br/> |<span data-ttu-id="c5f76-113">根據預設，參與者從兩個應用程式加入的會議，以及參與者撥入商務用 Skype會停用進入和離開通知。</span><span class="sxs-lookup"><span data-stu-id="c5f76-113">By default, entry and exit notifications are disabled for meetings where participants join from both Skype for Business apps and when they dial in.</span></span> <span data-ttu-id="c5f76-114">您可以在應用程式Skype會議選項中 **啟用** 商務用 Skype公告。</span><span class="sxs-lookup"><span data-stu-id="c5f76-114">You can enable the announcements in the **Skype Meeting Options** in the Skype for Business app.</span></span> <span data-ttu-id="c5f76-115">對於所有參與者撥入並加入會議的會議，系統預設會啟用進入和離開通知，因為參與者名冊無法供任何參與者使用。</span><span class="sxs-lookup"><span data-stu-id="c5f76-115">For a meeting where all participants dial in and join a meeting, entry and exit notifications are enabled by default as the participant roster isn't available to any participant.</span></span> <span data-ttu-id="c5f76-116">當只有參與者來電的會議開始時，進入和離開通知會開啟，但當參與者使用 商務用 Skype App 加入時，通知會關閉。</span><span class="sxs-lookup"><span data-stu-id="c5f76-116">When a meeting has started with only participants calling in, the entry and exit notifications will be turned on, but when a participant joins using a Skype for Business app, the notifications will be turned off.</span></span> <span data-ttu-id="c5f76-117">關閉時，您可以在應用程式 **Skype會議選項** 商務用 Skype通知。</span><span class="sxs-lookup"><span data-stu-id="c5f76-117">When turned off, the notifications can be enabled back using **Skype Meeting Options** in the Skype for Business app.</span></span> <br/> |<span data-ttu-id="c5f76-118">無因應措施。</span><span class="sxs-lookup"><span data-stu-id="c5f76-118">No workaround.</span></span>  <br/> |<span data-ttu-id="c5f76-119">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="c5f76-119">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="c5f76-120">如果使用者第一次被指派 E5 授權來進行配置，如果信箱未啟用，音訊會議歡迎電子郵件可能不會傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="c5f76-120">If a user is provisioned the first time by being assigned an E5 license, it might be possible for the Audio Conferencing welcome email to not be delivered to the user if the mailbox isn't enabled.</span></span>  <br/> |<span data-ttu-id="c5f76-121">如果發生這種情況，您隨時都可以使用系統管理中心的音訊會議，或使用 PowerShell重新商務用 Skype音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="c5f76-121">If this happens, you can always resend the audio conferencing information of the user using **Audio conferencing** in the Skype for Business admin center or using PowerShell.</span></span> <span data-ttu-id="c5f76-122">請參閱 [在音訊會議設定變更時啟用或停用傳送電子郵件](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="c5f76-122">See [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>  <br/> <span data-ttu-id="c5f76-123">**注意：** 若要將音訊會議 PIN 重新發回給使用者，PIN 必須重設。</span><span class="sxs-lookup"><span data-stu-id="c5f76-123">**Note:** In order to resend the audio conferencing PIN to the user, the PIN has to be reset.</span></span> <span data-ttu-id="c5f76-124">您也可以在系統管理中心使用音訊商務用 Skype或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c5f76-124">This can also be done by using **Audio conferencing** in the Skype for Business admin center or by using PowerShell.</span></span>          |<span data-ttu-id="c5f76-125">無因應措施。</span><span class="sxs-lookup"><span data-stu-id="c5f76-125">No workaround.</span></span>  <br/> |<span data-ttu-id="c5f76-126">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="c5f76-126">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="c5f76-127">音訊會議通話最多可能需要 24 小時才能顯示在使用方式報告中。</span><span class="sxs-lookup"><span data-stu-id="c5f76-127">Audio conferencing calls could take up to 24 hours to show in the usage reports.</span></span>  <br/> |<span data-ttu-id="c5f76-128">我們期待在未來服務更新中對此領域進行改良。</span><span class="sxs-lookup"><span data-stu-id="c5f76-128">We're looking forward to making improvements on this area in future service updates.</span></span>  <br/> |<span data-ttu-id="c5f76-129">無因應措施。</span><span class="sxs-lookup"><span data-stu-id="c5f76-129">No workaround.</span></span>  <br/> |<span data-ttu-id="c5f76-130">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="c5f76-130">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="c5f76-131">當來電者在會議被 商務用 Skype 使用者鎖定後撥入會議橋接器時，商務用 Skype 應用程式中沒有通知指出使用者正在等待大廳。</span><span class="sxs-lookup"><span data-stu-id="c5f76-131">When a caller dials in to a conference bridge after the meeting has been locked by a Skype for Business user, there isn't a notification in the Skype for Business app stating that the user is waiting in the lobby.</span></span>  <br/> |<span data-ttu-id="c5f76-132">這項功能目前是由設計所設計，但我們已針對在未來服務更新中支援這項功能提供意見。</span><span class="sxs-lookup"><span data-stu-id="c5f76-132">This is currently by design, but we've taken the feedback in regard to supporting this capability in future service updates.</span></span>  <br/> |<span data-ttu-id="c5f76-133">無因應措施。</span><span class="sxs-lookup"><span data-stu-id="c5f76-133">No workaround.</span></span>  <br/> |<span data-ttu-id="c5f76-134">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="c5f76-134">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="c5f76-135">商務用 Skype Server (2019) 3 月 1 日之前指派音訊會議授權的使用者，可能無法在會議邀請中看到撥入座標。</span><span class="sxs-lookup"><span data-stu-id="c5f76-135">A Skype for Business Server (on-prem) user assigned the Audio Conferencing license prior to March 1, 2019, might not see the dial in coordinates in their meeting invites.</span></span>  <br/> |<span data-ttu-id="c5f76-136">直到商務用 Skype Server，Teams音訊會議的使用者才受支援。</span><span class="sxs-lookup"><span data-stu-id="c5f76-136">Provisioning Skype for Business Server users for Teams Audio Conferencing was not supported until that date.</span></span> <span data-ttu-id="c5f76-137">現在支援它，且是會議 [第一部分](/microsoftteams/meetings-first)。</span><span class="sxs-lookup"><span data-stu-id="c5f76-137">It is now supported and is a component of [Meetings First](/microsoftteams/meetings-first).</span></span> <span data-ttu-id="c5f76-138">使用者必須擁有Teams授權。</span><span class="sxs-lookup"><span data-stu-id="c5f76-138">The user must have a Teams license.</span></span>  <br/> |<span data-ttu-id="c5f76-139">需要重新啟用資源調配管道。</span><span class="sxs-lookup"><span data-stu-id="c5f76-139">The provisioning pipeline needs to be reactivated.</span></span> <span data-ttu-id="c5f76-140">移除使用者的音訊會議授權、等候幾個小時，然後重新指派授權。</span><span class="sxs-lookup"><span data-stu-id="c5f76-140">Remove the user’s Audio Conferencing license, wait for a couple hours, and reassign the license.</span></span>  <br/> |<span data-ttu-id="c5f76-141">3/1/2019</span><span class="sxs-lookup"><span data-stu-id="c5f76-141">3/1/2019</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="c5f76-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="c5f76-142">Related topics</span></span>

[<span data-ttu-id="c5f76-143">嘗試或購買音訊會議Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="c5f76-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
