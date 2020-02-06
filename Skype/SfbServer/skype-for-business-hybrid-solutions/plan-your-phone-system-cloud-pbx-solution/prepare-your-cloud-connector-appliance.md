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
description: 瞭解如何在 Office 365 （雲端 PBX）中，準備您的雲端連接器裝置以進行部署與手機系統搭配使用。
ms.openlocfilehash: 6e6cb71353dc2a2339fe92ce45d0cd3dee9f21a1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814431"
---
# <a name="prepare-your-cloud-connector-appliance"></a>準備 Cloud Connector 設備

瞭解如何在 Office 365 （雲端 PBX）中，準備您的雲端連接器裝置以進行部署與手機系統搭配使用。

本節說明如何取得商務用 Skype 雲端連接器版本安裝檔案、安裝雲端連接器軟體，並準備您的雲端連接器裝置進行部署。 完成本節中的所有步驟之後，您就可以開始為單一網站或多個網站部署雲端連接器。 如果您已有雲端連接器部署，但尚未升級至雲端連接器版本2.1，請參閱[升級至新版雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)。

> [!NOTE]
> Microsoft 支援目前版本的雲端連接器版本2.1。 如果您設定了自動更新，雲端連接器將會自動更新。 如果您已設定手動更新，您將需要在發行前的60天內升級到版本2.1。 Microsoft 將在發行2.1 之後60天支援舊版，以允許您升級。 

> [!NOTE]
> 若是雲端連接器版本2.1 及更新版本，主機裝置必須安裝 .NET Framework 4.6.1 或更新版本。 

> [!IMPORTANT]
> 若要成功地進行部署，當您執行 Cmdlet 來設定商務用 Skype 雲端連接器版本時，請務必使用與您開始時相同的主控台會話。 避免在部署和設定期間切換到不同的會話。 

> [!NOTE]
> 您只會針對部署中的第一個裝置執行一些步驟：建立網站目錄的共用、下載 bits，以及從 Windows Server ISO 映像準備虛擬硬碟（VHDX）檔案。 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>下載商務用 Skype 雲端連接器版安裝程式

1. 在雲端連接器 Vm 將在其上執行的主機伺服器上，下載安裝檔[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)：。 

    > [!IMPORTANT]
    > 在安裝雲端連接器期間，主機伺服器必須能夠存取網際網路，因為在安裝期間會下載其他檔案。 

2. 在安裝期間，請執行安裝程式，並接受預設值。

3. 確認安裝已順利完成。

## <a name="verify-the-installation-and-configure-the-environment"></a>確認安裝並設定環境

1. 以系統管理員身分開啟 PowerShell 主控台，並確認使用下列 Cmdlet 來供應商務用 Skype 雲端連接器版本 Cmdlet：

   ```powershell
   Get-Command *-Cc*
   ```

    該命令應該會傳回商務用 Skype 雲端連接器版本的 Cmdlet 清單。

2. Vhd、SfBBits 及 VersionInfo 檔案將會儲存在**網站目錄**中。

    您可以使用下列 Cmdlet 找到**網站目錄**的位置：

   ```powershell
   Get-CcSiteDirectory
   ```

    該命令應該在您的檔案系統中傳回位置。 位置可以是本機資料夾或檔案共用。 **網站目錄**的預設位置為：%USERPROFILE%\CloudConnector\SiteRoot。 在每個網站建立的第一個裝置上，應將預設位置變更為檔案共用。

    您所選取的位置必須是：

   - 在每個網站建立的第一個裝置上建立。

   - 同一網站中其他主機伺服器（裝置）可存取的共用資料夾。

     若要將**網站目錄**設定為預設以外的位置，請執行下列 Cmdlet：

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    如果您要為網站部署高可用性（HA），請確定您執行的是 Cmdlet，以將**網站目錄**設定為網站中每個主機伺服器上的相同位置。

    當您登入並部署網站中的每個裝置時，請確定您目前的 [登入] 帳戶具備正確的**網站目錄**存取權。

3. **裝置目錄**是商務用 Skype 雲端連接器版本的本機工作根目錄，以及儲存外部憑證、實例及記錄的位置。 預設位置為：%USERPROFILE%\CloudConnector\ApplianceRoot。

    若要尋找**裝置目錄**的位置，請執行下列 Cmdlet：

   ```powershell
   Get-CcApplianceDirectory
   ```

    若要將**裝置目錄**設定為預設以外的位置，請執行下列 Cmdlet：

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    裝置目錄應該設定為裝置上的本機資料夾。 您只應該在啟動商務用 Skype 雲端連接器版本部署之前，先設定**裝置目錄**。 如果您在部署之後進行變更，您將需要重新部署主機伺服器。

    > [!IMPORTANT]
    > **裝置目錄**的路徑不能包含任何空格。

## <a name="set-the-path-for-the-external-edge-certificate"></a>設定外部邊緣憑證的路徑

- 執行下列 Cmdlet，將路徑（包含檔案名）設定為外部邊緣證書。 例如： C:\certs\cce\ap.contoso.com.pfx。 憑證必須包含私用金鑰。

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > 請注意，-Target 參數是舊版1.4.2 及更新版本。 

    指定外部憑證的完整路徑，包括檔案名。 憑證可以儲存在本機或檔案共用中。 如果憑證儲存在共用資料夾中，則必須在每個網站的第一個裝置上建立共用資料夾，且必須可供屬於相同網站的其他裝置存取。 這個 Cmdlet 會將外部憑證複製到**裝置目錄**。

    > [!IMPORTANT]
    > **如果您已更新為雲端連接器版本1.4.2 或**更新版本，請確認準備好的外部憑證包含私密金鑰以及完整的憑證鏈，包括根 CA 憑證及中間 ca 憑證。 **如果您尚未更新為雲端連接器版本 1.4.2**，請確定您準備的外部憑證包含私密金鑰。 這個外部憑證必須由 Windows 信任的憑證頒發機構所頒發。

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>設定外部 PSTN 閘道/SBC 憑證的路徑

如果您使用的是在中繼伺服器與 PSTN 閘道/SBC 之間的 TLS，請執行下列 Cmdlet，將路徑（包括檔案名）設定為閘道憑證。 例如： C:\certs\cce\sbc.contoso.com.cer。 憑證必須包含根 CA 和指派給閘道之憑證的中間鏈：

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> 請注意，-Target 參數是舊版1.4.2 及更新版本。 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>在 Hyper-v 管理員中建立虛擬交換器

1. 開啟 [ **hyper-v Manager** > **虛擬交換器管理器**]，然後選取 [**新增虛擬交換器管理器**]。

2. 建立外部虛擬交換器，並將它系結到與您的內部網路網域連接的物理網路介面卡：

    選取 [**允許管理作業系統與此虛擬交換器共用此網路介面卡**]。

3. 建立外部虛擬交換器，並將它系結到路由至網際網路的物理網路介面卡：

    取消選取 [**允許管理作業系統與此虛擬交換器共用此網路介面卡**]。

4. 設定將周邊網路連接至您的內部網路網域**SFB CCE 網路交換器**的交換器名稱。

    設定將周邊網路連接至網際網路**SFB CCE 網際網路切換**的交換器名稱。

## <a name="update-the-cloudconnectorini-configuration-file"></a>更新 CloudConnector 的設定檔

使用您在 [[商務用 Skype 雲端連接器的方案](plan-skype-for-business-cloud-connector-edition.md)][主題中收集](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)的資訊來準備 CloudConnector 檔案。

若要更新檔案，請先執行下列 Cmdlet 來取得範例範本（CloudConnector）：

```powershell
Export-CcConfigurationSampleFile
```

範例範本會儲存在**裝置目錄**中。

在您的環境值更新之後，請將檔案另存為**裝置目錄**中的 CloudConnector。 您可以執行**CcApplianceDirectory**來判斷**裝置目錄**的路徑。

更新 .ini 檔案時，請考慮下列事項：

> [!NOTE]
> 並非 .ini 檔案的所有值都會在此區段中討論，這裡只講述那些只有特殊考慮的值。 如需完整清單，請參閱在[商務用 Skype 雲端連接器版方案](plan-skype-for-business-cloud-connector-edition.md)中的 [[決定部署參數](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)] 區段主題。 如需有關其他裝置或新網站需要變更之值的詳細資訊，請參閱[與多網站部署相比](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site)，在[雲端連接器中部署多個網站](deploy-multiple-sites-in-cloud-connector.md)的單一網站（HA）。 

- **SiteName：** 預設值為**Site1**。 您必須在部署雲端連接器前進行更新，因為當您執行**CcAppliance 註冊**裝置至現有或新的網站時，此 Cmdlet 會使用**SiteName**來決定要註冊哪個網站。

     如果您想要將裝置註冊到新的網站， **SiteName**的價值必須是唯一的，而且與現有的網站不同。 如果您想要將裝置註冊至現有的網站，則在 .ini 檔案中的**SiteName**的值必須符合您在 Office 365 租使用者設定中定義的名稱。 如果您要將設定檔從一個網站複製到另一個網站，請務必為每個網站的**SiteName**更新此值。

- **伺服器名稱：** 伺服器名稱不應該包含功能變數名稱，且不應超過15個字元。

- **HardwareType：** 如果您沒有設定或將值保留為 null，則會使用**標準**的預設值。 如果您打算部署較大版本的雲端連接器，以支援針對[商務用 Skype 雲端連接器版本規劃](plan-skype-for-business-cloud-connector-edition.md)中的每個主機電腦同時撥打500，請使用 [**標準**模式]。 在支援50同時通話的較小部署中使用 [**最小值**]。

- **網際網路/公司網路/管理虛擬交換器：**：新增您建立的虛擬交換器名稱。 針對管理虛擬交換器，請保留預設值。 部署腳本將會在部署開始時建立管理虛擬交換器，並在部署完成時將它刪除。

- **ManagementIPPrefix：** ManagementIPPrefix 中的 [網路] 區段必須是其他內部 Ip 的不同子網。 例如，如預設值所示，ManagementIPPrefix 是192.168.213.0，而 AD IPAddress 則是192.168.0.238。

    部署腳本會在每個虛擬機器上建立管理網路介面卡、指派管理 IP，然後將其連線至管理虛擬交換器。 這可讓主機伺服器透過此管理網路連線並管理每個虛擬機器。 完成部署時，會刪除管理虛擬交換器。

- **基本 VM 特定配置：** 此區段中的設定必須針對**Convert CcIsoToVhdx** Cmdlet 進行設定。

    在基本 VM 影像準備期間，基底 VM 將會連線到內部網路交換器。 下列設定對於 VM 能夠存取網際網路而言是至關重要的：

  - 常見問題解答BaseVMIP：要指派給基底 VM 的企業電子郵件 IP 位址。

  - 局域網CorpnetDefaultGateway：要指派給基底 VM 的預設閘道。

  - 局域網CorpnetDNSIPAddress：要指派給基底 VM 的 DNS IP 位址。

  - 局域網WSUSServer： Windows Server Update 服務的 IP 位址。

  - 局域網WSUSStatusServer： Windows Server Update Services 狀態伺服器的 IP 位址。

  - 局域網EnableReferSupport：這將會定義在幹線設定上啟用或停用 SIP 對您的 IP/PBX 是否有 SIP。

- **內部 Ip：**

  - 請確定子網路遮罩 CorpnetIPPrefixLength 正確無誤。

  - 請確定這些內部 Ip 沒有 IP 衝突。

- **外部 Ip：**

  - 若是 MR 公用 IP：請為 NAT 的非 NAT 或 ExternalMRPublicIPs 指定 ExternalMRIPs。

  - ExternalSIPIPs 和 ExternalMRIPs 可以是相同的。

  - 請確定子網路遮罩 InternetIPPrefixLength 正確無誤。

  - 請確定這些外部 Ip 沒有 IP 衝突。

- **版**

  - 如果您只有一個閘道，請移除副閘道的節。 如果您有超過兩個閘道，請複製並貼上現有的節，然後進行更新，以建立其他章節。

  - 確認閘道的 IP 位址與埠正確無誤。

  - 若要支援 PSTN 閘道層級 HA，請離開副閘道，然後新增您要使用的任何其他閘道。 您可以複製並貼上現有的專案，然後加以更新。

- 您也可以更新 LocalRoute 值，以限制撥出電話號碼。

## <a name="download-the-bits-to-the-site-directory"></a>下載 bits 至網站目錄

執行下列 Cmdlet，將 bits 與版本資訊檔案下載到**網站目錄**：

```powershell
Start-CcDownload
```

> [!NOTE]
> 您只需要針對第一個裝置執行此步驟。 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>從下載的 ISO 檔案準備基底虛擬磁片（VHDX）

此步驟會從 Windows Server 2012 ISO 映像準備虛擬硬碟（VHDX）檔案。 在部署期間，VHDX 將用來建立虛擬機器。 將會建立暫時的虛擬機器（基本 VM），並會從 ISO 檔案安裝 Windows Server 2012。 建立 VM 之後，將會安裝一些必要的元件，並會套用最新的 Windows 更新。 最後，基本 VM 將會成為一般化（sysprep）並清除，只留下所產生的虛擬磁片檔案。

> [!NOTE]
> 您只需要針對第一個裝置執行此步驟。 

在繼續進行這個步驟之前，請先確定已建立企業用交換器。 此外，請確認 CloudConnector 檔案中的下列設定是否已正確設定：

- 局域網CorpnetSwitchName

- 常見問題解答BaseVMIP

- 局域網CorpnetIPPrefixLength

- 局域網CorpnetDefaultGateway

- 局域網CorpnetDNSIPAddress

以系統管理員身分啟動 PowerShell 主機，並執行下列 Cmdlet，以將 ISO 影像轉換成虛擬硬碟（VHD）：

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

指定 ISO 映像的完整路徑，包括檔案名。 例如： C:\ISO\WindowsServer2012R2.iso。

建立的 VHD 檔案會儲存在 [**網站目錄**\Bits\VHD] 資料夾中。 您可以執行**CcSiteDirectory**，以取得**網站目錄**的路徑。

> [!IMPORTANT]
> 根據預設，不會在基本 VM 上設定 proxy 設定。 如果您的網路環境需要有 proxy，才能透過 Windows Update 來更新 VM，您應該在執行「Convert-CcIsoToVhdx」時，新增-PauseBeforeUpdate 開關。 在 Windows 更新之前，腳本會暫停，您就有機會在 VM 上手動設定 proxy。 在設定 proxy 且 VM 可以存取網際網路之後，您可以繼續執行腳本來完成剩餘的步驟。 

### <a name="create-vhds-for-a-multi-site-deployment"></a>建立多網站部署的 Vhd

這是一個僅適用于多網站部署的選用步驟。

如果您要部署多網站部署，就不需要將 ISO 轉換成每個網站的 VHD。 您可以將針對第一個網站所建立的 VHDX，複製到第二個網站的主伺服器。

 將檔案複製到相同的檔案位置（**網站目錄**\Bits\VHD 資料夾），並使用相同的檔案名在主機伺服器上其他網站。

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>將 PowerShell 執行原則設定為 RemoteSigned

提供的 PowerShell 腳本需要將執行原則設定為 RemoteSigned。 若要查看目前的設定，請以系統管理員身分開啟 PowerShell 主控台，然後執行下列 Cmdlet：

```powershell
Get-ExecutionPolicy
```

如果未設定為 "RemoteSigned"，請執行下列 Cmdlet 加以變更：

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>變更主機電腦上的本機組策略（版本1.4.1 及更舊版本）

> [!NOTE]
> 雲端連接器版本1.4.2 及更新版本不需要這項工作。 

CceService 帳戶是在商務用 Skype 雲端連接器版本部署期間建立。 它會執行雲端連接器管理服務，並需要許可權才能卸載 cloudconnector。 您必須在雲端連接器主機電腦上變更群組原則設定，以指定使用者登出時不應該卸載使用者登錄。 請遵循下列步驟：

### <a name="to-change-the-group-policy-setting"></a>變更群組原則設定

1. 執行 gpedit.msc 來開啟 [**群組原則編輯器**]。

2. 在 [**群組原則編輯器**] 中，流覽至 [系統 > UserProfile] > 的 [管理範本] > 不要在使用者登出時強制卸載使用者登錄。 

3. 將它的值設定為 [**啟用**]。

## <a name="set-up-your-office-365-tenant"></a>設定您的 Office 365 租使用者

需要 Office 365 中的商務用 Skype Online 和手機系統的 Office 365 租使用者。 在嘗試使用雲端連接器前，請確定您的租使用者已設定並設定。

某些 Office 365 設定步驟需要您使用租使用者遠端 PowerShell （TRPS）來設定您的 Office 365 租使用者。 **這應該安裝在主機伺服器上。** 您可以從以下網站下載適用于 PowerShell 的商務用 Skype Online 模組：[商務用 Skype online、Windows PowerShell 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)。

為雲端連接器線上管理建立專用的商務用 Skype 系統管理員帳戶，例如 CceOnlineManagmentAdministrator。 裝置將會使用這個帳戶來新增或移除裝置、啟用或停用自動 OS 更新、啟用或停用自動二進位更新。 將此帳戶的密碼設為永不過期，這樣您就不需要在每次到期時變更服務的密碼。


