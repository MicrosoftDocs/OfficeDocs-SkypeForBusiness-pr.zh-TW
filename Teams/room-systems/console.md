---
title: 設定 Microsoft 團隊聊天室主控台
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 本文說明如何設定 Microsoft 團隊聊天室主控台及其外設。
ms.openlocfilehash: 1bb1e45eca95628222b799d94c953bb49da1ea17
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243473"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a><span data-ttu-id="a0d4a-103">設定 Microsoft 團隊聊天室主控台</span><span class="sxs-lookup"><span data-stu-id="a0d4a-103">Configure a Microsoft Teams Rooms console</span></span>

<span data-ttu-id="a0d4a-104">本文說明如何設定 Microsoft 團隊聊天室主控台及其外設。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-104">This article describes how to set up the Microsoft Teams Rooms console and its peripherals.</span></span>
  
<span data-ttu-id="a0d4a-105">如果已建立並測試必要的 Microsoft 團隊或商務用 Skype 與 Exchange 帳戶, 請依照[部署 Microsoft 團隊聊天室](room-systems-v2.md)中的說明, 只需執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-105">You should only perform these steps if the necessary Microsoft Teams or Skype for Business and Exchange accounts have already been created and tested as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span> <span data-ttu-id="a0d4a-106">您將需要[Microsoft 團隊會議室需求](requirements.md)中所述的硬體和軟體。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-106">You will need the hardware and software described in [Microsoft Teams Rooms requirements](requirements.md).</span></span> <span data-ttu-id="a0d4a-107">本主題包含下列各節:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-107">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="a0d4a-108">準備安裝媒體</span><span class="sxs-lookup"><span data-stu-id="a0d4a-108">Prepare the installation media</span></span>](console.md#Prep_Media)
- [<span data-ttu-id="a0d4a-109">在主控台上安裝私人 CA 憑證</span><span class="sxs-lookup"><span data-stu-id="a0d4a-109">Install a private CA certificate on the console</span></span>](console.md#Certs)
- [<span data-ttu-id="a0d4a-110">安裝 Windows 10 和 Microsoft 團隊聊天室主控台應用程式</span><span class="sxs-lookup"><span data-stu-id="a0d4a-110">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>](console.md#Reimage)
- [<span data-ttu-id="a0d4a-111">主機的初始設定</span><span class="sxs-lookup"><span data-stu-id="a0d4a-111">Initial set up of the console</span></span>](console.md#Initial)
- [<span data-ttu-id="a0d4a-112">Microsoft 團隊聊天室部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="a0d4a-112">Microsoft Teams Rooms deployment checklist</span></span>](console.md#Checklist)

> [!NOTE]
> <span data-ttu-id="a0d4a-113">Microsoft 團隊聊天室只能在設定正確的 Microsoft 團隊或商務用 Skype 環境中運作, 如[部署 Microsoft 團隊聊天室](room-systems-v2.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-113">Microsoft Teams Rooms will only work in a properly configured Microsoft Teams or Skype for Business environment where the device accounts are set up correctly as described in [Deploy Microsoft Teams Rooms](room-systems-v2.md).</span></span>
  
## <a name="prepare-the-installation-media"></a><span data-ttu-id="a0d4a-114">準備安裝媒體</span><span class="sxs-lookup"><span data-stu-id="a0d4a-114">Prepare the installation media</span></span>
<span data-ttu-id="a0d4a-115"><a name="Prep_Media"> </a></span><span class="sxs-lookup"><span data-stu-id="a0d4a-115"></span></span>

<span data-ttu-id="a0d4a-116">安裝 Microsoft 團隊聊天室主控台 app 需要至少32GB 容量的 USB 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-116">Installing the Microsoft Teams Rooms console app requires a USB storage device with at least 32GB of capacity.</span></span> <span data-ttu-id="a0d4a-117">裝置上不應有任何其他檔案;USB 儲存空間中的任何現有檔案將會遺失。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-117">There should be no other files on the device; any existing files on the USB storage will be lost.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0d4a-118">無法根據這些指示建立您的 Microsoft 團隊會議室安裝媒體, 可能會導致意外的行為。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-118">Failure to create your Microsoft Teams Rooms installation media according to these instructions will likely result in unexpected behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="a0d4a-119">下列程式適用于建立安裝媒體至影像新的 Microsoft 團隊聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-119">The process below is for creating installation media to image new Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="a0d4a-120">根據預設, 現有的裝置會自動從 Windows Update 和 Windows 市集中更新。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-120">Existing devices, by default, update automatically from Windows Update and the Windows Store.</span></span>
  
1. <span data-ttu-id="a0d4a-121">下載[CreateSrsMedia. ps1 腳本](https://go.microsoft.com/fwlink/?linkid=867842)。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-121">Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).</span></span>
2. <span data-ttu-id="a0d4a-122">從 Windows 10 電腦上的提升提示執行 CreateSrsMedia 腳本。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-122">Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows 10 machine.</span></span>
3. <span data-ttu-id="a0d4a-123">遵循腳本的指示來建立 Microsoft 團隊聊天室 USB 安裝盤。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-123">Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.</span></span>


> [!TIP]
> <span data-ttu-id="a0d4a-124">每次 CreateSrsMedia 腳本啟動時, 畫面輸出都會包含會話的記錄檔案名稱或記錄名。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-124">Each time the CreateSrsMedia.ps1 script starts, the screen output will include the name of a log file or transcript for the session.</span></span> <span data-ttu-id="a0d4a-125">如果執行腳本時發生問題, 請務必在要求支援時提供該記錄的複本。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-125">If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.</span></span> 

<span data-ttu-id="a0d4a-126">CreateSrsMedia. ps1 腳本會自動執行下列任務:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-126">The CreateSrsMedia.ps1 script automates the following tasks:</span></span>

1. <span data-ttu-id="a0d4a-127">下載適用于 Microsoft 團隊聊天室的最新 MSI 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-127">Download the latest MSI installer for Microsoft Teams Rooms.</span></span>
2. <span data-ttu-id="a0d4a-128">決定使用者必須提供的 Windows 組建。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-128">Determine the build of Windows that the user must supply.</span></span> <span data-ttu-id="a0d4a-129">最近發行的版本可能與或不受測試, 而且不支援與 Microsoft 團隊聊天室裝置搭配使用。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-129">The most recently released versions may or may not be tested and supported for use with Microsoft Teams Rooms devices.</span></span>
3. <span data-ttu-id="a0d4a-130">下載必要的支援元件。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-130">Download necessary supporting components.</span></span>
4. <span data-ttu-id="a0d4a-131">在安裝媒體上組裝所需的元件。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-131">Assemble the needed components on the installation media.</span></span>

<span data-ttu-id="a0d4a-132">需要 Windows 10 的特定版本, 而且這個版本只提供大量授權客戶。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-132">A specific version of Windows 10 is required, and this version is only available to volume licensing customers.</span></span>  <span data-ttu-id="a0d4a-133">您可以從[大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/)取得複本。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-133">You can get a copy from the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).</span></span>

<span data-ttu-id="a0d4a-134">完成後, 請從您的電腦中移除 USB 磁片, 然後繼續[安裝 Windows 10 和 Microsoft 團隊聊天室主控台 app](console.md#Reimage)。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-134">When finished, remove the USB disk from your computer and proceed to [Install Windows 10 and the Microsoft Teams Rooms console app](console.md#Reimage).</span></span>

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a><span data-ttu-id="a0d4a-135">安裝 Windows 10 和 Microsoft 團隊聊天室主控台應用程式</span><span class="sxs-lookup"><span data-stu-id="a0d4a-135">Install Windows 10 and the Microsoft Teams Rooms console app</span></span>
<span data-ttu-id="a0d4a-136"><a name="Reimage"> </a></span><span class="sxs-lookup"><span data-stu-id="a0d4a-136"></span></span>

<span data-ttu-id="a0d4a-137">您現在必須套用您所建立的安裝媒體。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-137">You now need to apply the setup media you've created.</span></span> <span data-ttu-id="a0d4a-138">目標裝置將會以裝置的方式執行, 而且預設使用者將會設定為只執行 Microsoft 團隊聊天室主控台 app。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-138">The target device will run as an appliance and the default user will be set to only run the Microsoft Teams Rooms console app.</span></span>

1. <span data-ttu-id="a0d4a-139">如果目標裝置將會安裝在 dock 中 (例如 Surface Pro), 請將它從 dock 中中斷。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-139">If the target device will be installed in a dock (e.g., a Surface Pro), disconnect it from the dock.</span></span>

2. <span data-ttu-id="a0d4a-140">確定目標裝置未連線至網路。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-140">Ensure the target device is not connected to the network.</span></span>

3. <span data-ttu-id="a0d4a-141">確定目標裝置已連線至交流電源。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-141">Ensure the target device is connected to AC power.</span></span>

4. <span data-ttu-id="a0d4a-142">將 USB 安裝盤插入目標裝置。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-142">Plug your USB setup disk into the target device.</span></span>

5. <span data-ttu-id="a0d4a-143">啟動至 USB 安裝盤。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-143">Boot to the USB setup disk.</span></span> <span data-ttu-id="a0d4a-144">請參閱製造商的指示。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-144">Refer to the manufacturer instructions.</span></span> <span data-ttu-id="a0d4a-145">如果您的目標裝置是 Surface Pro, 請使用下列步驟引導至 USB 安裝盤:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-145">If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:</span></span>

    <span data-ttu-id="a0d4a-146">是.</span><span class="sxs-lookup"><span data-stu-id="a0d4a-146">a.</span></span> <span data-ttu-id="a0d4a-147">按下並持續按住音量 (-) 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-147">Press and continue to hold the volume down (-) button.</span></span>

    <span data-ttu-id="a0d4a-148">乙.</span><span class="sxs-lookup"><span data-stu-id="a0d4a-148">b.</span></span> <span data-ttu-id="a0d4a-149">按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-149">Press and release the power button.</span></span>

    <span data-ttu-id="a0d4a-150">c-clip.</span><span class="sxs-lookup"><span data-stu-id="a0d4a-150">c.</span></span> <span data-ttu-id="a0d4a-151">啟動 Windows 安裝程式後, 請放開 volume (-) 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-151">Once Windows setup is booted, release the volume down (-) button.</span></span>

8. <span data-ttu-id="a0d4a-152">安裝完成後, 系統會關閉。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-152">The system will shut down once installation is complete.</span></span>
    
<span data-ttu-id="a0d4a-153">系統關閉之後, 就可以安全地移除 USB 安裝盤了。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-153">After the system has shut down, it is safe to remove the USB setup disk.</span></span> <span data-ttu-id="a0d4a-154">此時, 您可以將目標裝置放在它的 dock 中 (如果使用的是 dock 產品), 附加會議室所需的外設, 然後連線到網路。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-154">At this point, you can place the target device in its dock (if using a dock-based product), attach the peripherals needed for your meeting room, and connect to the network.</span></span> <span data-ttu-id="a0d4a-155">請參閱製造商的指示。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-155">Refer to the manufacturer instructions.</span></span>
  
### <a name="selecting-a-language"></a><span data-ttu-id="a0d4a-156">選取語言</span><span class="sxs-lookup"><span data-stu-id="a0d4a-156">Selecting a language</span></span> 

<span data-ttu-id="a0d4a-157">在建立者的更新中, 當隱含語言選取不提供使用者所需的實際應用程式語言 (例如, 他們想要讓主控台 app 以法文進行) 時, 您必須使用 ApplyCurrentRegionAndLanguage. ps1 腳本 (也就是它會以英文提供。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-157">In Creator's Update, you will need to use the ApplyCurrentRegionAndLanguage.ps1 script in scenarios where implicit language selection does not provide the user with the actual application language they want (e.g., they want the console app to come up in French, but it's coming up in English).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0d4a-158">下列指示僅適用于使用 Windows Creator 更新程式建立的主控台。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-158">The following instructions work only for consoles created using Windows Creator's Update.</span></span> <span data-ttu-id="a0d4a-159">未使用新置備系統的媒體進行設定的舊版/內建系統將無法使用這些指示, 但也不會受到需要此手動干預的初始問題 (周年紀念版本可讓您挑選在安裝程式中明確地做為應用程式語言。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-159">Legacy/in-market systems that have not been set up using media with the new provisioning system will not be able to use these instructions, but should also not suffer from the initial issue that requires this manual intervention (Anniversary Edition let you pick your app language explicitly as part of setup).</span></span>
  
### <a name="to-apply-your-desired-language"></a><span data-ttu-id="a0d4a-160">若要套用您想要的語言</span><span class="sxs-lookup"><span data-stu-id="a0d4a-160">To apply your desired language</span></span>

1. <span data-ttu-id="a0d4a-161">切換到 [管理員模式]。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-161">Switch to Admin mode.</span></span>
    
2. <span data-ttu-id="a0d4a-162">選取 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-162">Select the Start menu.</span></span>
    
3. <span data-ttu-id="a0d4a-163">選取齒輪圖示以啟動 [**設定**] app。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-163">Select the gear icon to launch the **Settings** app.</span></span>
    
4. <span data-ttu-id="a0d4a-164">選取 **[ &amp;時間語言**]。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-164">Select **Time &amp; language**.</span></span>
    
5. <span data-ttu-id="a0d4a-165">選取 **[ &amp;地區語言**]。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-165">Select **Region &amp; language**.</span></span>
    
6. <span data-ttu-id="a0d4a-166">選取 [**新增語言**]。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-166">Select **Add a language**.</span></span>
    
7. <span data-ttu-id="a0d4a-167">選取您想要新增的語言。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-167">Select the language you wish to add.</span></span>
    
8. <span data-ttu-id="a0d4a-168">選取您剛才新增至 [語言] 清單的語言。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-168">Select the language you just added to the "Languages" list.</span></span>
    
9. <span data-ttu-id="a0d4a-169">選取 [**設成預設值**]。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-169">Select **Set as default**.</span></span>
    
10. <span data-ttu-id="a0d4a-170">針對您想要移除的任何語言:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-170">For any languages you wish to remove:</span></span>
    
    <span data-ttu-id="a0d4a-171">是.</span><span class="sxs-lookup"><span data-stu-id="a0d4a-171">a.</span></span> <span data-ttu-id="a0d4a-172">選取您要移除的語言。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-172">Select the language you wish to remove.</span></span>
    
    <span data-ttu-id="a0d4a-173">乙.</span><span class="sxs-lookup"><span data-stu-id="a0d4a-173">b.</span></span> <span data-ttu-id="a0d4a-174">選取 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-174">Select **Remove**.</span></span>
    
11. <span data-ttu-id="a0d4a-175">啟動提升許可權的命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-175">Start an elevated command prompt.</span></span>
    
12. <span data-ttu-id="a0d4a-176">執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-176">Run the following command:</span></span> 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. <span data-ttu-id="a0d4a-177">重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-177">Restart the system.</span></span>
    
<span data-ttu-id="a0d4a-178">您想要的語言現在已套用至 Microsoft 團隊聊天室主控台。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-178">Your desired language is now applied to the Microsoft Teams Rooms console.</span></span>
## <a name="initial-set-up-of-the-console"></a><span data-ttu-id="a0d4a-179">主機的初始設定</span><span class="sxs-lookup"><span data-stu-id="a0d4a-179">Initial set up of the console</span></span>
<span data-ttu-id="a0d4a-180"><a name="Initial"> </a></span><span class="sxs-lookup"><span data-stu-id="a0d4a-180"></span></span>

<span data-ttu-id="a0d4a-181">安裝 Windows 之後, 當您下一次啟動或選取 [/reboot] 選項時, Microsoft [小組聊天室] 主控台 app 就會進入初始設定處理常式。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-181">After Windows is installed, the Microsoft Teams Rooms console app will go into its initial Setup process when it is started next or if the /reboot option was chosen.</span></span>
  
1. <span data-ttu-id="a0d4a-182">[使用者帳戶] 畫面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-182">The User Account screen appears.</span></span> <span data-ttu-id="a0d4a-183">輸入要與主機搭配使用之房間帳戶的 Skype 登入位址 (以使用者 @ 網域格式)。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-183">Enter the Skype sign-in address (in user@domain format) of the room account to be used with the console.</span></span>
    
2. <span data-ttu-id="a0d4a-184">輸入房間帳戶的密碼, 然後重新輸入以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-184">Enter the password for the room account, and re-enter it to verify.</span></span>
    
3. <span data-ttu-id="a0d4a-185">在 [設定網域] 底下, 設定商務用 Skype Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-185">Under "Configure Domain," set the FQDN for the Skype for Business Server.</span></span> <span data-ttu-id="a0d4a-186">如果商務用 Skype SIP 網域與使用者的 Exchange 網域不同, 請在此欄位中輸入 Exchange 網域。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-186">If the Skype for Business SIP domain is different from the Exchange domain of the user, enter the Exchange domain in this field.</span></span>
    
4. <span data-ttu-id="a0d4a-187">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-187">Click **Next**.</span></span>
    
5. <span data-ttu-id="a0d4a-188">在 [功能] 畫面上選取所指示的裝置, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-188">Select the indicated devices on the Features screen and click **Next**.</span></span> <span data-ttu-id="a0d4a-189">預設值是將 [自動螢幕共用] 設定為 [開啟], 並隱藏會議名稱設定為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-189">The default is to have Auto Screen sharing set to On and Hide meeting names set to Off.</span></span> <span data-ttu-id="a0d4a-190">要選取的裝置包括:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-190">The devices to select are:</span></span>
    
   - <span data-ttu-id="a0d4a-191">會議麥克風: 此會議室的預設麥克風。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-191">Microphone for Conferencing: the default microphone for this conference room.</span></span>
    
   - <span data-ttu-id="a0d4a-192">會議的演講者: 會議的預設喇叭。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-192">Speaker for Conferencing: the default speaker for conferencing.</span></span> 
    
   - <span data-ttu-id="a0d4a-193">預設喇叭: 從 HDMI 接收音訊所用的喇叭。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-193">Default Speaker: the speaker used for audio from the HDMI ingest.</span></span>
    
     <span data-ttu-id="a0d4a-194">每個專案都有下拉式清單, 其中包含選取的選項。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-194">Each item has a drop-down menu of options to select from.</span></span> <span data-ttu-id="a0d4a-195">您必須為每個裝置進行選取。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-195">You must make a selection for each device.</span></span>
    
6. <span data-ttu-id="a0d4a-196">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-196">Click **Finish**.</span></span>
    
<span data-ttu-id="a0d4a-197">Microsoft [團隊聊天室] 主控台 app 應該會立即開始使用上述輸入的認證來登入商務用 Skype Server, 也應該使用相同的認證開始與 Exchange 同步處理其行事曆。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-197">The Microsoft Teams Rooms console app should immediately start signing in to Skype for Business Server with the credentials entered above, and should also begin syncing its calendar with Exchange using those same credentials.</span></span> <span data-ttu-id="a0d4a-198">如需使用主控台 app 的詳細資料, 請參閱[Microsoft 團隊聊天室](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)說明。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-198">For details on using the console app, refer to the [Microsoft Teams Rooms help](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a0d4a-199">Microsoft 團隊聊天室會依賴已認證的主控台硬體是否存在。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-199">Microsoft Teams Rooms relies on the presence of certified console hardware.</span></span> <span data-ttu-id="a0d4a-200">即使有正確建立的包含 Microsoft 團隊聊天室主控台應用程式的影像, 也不會超過初始設定程式 (除非偵測到主控台硬體), 否則不會啟動。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-200">Even a correctly created image containing the Microsoft Teams Rooms console app will not boot past the initial setup procedure unless the console hardware is detected.</span></span> <span data-ttu-id="a0d4a-201">針對 Surface Pro 解決方案, Surface Pro 必須連線至其隨附的 dock 硬體, 才能傳送此檢查。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-201">For Surface Pro based solutions, the Surface Pro must be connected to its accompanying dock hardware to pass this check.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0d4a-202">某些非英文語言的使用者在初始設定期間, 可能需要有一個與主機連接的物理鍵盤, 在觸控式鍵盤上不支援此符號。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-202">Some non-English language users may need a physical keyboard connected to the console during initial setup in the event that symbols are not supported on the touch keyboard.</span></span>
  
### <a name="install-a-private-ca-certificate-on-the-console"></a><span data-ttu-id="a0d4a-203">在主控台上安裝私人 CA 憑證</span><span class="sxs-lookup"><span data-stu-id="a0d4a-203">Install a private CA certificate on the console</span></span>
<span data-ttu-id="a0d4a-204"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="a0d4a-204"></span></span>

<span data-ttu-id="a0d4a-205">Microsoft [小組聊天室] 主控台需要信任其所連接之伺服器所使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-205">The Microsoft Teams Rooms console needs to trust the certificates used by the servers it connects to.</span></span> <span data-ttu-id="a0d4a-206">針對 O365, 這會自動完成, 因為這些伺服器使用的是公用憑證授權單位, 且這些伺服器會自動受 Windows 10 信任。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-206">For O365 this is done automatically, since these servers are using public Certificate Authorities and these are automatically trusted by Windows 10.</span></span> <span data-ttu-id="a0d4a-207">在憑證授權單位是私人的情況下 (例如, 內部部署與 Active Directory 和 Windows Certificate 機關), 您可以使用下列幾種方式將憑證新增到 Microsoft 團隊聊天室主控台:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-207">In a case where the Certificate Authority is private, for instance an on-premises deployment with Active Directory and the Windows Certificate Authority, you can add the certificate to the Microsoft Teams Rooms console in a couple of ways:</span></span>
  
- <span data-ttu-id="a0d4a-208">您可以將主機加入 Active Directory, 而且會自動將給定憑證授權單位所需的憑證發佈至 Active Directory (標準部署選項)。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-208">You can join the console to Active Directory and that will automatically add the required certificates given the Certificate Authority is published to Active Directory (normal deployment option).</span></span>
    
- <span data-ttu-id="a0d4a-209">您可以在影像處理常式之後, 手動安裝證書。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-209">You can install the certificate manually after the imaging process.</span></span> <span data-ttu-id="a0d4a-210">在執行此動作之前, 您必須先完成主機[的初始設定](console.md#Initial)。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-210">Before you do this, you must complete [Initial set up of the console](console.md#Initial).</span></span>
    
### <a name="to-manually-install-the-certificate"></a><span data-ttu-id="a0d4a-211">手動安裝憑證</span><span class="sxs-lookup"><span data-stu-id="a0d4a-211">To manually install the certificate</span></span>

1. <span data-ttu-id="a0d4a-212">將 CA 憑證下載到您的電腦, 並將它儲存到 [C:\Skype 聊天室 Systems\x64\Scripts\Provisioning\CAcertificate.cer]。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-212">Download the CA certificate to your computer and save it to "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".</span></span>
    
2. <span data-ttu-id="a0d4a-213">將主機置於 [系統管理] 模式 (請參閱 [[管理員模式] 和 [裝置管理]](room-systems-v2-operations.md#AdminMode))。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-213">Place the console in admin mode (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
3. <span data-ttu-id="a0d4a-214">執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-214">Run the following command:</span></span>
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a><span data-ttu-id="a0d4a-215">加入 Active Directory 網域 (選用)</span><span class="sxs-lookup"><span data-stu-id="a0d4a-215">Join an Active Directory domain (Optional)</span></span>
<span data-ttu-id="a0d4a-216"><a name="Certs"> </a></span><span class="sxs-lookup"><span data-stu-id="a0d4a-216"></span></span>

<span data-ttu-id="a0d4a-217">您可以將 Microsoft 團隊聊天室主控台加入您的網域。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-217">You can join Microsoft Teams Rooms consoles to your domain.</span></span> <span data-ttu-id="a0d4a-218">Microsoft 團隊聊天室主控台應該與電腦工作站放在不同的 OU 中, 因為許多工作站原則都不與 Microsoft 團隊聊天室相容。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-218">Microsoft Teams Rooms consoles should be placed in a separate OU from your PC workstations because many workstation policies are not compatible with Microsoft Teams Rooms.</span></span> <span data-ttu-id="a0d4a-219">常見的範例是密碼強制原則, 可避免 Microsoft 團隊聊天室自動啟動。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-219">A common example are password enforcement policies that will prevent Microsoft Teams Rooms from starting up automatically.</span></span> <span data-ttu-id="a0d4a-220">如需管理 GPO 設定的相關資訊, 請參閱[管理 Microsoft 團隊聊天室](room-systems-v2-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-220">For information about the management of GPO settings, please refer to [Manage Microsoft Teams Rooms](room-systems-v2-operations.md).</span></span>
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a><span data-ttu-id="a0d4a-221">將 Microsoft 團隊聊天室加入網域</span><span class="sxs-lookup"><span data-stu-id="a0d4a-221">To join Microsoft Teams Rooms to a domain</span></span>

1. <span data-ttu-id="a0d4a-222">從系統管理員帳戶登入主機 (請參閱系統管理[模式和裝置管理](room-systems-v2-operations.md#AdminMode))。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-222">Sign into the console from the admin account (see [Admin mode and device management](room-systems-v2-operations.md#AdminMode)).</span></span>
    
2. <span data-ttu-id="a0d4a-223">啟動提升的 Powershell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-223">Launch elevated Powershell command prompt.</span></span>
    
3. <span data-ttu-id="a0d4a-224">在 Powershell 中輸入下列命令:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-224">Enter the following command in Powershell:</span></span>
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

<span data-ttu-id="a0d4a-225">例如, 如果您的完整網域是 redmond.corp.microsoft.com, 而您想要將 Microsoft 團隊聊天室主控台放在作為「資源」 OU 子級的「Microsoft 球隊聊天室」 OU 中, 則此命令將會是:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-225">For example, if your fully qualified domain is redmond.corp.microsoft.com and you want your Microsoft Teams Rooms consoles to be in a "Microsoft Teams Rooms" OU that is a child of a "Resources" OU, the command will be:</span></span>
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 <span data-ttu-id="a0d4a-226">如果您想要在將電腦加入網域時重新命名, 請使用-NewName 標誌, 後面接著電腦的新名稱。</span><span class="sxs-lookup"><span data-stu-id="a0d4a-226">If you would like to rename the computer when joining it to a domain, use the -NewName flag followed by the computer's new name.</span></span>
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a><span data-ttu-id="a0d4a-227">Microsoft 團隊聊天室部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="a0d4a-227">Microsoft Teams Rooms deployment checklist</span></span>
<span data-ttu-id="a0d4a-228"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="a0d4a-228"></span></span>

<span data-ttu-id="a0d4a-229">在執行最終驗證時, 請使用下列檢查清單, 並對所有週邊設備進行完整的設定:</span><span class="sxs-lookup"><span data-stu-id="a0d4a-229">Use the following checklist while doing a final verification that the console and all its peripherals are fully configured:</span></span>
  
<span data-ttu-id="a0d4a-230">**應用程式設定**</span><span class="sxs-lookup"><span data-stu-id="a0d4a-230">**Application settings**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a0d4a-231">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-231">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-232">在主控台畫面右上方能正確顯示房間帳戶名稱和電話 # (如果 PSTN 啟用)</span><span class="sxs-lookup"><span data-stu-id="a0d4a-232">Room account name and phone # (if PSTN enabled) are correctly displayed in top right of console screen</span></span>  <br/> |
|<span data-ttu-id="a0d4a-233">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-233">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-234">Windows 電腦名稱稱設定正確 (適用于遠端系統管理)</span><span class="sxs-lookup"><span data-stu-id="a0d4a-234">Windows computer name is set correctly (useful for remote administration)</span></span>  <br/> |
|<span data-ttu-id="a0d4a-235">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-235">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-236">已設定並驗證管理員帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="a0d4a-236">Administrator account password set and verified</span></span>  <br/> |
|<span data-ttu-id="a0d4a-237">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-237">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-238">已套用所有的固件更新</span><span class="sxs-lookup"><span data-stu-id="a0d4a-238">All firmware updates have been applied</span></span>  <br/> |
   
<span data-ttu-id="a0d4a-239">**音訊/視頻外設**</span><span class="sxs-lookup"><span data-stu-id="a0d4a-239">**Audio/video peripherals**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a0d4a-240">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-240">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-241">相機週邊版固件版本正確 (如果適用的話)</span><span class="sxs-lookup"><span data-stu-id="a0d4a-241">Camera peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="a0d4a-242">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-242">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-243">相機功能和定位最佳</span><span class="sxs-lookup"><span data-stu-id="a0d4a-243">Camera functional and positioned optimally</span></span>  <br/> |
|<span data-ttu-id="a0d4a-244">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-244">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-245">[播放預設裝置] 和 [播放預設通訊裝置] 設定設為預期音訊外設的設定</span><span class="sxs-lookup"><span data-stu-id="a0d4a-245">Settings for Playback Default Device and Playback Default Communications Device set to intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="a0d4a-246">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-246">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-247">錄製預設通訊裝置設定為預期音訊外設的設定</span><span class="sxs-lookup"><span data-stu-id="a0d4a-247">Settings for Recording Default Communication Device set to the intended audio peripheral</span></span>  <br/> |
|<span data-ttu-id="a0d4a-248">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-248">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-249">音訊週邊版固件版本正確 (如果適用的話)</span><span class="sxs-lookup"><span data-stu-id="a0d4a-249">Audio peripheral firmware version is correct (if applicable)</span></span>  <br/> |
|<span data-ttu-id="a0d4a-250">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-250">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-251">音訊輸入裝置功能與最佳位置</span><span class="sxs-lookup"><span data-stu-id="a0d4a-251">Audio input device functional and optimally positioned</span></span>  <br/> |
|<span data-ttu-id="a0d4a-252">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-252">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-253">音訊輸出裝置功能與最佳位置</span><span class="sxs-lookup"><span data-stu-id="a0d4a-253">Audio output device functional and optimally positioned</span></span>  <br/> |
   
<span data-ttu-id="a0d4a-254">**進貨**</span><span class="sxs-lookup"><span data-stu-id="a0d4a-254">**Dock**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a0d4a-255">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-255">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-256">纜線安全且無法 pinched</span><span class="sxs-lookup"><span data-stu-id="a0d4a-256">Cables are secure and not pinched</span></span>  <br/> |
|<span data-ttu-id="a0d4a-257">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-257">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-258">在 HDMI 上的音訊攝取功能正常運作</span><span class="sxs-lookup"><span data-stu-id="a0d4a-258">Audio ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="a0d4a-259">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-259">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-260">在 HDMI 上的影片接收功能正常運作</span><span class="sxs-lookup"><span data-stu-id="a0d4a-260">Video ingest over HDMI is functional</span></span>  <br/> |
|<span data-ttu-id="a0d4a-261">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-261">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-262">固定塢可自由旋轉</span><span class="sxs-lookup"><span data-stu-id="a0d4a-262">Dock can swivel freely</span></span>  <br/> |
|<span data-ttu-id="a0d4a-263">☐</span><span class="sxs-lookup"><span data-stu-id="a0d4a-263">☐</span></span>  <br/> |<span data-ttu-id="a0d4a-264">環境可接受顯示器亮度</span><span class="sxs-lookup"><span data-stu-id="a0d4a-264">Display brightness is acceptable for environment</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a0d4a-265">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a0d4a-265">See also</span></span>
<span data-ttu-id="a0d4a-266"><a name="Checklist"> </a></span><span class="sxs-lookup"><span data-stu-id="a0d4a-266"></span></span>

[<span data-ttu-id="a0d4a-267">規劃 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="a0d4a-267">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="a0d4a-268">部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="a0d4a-268">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="a0d4a-269">設定 Microsoft 團隊聊天室主控台</span><span class="sxs-lookup"><span data-stu-id="a0d4a-269">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="a0d4a-270">管理 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="a0d4a-270">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
