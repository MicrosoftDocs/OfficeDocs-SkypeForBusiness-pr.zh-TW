---
title: 準備 Cloud Connector 設備
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
description: 瞭解如何準備您的雲端連接器裝置，以進行部署，並與電話系統 (Cloud PBX) 搭配使用。
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358939"
---
# <a name="prepare-your-cloud-connector-appliance"></a>準備 Cloud Connector 設備

> [!Important]
> 雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。 當您的組織升級至小組後，請瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。

瞭解如何準備您的雲端連接器裝置，以進行部署，並與電話系統 (Cloud PBX) 搭配使用。

本節說明如何取得商務用 Skype 雲端連接器 Edition 安裝檔案、安裝雲端連接器軟體，以及準備用於部署的雲端連接器裝置。 在您完成本節中的所有步驟之後，您就可以為單一網站或多個網站部署雲端連接器。 如果您有現有的雲端連接器部署，但尚未升級為雲端連接器版本2.1，請參閱 [Upgrade to An Cloud connector 的新版本](upgrade-to-a-new-version-of-cloud-connector.md)。

> [!NOTE]
> Microsoft 支援目前版本的 Cloud Connector Edition，版本2.1。 如果您設定了自動更新，Cloud Connector 將會自動更新。 如果您已設定手動更新，您將需要在發行前的60天內，升級至版本2.1。 Microsoft 會在發行2.1 後的60天內支援舊版，以供您升級時間。 

> [!NOTE]
> 若為雲端連接器版本2.1 和更新版本，主機裝置必須已安裝 .NET Framework 4.6.1 或更新版本。 

> [!IMPORTANT]
> 若要順利進行部署，當您執行 Cmdlet 以設定商務用 Skype 雲端連接器 Edition 時，請務必使用與您在中開始的相同主控台會話。 避免在部署及設定期間切換至不同的會話。 

> [!NOTE]
> 您只需針對部署中的第一個裝置執行一些步驟：建立網站目錄的共用、下載 bits，以及準備虛擬硬碟 (VHDX) 來自 Windows Server ISO 映像的檔案。 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>下載商務用 Skype 雲端連接器 Edition 安裝程式

1. 在雲端連接器 Vm 即將執行的主機伺服器上，下載安裝檔案： [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。 

    > [!IMPORTANT]
    > 在安裝雲端連接器期間，主伺服器必須能夠存取網際網路，因為在安裝期間會下載其他檔案。 

2. 執行安裝程式，並在安裝期間接受預設值。

3. 確認安裝已成功完成。

## <a name="verify-the-installation-and-configure-the-environment"></a>驗證安裝及設定環境

1. 以系統管理員身分開啟 PowerShell 主控台，並確認商務用 Skype 雲端連接器 Edition Cmdlet 可使用下列 Cmdlet：

   ```powershell
   Get-Command *-Cc*
   ```

    該命令應該會傳回商務用 Skype 雲端連接器 Edition 的 Cmdlet 清單。

2. Vhd、SfBBits 及 VersionInfo 檔會儲存在 **網站目錄**中。

    您可以使用下列 Cmdlet 找到 **網站目錄** 的位置：

   ```powershell
   Get-CcSiteDirectory
   ```

    命令應該會傳回您的檔案系統中的位置。 該位置可以是本機資料夾或檔案共用。 **網站目錄**的預設位置為：%USERPROFILE%\CloudConnector\SiteRoot。 在每個網站中建立的第一個裝置上，應將預設位置變更為檔案共用。

    您選取的位置必須是：

   - 在每個網站中建立的第一個裝置上建立。

   - 其他主機伺服器存取的共用資料夾， (裝置) 相同的網站中。

     若要將 **網站目錄** 設定為預設以外的位置，請執行下列 Cmdlet：

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    若要為網站部署高可用性 (HA) ，請確定您執行 Cmdlet，將 **網站目錄** 設定為網站中每個主機伺服器上的相同位置。

    當您登入並部署網站中的每個裝置時，請確定您目前的登入帳戶具有 **網站目錄**的正確存取權。

3. **裝置目錄**是商務用 Skype 雲端連接器 Edition 的本機工作根目錄，以及儲存外部憑證、實例及記錄檔的位置。 預設位置為：%USERPROFILE%\CloudConnector\ApplianceRoot。

    若要尋找 **裝置目錄**的位置，請執行下列 Cmdlet：

   ```powershell
   Get-CcApplianceDirectory
   ```

    若要將 **裝置目錄** 設定為預設之外的位置，請執行下列 Cmdlet：

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    裝置目錄應設定為裝置上的本機資料夾。 您應只在啟動商務用 Skype Cloud Connector Edition 部署之前，先設定 **裝置目錄** 。 如果您在部署後變更它，您將需要重新部署主伺服器。

    > [!IMPORTANT]
    > **裝置目錄**的路徑不能包含任何空格。

## <a name="set-the-path-for-the-external-edge-certificate"></a>設定外部 Edge 憑證的路徑

- 執行下列 Cmdlet，將路徑（包括檔案名）設定為外部 Edge 憑證。 例如： C:\certs\cce\ap.contoso.com.pfx。 憑證必須包含私密金鑰。

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > 請注意，-Target 參數是版本1.4.2 和更新版本特有的。 

    指定外部憑證的完整路徑，包含檔案名。 憑證可以儲存在本機或檔案共用上。 如果憑證儲存于共用資料夾中，則必須在每個網站的第一個裝置上建立共用資料夾，而且必須可供屬於相同網站的其他裝置存取。 此 Cmdlet 會將外部憑證複製到 **裝置目錄**。

    > [!IMPORTANT]
    > **如果您已更新 Cloud Connector 版本1.4.2 或更新版本**，請確定準備好的外部憑證包含私密金鑰和完整的憑證鏈，包括根 ca 憑證和中間 ca 憑證。 若尚未**更新為雲端連接器版本 1.4.2**，請確定準備好的外部憑證包含私密金鑰。 此外部憑證必須由 Windows 所信任的憑證授權單位單位所發出。

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>設定外部 PSTN 閘道/SBC 憑證的路徑

如果您是在轉送伺服器和 PSTN 閘道/SBC 之間使用 TLS，請執行下列 Cmdlet，將路徑（包括檔案名）設定為閘道憑證。 例如： C:\certs\cce\sbc.contoso.com.cer。 憑證必須包含根 CA 和指派給閘道之憑證的中間階層：

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> 請注意，-Target 參數是版本1.4.2 和更新版本特有的。 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>在 Hyper-V 管理員中建立虛擬交換器

1. 開啟**Hyper-V 管理員**  >  **虛擬交換器管理員**]，然後選取 [**新增虛擬交換器管理員**]。

2. 建立外部虛擬交換器，並將它系結至連接至您的內部網路網域的實體網路介面卡：

    選取 [ **允許管理作業系統為此虛擬交換器共用此網路介面卡** ]。

3. 建立外部虛擬交換器，並將它系結至路由傳送至網際網路的實體網路介面卡：

    取消選取 [ **允許管理作業系統為此虛擬交換器共用此網路介面卡** ]。

4. 設定將周邊網路連接至內部網路網域的交換器名稱 **SFB CCE**網路的參數。

    設定將周邊網路連接至網際網路 **SFB CCE 網際網路參數**的交換器名稱。

## <a name="update-the-cloudconnectorini-configuration-file"></a>更新 CloudConnector.ini 設定檔

使用您在 [在[商務用 Skype 雲端連接器的方案](plan-skype-for-business-cloud-connector-edition.md)] 中收集的[部署參數](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)中所收集的資訊準備 CloudConnector.ini 檔案。

若要更新檔，請先執行下列 Cmdlet，以取得範例範本 ( # A0) ：

```powershell
Export-CcConfigurationSampleFile
```

範例範本是儲存在 **裝置目錄**中。

在您使用環境的值進行更新後，請將檔案儲存為 **裝置目錄**中的 CloudConnector.ini。 您可以執行 **CcApplianceDirectory** 來決定 **裝置目錄**的路徑。

更新 .ini 檔案時，請考慮下列各項：

> [!NOTE]
> 本節並未討論 .ini 檔案的所有值，這裡只會提及那些具有特殊考慮的值。 如需完整清單，請參閱[Plan For 商務用 Skype 雲端連接器 Edition](plan-skype-for-business-cloud-connector-edition.md)主題中的 [[決定部署參數](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)] 區段。 如需更多有關其他裝置或新網站之值的相關資訊，請參閱 [具有高可用性的單一網站 (HA) 與](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) 主題在 [雲端連接器中部署多個網站](deploy-multiple-sites-in-cloud-connector.md)」中的多網站部署。 

- **SiteName：** 預設值為 **Site1**。 您必須先將它更新，然後再部署雲端連接器，因為當您執行 **CcAppliance** 將裝置登錄至現有或新的網站時，Cmdlet 會使用 **SiteName** 來判斷要註冊的網站。

     如果您想要將裝置登錄至新的網站， **SiteName** 的值必須是唯一的，且與現有的網站不同。 若要將裝置登錄至現有的網站， **SiteName** .ini 檔案中的值必須符合您的 Microsoft 365 或 Office 365 組織設定中所定義的名稱。 若要將設定檔從一個網站複製到另一個網站，請確定為每個網站更新 **SiteName** 的值。

- **ServerName：** 伺服器名稱不應該包含功能變數名稱，且應該限制為15個字元。

- **HardwareType：** 如果您未設定或保留值為 null，則會使用 **標準** 的預設值。 如果您打算部署較大型版本的雲端連接器，以支援500的[商務用 Skype 雲端連接器 Edition](plan-skype-for-business-cloud-connector-edition.md)中所述的，請使用**Normal** 。 使用 **最小值** 進行同時支援50同時通話的部署。

- **網際網路/公司網路/管理虛擬交換器：**：新增您已建立的虛擬交換器名稱。 針對管理虛擬交換器，保留預設值。 部署腳本會在部署開始時建立管理虛擬交換器，並在部署完成時加以刪除。

- **ManagementIPPrefix：** Network 區段中的 ManagementIPPrefix 必須是其他內部 Ip 的不同子網。 例如，預設值會顯示 ManagementIPPrefix 為192.168.213.0，而 AD IPAddress 為192.168.0.238。

    部署腳本會在每一部虛擬機器上建立管理網路介面卡、指派管理 IP，並將其連線至管理虛擬交換器。 這可讓主機伺服器透過此管理網路連接並管理每個虛擬機器。 完成部署時，會刪除管理虛擬交換器。

- **基本 VM 特定設定：** 必須為 **CcIsoToVhdx** Cmdlet 設定本節中的設定。

    在基本 VM 影像準備期間，基本 VM 將會連線至內部網路交換器。 下列設定對 VM 能夠存取網際網路很重要：

  - 相同BaseVMIP：要指派給基底 VM 的公司間 IP 位址。

  - 網路CorpnetDefaultGateway：要指派給基底 VM 的預設閘道。

  - 網路CorpnetDNSIPAddress：要指派給基底 VM 的 DNS IP 位址。

  - 網路WSUSServer： Windows Server Update Service 的 IP 位址。

  - 網路WSUSStatusServer： Windows Server Update Service 狀態伺服器的 IP 位址。

  - 網路EnableReferSupport：這會定義在主幹設定上啟用或停用 SIP 對您 IP/PBX 的 SIP 是否支援。

- **內部 Ip：**

  - 請確定 subnet mask CorpnetIPPrefixLength 是正確的。

  - 請確定這些內部 Ip 沒有任何 IP 衝突。

- **外部 Ip：**

  - 尊敬的公用 IP：針對 NAT，請指定 ExternalMRIPs 的非 NAT 或 ExternalMRPublicIPs。

  - ExternalSIPIPs 與 ExternalMRIPs 可以相同。

  - 請確定 subnet mask InternetIPPrefixLength 是正確的。

  - 請確定這些外部 Ip 沒有任何 IP 衝突。

- **閘道：**

  - 如果您只有一個閘道，請移除次要閘道的區段。 如果您有兩個以上的閘道，請複製並貼上現有的區段，然後更新它，以建立其他章節。

  - 確定閘道 (s) 的 IP 位址及埠正確無誤。

  - 若要支援 PSTN 閘道層級 HA，請離開次要閘道，然後新增您要使用的任何其他閘道。 您可以複製並貼上現有的專案，然後進行更新。

- 您也可以更新 LocalRoute 值以限制撥出電話號碼。

## <a name="download-the-bits-to-the-site-directory"></a>將 bits 下載至網站目錄

執行下列 Cmdlet，將 bits 及版本資訊檔下載至 **網站目錄**：

```powershell
Start-CcDownload
```

> [!NOTE]
> 您只需要為第一個裝置執行此步驟。 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>從下載的 ISO 檔案準備基本虛擬磁片 (VHDX) 

此步驟會從 Windows Server 2012 ISO 映像準備虛擬硬碟 (VHDX) 檔案。 VHDX 將用來在部署期間建立虛擬機器。 將會建立 (基本 VM) 的臨時虛擬機器，且會從 ISO 檔案安裝 Windows Server 2012。 在建立 VM 之後，將會安裝一些必要的元件，並套用最新的 Windows 更新。 最後，基本 VM 將會泛化 (sysprep) 並進行清理，只留下所產生的虛擬磁片檔案。

> [!NOTE]
> 您只需要為第一個裝置執行此步驟。 

在繼續執行此步驟之前，請確定已建立公司間參數。 此外，請確認已在 CloudConnector.ini 檔案中正確設定下列設定：

- 網路CorpnetSwitchName

- 相同BaseVMIP

- 網路CorpnetIPPrefixLength

- 網路CorpnetDefaultGateway

- 網路CorpnetDNSIPAddress

以系統管理員身分啟動 PowerShell 主控台，並執行下列 Cmdlet，將 ISO 映像轉換為虛擬硬碟 (VHD) ：

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

指定 ISO 映像的完整路徑（包括檔案名）。 例如： C:\ISO\WindowsServer2012R2.iso。

建立的 VHD 檔案儲存在 [ **網站目錄** \Bits\VHD] 資料夾中。 您可以執行**CcSiteDirectory**，以取得**網站目錄**的路徑。

> [!IMPORTANT]
> 根據預設，不會在基本 VM 上設定 proxy 設定。 如果您的網路環境中需要有 proxy，以透過 Windows Update 更新 VM，您應該在執行 "Convert-CcIsoToVhdx" 時，新增-PauseBeforeUpdate 參數。 在 Windows 更新之前，腳本會暫停，您將有機會手動設定 VM 上的 proxy。 在設定 proxy 並且 VM 可以存取網際網路之後，您可以繼續執行腳本，以完成其餘的步驟。 

### <a name="create-vhds-for-a-multi-site-deployment"></a>建立多網站部署的 Vhd

這是選用的步驟，僅適用于多網站部署。

若要部署多網站部署，您不需要將 ISO 轉換成每個網站的 VHD。 您可以將為第一個網站所建立的 VHDX 複製到第二個網站的主伺服器。

 將檔案複製到相同的檔案位置 ( 的 **網站目錄** \Bits\VHD 資料夾中) ，並使用相同的檔案名，在其他網站的主伺服器上。

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>將 PowerShell 執行原則設定為 RemoteSigned

提供的 PowerShell 腳本要求將執行原則設定為 RemoteSigned。 若要查看目前的設定，請以系統管理員身分開啟 PowerShell 主控台，然後執行下列 Cmdlet：

```powershell
Get-ExecutionPolicy
```

若未設定為 "RemoteSigned，請執行下列 Cmdlet 進行變更：

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>變更主機電腦上的本機組策略 (版本1.4.1 及更早版本) 

> [!NOTE]
> 雲端和更新的雲端連接器版本不需要這種工作。 

CceService 帳戶是在商務用 Skype Cloud Connector Edition 部署期間建立。 它會執行雲端連接器管理服務，並且需要卸載 cloudconnector.msi 的許可權。 您必須變更雲端連接器主機機上的「群組原則」設定，以指定使用者登出時不應該卸載使用者登錄。 請遵循下列步驟：

### <a name="to-change-the-group-policy-setting"></a>若要變更「群組原則」設定

1. 執行 gpedit.msc，以開啟 [ **群組原則編輯器** ]。

2. 在 [ **群組原則編輯器**] 中，流覽至 [系統 > 的系統管理範本 >] UserProfile > 不要在使用者登出時強制卸載使用者登錄。 

3. 將其值設為 [ **啟用**]。

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>設定您的 Microsoft 365 或 Office 365 組織

需要具有商務用 Skype Online 和電話系統的 Microsoft 365 或 Office 365 組織。 在嘗試使用雲端連接器之前，請確定您的租使用者已設定並設定。

某些 Microsoft 365 和 Office 365 設定步驟需要您使用租使用者 Remote PowerShell (TRPS) 來設定您的 Microsoft 365 或 Office 365 組織。 **這應該安裝在主伺服器上。** 您可以從： [商務用 Skype online、Windows PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)下載 PowerShell 的商務用 skype online 模組。

為雲端連接器線上管理建立專用的商務用 Skype 系統管理員帳戶，例如 CceOnlineManagmentAdministrator。 裝置將使用此帳戶來新增或移除裝置、啟用或停用自動作業系統更新、啟用或停用自動二進位更新。 將此帳戶的密碼設為永不過期，這樣就不需要在每次到期時變更服務。


