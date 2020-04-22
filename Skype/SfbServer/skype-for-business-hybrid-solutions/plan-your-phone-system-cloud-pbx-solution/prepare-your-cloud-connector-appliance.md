---
title: 準備您的雲端連接器裝置
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: 瞭解如何在 Office 365 （Cloud PBX）中準備用於部署和使用電話系統的雲端連接器裝置。
ms.openlocfilehash: 21943dfd8b86bfeabb4cbd28b501b80a3f2b5c45
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779239"
---
# <a name="prepare-your-cloud-connector-appliance"></a><span data-ttu-id="e9e35-103">準備您的雲端連接器裝置</span><span class="sxs-lookup"><span data-stu-id="e9e35-103">Prepare your Cloud Connector appliance</span></span>

<span data-ttu-id="e9e35-104">瞭解如何在 Office 365 （Cloud PBX）中準備用於部署和使用電話系統的雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="e9e35-104">Learn about how to prepare your Cloud Connector appliance for deployment and use with Phone System in Office 365 (Cloud PBX).</span></span>

<span data-ttu-id="e9e35-105">本節說明如何取得商務用 Skype 雲端連接器 Edition 安裝檔案、安裝雲端連接器軟體，以及準備用於部署的雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="e9e35-105">This section describes how to get the Skype for Business Cloud Connector Edition installation files, install Cloud Connector software, and prepare your Cloud Connector appliance for deployment.</span></span> <span data-ttu-id="e9e35-106">在您完成本節中的所有步驟之後，您就可以為單一網站或多個網站部署雲端連接器。</span><span class="sxs-lookup"><span data-stu-id="e9e35-106">After you have completed all steps in this section, you will be ready to deploy Cloud Connector for a single site or multiple sites.</span></span> <span data-ttu-id="e9e35-107">如果您有現有的雲端連接器部署，但尚未升級為雲端連接器版本2.1，請參閱[Upgrade to An Cloud connector 的新版本](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="e9e35-107">If you have an existing Cloud Connector deployment, and you have not yet upgraded to Cloud Connector version 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e9e35-108">Microsoft 支援目前版本的 Cloud Connector Edition，版本2.1。</span><span class="sxs-lookup"><span data-stu-id="e9e35-108">Microsoft supports the current version of Cloud Connector Edition, version 2.1.</span></span> <span data-ttu-id="e9e35-109">如果您設定了自動更新，Cloud Connector 將會自動更新。</span><span class="sxs-lookup"><span data-stu-id="e9e35-109">If you configured automatic update, Cloud Connector will update automatically.</span></span> <span data-ttu-id="e9e35-110">如果您已設定手動更新，您將需要在發行前的60天內，升級至版本2.1。</span><span class="sxs-lookup"><span data-stu-id="e9e35-110">If you configured manual update, you will need to upgrade to version 2.1 within 60 days of its release.</span></span> <span data-ttu-id="e9e35-111">Microsoft 會在發行2.1 後的60天內支援舊版，以供您升級時間。</span><span class="sxs-lookup"><span data-stu-id="e9e35-111">Microsoft will support the previous version for 60 days after the release of 2.1 to allow you time to upgrade.</span></span> 

> [!NOTE]
> <span data-ttu-id="e9e35-112">若為雲端連接器版本2.1 和更新版本，主機裝置必須已安裝 .NET Framework 4.6.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="e9e35-112">For Cloud Connector version 2.1 and later, the host appliance must have .NET Framework 4.6.1 or later installed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e9e35-113">若要順利進行部署，當您執行 Cmdlet 以設定商務用 Skype 雲端連接器 Edition 時，請務必使用與您在中開始的相同主控台會話。</span><span class="sxs-lookup"><span data-stu-id="e9e35-113">For successful deployment, when you run the cmdlets to configure Skype for Business Cloud Connector Edition, always use the same console session as the one you started in.</span></span> <span data-ttu-id="e9e35-114">避免在部署及設定期間切換至不同的會話。</span><span class="sxs-lookup"><span data-stu-id="e9e35-114">Avoid switching to different sessions during the deployment and configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="e9e35-115">您只需針對部署中的第一個裝置執行一些步驟：建立網站目錄的共用、下載 bits，以及準備來自 Windows Server ISO 映像的虛擬硬碟（VHDX）檔案。</span><span class="sxs-lookup"><span data-stu-id="e9e35-115">There are some steps that you perform only for the first appliance in your deployment: creating a share for the site directory, downloading the bits, and preparing a virtual hard disk (VHDX) file from the Windows Server ISO image.</span></span> 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a><span data-ttu-id="e9e35-116">下載商務用 Skype 雲端連接器 Edition 安裝程式</span><span class="sxs-lookup"><span data-stu-id="e9e35-116">Download the Skype for Business Cloud Connector Edition installer</span></span>

1. <span data-ttu-id="e9e35-117">在雲端連接器 Vm 即將執行的主機伺服器上，下載安裝檔案： [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。</span><span class="sxs-lookup"><span data-stu-id="e9e35-117">On the host server where the Cloud Connector VMs will run, download the installation files: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="e9e35-118">在安裝雲端連接器期間，主伺服器必須能夠存取網際網路，因為在安裝期間會下載其他檔案。</span><span class="sxs-lookup"><span data-stu-id="e9e35-118">The host server must be able to access the Internet during the installation of Cloud Connector because additional files are downloaded during the installation.</span></span> 

2. <span data-ttu-id="e9e35-119">執行安裝程式，並在安裝期間接受預設值。</span><span class="sxs-lookup"><span data-stu-id="e9e35-119">Run the installer and accept the default values during the installation.</span></span>

3. <span data-ttu-id="e9e35-120">確認安裝已成功完成。</span><span class="sxs-lookup"><span data-stu-id="e9e35-120">Confirm that the installation completed successfully.</span></span>

## <a name="verify-the-installation-and-configure-the-environment"></a><span data-ttu-id="e9e35-121">驗證安裝及設定環境</span><span class="sxs-lookup"><span data-stu-id="e9e35-121">Verify the installation and configure the environment</span></span>

1. <span data-ttu-id="e9e35-122">以系統管理員身分開啟 PowerShell 主控台，並確認商務用 Skype 雲端連接器 Edition Cmdlet 可使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e9e35-122">Open a PowerShell console as administrator and confirm that the Skype for Business Cloud Connector Edition cmdlets are available using the following cmdlet:</span></span>

   ```powershell
   Get-Command *-Cc*
   ```

    <span data-ttu-id="e9e35-123">該命令應該會傳回商務用 Skype 雲端連接器 Edition 的 Cmdlet 清單。</span><span class="sxs-lookup"><span data-stu-id="e9e35-123">The command should return a list of cmdlets for Skype for Business Cloud Connector Edition.</span></span>

2. <span data-ttu-id="e9e35-124">Vhd、SfBBits 及 VersionInfo 檔會儲存在**網站目錄**中。</span><span class="sxs-lookup"><span data-stu-id="e9e35-124">The VHDs, SfBBits, and VersionInfo files will be stored in the **Site Directory**.</span></span>

    <span data-ttu-id="e9e35-125">您可以使用下列 Cmdlet 找到**網站目錄**的位置：</span><span class="sxs-lookup"><span data-stu-id="e9e35-125">You can find the location of the **Site Directory** with the following cmdlet:</span></span>

   ```powershell
   Get-CcSiteDirectory
   ```

    <span data-ttu-id="e9e35-126">命令應該會傳回您的檔案系統中的位置。</span><span class="sxs-lookup"><span data-stu-id="e9e35-126">The command should return a location in your file system.</span></span> <span data-ttu-id="e9e35-127">該位置可以是本機資料夾或檔案共用。</span><span class="sxs-lookup"><span data-stu-id="e9e35-127">The location can be a local folder or a file share.</span></span> <span data-ttu-id="e9e35-128">**網站目錄**的預設位置為：%USERPROFILE%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="e9e35-128">The default location for the **Site Directory** is: %USERPROFILE%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="e9e35-129">在每個網站中建立的第一個裝置上，應將預設位置變更為檔案共用。</span><span class="sxs-lookup"><span data-stu-id="e9e35-129">The default location should be changed to a file share on the first appliance created in each site.</span></span>

    <span data-ttu-id="e9e35-130">您選取的位置必須是：</span><span class="sxs-lookup"><span data-stu-id="e9e35-130">The location you select must be:</span></span>

   - <span data-ttu-id="e9e35-131">在每個網站中建立的第一個裝置上建立。</span><span class="sxs-lookup"><span data-stu-id="e9e35-131">Created on the first appliance created in each site.</span></span>

   - <span data-ttu-id="e9e35-132">相同網站中其他主機伺服器（裝置）可以存取的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="e9e35-132">A shared folder that is accessible by the other host servers (appliances) in the same site.</span></span>

     <span data-ttu-id="e9e35-133">若要將**網站目錄**設定為預設以外的位置，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e9e35-133">To set the **Site Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    <span data-ttu-id="e9e35-134">若要為網站部署高可用性（HA），請確定您執行 Cmdlet，將**網站目錄**設定為網站中每個主機伺服器上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="e9e35-134">If you are deploying High Availability (HA) for the site, make sure you run the cmdlet to set the **Site Directory** to the same location on each host server within the site.</span></span>

    <span data-ttu-id="e9e35-135">當您登入並部署網站中的每個裝置時，請確定您目前的登入帳戶具有**網站目錄**的正確存取權。</span><span class="sxs-lookup"><span data-stu-id="e9e35-135">When you log on and deploy each appliance in the site, make sure your current logon account has the right access to the **Site Directory**.</span></span>

3. <span data-ttu-id="e9e35-136">**裝置目錄**是商務用 Skype 雲端連接器 Edition 的本機工作根目錄，以及儲存外部憑證、實例及記錄檔的位置。</span><span class="sxs-lookup"><span data-stu-id="e9e35-136">The **Appliance Directory** is the local working root directory for Skype for Business Cloud Connector Edition, and the location where external certificates, instances, and logs are saved.</span></span> <span data-ttu-id="e9e35-137">預設位置為：%USERPROFILE%\CloudConnector\ApplianceRoot。</span><span class="sxs-lookup"><span data-stu-id="e9e35-137">The default location is: %USERPROFILE%\CloudConnector\ApplianceRoot.</span></span>

    <span data-ttu-id="e9e35-138">若要尋找**裝置目錄**的位置，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e9e35-138">To find the location of the **Appliance Directory**, run the following cmdlet:</span></span>

   ```powershell
   Get-CcApplianceDirectory
   ```

    <span data-ttu-id="e9e35-139">若要將**裝置目錄**設定為預設之外的位置，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e9e35-139">To set the **Appliance Directory** to a location other than the default, run the following cmdlet:</span></span>

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    <span data-ttu-id="e9e35-140">裝置目錄應設定為裝置上的本機資料夾。</span><span class="sxs-lookup"><span data-stu-id="e9e35-140">The Appliance Directory should be set to a local folder on the appliance.</span></span> <span data-ttu-id="e9e35-141">您應只在啟動商務用 Skype Cloud Connector Edition 部署之前，先設定**裝置目錄**。</span><span class="sxs-lookup"><span data-stu-id="e9e35-141">You should only set the **Appliance Directory** before you start the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="e9e35-142">如果您在部署後變更它，您將需要重新部署主伺服器。</span><span class="sxs-lookup"><span data-stu-id="e9e35-142">If you change it after deployment, you'll need to redeploy the host server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e9e35-143">**裝置目錄**的路徑不能包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="e9e35-143">The path to the **Appliance Directory** must not contain any spaces.</span></span>

## <a name="set-the-path-for-the-external-edge-certificate"></a><span data-ttu-id="e9e35-144">設定外部 Edge 憑證的路徑</span><span class="sxs-lookup"><span data-stu-id="e9e35-144">Set the path for the external Edge certificate</span></span>

- <span data-ttu-id="e9e35-145">執行下列 Cmdlet，將路徑（包括檔案名）設定為外部 Edge 憑證。</span><span class="sxs-lookup"><span data-stu-id="e9e35-145">Run the following cmdlet to set the path, including the file name, to the external Edge certificate.</span></span> <span data-ttu-id="e9e35-146">例如： C:\certs\cce\ap.contoso.com.pfx。</span><span class="sxs-lookup"><span data-stu-id="e9e35-146">For example: C:\certs\cce\ap.contoso.com.pfx.</span></span> <span data-ttu-id="e9e35-147">憑證必須包含私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="e9e35-147">The certificate must contain private keys.</span></span>

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > <span data-ttu-id="e9e35-148">請注意，-Target 參數是版本1.4.2 和更新版本特有的。</span><span class="sxs-lookup"><span data-stu-id="e9e35-148">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

    <span data-ttu-id="e9e35-149">指定外部憑證的完整路徑，包含檔案名。</span><span class="sxs-lookup"><span data-stu-id="e9e35-149">Specify the full path to the external certificate, including the file name.</span></span> <span data-ttu-id="e9e35-150">憑證可以儲存在本機或檔案共用上。</span><span class="sxs-lookup"><span data-stu-id="e9e35-150">The certificate can be stored locally or on a file share.</span></span> <span data-ttu-id="e9e35-151">如果憑證儲存于共用資料夾中，則必須在每個網站的第一個裝置上建立共用資料夾，而且必須可供屬於相同網站的其他裝置存取。</span><span class="sxs-lookup"><span data-stu-id="e9e35-151">If the certificate is stored in a shared folder, the shared folder must be created on the first appliance of each site and must be accessible by other appliances belonging to the same site.</span></span> <span data-ttu-id="e9e35-152">此 Cmdlet 會將外部憑證複製到**裝置目錄**。</span><span class="sxs-lookup"><span data-stu-id="e9e35-152">This cmdlet copies the external certificate to the **Appliance Directory**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e9e35-153">**如果您已更新 Cloud Connector 版本1.4.2 或更新版本**，請確定準備好的外部憑證包含私密金鑰和完整的憑證鏈，包括根 ca 憑證和中間 ca 憑證。</span><span class="sxs-lookup"><span data-stu-id="e9e35-153">**If you have updated to Cloud Connector version 1.4.2 or later**, make sure your prepared external certificate contains private keys and the full certificate chain including the root CA certificate and the intermediate CA certificates.</span></span> <span data-ttu-id="e9e35-154">若尚未**更新為雲端連接器版本 1.4.2**，請確定準備好的外部憑證包含私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="e9e35-154">**If you have NOT yet updated to Cloud Connector version 1.4.2**, make sure your prepared external certificate contains private keys.</span></span> <span data-ttu-id="e9e35-155">此外部憑證必須由 Windows 所信任的憑證授權單位單位所發出。</span><span class="sxs-lookup"><span data-stu-id="e9e35-155">This external certificate must be issued by a Certificate Authority that is trusted by Windows by default.</span></span>

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a><span data-ttu-id="e9e35-156">設定外部 PSTN 閘道/SBC 憑證的路徑</span><span class="sxs-lookup"><span data-stu-id="e9e35-156">Set the path for the external PSTN gateway/SBC certificate</span></span>

<span data-ttu-id="e9e35-157">如果您是在轉送伺服器和 PSTN 閘道/SBC 之間使用 TLS，請執行下列 Cmdlet，將路徑（包括檔案名）設定為閘道憑證。</span><span class="sxs-lookup"><span data-stu-id="e9e35-157">If you are using TLS between the Mediation Server and the PSTN gateway/SBC, run the following cmdlet to set the path, including the file name, to the gateway certificate.</span></span> <span data-ttu-id="e9e35-158">例如： C:\certs\cce\sbc.contoso.com.cer。</span><span class="sxs-lookup"><span data-stu-id="e9e35-158">For example: C:\certs\cce\sbc.contoso.com.cer.</span></span> <span data-ttu-id="e9e35-159">憑證必須包含根 CA 和指派給閘道之憑證的中間階層：</span><span class="sxs-lookup"><span data-stu-id="e9e35-159">The certificate must contain the root CA and the intermediate chain for the certificate assigned to the gateway:</span></span>

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> <span data-ttu-id="e9e35-160">請注意，-Target 參數是版本1.4.2 和更新版本特有的。</span><span class="sxs-lookup"><span data-stu-id="e9e35-160">Note that the -Target parameter is specific to versions 1.4.2 and later.</span></span> 

## <a name="create-virtual-switches-in-hyper-v-manager"></a><span data-ttu-id="e9e35-161">在 Hyper-V 管理員中建立虛擬交換器</span><span class="sxs-lookup"><span data-stu-id="e9e35-161">Create virtual switches in Hyper-V Manager</span></span>

1. <span data-ttu-id="e9e35-162">開啟**Hyper-V 管理員** > **虛擬交換器管理員**]，然後選取 [**新增虛擬交換器管理員**]。</span><span class="sxs-lookup"><span data-stu-id="e9e35-162">Open **Hyper-V Manager** > **Virtual Switch Manager**, and select **New Virtual Switch Manager**.</span></span>

2. <span data-ttu-id="e9e35-163">建立外部虛擬交換器，並將它系結至連接至您的內部網路網域的實體網路介面卡：</span><span class="sxs-lookup"><span data-stu-id="e9e35-163">Create an External virtual switch and bind it to the physical network adapter that is connected to your internal network domain:</span></span>

    <span data-ttu-id="e9e35-164">選取 [**允許管理作業系統為此虛擬交換器共用此網路介面卡**]。</span><span class="sxs-lookup"><span data-stu-id="e9e35-164">Select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

3. <span data-ttu-id="e9e35-165">建立外部虛擬交換器，並將它系結至路由傳送至網際網路的實體網路介面卡：</span><span class="sxs-lookup"><span data-stu-id="e9e35-165">Create an External virtual switch and bind it to the physical network adapter that is routed to the Internet:</span></span>

    <span data-ttu-id="e9e35-166">取消選取 [**允許管理作業系統為此虛擬交換器共用此網路介面卡**]。</span><span class="sxs-lookup"><span data-stu-id="e9e35-166">De-select **Allow management operating system to share this network adapter** for this virtual switch.</span></span>

4. <span data-ttu-id="e9e35-167">設定將周邊網路連接至內部網路網域的交換器名稱**SFB CCE**網路的參數。</span><span class="sxs-lookup"><span data-stu-id="e9e35-167">Set the name of the switch that connects your perimeter network to your internal network domain **SfB CCE Corpnet Switch**.</span></span>

    <span data-ttu-id="e9e35-168">設定將周邊網路連接至網際網路**SFB CCE 網際網路參數**的交換器名稱。</span><span class="sxs-lookup"><span data-stu-id="e9e35-168">Set the name of the switch that connects your perimeter network to the Internet **SfB CCE Internet Switch**.</span></span>

## <a name="update-the-cloudconnectorini-configuration-file"></a><span data-ttu-id="e9e35-169">更新 CloudConnector 設定檔</span><span class="sxs-lookup"><span data-stu-id="e9e35-169">Update the CloudConnector.ini configuration file</span></span>

<span data-ttu-id="e9e35-170">使用您在 [在[商務用 Skype 雲端連接器](plan-skype-for-business-cloud-connector-edition.md)的方案[] 中所](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)收集的資訊來準備 CloudConnector 檔案。</span><span class="sxs-lookup"><span data-stu-id="e9e35-170">Prepare the CloudConnector.ini file using the information you gathered in [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) in the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span>

<span data-ttu-id="e9e35-171">若要更新檔，請先執行下列 Cmdlet 以取得範例範本（CloudConnector）：</span><span class="sxs-lookup"><span data-stu-id="e9e35-171">To update the file, first run the following cmdlet to get the sample template (CloudConnector.Sample.ini):</span></span>

```powershell
Export-CcConfigurationSampleFile
```

<span data-ttu-id="e9e35-172">範例範本是儲存在**裝置目錄**中。</span><span class="sxs-lookup"><span data-stu-id="e9e35-172">The sample template is stored in the **Appliance Directory**.</span></span>

<span data-ttu-id="e9e35-173">在您使用環境的值進行更新後，請將檔案儲存為 CloudConnector**裝置目錄**中的副檔名。</span><span class="sxs-lookup"><span data-stu-id="e9e35-173">After you update it with the values for your environment, save the file as CloudConnector.ini in the **Appliance Directory**.</span></span> <span data-ttu-id="e9e35-174">您可以執行**CcApplianceDirectory**來決定**裝置目錄**的路徑。</span><span class="sxs-lookup"><span data-stu-id="e9e35-174">You can run **Get-CcApplianceDirectory** to determine the path to the **Appliance Directory**.</span></span>

<span data-ttu-id="e9e35-175">更新 .ini 檔案時，請考慮下列各項：</span><span class="sxs-lookup"><span data-stu-id="e9e35-175">When updating the .ini file, consider the following:</span></span>

> [!NOTE]
> <span data-ttu-id="e9e35-176">本節並未討論 .ini 檔案的所有值，這裡只會提及那些具有特殊考慮的值。</span><span class="sxs-lookup"><span data-stu-id="e9e35-176">Not all values for the .ini file are discussed in this section, only those with a special consideration are covered here.</span></span> <span data-ttu-id="e9e35-177">如需完整清單，請參閱[Plan For 商務用 Skype 雲端連接器 Edition](plan-skype-for-business-cloud-connector-edition.md)主題中的 [[決定部署參數](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)] 區段。</span><span class="sxs-lookup"><span data-stu-id="e9e35-177">For a full list, see the [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) section of the [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) topic.</span></span> <span data-ttu-id="e9e35-178">如需有關其他裝置或新網站的哪些值需要變更的詳細資訊，請參閱[具有高可用性（HA）的單一網站](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)，與主題中[部署多個網站的雲端連接器](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="e9e35-178">For more information about what values need to be changed for additional appliances or new sites, see [Single site with High Availability (HA) compared to multi-site deployments](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) in the topic [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 

- <span data-ttu-id="e9e35-179">**SiteName：** 預設值為**Site1**。</span><span class="sxs-lookup"><span data-stu-id="e9e35-179">**SiteName:** The default value is **Site1**.</span></span> <span data-ttu-id="e9e35-180">您必須先將它更新，然後再部署雲端連接器，因為當您執行**CcAppliance**將裝置登錄至現有或新的網站時，Cmdlet 會使用**SiteName**來判斷要註冊的網站。</span><span class="sxs-lookup"><span data-stu-id="e9e35-180">You must update it before you deploy Cloud Connector, because when you run **Register-CcAppliance** to register an appliance to an existing or new site, the cmdlet will use **SiteName** to determine which site to register.</span></span>

     <span data-ttu-id="e9e35-181">如果您想要將裝置登錄至新的網站， **SiteName**的值必須是唯一的，且與現有的網站不同。</span><span class="sxs-lookup"><span data-stu-id="e9e35-181">If you want to register the appliance to a new site, the value of **SiteName** must be unique and different from existing sites.</span></span> <span data-ttu-id="e9e35-182">若要將裝置登錄至現有的網站， **SiteName** .ini 檔案中的值必須符合 Office 365 組織設定中所定義的名稱。</span><span class="sxs-lookup"><span data-stu-id="e9e35-182">If you want to register the appliance to an existing site, the value for **SiteName** in .ini file must match the name defined in your Office 365 organization configuration.</span></span> <span data-ttu-id="e9e35-183">若要將設定檔從一個網站複製到另一個網站，請確定為每個網站更新**SiteName**的值。</span><span class="sxs-lookup"><span data-stu-id="e9e35-183">If you are copying a configuration file from one site to another, make sure you update the value for **SiteName** for each site accordingly.</span></span>

- <span data-ttu-id="e9e35-184">**ServerName：** 伺服器名稱不應該包含功能變數名稱，且應該限制為15個字元。</span><span class="sxs-lookup"><span data-stu-id="e9e35-184">**ServerName:** The server name should not contain the domain name and should be limited to 15 characters.</span></span>

- <span data-ttu-id="e9e35-185">**HardwareType：** 如果您未設定或保留值為 null，則會使用**標準**的預設值。</span><span class="sxs-lookup"><span data-stu-id="e9e35-185">**HardwareType:** If you don't set or leave the value to null, the default value of **Normal** will be used.</span></span> <span data-ttu-id="e9e35-186">如果您打算部署較大型版本的雲端連接器，以支援500的[商務用 Skype 雲端連接器 Edition](plan-skype-for-business-cloud-connector-edition.md)中所述的，請使用**Normal** 。</span><span class="sxs-lookup"><span data-stu-id="e9e35-186">Use **Normal** if you plan to deploy the larger version of Cloud Connector to support 500 simultaneous calls per host machine as described in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> <span data-ttu-id="e9e35-187">使用**最小值**進行同時支援50同時通話的部署。</span><span class="sxs-lookup"><span data-stu-id="e9e35-187">Use **Minimum** for a smaller deployment that supports 50 simultaneous calls.</span></span>

- <span data-ttu-id="e9e35-188">**網際網路/公司網路/管理虛擬交換器：**：新增您已建立的虛擬交換器名稱。</span><span class="sxs-lookup"><span data-stu-id="e9e35-188">**Internet/Corpnet/Management virtual switches:**: Add the name of the virtual switches you have created.</span></span> <span data-ttu-id="e9e35-189">針對管理虛擬交換器，保留預設值。</span><span class="sxs-lookup"><span data-stu-id="e9e35-189">For the management virtual switch, leave the default value.</span></span> <span data-ttu-id="e9e35-190">部署腳本會在部署開始時建立管理虛擬交換器，並在部署完成時加以刪除。</span><span class="sxs-lookup"><span data-stu-id="e9e35-190">The deployment script will create the management virtual switch at the beginning of deployment and delete it when the deployment finishes.</span></span>

- <span data-ttu-id="e9e35-191">**ManagementIPPrefix：** Network 區段中的 ManagementIPPrefix 必須是其他內部 Ip 的不同子網。</span><span class="sxs-lookup"><span data-stu-id="e9e35-191">**ManagementIPPrefix:** ManagementIPPrefix in the Network section must be a different subnet from other internal IPs.</span></span> <span data-ttu-id="e9e35-192">例如，預設值會顯示 ManagementIPPrefix 為192.168.213.0，而 AD IPAddress 為192.168.0.238。</span><span class="sxs-lookup"><span data-stu-id="e9e35-192">For example, as the default value shows, ManagementIPPrefix is 192.168.213.0, while AD IPAddress is 192.168.0.238.</span></span>

    <span data-ttu-id="e9e35-193">部署腳本會在每一部虛擬機器上建立管理網路介面卡、指派管理 IP，並將其連線至管理虛擬交換器。</span><span class="sxs-lookup"><span data-stu-id="e9e35-193">The deployment scripts create a management network adapter on each virtual machine, assign a management IP, and connect it to a management virtual switch.</span></span> <span data-ttu-id="e9e35-194">這可讓主機伺服器透過此管理網路連接並管理每個虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="e9e35-194">This enables the host server to connect to and manage each virtual machine via this management network.</span></span> <span data-ttu-id="e9e35-195">完成部署時，會刪除管理虛擬交換器。</span><span class="sxs-lookup"><span data-stu-id="e9e35-195">The management virtual switch is deleted when the deployment is finished.</span></span>

- <span data-ttu-id="e9e35-196">**基本 VM 特定設定：** 必須為**CcIsoToVhdx** Cmdlet 設定本節中的設定。</span><span class="sxs-lookup"><span data-stu-id="e9e35-196">**Base VM specific configurations:** Settings in this section must be configured for the **Convert-CcIsoToVhdx** cmdlet.</span></span>

    <span data-ttu-id="e9e35-197">在基本 VM 影像準備期間，基本 VM 將會連線至內部網路交換器。</span><span class="sxs-lookup"><span data-stu-id="e9e35-197">During base VM image preparation, the base VM will be connected to the internal network switch.</span></span> <span data-ttu-id="e9e35-198">下列設定對 VM 能夠存取網際網路很重要：</span><span class="sxs-lookup"><span data-stu-id="e9e35-198">The following settings are critical for the VM to be able to access the Internet:</span></span>

  - <span data-ttu-id="e9e35-199">相同BaseVMIP：要指派給基底 VM 的公司間 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e9e35-199">[Common]BaseVMIP: the corpnet IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="e9e35-200">網路CorpnetDefaultGateway：要指派給基底 VM 的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="e9e35-200">[Network]CorpnetDefaultGateway: the default gateway to be assigned to the base VM.</span></span>

  - <span data-ttu-id="e9e35-201">網路CorpnetDNSIPAddress：要指派給基底 VM 的 DNS IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e9e35-201">[Network]CorpnetDNSIPAddress: the DNS IP address to be assigned to the base VM.</span></span>

  - <span data-ttu-id="e9e35-202">網路WSUSServer： Windows Server Update Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e9e35-202">[Network]WSUSServer: the IP address of Windows Server Update Service.</span></span>

  - <span data-ttu-id="e9e35-203">網路WSUSStatusServer： Windows Server Update Service 狀態伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e9e35-203">[Network]WSUSStatusServer: the IP address of Windows Server Update Service status server.</span></span>

  - <span data-ttu-id="e9e35-204">網路EnableReferSupport：這會定義在主幹設定上啟用或停用 SIP 對您 IP/PBX 的 SIP 是否支援。</span><span class="sxs-lookup"><span data-stu-id="e9e35-204">[Network]EnableReferSupport: this will define whether SIP REFER support is enabled or disabled on the Trunk Configuration to your IP/PBX.</span></span>

- <span data-ttu-id="e9e35-205">**內部 Ip：**</span><span class="sxs-lookup"><span data-stu-id="e9e35-205">**Internal IPs:**</span></span>

  - <span data-ttu-id="e9e35-206">請確定 subnet mask CorpnetIPPrefixLength 是正確的。</span><span class="sxs-lookup"><span data-stu-id="e9e35-206">Make sure subnet mask CorpnetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="e9e35-207">請確定這些內部 Ip 沒有任何 IP 衝突。</span><span class="sxs-lookup"><span data-stu-id="e9e35-207">Make sure there are no IP conflicts for these internal IPs.</span></span>

- <span data-ttu-id="e9e35-208">**外部 Ip：**</span><span class="sxs-lookup"><span data-stu-id="e9e35-208">**External IPs:**</span></span>

  - <span data-ttu-id="e9e35-209">尊敬的公用 IP：針對 NAT，請指定 ExternalMRIPs 的非 NAT 或 ExternalMRPublicIPs。</span><span class="sxs-lookup"><span data-stu-id="e9e35-209">For MR public IP: specify either ExternalMRIPs for non-NAT or ExternalMRPublicIPs for NAT.</span></span>

  - <span data-ttu-id="e9e35-210">ExternalSIPIPs 與 ExternalMRIPs 可以相同。</span><span class="sxs-lookup"><span data-stu-id="e9e35-210">ExternalSIPIPs and ExternalMRIPs can be the same.</span></span>

  - <span data-ttu-id="e9e35-211">請確定 subnet mask InternetIPPrefixLength 是正確的。</span><span class="sxs-lookup"><span data-stu-id="e9e35-211">Make sure subnet mask InternetIPPrefixLength is correct.</span></span>

  - <span data-ttu-id="e9e35-212">請確定這些外部 Ip 沒有任何 IP 衝突。</span><span class="sxs-lookup"><span data-stu-id="e9e35-212">Make sure there are no IP conflicts for these external IPs.</span></span>

- <span data-ttu-id="e9e35-213">**閘道：**</span><span class="sxs-lookup"><span data-stu-id="e9e35-213">**Gateways:**</span></span>

  - <span data-ttu-id="e9e35-214">如果您只有一個閘道，請移除次要閘道的區段。</span><span class="sxs-lookup"><span data-stu-id="e9e35-214">If you have only one gateway, remove the section for the secondary gateway.</span></span> <span data-ttu-id="e9e35-215">如果您有兩個以上的閘道，請複製並貼上現有的區段，然後更新它，以建立其他章節。</span><span class="sxs-lookup"><span data-stu-id="e9e35-215">If you have more than two gateways, create additional sections by copying and pasting the existing one and then updating it.</span></span>

  - <span data-ttu-id="e9e35-216">確定閘道的 IP 位址及埠正確無誤。</span><span class="sxs-lookup"><span data-stu-id="e9e35-216">Make sure that the IP address and port of the gateway(s) are correct.</span></span>

  - <span data-ttu-id="e9e35-217">若要支援 PSTN 閘道層級 HA，請離開次要閘道，然後新增您要使用的任何其他閘道。</span><span class="sxs-lookup"><span data-stu-id="e9e35-217">To support PSTN gateway level HA, leave the secondary gateway, and add any additional gateways you will use.</span></span> <span data-ttu-id="e9e35-218">您可以複製並貼上現有的專案，然後進行更新。</span><span class="sxs-lookup"><span data-stu-id="e9e35-218">You can copy and paste an existing entry and then update it.</span></span>

- <span data-ttu-id="e9e35-219">您也可以更新 LocalRoute 值以限制撥出電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e9e35-219">Optionally, you can update the LocalRoute value to restrict outbound call numbers.</span></span>

## <a name="download-the-bits-to-the-site-directory"></a><span data-ttu-id="e9e35-220">將 bits 下載至網站目錄</span><span class="sxs-lookup"><span data-stu-id="e9e35-220">Download the bits to the Site Directory</span></span>

<span data-ttu-id="e9e35-221">執行下列 Cmdlet，將 bits 及版本資訊檔下載至**網站目錄**：</span><span class="sxs-lookup"><span data-stu-id="e9e35-221">Run the following cmdlet to download the bits and version information files to the **Site Directory**:</span></span>

```powershell
Start-CcDownload
```

> [!NOTE]
> <span data-ttu-id="e9e35-222">您只需要為第一個裝置執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="e9e35-222">You need to perform this step for the first appliance only.</span></span> 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a><span data-ttu-id="e9e35-223">從下載的 ISO 檔案準備基本虛擬磁片（VHDX）</span><span class="sxs-lookup"><span data-stu-id="e9e35-223">Prepare base virtual disk (VHDX) from the downloaded ISO file</span></span>

<span data-ttu-id="e9e35-224">此步驟會從 Windows Server 2012 ISO 映像準備虛擬硬碟（VHDX）檔案。</span><span class="sxs-lookup"><span data-stu-id="e9e35-224">This step prepares a virtual hard disk (VHDX) file from the Windows Server 2012 ISO image.</span></span> <span data-ttu-id="e9e35-225">VHDX 將用來在部署期間建立虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="e9e35-225">The VHDX will be used to create virtual machines during deployment.</span></span> <span data-ttu-id="e9e35-226">將會建立暫時的虛擬機器（基本 VM），並且會從 ISO 檔案安裝 Windows Server 2012。</span><span class="sxs-lookup"><span data-stu-id="e9e35-226">A temporary virtual machine (base VM) will be created and Windows Server 2012 will be installed from the ISO file.</span></span> <span data-ttu-id="e9e35-227">在建立 VM 之後，將會安裝一些必要的元件，並套用最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e9e35-227">After the VM is created, some necessary components will be installed and the latest Windows update will be applied.</span></span> <span data-ttu-id="e9e35-228">最後，基本 VM 將會進行一般化（sysprep）和清理，只留下所產生的虛擬磁片檔。</span><span class="sxs-lookup"><span data-stu-id="e9e35-228">At the end, the base VM will be generalized (sysprep) and cleaned up, leaving only the generated virtual disk file.</span></span>

> [!NOTE]
> <span data-ttu-id="e9e35-229">您只需要為第一個裝置執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="e9e35-229">You need to perform this step for the first appliance only.</span></span> 

<span data-ttu-id="e9e35-230">在繼續執行此步驟之前，請確定已建立公司間參數。</span><span class="sxs-lookup"><span data-stu-id="e9e35-230">Before proceeding with this step, make sure that the corpnet switch is created.</span></span> <span data-ttu-id="e9e35-231">此外，請確認已在 CloudConnector 檔案中正確設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="e9e35-231">Also, confirm that the following settings are correctly configured in the CloudConnector.ini file:</span></span>

- <span data-ttu-id="e9e35-232">網路CorpnetSwitchName</span><span class="sxs-lookup"><span data-stu-id="e9e35-232">[Network]CorpnetSwitchName</span></span>

- <span data-ttu-id="e9e35-233">相同BaseVMIP</span><span class="sxs-lookup"><span data-stu-id="e9e35-233">[Common]BaseVMIP</span></span>

- <span data-ttu-id="e9e35-234">網路CorpnetIPPrefixLength</span><span class="sxs-lookup"><span data-stu-id="e9e35-234">[Network]CorpnetIPPrefixLength</span></span>

- <span data-ttu-id="e9e35-235">網路CorpnetDefaultGateway</span><span class="sxs-lookup"><span data-stu-id="e9e35-235">[Network]CorpnetDefaultGateway</span></span>

- <span data-ttu-id="e9e35-236">網路CorpnetDNSIPAddress</span><span class="sxs-lookup"><span data-stu-id="e9e35-236">[Network]CorpnetDNSIPAddress</span></span>

<span data-ttu-id="e9e35-237">以系統管理員身分啟動 PowerShell 主控台，並執行下列 Cmdlet，將 ISO 映像轉換為虛擬硬碟（VHD）：</span><span class="sxs-lookup"><span data-stu-id="e9e35-237">Start a PowerShell console as administrator and run the following cmdlet to convert the ISO image to a virtual hard disk (VHD):</span></span>

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

<span data-ttu-id="e9e35-238">指定 ISO 映像的完整路徑（包括檔案名）。</span><span class="sxs-lookup"><span data-stu-id="e9e35-238">Specify the full path, including file name, to the ISO image.</span></span> <span data-ttu-id="e9e35-239">例如： C:\ISO\WindowsServer2012R2.iso。</span><span class="sxs-lookup"><span data-stu-id="e9e35-239">For example: C:\ISO\WindowsServer2012R2.iso.</span></span>

<span data-ttu-id="e9e35-240">建立的 VHD 檔案儲存在 [**網站目錄**\Bits\VHD] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="e9e35-240">The created VHD file is stored in the **Site Directory** \Bits\VHD folder.</span></span> <span data-ttu-id="e9e35-241">您可以執行**CcSiteDirectory**，以取得**網站目錄**的路徑。</span><span class="sxs-lookup"><span data-stu-id="e9e35-241">You can get the path to the **Site Directory** by running the **Get-CcSiteDirectory**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9e35-242">根據預設，不會在基本 VM 上設定 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="e9e35-242">By default, proxy settings are not configured on the base VM.</span></span> <span data-ttu-id="e9e35-243">如果您的網路環境中需要有 proxy，以透過 Windows Update 更新 VM，您應該在執行 "Convert-CcIsoToVhdx" 時，新增-PauseBeforeUpdate 參數。</span><span class="sxs-lookup"><span data-stu-id="e9e35-243">If a proxy is required in your network environment to update the VM via Windows Update, you should add the -PauseBeforeUpdate switch when you run "Convert-CcIsoToVhdx".</span></span> <span data-ttu-id="e9e35-244">在 Windows 更新之前，腳本會暫停，您將有機會手動設定 VM 上的 proxy。</span><span class="sxs-lookup"><span data-stu-id="e9e35-244">The script will pause before Windows Update and you'll have a chance to manually set up proxy on the VM.</span></span> <span data-ttu-id="e9e35-245">在設定 proxy 並且 VM 可以存取網際網路之後，您可以繼續執行腳本，以完成其餘的步驟。</span><span class="sxs-lookup"><span data-stu-id="e9e35-245">After the proxy is setup and the VM can access Internet, you can resume the script to complete the remaining steps.</span></span> 

### <a name="create-vhds-for-a-multi-site-deployment"></a><span data-ttu-id="e9e35-246">建立多網站部署的 Vhd</span><span class="sxs-lookup"><span data-stu-id="e9e35-246">Create VHDs for a multi-site deployment</span></span>

<span data-ttu-id="e9e35-247">這是選用的步驟，僅適用于多網站部署。</span><span class="sxs-lookup"><span data-stu-id="e9e35-247">This is an optional step that applies only to multi-site deployments.</span></span>

<span data-ttu-id="e9e35-248">若要部署多網站部署，您不需要將 ISO 轉換成每個網站的 VHD。</span><span class="sxs-lookup"><span data-stu-id="e9e35-248">If you are deploying a multi-site deployment, you do not need to convert the ISO to a VHD for each site.</span></span> <span data-ttu-id="e9e35-249">您可以將為第一個網站所建立的 VHDX 複製到第二個網站的主伺服器。</span><span class="sxs-lookup"><span data-stu-id="e9e35-249">You can copy the VHDX created for the first site to the host server for a second site.</span></span>

 <span data-ttu-id="e9e35-250">將檔案複製到另一個網站的主伺服器上的相同檔案位置（**網站目錄**\Bits\VHD 資料夾）及相同檔案名。</span><span class="sxs-lookup"><span data-stu-id="e9e35-250">Copy the file to the same file location ( **Site Directory** \Bits\VHD folder), and with the same file name, on the host server for an additional site.</span></span>

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a><span data-ttu-id="e9e35-251">將 PowerShell 執行原則設定為 RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="e9e35-251">Set the PowerShell Execution policy to RemoteSigned</span></span>

<span data-ttu-id="e9e35-252">提供的 PowerShell 腳本要求將執行原則設定為 RemoteSigned。</span><span class="sxs-lookup"><span data-stu-id="e9e35-252">The PowerShell scripts provided require that the execution policy be set to RemoteSigned.</span></span> <span data-ttu-id="e9e35-253">若要查看目前的設定，請以系統管理員身分開啟 PowerShell 主控台，然後執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e9e35-253">To see the current setting, open a PowerShell console as administrator and then run the following cmdlet:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="e9e35-254">若未設定為 "RemoteSigned，請執行下列 Cmdlet 進行變更：</span><span class="sxs-lookup"><span data-stu-id="e9e35-254">If it is not set to "RemoteSigned," run the following cmdlet to change it:</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a><span data-ttu-id="e9e35-255">變更主機電腦上的本機組策略（版本1.4.1 及更舊版本）</span><span class="sxs-lookup"><span data-stu-id="e9e35-255">Change local Group Policy on the host machine (versions 1.4.1 and earlier)</span></span>

> [!NOTE]
> <span data-ttu-id="e9e35-256">雲端和更新的雲端連接器版本不需要這種工作。</span><span class="sxs-lookup"><span data-stu-id="e9e35-256">This task is not required for Cloud Connector versions 1.4.2 and later.</span></span> 

<span data-ttu-id="e9e35-257">CceService 帳戶是在商務用 Skype Cloud Connector Edition 部署期間建立。</span><span class="sxs-lookup"><span data-stu-id="e9e35-257">The CceService account is created during the Skype for Business Cloud Connector Edition deployment.</span></span> <span data-ttu-id="e9e35-258">它會執行雲端連接器管理服務，並要求卸載 cloudconnector 的許可權。</span><span class="sxs-lookup"><span data-stu-id="e9e35-258">It runs the Cloud Connector Management Service and requires permission to uninstall the cloudconnector.msi.</span></span> <span data-ttu-id="e9e35-259">您必須變更雲端連接器主機機上的「群組原則」設定，以指定使用者登出時不應該卸載使用者登錄。</span><span class="sxs-lookup"><span data-stu-id="e9e35-259">You must change the group policy setting on the Cloud Connector host machine to specify that the user registry should not be unloaded when the user logs off.</span></span> <span data-ttu-id="e9e35-260">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e9e35-260">Follow the steps below:</span></span>

### <a name="to-change-the-group-policy-setting"></a><span data-ttu-id="e9e35-261">若要變更「群組原則」設定</span><span class="sxs-lookup"><span data-stu-id="e9e35-261">To change the Group Policy setting</span></span>

1. <span data-ttu-id="e9e35-262">執行 gpedit.msc，以開啟 [**群組原則編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="e9e35-262">Open the **Group Policy Editor** by running gpedit.msc.</span></span>

2. <span data-ttu-id="e9e35-263">在 [**群組原則編輯器**] 中，流覽至 [系統 > 的系統管理範本 >] UserProfile > 不要在使用者登出時強制卸載使用者登錄。</span><span class="sxs-lookup"><span data-stu-id="e9e35-263">In the **Group Policy Editor**, navigate to Administrative Templates > System > UserProfile > Do not forcefully unload the user registry at user logoff.</span></span> 

3. <span data-ttu-id="e9e35-264">將其值設為 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="e9e35-264">Set its value to **Enabled**.</span></span>

## <a name="set-up-your-office-365-organization"></a><span data-ttu-id="e9e35-265">設定 Office 365 組織</span><span class="sxs-lookup"><span data-stu-id="e9e35-265">Set up your Office 365 organization</span></span>

<span data-ttu-id="e9e35-266">需要 office 365 組織，且需要 Office 365 中的商務用 Skype Online 和電話系統。</span><span class="sxs-lookup"><span data-stu-id="e9e35-266">An Office 365 organization with Skype for Business Online and Phone System in Office 365 is required.</span></span> <span data-ttu-id="e9e35-267">在嘗試使用雲端連接器之前，請確定您的租使用者已設定並設定。</span><span class="sxs-lookup"><span data-stu-id="e9e35-267">Make sure your tenant is set up and configured before attempting to use Cloud Connector.</span></span>

<span data-ttu-id="e9e35-268">某些 Office 365 設定步驟需要您使用租使用者遠端 PowerShell （TRPS）來設定您的 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="e9e35-268">Some Office 365 setup steps require you to use Tenant Remote PowerShell (TRPS) to configure your Office 365 organization.</span></span> <span data-ttu-id="e9e35-269">**這應該安裝在主伺服器上。**</span><span class="sxs-lookup"><span data-stu-id="e9e35-269">**This should be installed on the host server.**</span></span> <span data-ttu-id="e9e35-270">您可以從：[商務用 Skype online、Windows PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)下載 PowerShell 的商務用 skype online 模組。</span><span class="sxs-lookup"><span data-stu-id="e9e35-270">You can download the Skype for Business Online module for PowerShell from: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="e9e35-271">為雲端連接器線上管理建立專用的商務用 Skype 系統管理員帳戶，例如 CceOnlineManagmentAdministrator。</span><span class="sxs-lookup"><span data-stu-id="e9e35-271">Create a dedicated Skype for Business administrator account for Cloud Connector online management, for example CceOnlineManagmentAdministrator.</span></span> <span data-ttu-id="e9e35-272">裝置將使用此帳戶來新增或移除裝置、啟用或停用自動作業系統更新、啟用或停用自動二進位更新。</span><span class="sxs-lookup"><span data-stu-id="e9e35-272">This account will be used by appliance to add or remove appliance, enable or disable automatic OS update, enable or disable automatic binary update.</span></span> <span data-ttu-id="e9e35-273">將此帳戶的密碼設為永不過期，這樣就不需要在每次到期時變更服務。</span><span class="sxs-lookup"><span data-stu-id="e9e35-273">Set the password for this account to never expire so that you do not need to change it for the service each time it expires.</span></span>


