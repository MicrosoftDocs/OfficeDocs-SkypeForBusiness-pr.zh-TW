---
title: 修改現有 Cloud Connector 部署的組態
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 遵循此主題中的步驟，修改現有商務用 Skype Cloud Connector Edition 1.4.1 或更新版本的部署設定。
ms.openlocfilehash: 5d0771e1f6a62015cf040a899c88696016366e47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590007"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>修改現有 Cloud Connector 部署的組態

> [!Important]
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。

遵循此主題中的步驟，修改現有商務用 Skype Cloud Connector Edition 1.4.1 或更新版本的部署設定。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>修改單一網站的設定
<a name="BKMK_SIngleSite"> </a>

如果網站中只有一個裝置，當您想要在部署裝置之後變更設定設定時，您可以修改 CloudConnector.ini 檔案，然後重新開機部署。
  
1. 執行下列 Cmdlet，以卸載主機伺服器上的所有現有虛擬機器： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 執行下列 Cmdlet 以取消登錄裝置：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新裝置目錄中的 CloudConnector.ini 檔案。
    
4. 執行下列 Cmdlet 來更新設定： (此步驟僅適用于版本 2;若為舊版，請跳至下一個步驟。 ) 
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 請執行下列 Cmdlet 重新註冊裝置：
    
   ```powershell
   Register-CcAppliance
   ```

6. 執行下列 Cmdlet 以安裝商務用 Skype Cloud Connector Edition：
    
   ```powershell
   Install-CcAppliance
   ```

如果網站中有一個以上的裝置，您必須遵循下列步驟，修改 CloudConnector.ini 檔案，然後逐個重新部署裝置。
  
1. 執行下列 Cmdlet，以卸載目前裝置上的所有現有虛擬機器： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 執行下列 Cmdlet 以取消登錄裝置：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新裝置目錄中的 CloudConnector.ini 檔案。
    
4. 執行下列 Cmdlet 來更新設定： (此步驟僅適用于版本 2;若為舊版，請跳至下一個步驟。 ) 
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 請執行下列 Cmdlet 重新註冊裝置：
    
   ```powershell
   Register-CcAppliance
   ```

6. 在網站中的所有其他裝置上執行下列 Cmdlet，以挑選最新的設定：
    
   ```powershell
   Publish-CcAppliance
   ```

7. 在目前的裝置上執行下列 Cmdlet 重新部署雲端連接器：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>修改多個網站的設定
<a name="BKMK_MultipleSites"> </a>

若要在部署中修改多個網站的設定，請遵循單一網站的步驟，一次更新一個網站。
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>修改 Microsoft 365 或 Office 365 組織的設定以啟用自動更新
<a name="BKMK_MultipleSites"> </a>

若要啟用作業系統自動更新和 Bits 自動更新，您必須使用商務用 Skype 的承租人系統管理員帳戶進行線上管理，並使用租使用者遠端 PowerShell，如下所示。
  
如果您停用作業系統自動更新或 Bits 自動更新，您的主機和虛擬機器可能會錯過重要的 Windows 更新，而雲端連接器將不會自動升級至新版本。 強烈建議您啟用自動更新。
  
1. 網站的 EnableAutoUpdate 屬性必須設定為 true (預設值) 。 請執行下列 Cmdlet，確定 EnableAutoUpdate 設定為 true：
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. 建立租使用者的自動更新時間範圍。
    
    時段可以是每天、每週及每月。 Windows 所有的時間都需要開始時間和持續時間。
    
   - 針對每日時段，只需要開始時間和持續時間。 
    
   - 若為每週時段，需要天數，其可為一天或多天。
    
   - 在每月的時段中，可能會有兩種類型。 第一種類型是指定一月中的第幾天，也就是一天。 第二種類型是指定每月的周數，也就是一周中的天數，這兩者都可以是單一專案或多個專案。
    
   - 每個租使用者可定義20個時間視窗。 將新租使用者的預設時段，當作作業系統更新和 Bits 更新的預設時間範圍而建立。 執行下列 Cmdlet (s) 設定每日、每週或每月的時間範圍：
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - 將更新時間視窗指派至網站。 
    
     會個別設定 Bits 更新時間與 OS 更新時間視窗。 這兩者都可以指派一或多個時間視窗。 每個時段都可以指派至不同的網站，而不同的目的 (Bits 更新和 OS 更新) 。 執行下列 Cmdlet 來設定網站的時間範圍： 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>更新專用的租使用者系統管理員認證
<a name="BKMK_MultipleSites"> </a>

您可以從具有必要許可權的帳戶，在 Microsoft 365 或 Office 365 組織的雲端連接器中進行管理變更。 在2.0 之前的雲端連接器版本中，該帳戶是專用的全域租使用者管理員帳戶。 在雲端連接器版本2.0 和更新版本中，該帳戶可以是具有商務用 Skype 系統管理員許可權的 Microsoft 365 或 Office 365 帳戶。
  
如果您的系統管理員帳號憑證 Microsoft 365 或 Office 365 中有所變更，您也需要在您部署的每個雲端連接器裝置上執行下列系統管理員 PowerShell 命令，以更新雲端連接器中的本機快取認證：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>更新主伺服器的密碼
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本節適用于雲端連接器版本2.0 和更新版本。 
  
所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "。 當主伺服器上的密碼變更時，您將需要更新本機儲存的認證。
  
若要在雲端連接器裝置上更新本機儲存的認證，請使用 [CcCredential](get-cccredential.md) 和 [CcCredential](set-cccredential.md) 指令程式，然後遵循下列步驟：
  
1. 執行下列命令，以取得稍後需要的密碼： 
    
   - Get-CcCredential AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential AccountType CceService-DisplayPassword
    
2. 變更您的帳戶在主伺服器上的密碼。
    
3. 重新開機主機伺服器。
    
4. 刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "。
    
5. 以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，以在描述之後重新輸入密碼。 請確定輸入的密碼與您在雲端連接器部署之前輸入的密碼相同。
    
根據預設，VmAdmin 和 DomainAdmin 會使用與 CceService 相同的密碼。 如果步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：
  
1. 執行 Set-CcCredential AccountType DomainAdmin，如下所示：
    
1. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
2. 當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 DomainAdmin 密碼的密碼。
    
2. 執行 Set-CcCredential AccountType VmAdmin，如下所示：
    
1. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
2. 當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 VmAdmin 密碼的密碼。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>更新 CceService 帳戶的密碼
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本節適用于雲端連接器2.0.1 版及更新版本。 
  
雲端連接器服務會執行雲端連接器管理服務。 在雲端連接器版本部署期間建立 CceService 帳戶，並儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "和"% 系統磁片% \Programdata\Cloudconnector\credentials..CceService.xml "。
  
為了確保所有裝置都可以存取網站目錄共用，CceService 帳戶的密碼在網站中部署的所有裝置上都必須相同。 請記住下列事項：
  
- 根據預設，CceService 帳戶會設定為「密碼永不到期」。 當您更新密碼時，Microsoft 建議您保留此設定。
    
- 您應該在非峰使用期間更新密碼，並在自動更新時間範圍外更新 bits 或 Windows 更新。 當您更新密碼時，裝置必須耗盡並重新啟動，這需要一些時間。 重新開機裝置會中斷自動更新作業。 
    
- 當您變更 CceService 帳戶密碼時，您必須指定所有的認證，並在本機儲存的檔案中進行更新。 
    
針對屬於相同 PSTN 網站的每一個裝置，您必須指定下列各項： 
  
1. 執行下列命令，以取得稍後將使用的帳戶名稱和密碼：
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. 執行 Enter-CcUpdate Cmdlet 以耗盡裝置，並將其移入手動維護模式。
    
3. 更新主伺服器上 CceService 帳戶的密碼。
    
4. 重新開機主機伺服器。
    
5. 執行 Restore-CcCredentials Cmdlet，以在描述之後重新輸入密碼。 
    
    請確定輸入的密碼與您在雲端連接器部署之前所輸入的密碼相同，但 CceService 帳戶除外。 若為 CceService 帳戶，請輸入新的密碼。 請確定 CceService 帳戶的新密碼對 PSTN 網站中的所有裝置都是相同的。
    
6. 根據預設，VmAdmin 和 DomainAdmin 會使用與 CceService 相同的密碼。 如果步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：
    
7. 執行 Set-CcCredential AccountType DomainAdmin，如下所示：
    
   - 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
   - 當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 DomainAdmin 密碼的密碼。
    
8. 執行 Set-CcCredential AccountType VmAdmin，如下所示：
    
   - 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
   - 當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 VmAdmin 密碼的密碼。 
    
9. 執行 Exit-CcUpdate Cmdlet，將裝置移出手動維護模式。
    
10. 在相同 PSTN 網站中的所有裝置上完成這些步驟之後，請在網站根目錄中刪除下列檔案：
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>新增 SIP 網域
<a name="BKMK_UpdatePassword"> </a>

若要將新的 SIP 網域 (或多個 SIP 網域新增至現有的雲端連接器部署) ，請執行下列操作：
  
1. 請確定您已完成 Microsoft 365 或 Office 365 中的網域更新的步驟，且具有新增 DNS 記錄的能力。 如需如何在 Microsoft 365 或 Office 365 中設定網域的詳細資訊，請參閱[Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 使用新的 SIP 網域或網域更新雲端連接器的設定檔。
    
3. 針對您的雲端連接器設定中所定義的每個 SIP 網域，向新的 Edge 外部憑證要求 sip 的其他 SAN 名稱。 
    
4. 設定新 Edge 外部憑證的路徑，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    依照指示 [修改單一網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 設定或 [修改多個網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)設定。
    
## <a name="modify-the-primary-sip-domain"></a>修改主要 SIP 網域
<a name="BKMK_UpdatePassword"> </a>

如果您需要在您的雲端連接器部署中變更主要 SIP 網域，請執行下列操作：
  
1. 請確定您已完成 Microsoft 365 或 Office 365 中的網域更新的步驟，且具有新增 DNS 記錄的能力。 如需如何在 Microsoft 365 或 Office 365 中設定網域的詳細資訊，請參閱[Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 使用新的 SIP 網域更新雲端連接器的設定檔。
    
3. 針對您的雲端連接器設定中所定義的每個 SIP 網域，向新的 Edge 外部憑證要求 sip 的其他 SAN 名稱。 
    
4. 設定新 Edge 外部憑證的路徑，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    在雲端連接器的系統管理員 PowerShell 中執行下列指令程式，以移除網站中每一個裝置的承租人註冊。
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    在商務用 Skype Online 中執行下列 Cmdlet，以移除每個網站的網站註冊 PowerShell:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    在 Cloud Connector 上的系統管理員 PowerShell 中執行下列 Cmdlet，以卸載每個裝置：
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     在 Cloud Connector 上的系統管理員 PowerShell 中執行下列 Cmdlet，以登錄每個裝置：
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     逐個安裝每一個裝置，在雲端連接器的系統管理員 PowerShell 中執行下列 Cmdlet：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>以新憑證取代外部 Edge 憑證
<a name="BKMK_UpdatePassword"> </a>

當您需要取代雲端連接器裝置上的外部 Edge 憑證時，您必須取得新的 Edge 憑證，準備包含私密金鑰和完整憑證鏈的 PFX 檔案，然後在每個裝置上執行下列動作：
  
1. 使用 Enter-CcUpdate Cmdlet，將裝置置於維護模式。
    
2. 執行下列命令： 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    如果新憑證的密碼與舊憑證相同，則匯入將會成功。 如果密碼不同，您會收到錯誤訊息，指出密碼錯誤，您必須使用-Local 參數執行 Register-CcAppliance Cmdlet 來重設密碼，然後重複步驟2。 
    
4. 使用 CcUpdate 指令程式，讓裝置停止維護模式。
