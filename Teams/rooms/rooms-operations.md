---
title: Microsoft 團隊會議室維護和作業
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 請閱讀本主題，以瞭解 Microsoft 團隊聊天室（即新一代 Skype 房間系統）的管理。
ms.openlocfilehash: 109d07bdf7b4925f7c3d0481e1ff7facef3de8f8
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "43580701"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="e5702-103">Microsoft 團隊會議室維護和作業</span><span class="sxs-lookup"><span data-stu-id="e5702-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="e5702-104">請閱讀本主題，以瞭解 Microsoft 團隊聊天室（即新一代 Skype 房間系統）的管理。</span><span class="sxs-lookup"><span data-stu-id="e5702-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="e5702-105">Microsoft [團隊聊天室] 是 Microsoft 的最新會議解決方案，旨在將您的會議室轉換為豐富且共同合作的體驗。</span><span class="sxs-lookup"><span data-stu-id="e5702-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="e5702-106">使用者將享有其熟悉的 Microsoft 團隊或商務用 Skype 介面，IT 系統管理員會欣賞輕鬆部署和管理的 Windows 10 Skype 會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="e5702-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="e5702-107">Microsoft [團隊聊天室] 的設計目的是利用 LCD 面板等現有的裝置，輕鬆安裝，讓 Microsoft 團隊或商務用 Skype 融入會議室。</span><span class="sxs-lookup"><span data-stu-id="e5702-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="e5702-108">有了其他設定，就可以使用 Microsoft Azure 監視器進行遠端系統管理，如在[使用 Azure 監視器規劃 Microsoft 團隊聊天室管理](azure-monitor-plan.md)中所述，使用 azure 監視器[部署](azure-monitor-deploy.md)microsoft 團隊聊天室管理，[並使用 Azure 監視器管理 microsoft 團隊機房裝置](azure-monitor-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="e5702-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="e5702-109">您也可以[使用 XML 設定檔來遠端系統管理 Microsoft 團隊聊天室的主控台設定](xml-config-file.md)，包括套用自訂顯示主題。</span><span class="sxs-lookup"><span data-stu-id="e5702-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="e5702-110">在 Microsoft 團隊聊天室收集記錄</span><span class="sxs-lookup"><span data-stu-id="e5702-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="e5702-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-111"><a name="Logs"> </a></span></span>

<span data-ttu-id="e5702-112">若要收集記錄，您必須呼叫由 Microsoft 團隊聊天室應用程式隨附的記錄集合腳本。</span><span class="sxs-lookup"><span data-stu-id="e5702-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="e5702-113">在 [系統管理模式] 中，啟動提升許可權的命令提示字元，然後發出下列命令：</span><span class="sxs-lookup"><span data-stu-id="e5702-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="e5702-114">在 c:\rigel. 中，會將記錄輸出為 ZIP 檔案</span><span class="sxs-lookup"><span data-stu-id="e5702-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="e5702-115">房間顯示設定的正面</span><span class="sxs-lookup"><span data-stu-id="e5702-115">Front of Room Display Settings</span></span>
<span data-ttu-id="e5702-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-116"><a name="Display"> </a></span></span>

<span data-ttu-id="e5702-117">將會議室的正面顯示設定為 [延伸] 模式。</span><span class="sxs-lookup"><span data-stu-id="e5702-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="e5702-118">如此一來，就能確保當您重新開啟電源時，系統不會在該顯示器上複製主控台 UI。</span><span class="sxs-lookup"><span data-stu-id="e5702-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5702-119">如果您希望在來源從待機模式喚醒時自動切換到活動影片來源（例如 MTR 主控台），必須符合某些條件。</span><span class="sxs-lookup"><span data-stu-id="e5702-119">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="e5702-120">此功能是選擇性的，但 Microsoft 團隊聊天室軟體支援，提供基礎硬體支援此功能。</span><span class="sxs-lookup"><span data-stu-id="e5702-120">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="e5702-121">在房間顯示中使用的消費者電視需要支援 HDMI 的消費電子產品控制（CEC）功能。</span><span class="sxs-lookup"><span data-stu-id="e5702-121">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="e5702-122">根據所選的 dock 或主機（可能不支援 CEC，請參閱製造商支援檔），從 Extron Crestron 或[EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad)中的一個控制器（例如，可能需要從的[hd RX-201-E-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) ）來啟用所需的行為。</span><span class="sxs-lookup"><span data-stu-id="e5702-122">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a controller such as an [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) from Crestron or [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) from Extron may be needed to enable the desired behavior.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="e5702-123">Microsoft 團隊會議室重設（工廠還原）</span><span class="sxs-lookup"><span data-stu-id="e5702-123">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="e5702-124"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-124"><a name="Reset"> </a></span></span>

<span data-ttu-id="e5702-125">如果 Microsoft 團隊聊天室無法正常運作，可能會執行重設回原值。</span><span class="sxs-lookup"><span data-stu-id="e5702-125">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="e5702-126">若要這樣做，請使用[Microsoft 團隊聊天室恢復工具](recovery-tool.md)，並遵循工廠還原指示進行。</span><span class="sxs-lookup"><span data-stu-id="e5702-126">To do this, use the [Microsoft Teams Room recovery tool](recovery-tool.md) and follow the factory restore instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="e5702-127">如果 [保留我的檔案] **：移除 app 和設定，但**在 Windows 重設程式期間已選取 [保留您的個人檔案] 選項，則 Microsoft 團隊聊天室可能無法使用的已知問題。</span><span class="sxs-lookup"><span data-stu-id="e5702-127">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="e5702-128">請勿*使用此*選項。</span><span class="sxs-lookup"><span data-stu-id="e5702-128">Do *not* use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="e5702-129">支援的遠端選項</span><span class="sxs-lookup"><span data-stu-id="e5702-129">Supported Remote Options</span></span>
<span data-ttu-id="e5702-130"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-130"><a name="RemoteOptions"> </a></span></span>

<span data-ttu-id="e5702-131">下表摘要列出可能的遠端作業，以及您可以用來完成它們的方法。</span><span class="sxs-lookup"><span data-stu-id="e5702-131">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="e5702-132">工作組</span><span class="sxs-lookup"><span data-stu-id="e5702-132">Workgroup</span></span>|<span data-ttu-id="e5702-133">未加入網域</span><span class="sxs-lookup"><span data-stu-id="e5702-133">Not domain joined</span></span>|<span data-ttu-id="e5702-134">已加入網域</span><span class="sxs-lookup"><span data-stu-id="e5702-134">Domain joined</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5702-135">重</span><span class="sxs-lookup"><span data-stu-id="e5702-135">Restart</span></span>  <br/> |<span data-ttu-id="e5702-136">遠端桌面</span><span class="sxs-lookup"><span data-stu-id="e5702-136">Remote desktop</span></span>  <br/> <span data-ttu-id="e5702-137">遠端 Powershell</span><span class="sxs-lookup"><span data-stu-id="e5702-137">Remote Powershell</span></span>  <br/> |<span data-ttu-id="e5702-138">遠端桌面（需要進一步配置）</span><span class="sxs-lookup"><span data-stu-id="e5702-138">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="e5702-139">遠端 Powershell （需要進一步配置）</span><span class="sxs-lookup"><span data-stu-id="e5702-139">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="e5702-140">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e5702-140">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="e5702-141">更新作業系統</span><span class="sxs-lookup"><span data-stu-id="e5702-141">Update OS</span></span>  <br/> |<span data-ttu-id="e5702-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="e5702-142">Windows Update</span></span>  <br/> |<span data-ttu-id="e5702-143">Windows Update</span><span class="sxs-lookup"><span data-stu-id="e5702-143">Windows Update</span></span>  <br/> <span data-ttu-id="e5702-144">結合</span><span class="sxs-lookup"><span data-stu-id="e5702-144">WSUS</span></span>  <br/> |
|<span data-ttu-id="e5702-145">App 更新</span><span class="sxs-lookup"><span data-stu-id="e5702-145">App update</span></span>  <br/> |<span data-ttu-id="e5702-146">Windows 網上商店</span><span class="sxs-lookup"><span data-stu-id="e5702-146">Windows Store</span></span>  <br/> |<span data-ttu-id="e5702-147">Windows 網上商店</span><span class="sxs-lookup"><span data-stu-id="e5702-147">Windows Store</span></span>  <br/> <span data-ttu-id="e5702-148">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e5702-148">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="e5702-149">Skype 帳戶配置</span><span class="sxs-lookup"><span data-stu-id="e5702-149">Skype Account Config</span></span>  <br/> |<span data-ttu-id="e5702-150">目前不支援</span><span class="sxs-lookup"><span data-stu-id="e5702-150">Not currently supported</span></span>  <br/> |<span data-ttu-id="e5702-151">目前不支援</span><span class="sxs-lookup"><span data-stu-id="e5702-151">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="e5702-152">Access 記錄</span><span class="sxs-lookup"><span data-stu-id="e5702-152">Access logs</span></span>  <br/> |<span data-ttu-id="e5702-153">目前不支援</span><span class="sxs-lookup"><span data-stu-id="e5702-153">Not currently supported</span></span>  <br/> |<span data-ttu-id="e5702-154">目前不支援</span><span class="sxs-lookup"><span data-stu-id="e5702-154">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="e5702-155">為 Microsoft 團隊聊天室設定群組原則</span><span class="sxs-lookup"><span data-stu-id="e5702-155">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="e5702-156"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-156"><a name="GroupPolicy"> </a></span></span>

<span data-ttu-id="e5702-157">本節涵蓋 Microsoft 團隊聊天室所依賴的系統設定，以正常運作。</span><span class="sxs-lookup"><span data-stu-id="e5702-157">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="e5702-158">當您將 Microsoft 團隊聊天室加入網域時，請確定您的群組原則不會覆寫下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="e5702-158">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="e5702-159">設定</span><span class="sxs-lookup"><span data-stu-id="e5702-159">Setting</span></span>|<span data-ttu-id="e5702-160">讓</span><span class="sxs-lookup"><span data-stu-id="e5702-160">Allows</span></span>|
|:-----|:-----|
|<span data-ttu-id="e5702-161">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = （REG_SZ）1</span><span class="sxs-lookup"><span data-stu-id="e5702-161">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="e5702-162">可讓 Microsoft 團隊聊天室啟動</span><span class="sxs-lookup"><span data-stu-id="e5702-162">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="e5702-163">電源管理- \> 在 AC 上，10分鐘後關閉螢幕</span><span class="sxs-lookup"><span data-stu-id="e5702-163">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="e5702-164">電源管理- \> 在交流電上，請勿將系統置於睡眠狀態</span><span class="sxs-lookup"><span data-stu-id="e5702-164">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="e5702-165">讓 Microsoft 團隊聊天室關閉附加的顯示，並自動喚醒</span><span class="sxs-lookup"><span data-stu-id="e5702-165">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="e5702-166">淨帳戶/maxpwage：無限制</span><span class="sxs-lookup"><span data-stu-id="e5702-166">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="e5702-167">或同等的方式，在本機帳戶上停用密碼過期。</span><span class="sxs-lookup"><span data-stu-id="e5702-167">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="e5702-168">如果不這麼做，最終會導致 Skype 帳戶無法針對過期密碼登入。</span><span class="sxs-lookup"><span data-stu-id="e5702-168">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="e5702-169">請注意，這會影響電腦上的所有本機帳戶，因此無法設定這種情況，也會導致盒上的系統管理帳戶最終過期。</span><span class="sxs-lookup"><span data-stu-id="e5702-169">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="e5702-170">讓 Skype 帳戶永遠登入</span><span class="sxs-lookup"><span data-stu-id="e5702-170">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="e5702-171">使用群組原則來傳送檔案將在 [[設定檔案專案](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)] 中討論。</span><span class="sxs-lookup"><span data-stu-id="e5702-171">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="e5702-172">當 Microsoft 團隊聊天室裝置與下一版的 Windows 10 OS 相容時，裝置會透過 Windows Update 自動更新至下一個版本。</span><span class="sxs-lookup"><span data-stu-id="e5702-172">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="e5702-173">Microsoft 團隊聊天室裝置不應升級至 Windows 10 的下一次發行，或透過啟用商務用 Windows Update （WUFB）群組原則，選取您想要接收之更新的 Windows 就緒層級，然後透過 GPO 選取何時接收預覽版和功能更新。</span><span class="sxs-lookup"><span data-stu-id="e5702-173">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="e5702-174">已啟用這些群群組原則的裝置已知會遇到 Microsoft 小組聊天室 app 的 Windows 10 OS 更新問題。</span><span class="sxs-lookup"><span data-stu-id="e5702-174">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="e5702-175">使用 PowerShell 進行遠端系統管理</span><span class="sxs-lookup"><span data-stu-id="e5702-175">Remote Management using PowerShell</span></span>
<span data-ttu-id="e5702-176"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-176"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="e5702-177">您可以使用 PowerShell 遠端執行下列管理作業（請參閱下表以取得腳本範例）：</span><span class="sxs-lookup"><span data-stu-id="e5702-177">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="e5702-178">取得連接的裝置</span><span class="sxs-lookup"><span data-stu-id="e5702-178">Get attached devices</span></span>
- <span data-ttu-id="e5702-179">取得 app 狀態</span><span class="sxs-lookup"><span data-stu-id="e5702-179">Get app status</span></span>
- <span data-ttu-id="e5702-180">取得系統資訊</span><span class="sxs-lookup"><span data-stu-id="e5702-180">Get system info</span></span>
- <span data-ttu-id="e5702-181">重新開機系統</span><span class="sxs-lookup"><span data-stu-id="e5702-181">Reboot system</span></span>
- <span data-ttu-id="e5702-182">檢索記錄</span><span class="sxs-lookup"><span data-stu-id="e5702-182">Retrieve logs</span></span>
- <span data-ttu-id="e5702-183">傳輸檔案（需要加入網域的 Microsoft 團隊會議室）</span><span class="sxs-lookup"><span data-stu-id="e5702-183">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="e5702-184">此功能預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="e5702-184">This functionality is off by default.</span></span> <span data-ttu-id="e5702-185">您必須在 Microsoft 團隊聊天室系統上為您的環境啟用遠端 PowerShell，才能執行下列作業。</span><span class="sxs-lookup"><span data-stu-id="e5702-185">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="e5702-186">如需有關如何啟用遠端 PowerShell 的資訊，請參閱**[啟用-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="e5702-186">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="e5702-187">例如，您可以啟用遠端 PowerShell，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e5702-187">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="e5702-188">以系統管理員身分登入 Microsoft 團隊聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="e5702-188">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="e5702-189">開啟提升許可權的 PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="e5702-189">Open an elevated PowerShell command prompt.</span></span>
3. <span data-ttu-id="e5702-190">輸入下列命令： Enable-PSRemoting-force</span><span class="sxs-lookup"><span data-stu-id="e5702-190">Enter the following command: Enable-PSRemoting -force</span></span>

<span data-ttu-id="e5702-191">若要執行管理作業：</span><span class="sxs-lookup"><span data-stu-id="e5702-191">To perform a management operation:</span></span>
  
1. <span data-ttu-id="e5702-192">以具備在 Microsoft 團隊聊天室裝置上執行 PowerShell 命令許可權的帳號憑證登入電腦。</span><span class="sxs-lookup"><span data-stu-id="e5702-192">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="e5702-193">在電腦上開啟一般的 PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="e5702-193">Open a regular PowerShell command prompt on the PC.</span></span>
3. <span data-ttu-id="e5702-194">從下表複製命令文字，並在出現提示時貼上。</span><span class="sxs-lookup"><span data-stu-id="e5702-194">Copy the command text from the table below and paste it at the prompt.</span></span>
4. <span data-ttu-id="e5702-195">以 `<Device fqdn>` 適合您環境的 FQDN 值取代欄位。</span><span class="sxs-lookup"><span data-stu-id="e5702-195">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
5. <span data-ttu-id="e5702-196">以主 SkypeSettings 配置檔案（或主題圖像）的檔案名和本機路徑取代\* \< 路徑 \> \* 。</span><span class="sxs-lookup"><span data-stu-id="e5702-196">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="e5702-197">取得連接的裝置</span><span class="sxs-lookup"><span data-stu-id="e5702-197">To Get Attached Devices</span></span>
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="e5702-198">取得 App 狀態</span><span class="sxs-lookup"><span data-stu-id="e5702-198">Get App Status</span></span>
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="e5702-199">取得系統資訊</span><span class="sxs-lookup"><span data-stu-id="e5702-199">Get System Info</span></span>
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="e5702-200">重新開機系統</span><span class="sxs-lookup"><span data-stu-id="e5702-200">Reboot System</span></span>
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="e5702-201">檢索記錄</span><span class="sxs-lookup"><span data-stu-id="e5702-201">Retrieve Logs</span></span>
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="e5702-202">推入 XML 設定檔（或主題圖形）</span><span class="sxs-lookup"><span data-stu-id="e5702-202">Push an XML configuration file (or theme graphic)</span></span>
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="e5702-203">軟體更新</span><span class="sxs-lookup"><span data-stu-id="e5702-203">Software updates</span></span>
<span data-ttu-id="e5702-204"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-204"><a name="SWupdate"> </a></span></span>

<span data-ttu-id="e5702-205">根據預設，Microsoft 團隊聊天室會嘗試連線到 Windows 市集中，以取得最新版本的 Microsoft 團隊聊天室軟體，因此裝置需要進行一般的網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="e5702-205">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="e5702-206">在與 Microsoft 取得支援問題之前，請務必先使用最新版本的 app 載入 Microsoft 團隊聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="e5702-206">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="e5702-207">根據預設，Microsoft 球隊聊天室會連線至 Windows Update，以檢索作業系統和 USB 週邊裝置固件更新，並將其安裝在已設定的商務時間以外。</span><span class="sxs-lookup"><span data-stu-id="e5702-207">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="e5702-208">您可以登入管理員帳戶並執行 [設定] 應用程式，來設定上班時間。</span><span class="sxs-lookup"><span data-stu-id="e5702-208">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="e5702-209">如果您想要手動管理更新，且無法遵循[Microsoft 網上商店 For Business](https://businessstore.microsoft.com/store) [發佈離線 app](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)的一般程式，您可以從[部署套件](https://go.microsoft.com/fwlink/?linkid=851168)取得適當的 APPX 檔案和相依性（從指示[設定 Microsoft 團隊聊天室主控台](console.md)），可與 Configuration Manager 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="e5702-209">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with Configuration Manager.</span></span> <span data-ttu-id="e5702-210">部署套件版本滯後于商店發行版本本，因此可能不一定會與最新的可用組建相符。</span><span class="sxs-lookup"><span data-stu-id="e5702-210">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="e5702-211">使用 Powershell 更新</span><span class="sxs-lookup"><span data-stu-id="e5702-211">To update using Powershell</span></span>

1. <span data-ttu-id="e5702-212">從安裝[MSI](https://go.microsoft.com/fwlink/?linkid=851168)將套件解壓縮至裝置可以存取的共用。</span><span class="sxs-lookup"><span data-stu-id="e5702-212">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
2. <span data-ttu-id="e5702-213">針對 Microsoft 團隊聊天室裝置執行下列腳本， \< 視需要將共用變更 \> 為裝置共用：</span><span class="sxs-lookup"><span data-stu-id="e5702-213">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="e5702-214">系統管理模式與裝置管理</span><span class="sxs-lookup"><span data-stu-id="e5702-214">Admin mode and device management</span></span>
<span data-ttu-id="e5702-215"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-215"><a name="AdminMode"> </a></span></span>

<span data-ttu-id="e5702-216">某些管理功能（例如手動安裝私人 CA 憑證）需要將 Surface Pro 裝置放在系統管理模式中。</span><span class="sxs-lookup"><span data-stu-id="e5702-216">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="e5702-217">當 Microsoft 團隊聊天室 app 執行時，切換到 [管理員模式] 並返回 [返回]</span><span class="sxs-lookup"><span data-stu-id="e5702-217">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="e5702-218">掛斷任何正在進行的通話，然後返回主畫面。</span><span class="sxs-lookup"><span data-stu-id="e5702-218">Hang up any ongoing calls, and return to the home screen.</span></span>
2. <span data-ttu-id="e5702-219">選取齒輪圖示並顯示功能表（選項為 [**設定**]、[**協助工具**] 和 [**重新開機裝置**]）。</span><span class="sxs-lookup"><span data-stu-id="e5702-219">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
3. <span data-ttu-id="e5702-220">選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="e5702-220">Select **Settings**.</span></span>
4. <span data-ttu-id="e5702-221">輸入系統管理員密碼。</span><span class="sxs-lookup"><span data-stu-id="e5702-221">Enter the Administrator Password.</span></span> <span data-ttu-id="e5702-222">[設定] 畫面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="e5702-222">The Setup screen will appear.</span></span>  <span data-ttu-id="e5702-223">如果裝置未加入網域，則預設會使用本機系統管理帳戶（username "Admin"）。</span><span class="sxs-lookup"><span data-stu-id="e5702-223">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="e5702-224">此帳戶的預設密碼是 [sfb]，請儘快變更密碼。</span><span class="sxs-lookup"><span data-stu-id="e5702-224">The default password for this account is 'sfb', change the password as soon as possible.</span></span> <span data-ttu-id="e5702-225">如果電腦已加入網域，您可以使用適當許可權的網域帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e5702-225">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
5. <span data-ttu-id="e5702-226">選取左欄中的 [ **Windows 設定**]。</span><span class="sxs-lookup"><span data-stu-id="e5702-226">Select **Windows Settings** in the left column.</span></span>
6. <span data-ttu-id="e5702-227">選擇 [**移至系統管理員登入**]。</span><span class="sxs-lookup"><span data-stu-id="e5702-227">Choose **Go to Admin Sign-in**.</span></span>
7. <span data-ttu-id="e5702-228">輸入系統管理員密碼。</span><span class="sxs-lookup"><span data-stu-id="e5702-228">Enter the Administrator Password.</span></span> <span data-ttu-id="e5702-229">這會適當地登出應用程式，並將您帶到 Windows 登入畫面。</span><span class="sxs-lookup"><span data-stu-id="e5702-229">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
8. <span data-ttu-id="e5702-230">使用您的管理認證登入桌面。</span><span class="sxs-lookup"><span data-stu-id="e5702-230">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="e5702-231">您將擁有管理裝置所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="e5702-231">You'll have the necessary privileges to manage the device.</span></span>
9. <span data-ttu-id="e5702-232">執行必要的管理工作。</span><span class="sxs-lookup"><span data-stu-id="e5702-232">Perform the necessary administrative tasks.</span></span>
10. <span data-ttu-id="e5702-233">從管理員帳戶登出。</span><span class="sxs-lookup"><span data-stu-id="e5702-233">Sign out from the Admin account.</span></span>
11. <span data-ttu-id="e5702-234">選取畫面最左邊的 [使用者帳戶] 圖示，然後選取 [ **Skype**]，回到 Microsoft 團隊聊天室。</span><span class="sxs-lookup"><span data-stu-id="e5702-234">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="e5702-235">如果沒有列出**Skype**使用者，您可能需要選取 [**其他使用者**]，然後輸入 **.\skype**做為使用者名稱，然後登入。</span><span class="sxs-lookup"><span data-stu-id="e5702-235">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="e5702-236">現在，主機會回到其正常操作模式。下列程式需要您在裝置上附加鍵盤（如果尚未連接的話）。</span><span class="sxs-lookup"><span data-stu-id="e5702-236">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="e5702-237">當 Microsoft 小組聊天室 app 當機時切換至 [系統管理] 模式並返回回去</span><span class="sxs-lookup"><span data-stu-id="e5702-237">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="e5702-238">快速連續按下 Windows 鍵五次。</span><span class="sxs-lookup"><span data-stu-id="e5702-238">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="e5702-239">這會將您帶到 Windows 登入畫面。</span><span class="sxs-lookup"><span data-stu-id="e5702-239">This will bring you to the Windows logon screen.</span></span> 
2. <span data-ttu-id="e5702-240">使用您的管理認證登入桌面。</span><span class="sxs-lookup"><span data-stu-id="e5702-240">Log in to the desktop with your administrative credentials.</span></span>
3. <span data-ttu-id="e5702-241">執行必要的管理工作。</span><span class="sxs-lookup"><span data-stu-id="e5702-241">Perform the necessary administrative tasks.</span></span>
4. <span data-ttu-id="e5702-242">完成後，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="e5702-242">Restart the machine when you're finished.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5702-243">這個方法不會記錄 Skype 使用者，或適當地終止應用程式，但如果應用程式沒有回應且其他方法無法使用，您就可以使用它。</span><span class="sxs-lookup"><span data-stu-id="e5702-243">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 

   <span data-ttu-id="e5702-244">主控台會重新開機至正常的操作模式，並執行 Microsoft 團隊聊天室 app。</span><span class="sxs-lookup"><span data-stu-id="e5702-244">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="e5702-245">如果您已附加鍵盤，您就可以移除它，以允許您執行此程式。</span><span class="sxs-lookup"><span data-stu-id="e5702-245">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="e5702-246">疑難排解提示</span><span class="sxs-lookup"><span data-stu-id="e5702-246">Troubleshooting tips</span></span>
   <span data-ttu-id="e5702-247"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="e5702-247"><a name="TS"> </a></span></span>

- <span data-ttu-id="e5702-248">在跨網域邊界傳送時，會議邀請可能不會出現（例如，在兩個公司之間）。</span><span class="sxs-lookup"><span data-stu-id="e5702-248">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="e5702-249">在這種情況下，IT 系統管理員應該決定是否要允許外部使用者排程會議。</span><span class="sxs-lookup"><span data-stu-id="e5702-249">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
- <span data-ttu-id="e5702-250">Microsoft 團隊聊天室不支援透過 Exchange 2010 的 Exchange 自動探索重新導向。</span><span class="sxs-lookup"><span data-stu-id="e5702-250">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
- <span data-ttu-id="e5702-251">一般來說，IT 管理員要停用任何不想要使用的音訊端點是一個不錯的做法。</span><span class="sxs-lookup"><span data-stu-id="e5702-251">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
- <span data-ttu-id="e5702-252">如果在會議室預覽中顯示鏡像影像，IT 系統管理員可以使用相機遙控器來重啟相機電源或翻轉影像方向來修正。</span><span class="sxs-lookup"><span data-stu-id="e5702-252">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
- <span data-ttu-id="e5702-253">已已知失去主控台觸控式螢幕的存取權。</span><span class="sxs-lookup"><span data-stu-id="e5702-253">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="e5702-254">在這種情況下，可能會因重新開機 Microsoft 團隊聊天室系統來解決此問題。</span><span class="sxs-lookup"><span data-stu-id="e5702-254">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
- <span data-ttu-id="e5702-255">透過有線攝取將電腦連線到主控台時，會遺失本機音訊。</span><span class="sxs-lookup"><span data-stu-id="e5702-255">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="e5702-256">在這種情況下，重新開機電腦可以解決本機音訊播放問題。</span><span class="sxs-lookup"><span data-stu-id="e5702-256">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
