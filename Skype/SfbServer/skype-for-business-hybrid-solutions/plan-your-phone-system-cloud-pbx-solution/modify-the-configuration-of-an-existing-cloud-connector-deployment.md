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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 請依照本主題中的步驟，修改現有的商務用 Skype 雲端連接器 Edition 1.4.1 或更新版本的部署設定。
ms.openlocfilehash: 32a231ed85b94c09591adfcc6299cba704be267f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799433"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>修改現有 Cloud Connector 部署的組態
 
請依照本主題中的步驟，修改現有的商務用 Skype 雲端連接器 Edition 1.4.1 或更新版本的部署設定。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>修改單一網站的設定
<a name="BKMK_SIngleSite"> </a>

如果網站中只有一個裝置，而您想要在部署裝置之後變更設定設定，您可以修改 CloudConnector 檔案並再次開始部署。
  
1. 執行下列 Cmdlet 以卸載主機伺服器上所有現有的虛擬機器： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 執行下列 Cmdlet 以取消註冊裝置：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新裝置目錄中的 CloudConnector 檔案。
    
4. 執行下列 Cmdlet 來更新設定：（這個步驟僅適用于版本 2; 適用于舊版），請跳到下一個步驟。）
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 請執行下列 Cmdlet 再次註冊裝置：
    
   ```powershell
   Register-CcAppliance
   ```

6. 執行下列 Cmdlet 來安裝商務用 Skype 雲端連接器版本：
    
   ```powershell
   Install-CcAppliance
   ```

如果網站中有一個以上的裝置，您必須遵循下列步驟，修改 CloudConnector 檔案，然後逐一重新部署裝置。
  
1. 執行下列 Cmdlet 以卸載目前裝置上所有現有的虛擬機器： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 執行下列 Cmdlet 以取消註冊裝置：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新裝置目錄中的 CloudConnector 檔案。
    
4. 執行下列 Cmdlet 來更新設定：（這個步驟僅適用于版本 2; 適用于舊版），請跳到下一個步驟。）
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 請執行下列 Cmdlet 再次註冊裝置：
    
   ```powershell
   Register-CcAppliance
   ```

6. 在網站中的所有其他裝置上執行下列 Cmdlet，以取得最新的設定：
    
   ```powershell
   Publish-CcAppliance
   ```

7. 在目前的裝置上執行下列 Cmdlet 來重新部署雲端連接器：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>修改多個網站的設定
<a name="BKMK_MultipleSites"> </a>

若要在部署中修改多個網站的設定，請遵循單一網站的步驟，一次更新一個網站。
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>修改 Office 365 租使用者的設定以啟用自動更新
<a name="BKMK_MultipleSites"> </a>

若要啟用作業系統自動更新和 Bits 自動更新，您必須使用商務用 Skype 租使用者系統管理員帳戶進行線上管理，並使用租使用者遠端 PowerShell，如下所示。
  
如果您已停用作業系統自動更新或 Bits 自動更新，您的主機和虛擬機器可能會錯過重要的 Windows 更新，而雲端連接器將無法自動升級至新版本。 強烈建議您啟用自動更新。
  
1. 網站的 EnableAutoUpdate 屬性必須設定為 true （預設值）。 請執行下列 Cmdlet，確認 EnableAutoUpdate 已設定為 true：
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. 建立租使用者的自動更新時間範圍。
    
    時間範圍可以是 [每日]、[每週] 和 [每月]。 所有時間視窗都需要開始時間和持續時間。
    
   - 針對每日時間範圍，只需要 [開始時間] 和 [持續時間]。 
    
   - 針對每週時間視窗，需要星期幾，可以是一天或幾天。
    
   - 針對每月的時間範圍，可以有兩種類型。 第一種類型是指定月份中的日期，這可以是一天。 第二種類型是指定月份的周數，以及每週的天數，兩者都可以是單一專案或多個專案。
    
   - 每個租使用者都可以定義20個時間視窗。 系統會針對新的租使用者建立預設時間視窗，作為作業系統更新和 Bits 更新的預設時間範圍。 執行下列 Cmdlet 來設定 [每日]、[每週] 或 [每月] 時間範圍：
    
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

   - 指派更新時間視窗至網站。 
    
     Bits 更新時間與 OS 更新時間視窗是單獨設定的。 這兩者都可以指派為單一或多個時間視窗。 每個時間視窗都可以指派給不同的網站，以及不同用途（Bits 更新與 OS 更新）。 執行下列 Cmdlet 來設定網站的時間範圍： 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>更新專用租使用者管理員認證
<a name="BKMK_MultipleSites"> </a>

雲端連接器的 Office 365 租使用者的系統管理變更是從擁有所需許可權的帳戶中進行。 在2.0 之前的雲端連接器版本中，該帳戶是專用的全域租使用者管理員帳戶。 在雲端連接器版本2.0 及更新版本中，該帳戶可以是擁有商務用 Skype 系統管理員許可權的 Office 365 帳戶。
  
如果您的系統管理員帳號憑證變更在 Office 365 中，您也需要在部署的每個雲端連接器裝置上執行下列系統管理員 PowerShell 命令，以更新雲端連接器中的本機快取認證：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>更新主機伺服器的密碼
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本節適用于雲端連接器版本2.0 及更新版本。 
  
所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。 當主機伺服器上的密碼變更時，您將需要更新本機儲存的認證。
  
若要在雲端連接器裝置上更新本機儲存的認證，請使用[CcCredential](get-cccredential.md)和[CcCredential](set-cccredential.md) Cmdlet，然後依照下列步驟進行：
  
1. 執行下列命令，以在稍後檢索您需要的密碼： 
    
   - CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - CcCredential-AccountType VMAdmin-DisplayPassword
    
   - CcCredential-AccountType CceService-DisplayPassword
    
2. 變更主機伺服器上您帳戶的密碼。
    
3. 重新開機主機伺服器。
    
4. 刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。
    
5. 以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，在描述之後重新輸入密碼。 請務必輸入您在雲端連接器部署之前所輸入的密碼。
    
根據預設，VmAdmin 和 DomainAdmin 使用與 CceService 相同的密碼。 如果在步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：
  
1. 執行 CcCredential-AccountType DomainAdmin，如下所示：
    
1. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
2. 當系統提示您輸入新的帳號憑證時，請輸入步驟1中傳回之 DomainAdmin 密碼的密碼。
    
2. 執行 CcCredential-AccountType VmAdmin，如下所示：
    
1. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
2. 當系統提示您輸入新的帳號憑證時，請輸入步驟1中傳回之 VmAdmin 密碼的密碼。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>更新 CceService 帳戶的密碼
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 本節適用于雲端連接器版本2.0.1 及更新版本。 
  
雲端連接器服務會執行雲端連接器管理服務。 CceService 帳戶是在雲端連接器版本部署期間建立，並儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.Xml "和"%SystemDrive%\Programdata\Cloudconnector\credentials。。CceService "。
  
若要確保所有裝置都能存取網站目錄共用，在網站中部署的所有裝置上，CceService 帳戶的密碼都必須相同。 請記住下列事項：
  
- 根據預設，CceService 帳戶會設定為「密碼永不過期」。 更新密碼時，Microsoft 建議您保留此設定。
    
- 您應該在非高峰使用期間更新密碼，並在自動更新時間範圍之外的 bits 或 Windows 更新。 當您更新密碼時，裝置必須排出並重新啟動，這需要一些時間。 重新開機裝置將會中斷自動更新作業。 
    
- 當您變更 CceService 帳戶密碼時，您必須指定所有認證，並在本機儲存的檔案中進行更新。 
    
針對屬於同一個 PSTN 網站的每個裝置，您必須指定下列專案： 
  
1. 執行下列命令，以取得您稍後會用到的帳戶名稱和密碼：
    
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

2. 執行輸入 CcUpdate Cmdlet 來排出裝置，並將它移到 [手動維護模式]。
    
3. 更新主機伺服器上的 CceService 帳戶密碼。
    
4. 重新開機主機伺服器。
    
5. 執行 Restore CcCredentials Cmdlet，以在描述之後重新輸入密碼。 
    
    請確認您輸入的密碼與您在雲端連接器部署之前所輸入的密碼相同，但 CceService 帳戶除外。 針對 CceService 帳戶，輸入您的新密碼。 請確定 CceService 帳戶的新密碼對於 PSTN 網站中的所有裝置都是相同的。
    
6. 根據預設，VmAdmin 和 DomainAdmin 使用與 CceService 相同的密碼。 如果在步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：
    
7. 執行 CcCredential-AccountType DomainAdmin，如下所示：
    
   - 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
   - 當系統提示您輸入新的帳號憑證時，請輸入步驟1中傳回之 DomainAdmin 密碼的密碼。
    
8. 執行 CcCredential-AccountType VmAdmin，如下所示：
    
   - 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
   - 當系統提示您輸入新的帳號憑證時，請輸入步驟1中傳回之 VmAdmin 密碼的密碼。 
    
9. 執行 Exit CcUpdate Cmdlet，將裝置移出手動維護模式。
    
10. 在同一 PSTN 網站中的所有裝置上完成這些步驟之後，請在網站根目錄中刪除下列檔案：
    
    - CcLockFile
    
    - Site_\<邊緣外部 Sip 池 fqdn\>
    
    - Tenant_\<邊緣外部 Sip 池 fqdn\>
    
    - TenantConfigLock_\<邊緣外部 Sip 池 fqdn\>
    
## <a name="add-a-new-sip-domain"></a>新增 SIP 網域
<a name="BKMK_UpdatePassword"> </a>

若要將新的 SIP 網域（或多個 SIP 網域）新增到您現有的雲端連接器部署，請執行下列動作：
  
1. 請確定您已完成 Office 365 中更新網域的步驟，並具備新增 DNS 記錄的功能。 如需如何在 Office 365 中設定網域的詳細資訊，請參閱[將網域新增至 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 使用新的 SIP 網域或網域更新雲端連接器設定檔。
    
3. 針對您的雲端連接器設定中定義的每個 SIP 網域，要求新的 Edge 外部憑證。 
    
4. 針對新的邊緣外部憑證設定路徑，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    依照指示來[修改單一網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)設定，或[修改多個網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)設定。
    
## <a name="modify-the-primary-sip-domain"></a>修改主要 SIP 網域
<a name="BKMK_UpdatePassword"> </a>

如果您需要在雲端連接器部署中變更主要 SIP 網域，請執行下列動作：
  
1. 請確定您已完成 Office 365 中更新網域的步驟，並具備新增 DNS 記錄的功能。 如需如何在 Office 365 中設定網域的詳細資訊，請參閱[將網域新增至 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 使用新的 SIP 網域更新雲端連接器設定檔。
    
3. 針對您的雲端連接器設定中定義的每個 SIP 網域，要求新的 Edge 外部憑證。 
    
4. 針對新的邊緣外部憑證設定路徑，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    在雲端連接器上的系統管理員 PowerShell 中執行下列 Cmdlet，以移除網站中每個裝置的租使用者註冊：
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    在商務用 Skype Online PowerShell 中執行下列 Cmdlet，以移除每個網站的網站註冊：
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    在雲端連接器上的系統管理員 PowerShell 中執行下列 Cmdlet，以卸載每個裝置：
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     在雲端連接器上的系統管理員 PowerShell 中執行下列 Cmdlet，以登錄每個裝置：
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     透過在雲端連接器上的系統管理員 PowerShell 中執行下列 Cmdlet，逐個安裝每個裝置：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>以新憑證取代外部邊緣憑證
<a name="BKMK_UpdatePassword"> </a>

當您需要取代雲端連接器裝置上的外部邊緣憑證時，您必須取得新的邊緣憑證、準備包含私人金鑰和完整憑證連結的 PFX 檔案，然後在每個裝置上執行下列動作：
  
1. 使用 Enter CcUpdate Cmdlet 將裝置置於 [維護] 模式。
    
2. 執行下列命令： 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    如果新憑證的密碼與舊版相同，則會成功匯入。 如果密碼不同，您會收到錯誤訊息，指出密碼錯誤，而且您必須執行 CcAppliance Cmdlet 與-Local 參數，然後重複步驟2，以重設密碼。 
    
4. 使用 CcUpdate Cmdlet 讓裝置離開維護模式。
    

