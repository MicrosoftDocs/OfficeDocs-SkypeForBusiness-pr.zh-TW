---
title: 使用商務用 Skype Server 部署 Lync VDI 外掛程式
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: 本主題討論在連線至遠端虛擬桌面時, 使用商務用 Skype 的部署程式。
ms.openlocfilehash: 8892bf8b8772bdb301f914bca134d61e67ea934b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234401"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="a890a-103">使用商務用 Skype Server 部署 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="a890a-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="a890a-104">本主題討論在連線至遠端虛擬桌面時, 使用商務用 Skype 的部署程式。</span><span class="sxs-lookup"><span data-stu-id="a890a-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="a890a-105">規劃[針對 VDI 環境中的商務用 Skype](../../plan-your-deployment/clients-and-devices/vdi-environments.md)規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="a890a-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="a890a-106">虛擬桌面基礎結構 (VDI) 環境是在安全性與合規性問題特別敏感的一些組織中使用。</span><span class="sxs-lookup"><span data-stu-id="a890a-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="a890a-107">其使用者位於本機 Windows 電腦上, 且使用虛擬機器上的用戶端。</span><span class="sxs-lookup"><span data-stu-id="a890a-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="a890a-108">在需要額外 VDI 外掛程式軟體的連線上使用商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="a890a-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="a890a-109">VDI 外掛程式元件 (由 Microsoft 提供並由 Citrix 提供) 提供兩種方案。</span><span class="sxs-lookup"><span data-stu-id="a890a-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="a890a-110">Microsoft 建議您在新的部署中使用新的 HDX 即時優化套件方案, 但仍會繼續支援原始的 Lync VDI 外掛程式, 以供其生命週期的剩餘部分使用。</span><span class="sxs-lookup"><span data-stu-id="a890a-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="a890a-111">本主題提供有關部署 Microsoft Lync VDI 外掛程式的詳細資料, 該外掛程式只支援 Windows 7 和 Windows 8 或 Windows Server 2008, 且只支援 Lync 2013 或商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a890a-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="a890a-112">沒有任何方案可用於更新此外掛程式, 但商務用 Skype 的[CITRIX HDX 即時優化套件](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)會視需要更新。</span><span class="sxs-lookup"><span data-stu-id="a890a-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="a890a-113">為 Lync VDI 外掛程式準備您的環境</span><span class="sxs-lookup"><span data-stu-id="a890a-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="a890a-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="a890a-114"></span></span>

1. <span data-ttu-id="a890a-115">在商務用 Skype Server 中, 確保所有 Lync VDI 外掛程式使用者的 EnableMediaRedirection 都設定為 TRUE。</span><span class="sxs-lookup"><span data-stu-id="a890a-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="a890a-116">如需詳細資訊, 請參閱[新版 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) Cmdlet 和[CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="a890a-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="a890a-117">在資料中心伺服器上, 在所有虛擬機器上安裝商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a890a-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="a890a-118">在本機電腦上, 安裝 Lync VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a890a-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="a890a-119">使用者現在應該將耳機或網路攝像頭等裝置連線至他們的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="a890a-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="a890a-120">設定遠端桌面連線設定</span><span class="sxs-lookup"><span data-stu-id="a890a-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="a890a-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="a890a-121"></span></span>

<span data-ttu-id="a890a-122">若要準備 Lync VDI 外掛程式的遠端桌面連線, 請在本機電腦上執行下列步驟:</span><span class="sxs-lookup"><span data-stu-id="a890a-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="a890a-123">如果本機電腦執行的是 Windows 8, 請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="a890a-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="a890a-124">如果本機電腦執行的是 Windows 7 與 SP1, 請安裝最新的 Windows 8 版本的[遠端桌面服務用戶端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。</span><span class="sxs-lookup"><span data-stu-id="a890a-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="a890a-125">按一下 [**開始**], 然後按一下 [**遠端桌面**連線], 啟動遠端桌面服務用戶端。</span><span class="sxs-lookup"><span data-stu-id="a890a-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="a890a-126">按一下 [**選項**]。</span><span class="sxs-lookup"><span data-stu-id="a890a-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="a890a-127">按一下 [**本機資源**] 索引標籤。在 [**遠端音訊**] 底下, 按一下 [**設定**], 然後執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="a890a-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="a890a-128">在 [**遠端音訊播放**] 底下, 選取 [**在這台電腦上播放**]。</span><span class="sxs-lookup"><span data-stu-id="a890a-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="a890a-129">在 [**遠端音訊錄製**] 底下, 選取 [不**錄製**]。</span><span class="sxs-lookup"><span data-stu-id="a890a-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="a890a-130">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a890a-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="a890a-131">按一下 [**體驗**] 索引標籤。在 [**效能**] 底下, 清除 [**永久點陣圖緩存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a890a-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="a890a-132">按一下 [**一般**] 索引標籤。在 [**電腦**] 中, 輸入虛擬機器的名稱, 然後按一下 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="a890a-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="a890a-133">在虛擬機器上登入並使用商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="a890a-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="a890a-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="a890a-134"></span></span>

<span data-ttu-id="a890a-135">啟用 Lync VDI 外掛程式之後, 當您在虛擬機器上登入商務用 Skype 時, 使用者會按照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="a890a-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="a890a-136">使用者在虛擬機器上執行的商務用 Skype 用戶端輸入其認證。</span><span class="sxs-lookup"><span data-stu-id="a890a-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="a890a-137">在商務用 Skype 偵測到 Lync VDI 外掛程式之後, 商務用 Skype 會提示使用者重新輸入認證。</span><span class="sxs-lookup"><span data-stu-id="a890a-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="a890a-138">在這個對話方塊中, 我們建議使用者選取 [**儲存我的密碼**] 核取方塊, 以便在進行後續登入時, 系統不會要求您輸入認證。</span><span class="sxs-lookup"><span data-stu-id="a890a-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="a890a-139">商務用 Skype 開始配對 Lync VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a890a-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="a890a-140">在這種情況下, 用戶端會在商務用 Skype 狀態列中顯示兩個圖示。</span><span class="sxs-lookup"><span data-stu-id="a890a-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="a890a-141">左下角的圖示表示沒有可用的音訊裝置, 右下方的閃爍圖示則表示正在進行 VDI 配對: a。</span><span class="sxs-lookup"><span data-stu-id="a890a-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="a890a-142">在已成功進行 VDI 配對之後, 圖示會變更, 以指示將用於通話的音訊裝置和 VDI 配對成功: b。</span><span class="sxs-lookup"><span data-stu-id="a890a-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="a890a-143">使用者現在可以在連線至本機電腦的商務用 Skype 相容裝置上看到他或她的目前狀態, 並照常撥打及接聽電話。</span><span class="sxs-lookup"><span data-stu-id="a890a-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="a890a-144">Lync VDI 外掛程式疑難排解</span><span class="sxs-lookup"><span data-stu-id="a890a-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="a890a-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="a890a-145"></span></span>

<span data-ttu-id="a890a-146">如果您在安裝 Lync VDI 外掛程式後遇到問題, 請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="a890a-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="a890a-147">安裝 Lync VDI 外掛程式的相關問題</span><span class="sxs-lookup"><span data-stu-id="a890a-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="a890a-148">如果安裝 Lync VDI 外掛程式時會發生問題, 請檢查下列專案:</span><span class="sxs-lookup"><span data-stu-id="a890a-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="a890a-149">確定您在 TEMP 及 TMP 系統變數中指定的資料夾中有足夠的空間。</span><span class="sxs-lookup"><span data-stu-id="a890a-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="a890a-150">確定已關閉 [防寫] 功能。</span><span class="sxs-lookup"><span data-stu-id="a890a-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="a890a-151">如需相關指示, 請參閱您的裝置製造商的檔。</span><span class="sxs-lookup"><span data-stu-id="a890a-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="a890a-152">對配對問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="a890a-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="a890a-153">當 Lync VDI 外掛程式配對失敗時, 右下角的配對圖示會顯示為紅色的 [X], 如下所示:</span><span class="sxs-lookup"><span data-stu-id="a890a-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="a890a-154">下列是失敗的可能原因, 以及您可以採取的動作來修正問題。</span><span class="sxs-lookup"><span data-stu-id="a890a-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="a890a-155">**使用者在登入期間輸入的認證不正確。**</span><span class="sxs-lookup"><span data-stu-id="a890a-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="a890a-156">使用者應該登出商務用 Skype, 然後使用正確的認證重新登入。</span><span class="sxs-lookup"><span data-stu-id="a890a-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="a890a-157">[配對] 對話方塊會再次出現, 並顯示配對是否成功。</span><span class="sxs-lookup"><span data-stu-id="a890a-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="a890a-158">**遠端桌面用戶端的另一個實例正在執行。**</span><span class="sxs-lookup"><span data-stu-id="a890a-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="a890a-159">如果他們是在 Windows 中使用 [遠端桌面連線], 使用者就應該執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="a890a-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="a890a-160">啟動 [工作管理員]: 按**Alt + Ctrl + Delete**, 然後按一下 [**啟動工作管理員**]。</span><span class="sxs-lookup"><span data-stu-id="a890a-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="a890a-161">按一下 [**處理**程式] 索引標籤, 然後在清單中尋找所有名為**mstsc**的進程。</span><span class="sxs-lookup"><span data-stu-id="a890a-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="a890a-162">醒目提示每個**mstsc**程式, 然後按一下 [**結束處理**程式]。</span><span class="sxs-lookup"><span data-stu-id="a890a-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="a890a-163">啟動新的遠端桌面會話, 然後再次嘗試連線。</span><span class="sxs-lookup"><span data-stu-id="a890a-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="a890a-164">**無法正確安裝所需的檔案。**</span><span class="sxs-lookup"><span data-stu-id="a890a-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="a890a-165">在本機電腦上安裝外掛程式之後, 請檢查以確定這些檔案存在於 C:\Program Files\Microsoft Office\Office15 (或適當的磁片磁碟機號) 下:</span><span class="sxs-lookup"><span data-stu-id="a890a-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="a890a-166">LyncVdiPlugin</span><span class="sxs-lookup"><span data-stu-id="a890a-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="a890a-167">UcVdi</span><span class="sxs-lookup"><span data-stu-id="a890a-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="a890a-168">**商務用 Skype 用戶端正在本機電腦上執行。**</span><span class="sxs-lookup"><span data-stu-id="a890a-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="a890a-169">若要使用 Lync VDI 外掛程式, 不一定要在本機電腦上執行商務用 Skype 用戶端, 否則配對將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a890a-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="a890a-170">最佳做法是, 使用者不應該在本機電腦上安裝商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a890a-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a890a-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a890a-171">See also</span></span>
<span data-ttu-id="a890a-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="a890a-172"></span></span>

[<span data-ttu-id="a890a-173">規劃 VDI 環境中的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="a890a-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
