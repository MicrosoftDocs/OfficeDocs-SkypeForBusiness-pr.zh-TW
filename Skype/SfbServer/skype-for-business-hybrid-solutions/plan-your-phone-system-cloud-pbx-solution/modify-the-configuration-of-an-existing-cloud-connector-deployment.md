---
title: 修改現有的雲端連接器部署的組態
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
description: 遵循此主題以便修改現有的 Skype 商務雲端連接器 Edition 1.4.1 或更新版本的部署的組態中的步驟。
ms.openlocfilehash: 4c2c0b8ad5340cd4ae4275f1ac009bf3d9d3ec0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018004"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>修改現有的雲端連接器部署的組態
 
遵循此主題以便修改現有的 Skype 商務雲端連接器 Edition 1.4.1 或更新版本的部署的組態中的步驟。 
  
## <a name="modify-the-configuration-of-a-single-site"></a>修改單一站台的組態
<a name="BKMK_SIngleSite"> </a>

如果沒有在網站中，只有一個 appliance 時您想要變更的組態設定，裝置所傳入部署之後，您可以修改 CloudConnector.ini 檔案，並開始重新部署。
  
1. 執行下列 cmdlet 以解除安裝所有現有的主機伺服器上的虛擬機器： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 執行下列 cmdlet 以取消登錄該裝置：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新 CloudConnector.ini 目錄中的檔案應用裝置。
    
4. 執行下列 cmdlet 以更新設定: （時，才適用第 2 版; 舊版此步驟，請跳到下一步）。
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 執行下列 cmdlet 以重新註冊裝置所傳入：
    
   ```powershell
   Register-CcAppliance
   ```

6. 執行下列 cmdlet 以安裝 Skype for Business 雲端連接器版：
    
   ```powershell
   Install-CcAppliance
   ```

如果有多個 appliance 站台中，您需要遵循這些步驟，修改 CloudConnector.ini 檔案，並重新部署設備逐一。
  
1. 執行下列 cmdlet 以解除安裝所有目前 appliance 上現有的虛擬機器： 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. 執行下列 cmdlet 以取消登錄該裝置：
    
   ```powershell
   Unregister-CcAppliance
   ```

3. 更新 CloudConnector.ini 目錄中的檔案應用裝置。
    
4. 執行下列 cmdlet 以更新設定: （時，才適用第 2 版; 舊版此步驟，請跳到下一步）。
    
   ```powershell
   Import-CcConfiguration 
   ```

5. 執行下列 cmdlet 以重新註冊裝置所傳入：
    
   ```powershell
   Register-CcAppliance
   ```

6. 所有其他設備中挑選最新的設定備份的網站上執行下列 cmdlet:
    
   ```powershell
   Publish-CcAppliance
   ```

7. 執行下列 cmdlet 以目前 appliance 上部署雲端連接器：
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>修改多個站台的組態
<a name="BKMK_MultipleSites"> </a>

若要修改的組態中部署多個站台，請依照下列單一站台，一次更新一個站台的步驟。
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>修改 Office 365 租用戶啟用自動更新的組態
<a name="BKMK_MultipleSites"> </a>

若要啟用作業系統自動更新 」 和 「 位元自動更新，您必須使用用 Skype online 管理的企業租用戶系統管理員帳戶及租用戶遠端 PowerShell，如下所示的使用。
  
如果您停用作業系統自動更新 」 或 「 位元自動更新，「 主機 」 和 「 虛擬機器可能遺漏重要的 Windows 更新，以及雲端連接器不會自動升級到新版本。 強烈建議您啟用 [自動更新。
  
1. 站台的 EnableAutoUpdate 屬性必須設為 true （預設值）。 執行下列 cmdlet 以確保 EnableAutoUpdate 設為 true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. 租用戶中建立自動更新時間間隔。
    
    每日、 每週及每月，可以是時間範圍。 所有時間 windows 都需要開始時間] 和 [持續時間。
    
   - 針對每日時間] 視窗中，所需僅 [開始時間] 和 [持續時間。 
    
   - 是每週的時間視窗，所需的一週的天數，可以是一天或數天。
    
   - 針對每月的時間範圍，可以有兩種類型。 第一個類型是指定月份日期，可以是一天。 第二個類型是月的指定、 週，這兩個可以是月的單一項目或多個項目以及星期數。
    
   - 每個租用戶可以有 20 次 windows 定義。 預設的 [時間] 視窗將會建立新租用戶，為作業系統更新] 和 [位元更新預設時間範圍。 執行下列 cmdlet(s) 若要設定的每日、 每週或每月時段：
    
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

   - 將更新時間 windows 指派至網站。 
    
     位元更新時間和 OS 更新時間 windows 會個別設定。 兩者都可以指派單一或多個時間 windows。 每個時間間隔可以指派給不同的站台和不同用途 （位元更新和 OS 更新）。 執行下列 cmdlet 以設定網站的 [時間] 視窗： 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>更新專用的租用戶系統管理員認證
<a name="BKMK_MultipleSites"> </a>

從具有必要的權限的帳戶進行雲端連接器在 Office 365 租用戶中的系統管理變更。 在雲端連接器版本 2.0 之前，該帳戶是專用的全域租用戶系統管理員帳戶。 在雲端連接器版本 2.0 和更新版本，該帳戶可以是 Office 365 帳戶與 Skype 商務系統管理員權限。
  
如果您的系統管理員帳戶認證變更 Office 365 中，您也需要您已部署每個雲端連接器 appliance 上執行下列系統管理員的 PowerShell 命令來更新雲端連接器中的本機快取的認證：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>更新主機伺服器的密碼
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 此區段可用於雲端連接器第 2.0 版及更新版本。 
  
所有雲端連接器認證會都儲存在下列檔案:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml 」。 在主機伺服器上的密碼變更時，您必須更新本機已儲存的認證。
  
若要更新雲端連接器 appliance 上本機已儲存的認證，使用[Get-CcCredential](get-cccredential.md)和[設定 CcCredential](set-cccredential.md)指令程式，請遵循下列步驟：
  
1. 執行下列命令，以擷取您稍後需要密碼： 
    
   - 取得 CcCredential-AccountType DomainAdmin DisplayPassword
    
   - 取得 CcCredential-AccountType VMAdmin DisplayPassword
    
   - 取得 CcCredential-AccountType CceService DisplayPassword
    
2. 變更您在主機伺服器上的帳戶的密碼。
    
3. 重新啟動主應用程式伺服器。
    
4. 刪除下列檔案:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml 」。
    
5. 啟動 PowerShell 主控台，身為管理員，然後再執行 「 註冊 CcAppliance-本機 「 重新輸入密碼描述。 請確定您輸入您所輸入之前的雲端連接器部署相同的密碼。
    
根據預設，VmAdmin 和 DomainAdmin 會使用相同的密碼作為 CceService。 如果步驟 1 中傳回 DomainAdmin、 VMAdmin，以及 CceService 密碼不同，您必須執行下列步驟：
  
1. 執行設定 CcCredential AccountType DomainAdmin 如下所示：
    
1. 時提示輸入舊的帳戶認證，請輸入您用於 CceService 密碼的認證。
    
2. 時提示輸入新的帳戶認證，請在步驟 1 中傳回的 DomainAdmin 密碼輸入密碼。
    
2. 執行設定 CcCredential AccountType VmAdmin 如下所示：
    
1. 時提示輸入舊的帳戶認證，請輸入您用於 CceService 密碼的認證。
    
2. 時提示輸入新的帳戶認證，請在步驟 1 中傳回的 VmAdmin 密碼輸入密碼。 
    
## <a name="update-the-password-for-the-cceservice-account"></a>更新 CceService 帳戶的密碼
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> 此區段可用於雲端連接器 2.0.1 版及更新版本。 
  
雲端連接器服務會執行雲端連接器管理服務。 CceService 帳戶是在雲端連接器 Edition 部署期間建立並儲存在下列檔案:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml 」 和 「 %systemdrive%\programdata\cloudconnector\credentials..CceService.xml 」。
  
若要確保所有設備可以都存取的網站目錄共用，CceService 帳戶的密碼必須部署站台內的所有設備相同。 請記住下列事項：
  
- 根據預設，CceService 帳戶已設定為 「 密碼永不過期 」。 當您更新密碼時，Microsoft 建議保持這種組態。
    
- 您應該在非尖峰使用時段和外部的位元或 Windows 更新的 [自動更新時間 windows 更新密碼。 當您更新密碼時，裝置所傳入必須清空並重新啟動，這需要花一些時間。 重新啟動該裝置將會中斷自動更新作業。 
    
- 當您變更 CceService 帳戶密碼時，您必須指定所有的認證，並加以更新在本機儲存檔案。 
    
屬於相同的 PSTN 網站每個 appliance，您必須指定下列項目： 
  
1. 執行下列命令，以擷取的帳戶名稱和密碼，您將在稍後使用：
    
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

2. 執行 redirect-message appliance，並將它移到手動維護模式 Enter CcUpdate cmdlet。
    
3. 更新主機伺服器上的 CceService 帳戶的密碼。
    
4. 重新啟動主應用程式伺服器。
    
5. 執行還原 CcCredentials 指令程式重新輸入密碼描述。 
    
    請確定您輸入您所輸入之前的雲端連接器部署，但不包括 CceService 帳戶相同的密碼。 CceService 帳戶] 中，輸入新的密碼。 請確定 CceService 帳戶的新密碼是相同的 PSTN 站台中的所有設備。
    
6. 根據預設，VmAdmin 和 DomainAdmin 會使用相同的密碼作為 CceService。 如果步驟 1 中傳回 DomainAdmin、 VMAdmin，以及 CceService 密碼不同，您必須執行下列步驟：
    
7. 執行設定 CcCredential AccountType DomainAdmin 如下所示：
    
   - 時提示輸入舊的帳戶認證，請輸入您用於 CceService 密碼的認證。
    
   - 時提示輸入新的帳戶認證，請在步驟 1 中傳回的 DomainAdmin 密碼輸入密碼。
    
8. 執行設定 CcCredential AccountType VmAdmin 如下所示：
    
   - 時提示輸入舊的帳戶認證，請輸入您用於 CceService 密碼的認證。
    
   - 時提示輸入新的帳戶認證，請在步驟 1 中傳回的 VmAdmin 密碼輸入密碼。 
    
9. 執行結束 CcUpdate cmdlet 來移動裝置所傳入手動維護模式。
    
10. 完成這些步驟在相同的 PSTN 站台中的所有設備之後，刪除的網站根目錄中的下列檔案：
    
    - CcLockFile
    
    - Site_\<Edge 外部 Sip 集區 fqdn\>
    
    - Tenant_\<Edge 外部 Sip 集區 fqdn\>
    
    - TenantConfigLock_\<Edge 外部 Sip 集區 fqdn\>
    
## <a name="add-a-new-sip-domain"></a>新增新的 SIP 網域
<a name="BKMK_UpdatePassword"> </a>

若要新增您現有的雲端連接器部署新的 SIP 網域 （或多個 SIP 網域），執行下列動作：
  
1. 請確定您已完成的步驟來更新 Office 365 中的網域，並有能力新增 DNS 記錄。 如需如何設定 Office 365 中的網域的詳細資訊，請參閱[新增網域至 Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 使用新的 SIP 網域] 或 [網域更新雲端連接器組態檔。
    
3. 要求新的 Edge 外部憑證 sip.domain 每個 SIP 網域雲端連接器組態中所定義的其他 SAN (英文） 名稱。 
    
4. 設定新的 Edge 外部憑證的路徑，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    若要[修改的單一站台組態](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)] 或 [[修改的多個站台組態](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)，請遵循指示。
    
## <a name="modify-the-primary-sip-domain"></a>修改的主要 SIP 網域
<a name="BKMK_UpdatePassword"> </a>

如果您要變更定域機組連接器部署中的主要 SIP 網域，請執行下列動作：
  
1. 請確定您已完成的步驟來更新 Office 365 中的網域，並有能力新增 DNS 記錄。 如需如何設定 Office 365 中的網域的詳細資訊，請參閱[新增網域至 Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
    
2. 使用新的 SIP 網域來更新雲端連接器組態檔。
    
3. 要求新的 Edge 外部憑證 sip.domain 每個 SIP 網域雲端連接器組態中所定義的其他 SAN (英文） 名稱。 
    
4. 設定新的 Edge 外部憑證的路徑，如下所示：
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    移除網站中每個 appliance 的租用戶註冊雲端連接器上系統管理員 PowerShell 中執行下列 cmdlet:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    移除的每個網站的網站註冊商務 Online powershell 中 Skype 執行下列 cmdlet:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    解除安裝每個 appliance 雲端連接器上系統管理員 PowerShell 中執行下列 cmdlet:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     登錄每個 appliance 雲端連接器上系統管理員 PowerShell 中執行下列 cmdlet:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     安裝每個 appliance，一個接著一個，藉由雲端連接器上系統管理員 PowerShell 中執行下列 cmdlet:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>外部邊緣憑證取代為新的憑證
<a name="BKMK_UpdatePassword"> </a>

當您要取代上您雲端連接器設備的外部邊緣憑證時，您必須取得新的邊緣憑證，準備 PFX 檔案包含私密金鑰及整個憑證鏈結，然後執行下列每個 appliance 上：
  
1. 使用 Enter CcUpdate 指令程式會處於維護模式裝置所傳入。
    
2. 執行下列命令： 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    如果舊的相同新憑證的密碼，匯入將會成功。 如果密碼不同，您會收到錯誤，密碼錯誤，且您想要執行註冊 CcAppliance 指令程式重設密碼使用-Local 參數，，然後重複步驟 2。 
    
4. 需要裝置所傳入退出維護模式使用 Exit CcUpdate 指令程式。
    

