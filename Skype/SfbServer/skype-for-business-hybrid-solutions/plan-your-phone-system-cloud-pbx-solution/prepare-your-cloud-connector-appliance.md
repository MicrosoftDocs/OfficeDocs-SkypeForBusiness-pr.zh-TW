---
title: 準備雲端連接器裝置
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: 瞭解如何在 Office 365 (雲端 PBX) 中, 準備您的雲端連接器裝置以進行部署與手機系統搭配使用。
ms.openlocfilehash: f2140eb0be25ba0b6935f389e5ae7b27bfc37359
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190711"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="0a0d2-103">準備雲端連接器裝置</span><span class="sxs-lookup"><span data-stu-id="0a0d2-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="0a0d2-104">瞭解如何在 Office 365 (雲端 PBX) 中, 準備您的雲端連接器裝置以進行部署與手機系統搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>

<span data-ttu-id="0a0d2-105">本節說明如何取得商務用 Skype 雲端連接器版本安裝檔案、安裝雲端連接器軟體, 並準備您的雲端連接器裝置進行部署。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="0a0d2-106">完成本節中的所有步驟之後, 您就可以開始為單一網站或多個網站部署雲端連接器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="0a0d2-107">如果您已有雲端連接器部署, 但尚未升級至雲端連接器版本 2.1, 請參閱[升級至新版雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0a0d2-108">Microsoft 支援目前版本的雲端連接器版本2.1。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="0a0d2-109">如果您設定了自動更新, 雲端連接器將會自動更新。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="0a0d2-110">如果您已設定手動更新, 您將需要在發行前的60天內升級到版本2.1。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="0a0d2-111">Microsoft 將在發行2.1 之後60天支援舊版, 以允許您升級。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="0a0d2-112">若是雲端連接器版本2.1 及更新版本, 主機裝置必須安裝 .NET Framework 4.6.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0a0d2-113">若要成功地進行部署, 當您執行 Cmdlet 來設定商務用 Skype 雲端連接器版本時, 請務必使用與您開始時相同的主控台會話。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="0a0d2-114">避免在部署和設定期間切換到不同的會話。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="0a0d2-115">您只會針對部署中的第一個裝置執行一些步驟: 建立網站目錄的共用、下載 bits, 以及從 Windows Server ISO 映像準備虛擬硬碟 (VHDX) 檔案。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="0a0d2-116">下載商務用 Skype 雲端連接器版安裝程式</span><span class="sxs-lookup"><span data-stu-id="0a0d2-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="0a0d2-117">在雲端連接器 Vm 將在其上執行的主機伺服器上, 下載安裝檔[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller):。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="0a0d2-118">在安裝雲端連接器期間, 主機伺服器必須能夠存取網際網路, 因為在安裝期間會下載其他檔案。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="0a0d2-119">在安裝期間, 請執行安裝程式, 並接受預設值。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="0a0d2-120">確認安裝已順利完成。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="0a0d2-121">確認安裝並設定環境</span><span class="sxs-lookup"><span data-stu-id="0a0d2-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="0a0d2-122">以系統管理員身分開啟 PowerShell 主控台, 並確認使用下列 Cmdlet 來供應商務用 Skype 雲端連接器版本 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```
   Get-Command *-Cc*
   ```

    <span data-ttu-id="0a0d2-123">該命令應該會傳回商務用 Skype 雲端連接器版本的 Cmdlet 清單。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="0a0d2-124">Vhd、SfBBits 及 VersionInfo 檔案將會儲存在**網站目錄**中。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="0a0d2-125">您可以使用下列 Cmdlet 找到**網站目錄**的位置:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="0a0d2-126">該命令應該在您的檔案系統中傳回位置。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-126">The command should return a location in your file system.</span></span> <span data-ttu-id="0a0d2-127">位置可以是本機資料夾或檔案共用。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="0a0d2-128">**網站目錄**的預設位置為:%USERPROFILE%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="0a0d2-129">在每個網站建立的第一個裝置上, 應將預設位置變更為檔案共用。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="0a0d2-130">您所選取的位置必須是:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-130">The location you select must be:</span></span>

   - <span data-ttu-id="0a0d2-131">在每個網站建立的第一個裝置上建立。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="0a0d2-132">同一網站中其他主機伺服器 (裝置) 可存取的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="0a0d2-133">若要將**網站目錄**設定為預設以外的位置, 請執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="0a0d2-134">如果您要為網站部署高可用性 (HA), 請確定您執行的是 Cmdlet, 以將**網站目錄**設定為網站中每個主機伺服器上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="0a0d2-135">當您登入並部署網站中的每個裝置時, 請確定您目前的 [登入] 帳戶具備正確的**網站目錄**存取權。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="0a0d2-136">**裝置目錄**是商務用 Skype 雲端連接器版本的本機工作根目錄, 以及儲存外部憑證、實例及記錄的位置。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="0a0d2-137">預設位置為:%USERPROFILE%\CloudConnector\ApplianceRoot。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="0a0d2-138">若要尋找**裝置目錄**的位置, 請執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="0a0d2-139">若要將**裝置目錄**設定為預設以外的位置, 請執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="0a0d2-140">裝置目錄應該設定為裝置上的本機資料夾。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="0a0d2-141">您只應該在啟動商務用 Skype 雲端連接器版本部署之前, 先設定**裝置目錄**。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="0a0d2-142">如果您在部署之後進行變更, 您將需要重新部署主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0a0d2-143">**裝置目錄**的路徑不能包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="0a0d2-144">設定外部邊緣憑證的路徑</span><span class="sxs-lookup"><span data-stu-id="0a0d2-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="0a0d2-145">執行下列 Cmdlet, 將路徑 (包含檔案名) 設定為外部邊緣證書。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-145">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="0a0d2-146">例如: C:\certs\cce\ap.contoso.com.pfx。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-146">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="0a0d2-147">憑證必須包含私用金鑰。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-147">The certificate must contain private keys.</span></span>

  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="0a0d2-148">請注意,-Target 參數是舊版1.4.2 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="0a0d2-149">指定外部憑證的完整路徑, 包括檔案名。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="0a0d2-150">憑證可以儲存在本機或檔案共用中。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="0a0d2-151">如果憑證儲存在共用資料夾中, 則必須在每個網站的第一個裝置上建立共用資料夾, 且必須可供屬於相同網站的其他裝置存取。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="0a0d2-152">這個 Cmdlet 會將外部憑證複製到**裝置目錄**。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0a0d2-153">**如果您已更新為雲端連接器版本1.4.2 或**更新版本, 請確認準備好的外部憑證包含私密金鑰以及完整的憑證鏈, 包括根 CA 憑證及中間 ca 憑證。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="0a0d2-154">**如果您尚未更新為雲端連接器版本 1.4.2**, 請確定您準備的外部憑證包含私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="0a0d2-155">這個外部憑證必須由 Windows 信任的憑證頒發機構所頒發。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="0a0d2-156">設定外部 PSTN 閘道/SBC 憑證的路徑</span><span class="sxs-lookup"><span data-stu-id="0a0d2-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="0a0d2-157">如果您使用的是在中繼伺服器與 PSTN 閘道/SBC 之間的 TLS, 請執行下列 Cmdlet, 將路徑 (包括檔案名) 設定為閘道憑證。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="0a0d2-158">例如: C:\certs\cce\sbc.contoso.com.cer。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="0a0d2-159">憑證必須包含根 CA 和指派給閘道之憑證的中間鏈:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="0a0d2-160">請注意,-Target 參數是舊版1.4.2 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="0a0d2-161">在 Hyper-v 管理員中建立虛擬交換器</span><span class="sxs-lookup"><span data-stu-id="0a0d2-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="0a0d2-162">開啟 [ **hyper-v Manager** > **虛擬交換器管理器**], 然後選取 [**新增虛擬交換器管理器**]。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="0a0d2-163">建立外部虛擬交換器, 並將它系結到與您的內部網路網域連接的物理網路介面卡:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="0a0d2-164">選取 [**允許管理作業系統與此虛擬交換器共用此網路介面卡**]。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="0a0d2-165">建立外部虛擬交換器, 並將它系結到路由至網際網路的物理網路介面卡:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="0a0d2-166">取消選取 [**允許管理作業系統與此虛擬交換器共用此網路介面卡**]。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="0a0d2-167">設定將周邊網路連接至您的內部網路網域**SFB CCE 網路交換器**的交換器名稱。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="0a0d2-168">設定將周邊網路連接至網際網路**SFB CCE 網際網路切換**的交換器名稱。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="0a0d2-169">更新 CloudConnector 的設定檔</span><span class="sxs-lookup"><span data-stu-id="0a0d2-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="0a0d2-170">使用您在 [[商務用 Skype 雲端連接器的方案](plan-skype-for-business-cloud-connector-edition.md)] [](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)主題中收集的資訊來準備 CloudConnector 檔案。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="0a0d2-171">若要更新檔案, 請先執行下列 Cmdlet 來取得範例範本 (CloudConnector):</span><span class="sxs-lookup"><span data-stu-id="0a0d2-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```
Export-CcConfigurationSampleFile
```

<span data-ttu-id="0a0d2-172">範例範本會儲存在**裝置目錄**中。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="0a0d2-173">在您的環境值更新之後, 請將檔案另存為**裝置目錄**中的 CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="0a0d2-174">您可以執行**CcApplianceDirectory**來判斷**裝置目錄**的路徑。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="0a0d2-175">更新 .ini 檔案時, 請考慮下列事項:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="0a0d2-176">並非 .ini 檔案的所有值都會在此區段中討論, 這裡只講述那些只有特殊考慮的值。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="0a0d2-177">如需完整清單, 請參閱在[商務用 Skype 雲端連接器版方案](plan-skype-for-business-cloud-connector-edition.md)中的 [[決定部署參數](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)] 區段主題。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="0a0d2-178">如需有關其他裝置或新網站需要變更之值的詳細資訊, 請參閱[與多網站部署相比](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site), 在[雲端連接器中部署多個網站](deploy-multiple-sites-in-cloud-connector.md)的單一網站 (HA)。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="0a0d2-179">**SiteName:** 預設值為**Site1**。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-179">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="0a0d2-180">您必須在部署雲端連接器前進行更新, 因為當您執行**CcAppliance 註冊**裝置至現有或新的網站時, 此 Cmdlet 會使用**SiteName**來決定要註冊哪個網站。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-180">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="0a0d2-181">如果您想要將裝置註冊到新的網站, **SiteName**的價值必須是唯一的, 而且與現有的網站不同。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="0a0d2-182">如果您想要將裝置註冊至現有的網站, 則在 .ini 檔案中的**SiteName**的值必須符合您在 Office 365 租使用者設定中定義的名稱。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 tenant configuration.</span></span> <span data-ttu-id="0a0d2-183">如果您要將設定檔從一個網站複製到另一個網站, 請務必為每個網站的**SiteName**更新此值。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="0a0d2-184">**伺服器名稱:** 伺服器名稱不應該包含功能變數名稱, 且不應超過15個字元。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="0a0d2-185">**HardwareType:** 如果您沒有設定或將值保留為 null, 則會使用**標準**的預設值。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="0a0d2-186">如果您打算部署較大版本的雲端連接器, 以支援針對[商務用 Skype 雲端連接器版本規劃](plan-skype-for-business-cloud-connector-edition.md)中的每個主機電腦同時撥打 500, 請使用 [**標準**模式]。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="0a0d2-187">在支援50同時通話的較小部署中使用 [**最小值**]。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="0a0d2-188">**網際網路/公司網路/管理虛擬交換器:**: 新增您建立的虛擬交換器名稱。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="0a0d2-189">針對管理虛擬交換器, 請保留預設值。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="0a0d2-190">部署腳本將會在部署開始時建立管理虛擬交換器, 並在部署完成時將它刪除。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="0a0d2-191">**ManagementIPPrefix:** ManagementIPPrefix 中的 [網路] 區段必須是其他內部 Ip 的不同子網。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-191">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="0a0d2-192">例如, 如預設值所示, ManagementIPPrefix 是 192.168.213.0, 而 AD IPAddress 則是192.168.0.238。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-192">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="0a0d2-193">部署腳本會在每個虛擬機器上建立管理網路介面卡、指派管理 IP, 然後將其連線至管理虛擬交換器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-193">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="0a0d2-194">這可讓主機伺服器透過此管理網路連線並管理每個虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-194">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="0a0d2-195">完成部署時, 會刪除管理虛擬交換器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-195">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="0a0d2-196">**基本 VM 特定配置:** 此區段中的設定必須針對**Convert CcIsoToVhdx** Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="0a0d2-197">在基本 VM 影像準備期間, 基底 VM 將會連線到內部網路交換器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-197">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="0a0d2-198">下列設定對於 VM 能夠存取網際網路而言是至關重要的:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-198">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="0a0d2-199">常見問題解答BaseVMIP: 要指派給基底 VM 的企業電子郵件 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="0a0d2-200">局域網CorpnetDefaultGateway: 要指派給基底 VM 的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="0a0d2-201">局域網CorpnetDNSIPAddress: 要指派給基底 VM 的 DNS IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="0a0d2-202">局域網WSUSServer: Windows Server Update 服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="0a0d2-203">局域網WSUSStatusServer: Windows Server Update Services 狀態伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="0a0d2-204">局域網EnableReferSupport: 這將會定義在幹線設定上啟用或停用 SIP 對您的 IP/PBX 是否有 SIP。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="0a0d2-205">**內部 Ip:**</span><span class="sxs-lookup"><span data-stu-id="0a0d2-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="0a0d2-206">請確定子網路遮罩 CorpnetIPPrefixLength 正確無誤。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="0a0d2-207">請確定這些內部 Ip 沒有 IP 衝突。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="0a0d2-208">**外部 Ip:**</span><span class="sxs-lookup"><span data-stu-id="0a0d2-208">**External IPs:**</span></span>

  - <span data-ttu-id="0a0d2-209">若是 MR 公用 IP: 請為 NAT 的非 NAT 或 ExternalMRPublicIPs 指定 ExternalMRIPs。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="0a0d2-210">ExternalSIPIPs 和 ExternalMRIPs 可以是相同的。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="0a0d2-211">請確定子網路遮罩 InternetIPPrefixLength 正確無誤。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="0a0d2-212">請確定這些外部 Ip 沒有 IP 衝突。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="0a0d2-213">**版**</span><span class="sxs-lookup"><span data-stu-id="0a0d2-213">**Gateways:**</span></span>

  - <span data-ttu-id="0a0d2-214">如果您只有一個閘道, 請移除副閘道的節。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-214">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="0a0d2-215">如果您有超過兩個閘道, 請複製並貼上現有的節, 然後進行更新, 以建立其他章節。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-215">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="0a0d2-216">確認閘道的 IP 位址與埠正確無誤。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="0a0d2-217">若要支援 PSTN 閘道層級 HA, 請離開副閘道, 然後新增您要使用的任何其他閘道。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="0a0d2-218">您可以複製並貼上現有的專案, 然後加以更新。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="0a0d2-219">您也可以更新 LocalRoute 值, 以限制撥出電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="0a0d2-220">下載 bits 至網站目錄</span><span class="sxs-lookup"><span data-stu-id="0a0d2-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="0a0d2-221">執行下列 Cmdlet, 將 bits 與版本資訊檔案下載到**網站目錄**:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="0a0d2-222">您只需要針對第一個裝置執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="0a0d2-223">從下載的 ISO 檔案準備基底虛擬磁片 (VHDX)</span><span class="sxs-lookup"><span data-stu-id="0a0d2-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="0a0d2-224">此步驟會從 Windows Server 2012 ISO 映像準備虛擬硬碟 (VHDX) 檔案。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="0a0d2-225">在部署期間, VHDX 將用來建立虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="0a0d2-226">將會建立暫時的虛擬機器 (基本 VM), 並會從 ISO 檔案安裝 Windows Server 2012。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="0a0d2-227">建立 VM 之後, 將會安裝一些必要的元件, 並會套用最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="0a0d2-228">最後, 基本 VM 將會成為一般化 (sysprep) 並清除, 只留下所產生的虛擬磁片檔案。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="0a0d2-229">您只需要針對第一個裝置執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="0a0d2-230">在繼續進行這個步驟之前, 請先確定已建立企業用交換器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-230">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="0a0d2-231">此外, 請確認 CloudConnector 檔案中的下列設定是否已正確設定:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-231">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="0a0d2-232">局域網CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="0a0d2-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="0a0d2-233">常見問題解答BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="0a0d2-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="0a0d2-234">局域網CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="0a0d2-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="0a0d2-235">局域網CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="0a0d2-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="0a0d2-236">局域網CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="0a0d2-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="0a0d2-237">以系統管理員身分啟動 PowerShell 主機, 並執行下列 Cmdlet, 以將 ISO 影像轉換成虛擬硬碟 (VHD):</span><span class="sxs-lookup"><span data-stu-id="0a0d2-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="0a0d2-238">指定 ISO 映像的完整路徑, 包括檔案名。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-238">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="0a0d2-239">例如: C:\ISO\WindowsServer2012R2.iso。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-239">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="0a0d2-240">建立的 VHD 檔案會儲存在 [**網站目錄**\Bits\VHD] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="0a0d2-241">您可以執行**CcSiteDirectory**, 以取得**網站目錄**的路徑。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a0d2-242">根據預設, 不會在基本 VM 上設定 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="0a0d2-243">如果您的網路環境需要有 proxy, 才能透過 Windows Update 來更新 VM, 您應該在執行「Convert-CcIsoToVhdx」時, 新增-PauseBeforeUpdate 開關。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="0a0d2-244">在 Windows 更新之前, 腳本會暫停, 您就有機會在 VM 上手動設定 proxy。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="0a0d2-245">在設定 proxy 且 VM 可以存取網際網路之後, 您可以繼續執行腳本來完成剩餘的步驟。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="0a0d2-246">建立多網站部署的 Vhd</span><span class="sxs-lookup"><span data-stu-id="0a0d2-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="0a0d2-247">這是一個僅適用于多網站部署的選用步驟。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="0a0d2-248">如果您要部署多網站部署, 就不需要將 ISO 轉換成每個網站的 VHD。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-248">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="0a0d2-249">您可以將針對第一個網站所建立的 VHDX, 複製到第二個網站的主伺服器。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-249">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="0a0d2-250">將檔案複製到相同的檔案位置 (**網站目錄**\Bits\VHD 資料夾), 並使用相同的檔案名在主機伺服器上其他網站。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="0a0d2-251">將 PowerShell 執行原則設定為 RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="0a0d2-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="0a0d2-252">提供的 PowerShell 腳本需要將執行原則設定為 RemoteSigned。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-252">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="0a0d2-253">若要查看目前的設定, 請以系統管理員身分開啟 PowerShell 主控台, 然後執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-253">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```
Get-ExecutionPolicy
```

<span data-ttu-id="0a0d2-254">如果未設定為 "RemoteSigned", 請執行下列 Cmdlet 加以變更:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="0a0d2-255">變更主機電腦上的本機組策略 (版本1.4.1 及更舊版本)</span><span class="sxs-lookup"><span data-stu-id="0a0d2-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="0a0d2-256">雲端連接器版本1.4.2 及更新版本不需要這項工作。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="0a0d2-257">CceService 帳戶是在商務用 Skype 雲端連接器版本部署期間建立。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="0a0d2-258">它會執行雲端連接器管理服務, 並需要許可權才能卸載 cloudconnector。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="0a0d2-259">您必須在雲端連接器主機電腦上變更群組原則設定, 以指定使用者登出時不應該卸載使用者登錄。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="0a0d2-260">請遵循下列步驟:</span><span class="sxs-lookup"><span data-stu-id="0a0d2-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="0a0d2-261">變更群組原則設定</span><span class="sxs-lookup"><span data-stu-id="0a0d2-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="0a0d2-262">執行 gpedit.msc 來開啟 [**群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="0a0d2-263">在 [**群組原則編輯器**] 中, 流覽至 [系統 > UserProfile] > 的 [管理範本] > 不要在使用者登出時強制卸載使用者登錄。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="0a0d2-264">將它的值設定為 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-office-365-tenant"></a><span data-ttu-id="0a0d2-265">設定您的 Office 365 租使用者</span><span class="sxs-lookup"><span data-stu-id="0a0d2-265">Set up your Office 365 tenant</span></span>

<span data-ttu-id="0a0d2-266">需要 Office 365 中的商務用 Skype Online 和手機系統的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-266">An Office 365 tenant with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="0a0d2-267">在嘗試使用雲端連接器前, 請確定您的租使用者已設定並設定。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="0a0d2-268">某些 Office 365 設定步驟需要您使用租使用者遠端 PowerShell (TRPS) 來設定您的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 tenant.</span></span> <span data-ttu-id="0a0d2-269">**這應該安裝在主機伺服器上。**</span><span class="sxs-lookup"><span data-stu-id="0a0d2-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="0a0d2-270">您可以從以下網站下載適用于 PowerShell 的商務用 Skype Online 模組:[商務用 Skype online、Windows PowerShell 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="0a0d2-271">為雲端連接器線上管理建立專用的商務用 Skype 系統管理員帳戶, 例如 CceOnlineManagmentAdministrator。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="0a0d2-272">裝置將會使用這個帳戶來新增或移除裝置、啟用或停用自動 OS 更新、啟用或停用自動二進位更新。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="0a0d2-273">將此帳戶的密碼設為永不過期, 這樣您就不需要在每次到期時變更服務的密碼。</span><span class="sxs-lookup"><span data-stu-id="0a0d2-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


