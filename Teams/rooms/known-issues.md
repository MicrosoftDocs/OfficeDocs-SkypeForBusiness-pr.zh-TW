---
title: 已知問題
ms.author: v-lanac
author: lanachin
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
description: 系統管理員可以瞭解 Microsoft 團隊聊天室的已知問題清單，包括更新、使用者介面、硬體、限制及預期行為。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d8f7dcd6453458885a35bdcf7b39e729cc776f5a
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905415"
---
# <a name="known-issues"></a><span data-ttu-id="2de19-103">已知問題</span><span class="sxs-lookup"><span data-stu-id="2de19-103">Known issues</span></span> 
 
<span data-ttu-id="2de19-104">本文列出 [Microsoft 團隊聊天室] 的已知問題（依功能區域）。</span><span class="sxs-lookup"><span data-stu-id="2de19-104">This article lists the known issues for Microsoft Teams Rooms, by feature area.</span></span>
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<span data-ttu-id="2de19-105"><a name="update"> </a></span><span class="sxs-lookup"><span data-stu-id="2de19-105"><a name="update"> </a></span></span>  
## <a name="update"></a><span data-ttu-id="2de19-106">時更新</span><span class="sxs-lookup"><span data-stu-id="2de19-106">Update</span></span> 

| <span data-ttu-id="2de19-107">問題標題</span><span class="sxs-lookup"><span data-stu-id="2de19-107">Issue title</span></span> |  <span data-ttu-id="2de19-108">行為\/症狀</span><span class="sxs-lookup"><span data-stu-id="2de19-108">Behavior \/ Symptom</span></span> | <span data-ttu-id="2de19-109">已知的因應措施</span><span class="sxs-lookup"><span data-stu-id="2de19-109">Known workaround</span></span> | <span data-ttu-id="2de19-110">知識庫文章</span><span class="sxs-lookup"><span data-stu-id="2de19-110">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|  <span data-ttu-id="2de19-111">App 已過期</span><span class="sxs-lookup"><span data-stu-id="2de19-111">App out of date</span></span>         |    <span data-ttu-id="2de19-112">Microsoft [團隊聊天室] 主控台顯示「系統組態已過期」錯誤。</span><span class="sxs-lookup"><span data-stu-id="2de19-112">The Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>                |   [<span data-ttu-id="2de19-113">使用 Microsoft 團隊會議室恢復工具</span><span class="sxs-lookup"><span data-stu-id="2de19-113">Use the Microsoft Teams Rooms recovery tool</span></span>](recovery-tool.md)             |  <span data-ttu-id="2de19-114">無</span><span class="sxs-lookup"><span data-stu-id="2de19-114">None</span></span> |
|  <span data-ttu-id="2de19-115">裝置更新為不受支援的 Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="2de19-115">Device updated to unsupported version of Windows 10</span></span>   |    <span data-ttu-id="2de19-116">Windows 10 裝置從版本1803更新至不受支援的版本1809。</span><span class="sxs-lookup"><span data-stu-id="2de19-116">Windows 10 device updated from version 1803 to version 1809, which is not supported.</span></span> <span data-ttu-id="2de19-117">支援的版本為1903。</span><span class="sxs-lookup"><span data-stu-id="2de19-117">The supported version is 1903.</span></span> |   <span data-ttu-id="2de19-118">如果 DeferFeatureUpdatesPeriodinDays 設定的[群組原則或 MDM](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)設定（可讓您將功能更新推遲至指定的天數），則會發生這種情況，將其設定為最大值365天。</span><span class="sxs-lookup"><span data-stu-id="2de19-118">This can happen if the [Group Policy or MDM setting for DeferFeatureUpdatesPeriodinDays](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) setting, which lets you defer feature updates for a specified number of days, is set to the maximum of 365 days.</span></span> <br><br> <span data-ttu-id="2de19-119">Microsoft 團隊聊天室不支援 Windows 10 版本1809，而版本1903則受支援。</span><span class="sxs-lookup"><span data-stu-id="2de19-119">Windows 10 version 1809 isn't supported with Microsoft Teams Rooms, while version 1903 is supported.</span></span> <span data-ttu-id="2de19-120">不過，從2020年3月27日起，版本1809超過365天。</span><span class="sxs-lookup"><span data-stu-id="2de19-120">However, as of March 27, 2020, version 1809 is over 365 days old.</span></span> <span data-ttu-id="2de19-121">如果此設定未變更，Windows 會嘗試安裝版本1809，這可能會導致 Microsoft 團隊聊天室發生問題。</span><span class="sxs-lookup"><span data-stu-id="2de19-121">If this setting isn't changed, Windows attempts to install version 1809, which may cause issues with Microsoft Teams Rooms.</span></span><br><br><span data-ttu-id="2de19-122">若要避免這種情況，請**移除**任何群組原則或任何推遲更新的 MDM 設定。</span><span class="sxs-lookup"><span data-stu-id="2de19-122">To avoid this situation, **remove** any Group Policy or MDM setting for deferring updates.</span></span> <span data-ttu-id="2de19-123">這可讓 Windows 更新到最新支援的 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="2de19-123">This allows Windows to update to the latest, supported OS version.</span></span> <br><br><span data-ttu-id="2de19-124">**重要**必須**移除**[群組原則] 或 [MDM] 設定（[保留未設定]），且**未設定為 0**。</span><span class="sxs-lookup"><span data-stu-id="2de19-124">**IMPORTANT** The Group Policy or MDM setting must be **removed** (left unconfigured) and **not set to 0**.</span></span> <span data-ttu-id="2de19-125">如果原則設定為0，Windows 會採用可能不受支援的最新可用版本。</span><span class="sxs-lookup"><span data-stu-id="2de19-125">If the policy is set to 0, Windows takes the latest available version which may not be supported.</span></span> |  <span data-ttu-id="2de19-126">無</span><span class="sxs-lookup"><span data-stu-id="2de19-126">None</span></span> |

<span data-ttu-id="2de19-127"><a name="OS-conflicts"> </a></span><span class="sxs-lookup"><span data-stu-id="2de19-127"><a name="OS-conflicts"> </a></span></span>  
## <a name="user-interface"></a><span data-ttu-id="2de19-128">使用者介面</span><span class="sxs-lookup"><span data-stu-id="2de19-128">User interface</span></span> 

| <span data-ttu-id="2de19-129">問題標題</span><span class="sxs-lookup"><span data-stu-id="2de19-129">Issue title</span></span> |  <span data-ttu-id="2de19-130">行為\/症狀</span><span class="sxs-lookup"><span data-stu-id="2de19-130">Behavior \/ Symptom</span></span> | <span data-ttu-id="2de19-131">已知的因應措施</span><span class="sxs-lookup"><span data-stu-id="2de19-131">Known workaround</span></span> | <span data-ttu-id="2de19-132">知識庫文章</span><span class="sxs-lookup"><span data-stu-id="2de19-132">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|<span data-ttu-id="2de19-133">找不到虛擬鍵盤</span><span class="sxs-lookup"><span data-stu-id="2de19-133">Virtual keyboard missing</span></span>   | <span data-ttu-id="2de19-134">當您需要在 Microsoft 團隊聊天室中輸入資訊時，不會顯示虛擬鍵盤。</span><span class="sxs-lookup"><span data-stu-id="2de19-134">The virtual keyboard doesn't appear when you need to enter information in Microsoft Teams Rooms.</span></span> <span data-ttu-id="2de19-135">這個問題會發生在 Windows 10 版本1903。</span><span class="sxs-lookup"><span data-stu-id="2de19-135">This issue occurs in Windows 10, version 1903.</span></span> | <span data-ttu-id="2de19-136">透過 Windows 更新，為 Windows 10 （版本1903）安裝2020-04 累積更新。</span><span class="sxs-lookup"><span data-stu-id="2de19-136">Install 2020-04 Cumulative Update for Windows 10, version 1903 for x64-based Systems through Windows Updates.</span></span>  | <span data-ttu-id="2de19-137">無</span><span class="sxs-lookup"><span data-stu-id="2de19-137">None</span></span> | 

<span data-ttu-id="2de19-138"><a name="Hardware"> </a></span><span class="sxs-lookup"><span data-stu-id="2de19-138"><a name="Hardware"> </a></span></span>  
## <a name="hardware"></a><span data-ttu-id="2de19-139">硬體</span><span class="sxs-lookup"><span data-stu-id="2de19-139">Hardware</span></span>

| <span data-ttu-id="2de19-140">問題標題</span><span class="sxs-lookup"><span data-stu-id="2de19-140">Issue title</span></span> |  <span data-ttu-id="2de19-141">行為\/症狀</span><span class="sxs-lookup"><span data-stu-id="2de19-141">Behavior \/ Symptom</span></span> | <span data-ttu-id="2de19-142">已知的因應措施</span><span class="sxs-lookup"><span data-stu-id="2de19-142">Known workaround</span></span> | <span data-ttu-id="2de19-143">知識庫文章</span><span class="sxs-lookup"><span data-stu-id="2de19-143">KB Article</span></span> |
|  ---        |      ---             |   ---            |   --- |
| <span data-ttu-id="2de19-144">未偵測到監視器</span><span class="sxs-lookup"><span data-stu-id="2de19-144">Monitors not detected</span></span> | <span data-ttu-id="2de19-145">當您在 Surface Pro （模型2017）裝置上執行 Microsoft 團隊聊天室時，系統不會偵測到監視器。</span><span class="sxs-lookup"><span data-stu-id="2de19-145">When you run Microsoft Teams Rooms on a Surface Pro (Model 2017) device, monitors are not detected.</span></span> |  <span data-ttu-id="2de19-146">按住 Surface Pro 電源按鈕20秒以上的時間。</span><span class="sxs-lookup"><span data-stu-id="2de19-146">Hold down the Surface Pro power button for 20 or more seconds.</span></span> <span data-ttu-id="2de19-147">當您這麼做時，裝置會重新開機並清除圖形快取。</span><span class="sxs-lookup"><span data-stu-id="2de19-147">When you do this, the device restarts and clears the graphics cache.</span></span> |[<span data-ttu-id="2de19-148">KB4055681</span><span class="sxs-lookup"><span data-stu-id="2de19-148">KB4055681</span></span>](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<span data-ttu-id="2de19-149"><a name="Limits"> </a></span><span class="sxs-lookup"><span data-stu-id="2de19-149"><a name="Limits"> </a></span></span>
## <a name="limitations-and-expected-behaviors"></a><span data-ttu-id="2de19-150">限制與預期行為</span><span class="sxs-lookup"><span data-stu-id="2de19-150">Limitations and expected behaviors</span></span>

***

<span data-ttu-id="2de19-151">Microsoft 團隊會議室不支援 HDCP 輸入，但已觀察到可導致 HDMI 攝取功能（影片、音訊）的問題。</span><span class="sxs-lookup"><span data-stu-id="2de19-151">Microsoft Teams Rooms does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="2de19-152">請務必小心，確定連線至 Microsoft 團隊聊天室的交換器已關閉 HDCP 選項。</span><span class="sxs-lookup"><span data-stu-id="2de19-152">Take care to ensure that switches connected to Microsoft Teams Rooms have HDCP options turned off.</span></span> 

***

<span data-ttu-id="2de19-153">如果您希望在來源從待機模式喚醒時自動切換到活動影片來源（例如 MTR 主控台），必須符合某些條件。</span><span class="sxs-lookup"><span data-stu-id="2de19-153">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="2de19-154">此功能是選擇性的，但 Microsoft 團隊聊天室軟體支援，提供基礎硬體支援此功能。</span><span class="sxs-lookup"><span data-stu-id="2de19-154">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="2de19-155">在房間顯示中使用的消費者電視需要支援 HDMI 的消費電子產品控制（CEC）功能。</span><span class="sxs-lookup"><span data-stu-id="2de19-155">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="2de19-156">根據所選的 dock 或 console （可能不支援 CEC，請參閱製造商支援檔），您可能需要使用工作區控制器（例如[EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad) ）來啟用所需的行為。</span><span class="sxs-lookup"><span data-stu-id="2de19-156">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a workspace controller such as an [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) may be needed to enable the desired behavior.</span></span> 

***

<span data-ttu-id="2de19-157">請務必使用有線 1 Gbps 網路連線，以確保您有所需的頻寬。</span><span class="sxs-lookup"><span data-stu-id="2de19-157">Always use a wired 1-Gbps network connection to assure you have the needed bandwidth.</span></span> 

***

<span data-ttu-id="2de19-158">如果您的 Microsoft 團隊聊天室裝置無法與網域失去信任，您就無法在裝置上進行驗證，也無法開啟 [設定]。</span><span class="sxs-lookup"><span data-stu-id="2de19-158">If your Microsoft Teams Rooms device loses trust with the domain, you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="2de19-159">例如，如果您在網域加入後從網域中移除 Microsoft 團隊聊天室，信任就會遺失。</span><span class="sxs-lookup"><span data-stu-id="2de19-159">For example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined, trust is lost.</span></span> <span data-ttu-id="2de19-160">解決方法是使用本機管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="2de19-160">The workaround is to log in with the local Admin account.</span></span> 
***
<span data-ttu-id="2de19-161">Microsoft 團隊聊天室版本3.0.12.0 不再支援64位版本的 Windows 10 Enterprise 周年紀念日（英文、版本1607）。</span><span class="sxs-lookup"><span data-stu-id="2de19-161">The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Microsoft Teams Rooms release 3.0.12.0.</span></span> 
***
<span data-ttu-id="2de19-162">Microsoft [團隊會議室] 是一個多視窗應用程式，且需要將房間顯示器正面連接到裝置的 HDMI 埠，才能讓 app 正常運作。</span><span class="sxs-lookup"><span data-stu-id="2de19-162">Microsoft Teams Rooms is a multi-window application and requires a front of room display to be connected to the HDMI port of the device, for the app to function correctly.</span></span> <span data-ttu-id="2de19-163">如果您正在測試，但尚未購買顯示器，請確定您已連接 HDMI 顯示器，或使用虛擬 HDMI 插頭。</span><span class="sxs-lookup"><span data-stu-id="2de19-163">Make sure that you either have an HDMI display connected or use a dummy HDMI plug if you are testing and do not have a display purchased yet.</span></span>
***
<span data-ttu-id="2de19-164"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="2de19-164"><a name="See"> </a></span></span>  
## <a name="see-also"></a><span data-ttu-id="2de19-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2de19-165">See also</span></span>

[<span data-ttu-id="2de19-166">Microsoft 團隊聊天室說明</span><span class="sxs-lookup"><span data-stu-id="2de19-166">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="2de19-167">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="2de19-167">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
