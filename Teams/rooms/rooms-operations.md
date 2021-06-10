---
title: Microsoft Teams 會議室維護與作業
ms.author: dstrome
author: dstrome
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
description: 請閱讀本主題以瞭解新一代會議室Microsoft Teams 會議室管理Skype管理。
ms.openlocfilehash: 52234f72c380c4f5af8f47fff51998fa8c3d1459
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117431"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="6c1ec-103">Microsoft Teams 會議室維護與作業</span><span class="sxs-lookup"><span data-stu-id="6c1ec-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="6c1ec-104">請閱讀本主題以瞭解新一代會議室Microsoft Teams 會議室管理Skype管理。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="6c1ec-105">Microsoft Teams 會議室是 Microsoft 的最新會議解決方案，專為將您的會議室轉換成豐富的共同合作體驗所設計。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="6c1ec-106">使用者將享有熟悉的Microsoft Teams或商務用 Skype介面，IT 系統管理員會感謝您在會議應用程式中輕鬆部署Windows 10 Skype管理。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="6c1ec-107">Microsoft Teams 會議室是設計用來利用現有設備 ，例如LCD 面板，方便安裝，Microsoft Teams或商務用 Skype會議室。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="6c1ec-108">使用 Microsoft Azure其他組組時，您可以如規劃 Microsoft Teams 會議室 管理與[Azure 監視器](azure-monitor-plan.md)、使用[Azure 監視器](azure-monitor-deploy.md)部署 Microsoft Teams 會議室 管理、使用 Azure 監視器管理 Microsoft Teams 會議室 裝置中所述，使用 Microsoft Teams 會議室 監視器進行遠端[管理](azure-monitor-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="6c1ec-109">您也可以使用 XML[設定檔](xml-config-file.md)Microsoft Teams 會議室管理主機設定，包括使用自訂顯示主題。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="6c1ec-110">收集記錄Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="6c1ec-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="6c1ec-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-111"><a name="Logs"> </a></span></span>

<span data-ttu-id="6c1ec-112">若要收集記錄，您必須調用隨應用程式一起Microsoft Teams 會議室腳本。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="6c1ec-113">在系統管理模式中，啟動提升的命令提示，併發出下列命令：</span><span class="sxs-lookup"><span data-stu-id="6c1ec-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="6c1ec-114">記錄會以 ZIP 檔案在 c：\rigel 中輸出。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="6c1ec-115">會議室顯示畫面設定</span><span class="sxs-lookup"><span data-stu-id="6c1ec-115">Front of Room Display Settings</span></span>
<span data-ttu-id="6c1ec-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-116"><a name="Display"> </a></span></span>

<span data-ttu-id="6c1ec-117">將會議室前方顯示設定為延伸模式。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="6c1ec-118">這麼做可確保當您在顯示器上迴圈使用電源時，主控台 UI 不會重複于該顯示器上。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c1ec-119">如果您希望會議室前方的顯示器自動切換到使用中的視 (例如當來源從待命模式喚醒時) 則必須符合某些條件。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-119">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="6c1ec-120">這項功能為選擇性，但Microsoft Teams 會議室支援，但基礎硬體支援此功能。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-120">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="6c1ec-121">做為會議室前顯示器的消費者電視需要支援消費者電子 (CEC) HDMI 功能。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-121">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="6c1ec-122">視選取的固定座或主機 (可能不支援 CEC，請參閱製造商支援檔) ，可能需要來自Crsron的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 Exron 的 [Exron HD CTL 100](https://www.extron.com/article/hdctl100ad) 控制器，才能啟用想要的行為。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-122">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a controller such as an [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) from Crestron or [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) from Extron may be needed to enable the desired behavior.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="6c1ec-123">Microsoft Teams 會議室重 (還原) </span><span class="sxs-lookup"><span data-stu-id="6c1ec-123">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="6c1ec-124"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-124"><a name="Reset"> </a></span></span>

<span data-ttu-id="6c1ec-125">如果Microsoft Teams 會議室運作不佳，執行出廠重設可能會有所説明。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-125">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="6c1ec-126">若要這麼做，請使用 Microsoft Teams[修復工具，](recovery-tool.md)並遵循出廠還原指示。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-126">To do this, use the [Microsoft Teams Room recovery tool](recovery-tool.md) and follow the factory restore instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="6c1ec-127">已知如果選取了 Microsoft Teams 會議室保留我的檔案 **-** 移除應用程式與設定，但保留您的個人檔案選項，Windows無法使用。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-127">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="6c1ec-128">請勿 *使用此選項* 。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-128">Do *not* use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="6c1ec-129">支援的遠端選項</span><span class="sxs-lookup"><span data-stu-id="6c1ec-129">Supported Remote Options</span></span>
<span data-ttu-id="6c1ec-130"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-130"><a name="RemoteOptions"> </a></span></span>

<span data-ttu-id="6c1ec-131">下表摘要列出可能的遠端作業，以及您可以用於完成這些作業的方法。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-131">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="6c1ec-132">工作組</span><span class="sxs-lookup"><span data-stu-id="6c1ec-132">Workgroup</span></span>|<span data-ttu-id="6c1ec-133">未加入網域</span><span class="sxs-lookup"><span data-stu-id="6c1ec-133">Not domain joined</span></span>|<span data-ttu-id="6c1ec-134">已加入網域</span><span class="sxs-lookup"><span data-stu-id="6c1ec-134">Domain joined</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c1ec-135">重新 啟動</span><span class="sxs-lookup"><span data-stu-id="6c1ec-135">Restart</span></span>  <br/> |<span data-ttu-id="6c1ec-136">Teams系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6c1ec-136">Teams admin center</span></span>  <br/> <span data-ttu-id="6c1ec-137">遠端桌面</span><span class="sxs-lookup"><span data-stu-id="6c1ec-137">Remote desktop</span></span>  <br/> <span data-ttu-id="6c1ec-138">遠端 Powershell</span><span class="sxs-lookup"><span data-stu-id="6c1ec-138">Remote Powershell</span></span>  <br/> | <br/><span data-ttu-id="6c1ec-139">遠端桌面 (需要進一步) </span><span class="sxs-lookup"><span data-stu-id="6c1ec-139">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="6c1ec-140">遠端 Powershell (需要進一步) </span><span class="sxs-lookup"><span data-stu-id="6c1ec-140">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="6c1ec-141">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6c1ec-141">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="6c1ec-142">更新作業系統</span><span class="sxs-lookup"><span data-stu-id="6c1ec-142">Update OS</span></span>  <br/> |<span data-ttu-id="6c1ec-143">Windows更新</span><span class="sxs-lookup"><span data-stu-id="6c1ec-143">Windows Update</span></span>  <br/> |<span data-ttu-id="6c1ec-144">Windows更新</span><span class="sxs-lookup"><span data-stu-id="6c1ec-144">Windows Update</span></span>  <br/> <span data-ttu-id="6c1ec-145">WSUS</span><span class="sxs-lookup"><span data-stu-id="6c1ec-145">WSUS</span></span>  <br/> |
|<span data-ttu-id="6c1ec-146">應用程式更新</span><span class="sxs-lookup"><span data-stu-id="6c1ec-146">App update</span></span>  <br/> |<span data-ttu-id="6c1ec-147">Windows商店</span><span class="sxs-lookup"><span data-stu-id="6c1ec-147">Windows Store</span></span>  <br/> |<span data-ttu-id="6c1ec-148">Windows商店</span><span class="sxs-lookup"><span data-stu-id="6c1ec-148">Windows Store</span></span>  <br/> <span data-ttu-id="6c1ec-149">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6c1ec-149">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="6c1ec-150">帳戶配置</span><span class="sxs-lookup"><span data-stu-id="6c1ec-150">Account Config</span></span>  <br/> |<span data-ttu-id="6c1ec-151">Teams系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6c1ec-151">Teams admin center</span></span>  <br/> |<span data-ttu-id="6c1ec-152">Teams系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6c1ec-152">Teams admin center</span></span>  <br/> |
|<span data-ttu-id="6c1ec-153">存取記錄</span><span class="sxs-lookup"><span data-stu-id="6c1ec-153">Access logs</span></span>  <br/> |<span data-ttu-id="6c1ec-154">Teams系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6c1ec-154">Teams admin center</span></span>  <br/> |<span data-ttu-id="6c1ec-155">Teams系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6c1ec-155">Teams admin center</span></span> <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="6c1ec-156">為使用者群組原則Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="6c1ec-156">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="6c1ec-157"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-157"><a name="GroupPolicy"> </a></span></span>

<span data-ttu-id="6c1ec-158">本節涵蓋系統設定，Microsoft Teams 會議室系統設定以正常運作。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-158">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="6c1ec-159">當您將Microsoft Teams 會議室網域時，請確保您的群組原則不會重寫下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-159">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="6c1ec-160">設定</span><span class="sxs-lookup"><span data-stu-id="6c1ec-160">Setting</span></span>|<span data-ttu-id="6c1ec-161">允許</span><span class="sxs-lookup"><span data-stu-id="6c1ec-161">Allows</span></span>|
|:-----|:-----|
|<span data-ttu-id="6c1ec-162">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="6c1ec-162">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="6c1ec-163">啟用Microsoft Teams 會議室啟動</span><span class="sxs-lookup"><span data-stu-id="6c1ec-163">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="6c1ec-164">Power Management - \> 在 AC 上，在 10 分鐘後關閉螢幕</span><span class="sxs-lookup"><span data-stu-id="6c1ec-164">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="6c1ec-165">Power Management - \> 在 AC 上，永不讓系統進入睡眠狀態</span><span class="sxs-lookup"><span data-stu-id="6c1ec-165">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="6c1ec-166">啟用Microsoft Teams 會議室關閉附加顯示器並自動喚醒</span><span class="sxs-lookup"><span data-stu-id="6c1ec-166">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="6c1ec-167">net accounts /maxpwage：unlimited</span><span class="sxs-lookup"><span data-stu-id="6c1ec-167">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="6c1ec-168">或是停用本地帳戶密碼到期的相同方式。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-168">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="6c1ec-169">若無法這麼做，最終會導致Skype帳戶無法登入抱怨密碼過期。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-169">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="6c1ec-170">請注意，這會影響電腦上所有的本機帳戶，因此如果無法設定此設定，也會導致方塊上的系統管理帳戶最後也會過期。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-170">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="6c1ec-171">讓Skype帳戶永遠登入</span><span class="sxs-lookup"><span data-stu-id="6c1ec-171">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="6c1ec-172">使用群組原則傳輸檔案在設定檔案專案 [中會進行討論](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-172">Transferring files using Group Policies is discussed in [Configure a File Item](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11)).</span></span>

> [!NOTE]
> <span data-ttu-id="6c1ec-173">當Microsoft Teams 會議室裝置與下一版的 Windows 10 OS 相容時，裝置會透過更新自動更新至Windows版本。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-173">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="6c1ec-174">Microsoft Teams 會議室 裝置不應透過 GPO 手動或啟用 Windows 商務用更新 (WUFB) 群群組原則「針對您想要接收的更新選取 Windows 準備等級」，以及透過 GPO 選取「何時收到預覽版建立與功能更新」來升級至下一版 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-174">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="6c1ec-175">已知啟用這些群組原則的裝置在應用程式Windows 10 OS 更新Microsoft Teams 會議室問題。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-175">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="6c1ec-176">使用 PowerShell 進行遠端系統管理</span><span class="sxs-lookup"><span data-stu-id="6c1ec-176">Remote Management using PowerShell</span></span>
<span data-ttu-id="6c1ec-177"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-177"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="6c1ec-178">您可以使用 PowerShell 遠端執行下列管理作業 (請參閱下表中的腳本範例) ：</span><span class="sxs-lookup"><span data-stu-id="6c1ec-178">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="6c1ec-179">取得附加裝置</span><span class="sxs-lookup"><span data-stu-id="6c1ec-179">Get attached devices</span></span>
- <span data-ttu-id="6c1ec-180">取得應用程式狀態</span><span class="sxs-lookup"><span data-stu-id="6c1ec-180">Get app status</span></span>
- <span data-ttu-id="6c1ec-181">取得系統資訊</span><span class="sxs-lookup"><span data-stu-id="6c1ec-181">Get system info</span></span>
- <span data-ttu-id="6c1ec-182">重新開機系統</span><span class="sxs-lookup"><span data-stu-id="6c1ec-182">Reboot system</span></span>
- <span data-ttu-id="6c1ec-183">取回記錄</span><span class="sxs-lookup"><span data-stu-id="6c1ec-183">Retrieve logs</span></span>
- <span data-ttu-id="6c1ec-184">傳輸檔案 (需要加入網域Microsoft Teams 會議室) </span><span class="sxs-lookup"><span data-stu-id="6c1ec-184">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c1ec-185">此功能預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-185">This functionality is off by default.</span></span> <span data-ttu-id="6c1ec-186">您需要為系統上的環境啟用遠端 PowerShell Microsoft Teams 會議室執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-186">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="6c1ec-187">請參閱 **[Enable-PSRemoting 相關](/powershell/module/microsoft.powershell.core/enable-psremoting)** 檔，以瞭解如何啟用遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-187">Refer to the documentation on **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="6c1ec-188">例如，您可以啟用遠端 PowerShell，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c1ec-188">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="6c1ec-189">在裝置上以系統管理員Microsoft Teams 會議室登錄。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-189">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="6c1ec-190">開啟提升的 PowerShell 命令提示。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-190">Open an elevated PowerShell command prompt.</span></span>
3. <span data-ttu-id="6c1ec-191">輸入下列命令： `Enable-PSRemoting -SkipNetworkProfileCheck -Force`</span><span class="sxs-lookup"><span data-stu-id="6c1ec-191">Enter the following command: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`</span></span>
4. <span data-ttu-id="6c1ec-192">開啟本地安全性原則，並新增 *系統管理員安全性群組* 至安全性設定  >  **原則**  >  **使用者許可權指派從** 網路存取  >  **此電腦**。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-192">Open the Local Security Policy and add the *Administrators* security group to **Security Settings** > **Local Policies** > **User Rights Assignment** > **Access this computer from the network**.</span></span>

<span data-ttu-id="6c1ec-193">若要執行管理作業：</span><span class="sxs-lookup"><span data-stu-id="6c1ec-193">To perform a management operation:</span></span>
  
1. <span data-ttu-id="6c1ec-194">使用擁有在裝置上執行 PowerShell 命令之許可權的帳號憑證，Microsoft Teams 會議室電腦。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-194">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="6c1ec-195">在 PC 上開啟一般 PowerShell 命令提示。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-195">Open a regular PowerShell command prompt on the PC.</span></span>
3. <span data-ttu-id="6c1ec-196">從下表複製命令文字，然後貼到提示。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-196">Copy the command text from the table below and paste it at the prompt.</span></span>
4. <span data-ttu-id="6c1ec-197">以  `<Device fqdn>` 適合您環境的 FQDN 值取代欄位。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-197">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
5. <span data-ttu-id="6c1ec-198">以主控設定檔的檔案名和本地路徑取代SkypeSettings.xml或主題 ( *\<path\>*  圖像) 。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-198">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="6c1ec-199">若要取得附加裝置</span><span class="sxs-lookup"><span data-stu-id="6c1ec-199">To Get Attached Devices</span></span>
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="6c1ec-200">取得應用程式狀態</span><span class="sxs-lookup"><span data-stu-id="6c1ec-200">Get App Status</span></span>
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="6c1ec-201">取得系統資訊</span><span class="sxs-lookup"><span data-stu-id="6c1ec-201">Get System Info</span></span>
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="6c1ec-202">重新開機系統</span><span class="sxs-lookup"><span data-stu-id="6c1ec-202">Reboot System</span></span>
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="6c1ec-203">取回記錄</span><span class="sxs-lookup"><span data-stu-id="6c1ec-203">Retrieve Logs</span></span>
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="6c1ec-204">將 XML 組 (或主題圖形) </span><span class="sxs-lookup"><span data-stu-id="6c1ec-204">Push an XML configuration file (or theme graphic)</span></span>
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="6c1ec-205">軟體更新</span><span class="sxs-lookup"><span data-stu-id="6c1ec-205">Software updates</span></span>
<span data-ttu-id="6c1ec-206"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-206"><a name="SWupdate"> </a></span></span>

<span data-ttu-id="6c1ec-207">根據預設，Microsoft Teams 會議室嘗試連接到 Windows Store 以取得最新版的 Microsoft Teams 會議室 軟體，因此裝置需要一般網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-207">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="6c1ec-208">在與 Microsoft 聯繫支援問題之前，Microsoft Teams 會議室裝置已載入最新版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-208">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="6c1ec-209">根據預設，Microsoft Teams 會議室更新Windows以取回作業系統和 USB 外接裝置固件更新，並安裝于已配置的上班時間以外。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-209">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="6c1ec-210">您可以登錄系統管理員帳戶並執行應用程式，以設定上班時間。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-210">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="6c1ec-211">如果您想要手動管理更新，而且無法遵循 商務用 Microsoft Store 發佈離線應用程式的一般程式，可以從部署套件[ (](https://go.microsoft.com/fwlink/?linkid=851168)從設定可與 Configuration Manager 一起使用的[](/microsoft-store/distribute-offline-apps)[Microsoft Teams 會議室](https://businessstore.microsoft.com/store)主控台) 的指示取得適當的 APPX[](console.md)檔案和相依性。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-211">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with Configuration Manager.</span></span> <span data-ttu-id="6c1ec-212">部署套件發行會落在市面發行之後，因此可能無法一直符合最新的可用版本。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-212">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="6c1ec-213">若要使用 Powershell 進行更新</span><span class="sxs-lookup"><span data-stu-id="6c1ec-213">To update using Powershell</span></span>

1. <span data-ttu-id="6c1ec-214">從安裝 [MSI 將套件解](https://go.microsoft.com/fwlink/?linkid=851168) 壓縮到裝置可以存取的共用。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-214">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
2. <span data-ttu-id="6c1ec-215">執行下列腳本，針對Microsoft Teams 會議室，並在適當時變更 \<share\> 為裝置共用：</span><span class="sxs-lookup"><span data-stu-id="6c1ec-215">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="6c1ec-216">系統管理模式與裝置管理</span><span class="sxs-lookup"><span data-stu-id="6c1ec-216">Admin mode and device management</span></span>
<span data-ttu-id="6c1ec-217"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-217"><a name="AdminMode"> </a></span></span>

<span data-ttu-id="6c1ec-218">有些管理功能 ，例如手動安裝私人 CA 憑證，需要將 Surface Pro裝置置於系統管理模式。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-218">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="6c1ec-219">切換至系統管理模式，Microsoft Teams 會議室應用程式執行時返回</span><span class="sxs-lookup"><span data-stu-id="6c1ec-219">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="6c1ec-220">掛斷任何進行中的通話，然後返回主畫面。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-220">Hang up any ongoing calls, and return to the home screen.</span></span>
2. <span data-ttu-id="6c1ec-221">選取齒輪圖示，然後顯示功能表 (**選項設定協助工具** 和重新開機 **裝置**) 。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-221">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
3. <span data-ttu-id="6c1ec-222">選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-222">Select **Settings**.</span></span>
4. <span data-ttu-id="6c1ec-223">輸入系統管理員密碼。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-223">Enter the Administrator Password.</span></span> <span data-ttu-id="6c1ec-224">系統會顯示設定畫面。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-224">The Setup screen will appear.</span></span>  <span data-ttu-id="6c1ec-225">如果裝置未加入網域，系統預設會使用 (使用者名稱「系統管理」) 系統管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-225">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="6c1ec-226">此帳戶的預設密碼是'sfb'，請儘快變更密碼。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-226">The default password for this account is 'sfb', change the password as soon as possible.</span></span> <span data-ttu-id="6c1ec-227">如果電腦已加入網域，您可以使用適當許可權的網域帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-227">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
5. <span data-ttu-id="6c1ec-228">選取 **Windows 設定** 欄的儲存格。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-228">Select **Windows Settings** in the left column.</span></span>
6. <span data-ttu-id="6c1ec-229">選擇 **前往系統管理登錄**。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-229">Choose **Go to Admin Sign-in**.</span></span>
7. <span data-ttu-id="6c1ec-230">輸入系統管理員密碼。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-230">Enter the Administrator Password.</span></span> <span data-ttu-id="6c1ec-231">這會正常登出應用程式，並帶您Windows畫面。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-231">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
8. <span data-ttu-id="6c1ec-232">使用系統管理認證登入桌面。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-232">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="6c1ec-233">您將擁有管理裝置的必要許可權。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-233">You'll have the necessary privileges to manage the device.</span></span>
9. <span data-ttu-id="6c1ec-234">執行必要的系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-234">Perform the necessary administrative tasks.</span></span>
10. <span data-ttu-id="6c1ec-235">從系統管理帳戶登出。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-235">Sign out from the Admin account.</span></span>
11. <span data-ttu-id="6c1ec-236">選取Microsoft Teams 會議室最左側的使用者帳戶圖示，然後選取 **Skype。**</span><span class="sxs-lookup"><span data-stu-id="6c1ec-236">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="6c1ec-237">如果未 **Skype** 使用者，您可能必須選取其他使用者，然後輸入 **.\skype** 做為使用者名稱，然後進行登錄。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-237">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="6c1ec-238">主機現在恢復為正常運作模式。下列程式要求您在裝置上附加鍵盤 ，如果尚未附加鍵盤。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-238">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="6c1ec-239">切換至系統管理模式，當應用程式Microsoft Teams 會議室時返回</span><span class="sxs-lookup"><span data-stu-id="6c1ec-239">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="6c1ec-240">連續連續Windows按五次按鍵。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-240">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="6c1ec-241">這會將您帶到登入Windows畫面。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-241">This will bring you to the Windows logon screen.</span></span> 
2. <span data-ttu-id="6c1ec-242">使用系統管理認證登入桌面。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-242">Log in to the desktop with your administrative credentials.</span></span>
3. <span data-ttu-id="6c1ec-243">執行必要的系統管理工作。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-243">Perform the necessary administrative tasks.</span></span>
4. <span data-ttu-id="6c1ec-244">完成後，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-244">Restart the machine when you're finished.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6c1ec-245">這個方法不會將使用者登出Skype或正常終止應用程式，但若應用程式沒有回應，且無法使用其他方法，您還是會使用它。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-245">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 

   <span data-ttu-id="6c1ec-246">主機會重新開機至其一般運作模式，執行 Microsoft Teams 會議室 App。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-246">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="6c1ec-247">您可以移除鍵盤 ，如果鍵盤已附加，讓您執行此程式。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-247">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="6c1ec-248">疑難排解秘訣</span><span class="sxs-lookup"><span data-stu-id="6c1ec-248">Troubleshooting tips</span></span>
   <span data-ttu-id="6c1ec-249"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="6c1ec-249"><a name="TS"> </a></span></span>

- <span data-ttu-id="6c1ec-250">跨網域邊界時可能不會顯示會議邀請 (例如，兩家公司之間的) 。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-250">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="6c1ec-251">在這種情況下，IT 系統管理員應決定是否允許外部使用者排程會議。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-251">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
- <span data-ttu-id="6c1ec-252">Microsoft Teams 會議室不支援透過 Exchange 2010 自動探索Exchange重新導向。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-252">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
- <span data-ttu-id="6c1ec-253">一般而言，IT 系統管理員可以停用他們不想使用的任何音訊端點。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-253">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
- <span data-ttu-id="6c1ec-254">如果會議室預覽中顯示鏡像影像，IT 系統管理員可以使用相機遙控器來切換相機電源或翻轉影像方向，以修正問題。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-254">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
- <span data-ttu-id="6c1ec-255">已知會遺失主控台觸控螢幕存取權。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-255">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="6c1ec-256">在這種情況下，此問題有時會重新開機系統Microsoft Teams 會議室解決。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-256">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
- <span data-ttu-id="6c1ec-257">已知透過有線輸入將電腦連接到主機時，會遺失本地音訊。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-257">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="6c1ec-258">在這種情況下，重新開機電腦可以解決本地音訊播放問題。</span><span class="sxs-lookup"><span data-stu-id="6c1ec-258">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
