---
title: 設定 Microsoft Teams 會議室主控台
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文將說明如何設定及設定主機Microsoft Teams 會議室及其周邊設備。
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117571"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="0dcbb-103">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="0dcbb-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="0dcbb-104">本文將說明如何設定主機Microsoft Teams 會議室及其周邊設備。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="0dcbb-105">您必須執行這些步驟，Microsoft Teams或商務用 Skype帳戶Exchange，並如部署帳戶中所述[Microsoft Teams 會議室。](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="0dcbb-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span> <span data-ttu-id="0dcbb-106">您需要上述的硬體和軟體Microsoft Teams 會議室[需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="0dcbb-107">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="0dcbb-108">準備安裝媒體</span><span class="sxs-lookup"><span data-stu-id="0dcbb-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="0dcbb-109">在主機上安裝私人 CA 憑證</span><span class="sxs-lookup"><span data-stu-id="0dcbb-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="0dcbb-110">安裝Windows 10主機Microsoft Teams 會議室應用程式</span><span class="sxs-lookup"><span data-stu-id="0dcbb-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="0dcbb-111">主機的初始設定</span><span class="sxs-lookup"><span data-stu-id="0dcbb-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="0dcbb-112">Microsoft Teams 會議室部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="0dcbb-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="0dcbb-113">Microsoft Teams 會議室只能在正確設定Microsoft Teams或商務用 Skype環境中運作，而裝置帳戶已正確設定，如部署[Microsoft Teams 會議室。](rooms-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="0dcbb-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](rooms-deploy.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="0dcbb-114">準備安裝媒體</span><span class="sxs-lookup"><span data-stu-id="0dcbb-114">Prepare the installation media</span></span>
<span data-ttu-id="0dcbb-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="0dcbb-115"><a name="Prep_Media"> </a></span></span>

<span data-ttu-id="0dcbb-116">安裝主機Microsoft Teams 會議室需要至少 32 GB 容量的 USB 儲存裝置。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="0dcbb-117">裝置上不應有其他檔案;USB 儲存空間上的任何現有檔案都會遺失。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0dcbb-118">根據這些指示Microsoft Teams 會議室建立您的安裝媒體可能會導致意外的行為。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="0dcbb-119">以下程式是建立安裝媒體以將新裝置Microsoft Teams 會議室影像。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="0dcbb-120">根據預設，現有裝置會從 Windows 和 Windows 自動更新。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dcbb-121">用來Windows 10安裝媒體Microsoft Teams 會議室電腦必須位於與目標安裝媒體相同的或Windows版本。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-121">The Windows 10 machine used to create the Microsoft Teams Rooms installation media must be on the same or later version of Windows as the target installation media.</span></span>
  
1. <span data-ttu-id="0dcbb-122">下載CreateSrsMedia.ps1 [ 腳本](https://go.microsoft.com/fwlink/?linkid=867842)。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-122">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="0dcbb-123">從CreateSrsMedia.ps1電腦上提升的提示執行Windows 10腳本。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-123">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="0dcbb-124">請遵循腳本的指示，在 USB Microsoft Teams 會議室建立磁片。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-124">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="0dcbb-125">每一次CreateSrsMedia.ps1腳本啟動時，畫面輸出會包含記錄檔案或會話記錄的名稱。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-125">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="0dcbb-126">如果執行腳本時發生問題，請務必在要求支援時提供該腳本的一份副本。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-126">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="0dcbb-127">腳本CreateSrsMedia.ps1自動化下列工作：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-127">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="0dcbb-128">下載最新的 MSI 安裝程式Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-128">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="0dcbb-129">決定使用者Windows的建立。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-129">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="0dcbb-130">最近發行的版本可能會受到測試，也可能不支援與Microsoft Teams 會議室一起使用。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-130">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="0dcbb-131">下載必要的支援元件。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-131">Download necessary supporting components.</span></span>
4. <span data-ttu-id="0dcbb-132">在安裝媒體上組合所需的元件。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-132">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="0dcbb-133">需要特定版本的 Windows 10，且此版本僅適用于大量授權客戶。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-133">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="0dcbb-134">您可以從大量授權服務中心 [取得副本](https://www.microsoft.com/Licensing/servicecenter/)。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-134">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="0dcbb-135">完成後，請從電腦移除 USB 磁片，然後繼續進行安裝 Windows 10 和 Microsoft Teams 會議室[App。](console.md#Reimage)</span><span class="sxs-lookup"><span data-stu-id="0dcbb-135">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="0dcbb-136">安裝Windows 10主機Microsoft Teams 會議室應用程式</span><span class="sxs-lookup"><span data-stu-id="0dcbb-136">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="0dcbb-137"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="0dcbb-137"><a name="Reimage"> </a></span></span>

<span data-ttu-id="0dcbb-138">您現在必須申請您建立安裝程式的媒體。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-138">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="0dcbb-139">目標裝置會以裝置執行，而預設使用者會設定為只執行Microsoft Teams 會議室應用程式。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-139">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="0dcbb-140">如果目標裝置會安裝在固定 (例如，Surface Pro) ，請將其從固定座中斷連接。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-140">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="0dcbb-141">確定目標裝置未連接至網路。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-141">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="0dcbb-142">確定目標裝置已連接到交流電源。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-142">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="0dcbb-143">將 USB 設定磁片插入目標裝置。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-143">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="0dcbb-144">啟動至 USB 設定磁片。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-144">Boot to the USB setup disk.</span></span> <span data-ttu-id="0dcbb-145">請參閱製造商指示。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-145">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="0dcbb-146">如果您的目標裝置是Surface Pro，請使用下列步驟引導至 USB 設定磁片：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-146">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="0dcbb-147">a.</span><span class="sxs-lookup"><span data-stu-id="0dcbb-147">a.</span></span> <span data-ttu-id="0dcbb-148">按並繼續按住音量 (按鈕) 音量。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-148">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="0dcbb-149">b.</span><span class="sxs-lookup"><span data-stu-id="0dcbb-149">b.</span></span> <span data-ttu-id="0dcbb-150">按並放開電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-150">Press and release the power button.</span></span>

    <span data-ttu-id="0dcbb-151">C。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-151">c.</span></span> <span data-ttu-id="0dcbb-152">啟動Windows設定後，請放開音量 () 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-152">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="0dcbb-153">安裝完成後，系統會關閉。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-153">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="0dcbb-154">系統關閉之後，可以安全地移除 USB 設定磁片。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-154">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="0dcbb-155">此時，您可以使用固定式產品 (，將目標裝置放在其固定位置) 附加會議室所需的周邊設備，然後連接至網路。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-155">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="0dcbb-156">請參閱製造商指示。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-156">Refer to the manufacturer instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="0dcbb-157">系統會自動從 Microsoft Teams 會議室 下載適用于 商務用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-157">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="0dcbb-158">請參閱[商務用 Microsoft Store與教育](/microsoft-store/prerequisites-microsoft-store-for-business)的先決條件，以驗證會議室主控台是否能夠存取儲存空間並自我更新。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-158">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>  

### <a name="selecting-a-language"></a><span data-ttu-id="0dcbb-159">選取語言</span><span class="sxs-lookup"><span data-stu-id="0dcbb-159">Selecting a language</span></span> 

<span data-ttu-id="0dcbb-160">在 Creator 的 Update 中，您必須在隱含語言選擇未提供使用者所需的實際應用程式語言的情況下使用 ApplyCurrentRegionAndLanguage.ps1 腳本 (例如，他們想要以法文顯示主控台應用程式，但即將以英文) 。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-160">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0dcbb-161">下列指示僅適用于使用 Creator 更新Windows的主機。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-161">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="0dcbb-162">尚未使用媒體與新設定系統進行設定的舊式/市集系統將無法使用這些指示，但也應該不會因為需要手動介入的初始問題而受到影響 (Anniversary Edition 讓您在設定) 中明確挑選您的應用程式語言。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-162">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="0dcbb-163">若要使用您想要的語言</span><span class="sxs-lookup"><span data-stu-id="0dcbb-163">To apply your desired language</span></span>

1. <span data-ttu-id="0dcbb-164">切換到系統管理模式。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-164">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="0dcbb-165">選取開始功能表。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-165">Select the Start menu.</span></span>
    
3. <span data-ttu-id="0dcbb-166">選取齒輪圖示以 **啟動設定應用程式**。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-166">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="0dcbb-167">選取 **時間 &amp; 語言**。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-167">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="0dcbb-168">選取 **地區 &amp; 語言**。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-168">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="0dcbb-169">選取 **新增語言**。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-169">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="0dcbb-170">選取要新增的語言。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-170">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="0dcbb-171">選取您剛剛新加入「語言」清單的語言。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-171">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="0dcbb-172">選取 **設定為預設值**。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-172">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="0dcbb-173">針對任何想要移除的語言：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-173">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="0dcbb-174">a.</span><span class="sxs-lookup"><span data-stu-id="0dcbb-174">a.</span></span> <span data-ttu-id="0dcbb-175">選取要移除的語言。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-175">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="0dcbb-176">b.</span><span class="sxs-lookup"><span data-stu-id="0dcbb-176">b.</span></span> <span data-ttu-id="0dcbb-177">選取 **移除**。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-177">Select **Remove**.</span></span>
    
11. <span data-ttu-id="0dcbb-178">啟動提升的命令提示。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-178">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="0dcbb-179">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-179">Run the following command:</span></span> 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="0dcbb-180">重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-180">Restart the system.</span></span>
    
<span data-ttu-id="0dcbb-181">您所需的語言現在會Microsoft Teams 會議室主控台。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-181">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="0dcbb-182">主機的初始設定</span><span class="sxs-lookup"><span data-stu-id="0dcbb-182">Initial set up of the console</span></span>
<span data-ttu-id="0dcbb-183"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="0dcbb-183"><a name="Initial"> </a></span></span>

<span data-ttu-id="0dcbb-184">安裝Windows之後，Microsoft Teams 會議室主機應用程式在下次啟動或已選擇 /重新開機選項時，會進入其初始設定程式。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-184">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="0dcbb-185">系統會顯示使用者帳戶畫面。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-185">The User Account screen appears.</span></span> <span data-ttu-id="0dcbb-186">在Skype中輸入 (user@domain) 帳戶的登錄位址。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-186">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="0dcbb-187">輸入會議室帳戶的密碼，然後重新輸入密碼進行驗證。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-187">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="0dcbb-188">在 「設定網域」下，設定該網域的 FQDN 商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-188">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="0dcbb-189">如果商務用 Skype SIP 網域與使用者Exchange網域不同，請在此欄位中Exchange網域。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-189">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="0dcbb-190">按一下 **[下一步**。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-190">Click **Next**.</span></span>
    
5. <span data-ttu-id="0dcbb-191">在 [功能畫面上選取指示的裝置，然後按一下 [ **下一步**> 。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-191">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="0dcbb-192">預設為將自動螢幕畫面共用設定為 On，而隱藏會議名稱則設為關閉。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-192">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="0dcbb-193">要選取的裝置有：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-193">The devices to select are:</span></span>
    
   - <span data-ttu-id="0dcbb-194">會議用麥克風：此會議室的預設麥克風。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-194">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="0dcbb-195">會議演講者：會議的預設喇叭。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-195">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="0dcbb-196">預設喇叭：用於從 HDMI 輸入音訊的喇叭。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-196">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="0dcbb-197">每個專案都有可選取之選項的下拉式功能表。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-197">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="0dcbb-198">您必須針對每個裝置進行選取。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-198">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="0dcbb-199">按一下 **[完成>**。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-199">Click **Finish**.</span></span>
    
<span data-ttu-id="0dcbb-200">Microsoft Teams 會議室主機應用程式應該會以上述輸入的認證商務用 Skype Server立即開始登錄 商務用 Skype Server，並且也應該使用這些相同的認證開始同步處理其Exchange日曆。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-200">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="0dcbb-201">有關使用主控台應用程式的詳細資訊，請參閱Microsoft Teams 會議室[說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-201">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0dcbb-202">Microsoft Teams 會議室取決於通過認證的主機硬體。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-202">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="0dcbb-203">即使正確建立的圖像包含 Microsoft Teams 會議室主機應用程式，除非偵測到主機硬體，否則不會在初始設定程式之後啟動。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-203">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="0dcbb-204">針對Surface Pro型解決方案，Surface Pro必須連接到其隨附的固定硬體，以通過此檢查。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-204">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0dcbb-205">如果觸控式鍵盤不支援符號，某些非英文使用者可能需要在初始設定期間將實體鍵盤連接到主機。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-205">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="0dcbb-206">在主機上安裝私人 CA 憑證</span><span class="sxs-lookup"><span data-stu-id="0dcbb-206">Install a private CA certificate on the console</span></span>
<span data-ttu-id="0dcbb-207"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="0dcbb-207"><a name="Certs"> </a></span></span>

<span data-ttu-id="0dcbb-208">Microsoft Teams 會議室主機必須信任所連接之伺服器所使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-208">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="0dcbb-209">針對 O365，系統會自動執行這項操作，因為這些伺服器是使用公用憑證頒發機構，而且這些伺服器會自動受到 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-209">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="0dcbb-210">如果憑證頒發機構是私人的，例如使用 Active Directory 和 Windows 憑證頒發機構進行內部部署，您可以用幾種方法將憑證新增到 Microsoft Teams 會議室 主控台：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-210">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="0dcbb-211">您可以將主控台加入 Active Directory，並自動新增所需的憑證，因為憑證頒發機構已發佈至 Active Directory (一般部署選項) 。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-211">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="0dcbb-212">您可以在映射處理之後手動安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-212">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="0dcbb-213">執行此操作之前，您必須完成 [主機的初始設定](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-213">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="0dcbb-214">若要手動安裝憑證</span><span class="sxs-lookup"><span data-stu-id="0dcbb-214">To manually install the certificate</span></span>

1. <span data-ttu-id="0dcbb-215">將 CA 憑證下載至您的電腦，並將其儲存到"C：\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-215">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="0dcbb-216">將主機放在系統管理模式 (請參閱 [系統管理模式和裝置管理](rooms-operations.md#AdminMode)) 。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-216">Place the console in admin mode (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="0dcbb-217">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-217">Run the following command:</span></span>
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="0dcbb-218">加入 Active Directory 網域 (選) </span><span class="sxs-lookup"><span data-stu-id="0dcbb-218">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="0dcbb-219"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="0dcbb-219"><a name="Certs"> </a></span></span>

<span data-ttu-id="0dcbb-220">您可以將主機Microsoft Teams 會議室網域。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-220">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="0dcbb-221">Microsoft Teams 會議室主機應置於與電腦工作站不同的 OU 中，因為許多工作站策略與 Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-221">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="0dcbb-222">常見的範例是密碼強制執行政策，可防止Microsoft Teams 會議室自動啟動。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-222">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="0dcbb-223">如需 GPO 設定管理的資訊，請參閱管理[Microsoft Teams 會議室。](rooms-operations.md)</span><span class="sxs-lookup"><span data-stu-id="0dcbb-223">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](rooms-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="0dcbb-224">若要加入Microsoft Teams 會議室網域</span><span class="sxs-lookup"><span data-stu-id="0dcbb-224">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="0dcbb-225">從系統管理帳戶登錄主機 [ (請參閱系統](rooms-operations.md#AdminMode) 管理模式) 。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-225">Sign into the console from the admin account (see [Admin mode and device management](rooms-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="0dcbb-226">啟動提升的 Powershell 命令提示。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-226">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="0dcbb-227">在 Powershell 中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-227">Enter the following command in Powershell:</span></span>
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="0dcbb-228">例如，如果您的完全合格的網域是 redmond.corp.microsoft.com，而您想要您的 Microsoft Teams 會議室 主機位於 「Microsoft Teams 會議室」 OU 中，且該 OU 為 「資源」OU 的子級，則命令為：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-228">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="0dcbb-229">如果您想要在將電腦加入網域時重新命名，請使用 -NewName 標號，後面接著電腦的新名稱。</span><span class="sxs-lookup"><span data-stu-id="0dcbb-229">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="0dcbb-230">Microsoft Teams 會議室部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="0dcbb-230">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="0dcbb-231"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="0dcbb-231"><a name="Checklist"> </a></span></span>

<span data-ttu-id="0dcbb-232">使用下列檢查清單，同時進行主機及其所有周邊設備已完全配置的驗證：</span><span class="sxs-lookup"><span data-stu-id="0dcbb-232">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="0dcbb-233">**應用程式設定**</span><span class="sxs-lookup"><span data-stu-id="0dcbb-233">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0dcbb-234">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-234">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-235">會議室帳戶名稱和電話 # (PSTN 啟用) 主機畫面右上方正確顯示</span><span class="sxs-lookup"><span data-stu-id="0dcbb-235">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="0dcbb-236">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-236">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-237">Windows正確設定電腦名稱稱 (遠端系統管理) </span><span class="sxs-lookup"><span data-stu-id="0dcbb-237">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="0dcbb-238">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-238">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-239">系統管理員帳戶密碼設定及驗證</span><span class="sxs-lookup"><span data-stu-id="0dcbb-239">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="0dcbb-240">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-240">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-241">已應用所有固件更新</span><span class="sxs-lookup"><span data-stu-id="0dcbb-241">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="0dcbb-242">**音訊/視音訊周邊**</span><span class="sxs-lookup"><span data-stu-id="0dcbb-242">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0dcbb-243">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-243">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-244">若適用，相機外 (固件版本正確) </span><span class="sxs-lookup"><span data-stu-id="0dcbb-244">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="0dcbb-245">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-245">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-246">相機功能與位置最佳</span><span class="sxs-lookup"><span data-stu-id="0dcbb-246">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="0dcbb-247">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-247">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-248">設定預設裝置和播放預設通訊裝置設為預定的音訊外周裝置</span><span class="sxs-lookup"><span data-stu-id="0dcbb-248">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="0dcbb-249">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-249">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-250">設定預設通訊裝置設定為預定的音訊周邊裝置</span><span class="sxs-lookup"><span data-stu-id="0dcbb-250">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="0dcbb-251">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-251">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-252">音訊周邊固件版本正確無誤 (適用) </span><span class="sxs-lookup"><span data-stu-id="0dcbb-252">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="0dcbb-253">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-253">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-254">音訊輸入裝置可運作且位置最佳</span><span class="sxs-lookup"><span data-stu-id="0dcbb-254">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="0dcbb-255">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-255">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-256">音訊輸出裝置可運作且位置最佳</span><span class="sxs-lookup"><span data-stu-id="0dcbb-256">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="0dcbb-257">**碼頭**</span><span class="sxs-lookup"><span data-stu-id="0dcbb-257">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0dcbb-258">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-258">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-259">纜線安全且不會捏合</span><span class="sxs-lookup"><span data-stu-id="0dcbb-259">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="0dcbb-260">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-260">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-261">HDMI 上的音訊輸入功能</span><span class="sxs-lookup"><span data-stu-id="0dcbb-261">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="0dcbb-262">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-262">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-263">在 HDMI 上輸入視像功能</span><span class="sxs-lookup"><span data-stu-id="0dcbb-263">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="0dcbb-264">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-264">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-265">Dock 可以自由旋轉</span><span class="sxs-lookup"><span data-stu-id="0dcbb-265">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="0dcbb-266">☐</span><span class="sxs-lookup"><span data-stu-id="0dcbb-266">☐</span></span>  <br/> |<span data-ttu-id="0dcbb-267">環境可接受顯示亮度</span><span class="sxs-lookup"><span data-stu-id="0dcbb-267">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0dcbb-268">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0dcbb-268">See also</span></span>
<span data-ttu-id="0dcbb-269"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="0dcbb-269"><a name="Checklist"> </a></span></span>

[<span data-ttu-id="0dcbb-270">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="0dcbb-270">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="0dcbb-271">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="0dcbb-271">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="0dcbb-272">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="0dcbb-272">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="0dcbb-273">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="0dcbb-273">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)