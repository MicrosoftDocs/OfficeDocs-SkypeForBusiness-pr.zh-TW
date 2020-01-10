---
title: 疑難排解您的 Cloud Connector 部署
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 針對您的雲端連接器版本部署進行疑難排解。
ms.openlocfilehash: 3edc67d5887c21543e4cbb01a6057a0c657e95e3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002073"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>疑難排解您的 Cloud Connector 部署
 
針對您的雲端連接器版本部署進行疑難排解。
  
本主題將說明雲端連接器版本部署常見問題的解決方案。 如果您在撥打電話給公眾的交換電話網絡（PSTN）中遇到問題，您可以依照本主題中所述的解決方案來調查。
  
雲端連接器提供可自動解決某些問題的內建機制。 自動偵測程式會尋找雲端連接器裝置的潛在問題，如有可能，您可以採取修正動作來解決這些問題，而不需管理員干預。 偵測處理常式的運作方式如下：
  
- **偵測順序：** 雲端連接器管理服務會每隔60秒執行一個處理常式，以偵測裝置是否已關閉。 在雲端連接器版本2.0 及更新版本中，檢測程式會使用商務用 Skype 的 [商務用 Skype] 交換器來建立雲端連接器電腦的 PowerShell 連線;針對2.0 之前的版本，檢測程式會使用雲端連接器管理開關。
    
    > [!NOTE]
    > 若要讓自動復原成功，主機和虛擬機器之間必須有通過主機網路交換器的網路連線。 請務必檢查網路連線，以確保自動偵測和復原能夠成功完成。 
  
- **監控：** 下列服務在雲端連接器版本2.0 和更新版本中受到監視：
    
  - 虛擬機器未連線至雲端連接器公司或網際網路虛擬交換器
    
  - 虛擬機器處於 [已儲存] 或 [已停止] 狀態
    
  - 中央管理伺服器服務：複本、主要
    
  - 中繼伺服器服務： REPLICA、RTCSRV 和 MEDSVC
    
  - Edge 伺服器服務： REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY
    
  - 在 Edge 伺服器上停用針對 CS RTCSRV 的入站防火牆規則，在轉送伺服器上的 CS RTCMEDSRV
    
    在雲端連接器版本1.4.2 中，只會監視下列服務：
    
  - 中繼伺服器服務： RTCSRV 和 MEDSVC
    
  - Edge 伺服器服務： RTCSRV
    
- **修復程式：** 如果任何受監視的服務已關閉，裝置會標示為關閉狀態，而且服務會停止並標示手動，直到所有問題都能解決為止。 這會防止呼叫路由至可能會導致呼叫失敗的裝置。
    
    雲端連接器管理服務將會重試自動復原，如下所示
    
  - 初始重試間隔是每十秒，最大間隔時間為1小時。
    
  - 在前三次的復原嘗試中，間隔時間為10秒。 從第四個重試開始，間隔時間會增加前一個間隔時間的兩倍。 例如，第四次重試會在20秒內執行，在40秒後會發生5次，依此類推。 
    
  - 當達到一個小時的最大間隔時間時，每小時都會繼續進行一次的重試。
    
  - 當復原成功時，間隔和重試計數會設定為其初始值。
    
  - 如果重新開機管理服務，間隔和重試計數會重設為其初始值。
    
## <a name="troubleshooting"></a>疑難排解

以下是經常遇到問題的解決方案：
  
- **問題：執行部署腳本時，部署失敗或停止回應。登入每個 VM 之後，該 IP 位址對於管理/內部/外部 NIC 而言遺失或不正確。**
    
    **解決方式：** 這個問題無法自動解決。 Nic 無法在執行時新增到 Vm 中。 請在 hyper-v manager 中關閉並移除這些 Vm，然後執行下列 Cmdlet：
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **問題：已安裝 Active Directory 伺服器與林之後，CMS 伺服器和/或中繼伺服器無法正確加入網域。**
    
    **解決方式：** 若要解決此問題，請執行下列步驟：
    
  - 登入 Active Directory 伺服器並確認已正確建立網域。
    
  - 登入 CMS/轉送伺服器，並確認已指派 [公司網路 NIC] 的有效 IP 位址，且有效的靜態 IP 和 DNS 已設定為 AD 伺服器的 IP 位址。
    
  - 登入 CMS/轉送伺服器，然後開啟命令提示字元。 請確定您可以 ping Active Directory 伺服器的 FQDN 和 IP 位址。 如果您無法這樣做，可能是 IP 位址發生衝突。 請嘗試為 Active Directory 指派新的 IP，並據此更新 CMS/轉送伺服器上的 DNS。
    
- **問題：您收到下列錯誤訊息：「移除-VMSwitch：移除虛擬乙太網路交換器時失敗。無法刪除虛擬交換器 [雲端連接器管理開關]，因為它正由執行虛擬機器或指派給子池。」**
    
    **解決方式：** 在部署之後，不會刪除「雲端連接器管理開關」。 如果您遇到此錯誤，請移至 Hyper-v 管理器並確認沒有虛擬機器仍與其連線。 如果有虛擬機器仍處於線上狀態，請將它們斷開並刪除管理開關。 如果管理開關仍無法刪除，請重新開機主機伺服器，然後再試一次。
    
- **問題：您收到下列錯誤訊息：「服務 RTCMRAUTH 無法啟動。請檢查以確定該服務未停用。**
    
    > [!NOTE]
    > 這個問題只適用于1.4.2 之前的雲端連接器版本。 
  
    啟動失敗也可能是因為這個前端伺服器先前已失敗（使用電腦容錯移轉）。 如果是這種情況，請喚醒呼叫返回（使用電腦的容錯回復）。
    
    **解決方式：** 當 Edge 伺服器不根信任 CA 憑證或中間 CA 憑證時，在 Edge 伺服器上就會發生此問題。 即使可匯入外部憑證，但已中斷憑證連結。 在這種情況下，RTCMRAUTH 和/或 RTCSRV 服務無法啟動。
    
    請將外部憑證的根 CA 憑證和所有中間 CA 憑證，手動匯入邊緣伺服器，然後重新開機 Edge 伺服器。 當您看到在 Edge 伺服器上開始的 RTCMRAUTH 和 RTCSRV 服務之後，請回到您的主機伺服器，以系統管理員身分啟動 PowerShell 主控台，然後執行下列 Cmdlet 以切換到新的部署：
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **問題：主機伺服器已在已套用 Windows 更新時重新開機，且由伺服器服務的呼叫失敗。**
    
    **解決方式：** 如果您部署了高可用性環境，Microsoft 會提供一個 Cmdlet，在您手動檢查並安裝 Windows 更新時，協助您將一台主機（部署實例）移入或移出目前拓撲。 使用下列步驟來完成此動作：
    
1. 在主機伺服器上，以系統管理員身分啟動 PowerShell 主控台，然後執行：
    
   ```powershell
   Enter-CcUpdate
   ```

2. 檢查是否有任何可用的更新並安裝。
    
3. 在 PowerShell 主控台中，執行下列 Cmdlet：
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **問題：使用 PSTN 號碼從商務用 Skype 用戶端撥打電話時，無法邀請另一個 PSTN 號碼將呼叫升級到會議。**
    
    **解決方式：** 若要解決此問題，請參閱[設定線上混合式轉送轉送伺服器設定](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。
    
- **問題：當您安裝 Active Directory server 時，系統會顯示關於 Windows Update 的警告訊息-「未啟用 Windows 自動更新。若要確保您新近安裝的角色或功能自動更新，請開啟 [Windows Update]。**
    
    **解決方式：** 使用商務用 Skype 租使用者管理員認證啟動租使用者遠端 PowerShell 會話，然後執行下列 Cmdlet 來檢查網站的_EnableAutoUpdate_設定：
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    如果_EnableAutoUpdate_設定為**True**，您可以放心地忽略此警告訊息，因為 CCEManagement 服務將會處理針對虛擬機器與主機伺服器的下載與安裝 Windows 更新。 如果_EnableAutoUpdate_設定為**False**，請執行下列 Cmdlet 將它設定為**True**。
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    或者，您也可以手動檢查並安裝更新。 請參閱下一節。
    
- **問題：您收到錯誤訊息：無法註冊裝置，因為您目前的輸入/ \<配置\> SiteName \<或\> APPLIANCENAME \<或轉送伺服器\> FQDN \<或轉送伺服器 IP\>位址與現有的裝置發生衝突。移除衝突裝置或更新您的輸入/配置資訊，然後再次註冊。' 在執行 Register CcAppliance 時，將目前裝置註冊至線上。**
    
    **解決方式：**\< \>ApplianceName 的\<值，中繼伺服器 FQDN\>和\<轉送伺服器 IP 位址\>必須是唯一的，且僅適用于一個裝置註冊。 根據預設， \<ApplianceName\>來自于主機名稱。 \<在配置 ini\>檔案\<中定義的仲介\>伺服器 FQDN 和轉送伺服器 IP 位址。
    
    例如，使用（ApplianceName = MyserverNew，中繼伺服器 FQDN = ms. contoso，轉送伺服器 IP 位址 = 10.10.10.10）登錄到 SiteName = [我的網站] （ApplianceName = Myserver，轉送伺服器 FQDN =ms.contoso.com、採集轉送伺服器 IP 位址 = 10.10.10.10），就會發生衝突。
    
    首先，請在 ApplianceRoot 目錄區段中查看您的 CloudConnector 檔案。 您將會\<在\>檔案\<中取得網站\>伺服器\<FQDN 和轉送伺服器\> IP 位址值。 \<ApplianceName\>是您的主機伺服器名稱。
    
    接著，使用您的商務用 Skype 租使用者管理員認證啟動承租人遠端 PowerShell，然後執行下列 Cmdlet 來檢查已註冊的裝置。
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    在識別任何衝突之後，您可以使用與已註冊裝置相符的資訊來更新 CloudConnector 檔案，或登出現有裝置以解決衝突。
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **問題：如果在主機上執行已部署的裝置，則 CcRunningVersion Cmdlet 會傳回空值。**
    
  **解決方式：** 當您從1.3.4 或1.3.8 升級至1.4.1 時，可能會發生這種情況。 在使用 .msi 安裝版本1.4.1 之後，您必須先執行`Register-CcAppliance` ，才能執行任何其他 Cmdlet。 `Register-CcAppliance`會將 module 檔案從%UserProfile%\CloudConnector 遷移至%ProgramData%\CloudConnector。 如果您遺漏了這個檔案，將會在%ProgramData%\CloudConnector 資料夾中建立新的 module .ini，並取代1.3.4 或1.3.8 的運行/備份版本資訊。
    
  比較%UserProfile%\CloudConnector 和%ProgramData%\CloudConnector 資料夾中的 boot.ini 檔案。 如果有差異，請在%ProgramData%\CloudConnector 中刪除 module 檔案，然後重新`Register-CcAppliance`執行。 您也可以手動修改檔案至正確的執行與備份版本。
    
- **問題：在您執行 CcVersion Cmdlet 以切換到不同于目前腳本版本的舊版版本之後，此舊版版本沒有高可用性支援。**
    
    **解決方式：** 例如，您已從1.4.1 升級到1.4.2。 您目前的腳本版本（可透過執行來決定`Get-CcVersion`）和執行中的版本，都可以透過執行兩`Get-CcRunningVersion`個1.4.2 來判斷。 此時，如果您執行`Switch-CcVersion`以將執行中的版本切換回1.4.1，就不會有此舊版版本的高可用性支援。
    
    若要取得完整的高可用性支援，請切換回 [1.4.2]，讓執行的版本與腳本版本相同。 如果您的1.4.2 部署遇到問題，請儘快卸載並重新安裝。
    
- **問題：頒發給中央管理商店、中繼伺服器和 Edge 伺服器的憑證授權單位憑證或內部憑證接近到期或遭到破壞。**
    
    **解決方式：** 商務用 Skype 憑證授權單位憑證有效期為五年。 已頒發給中央管理商店、中繼伺服器和 Edge 伺服器的內部憑證有效期為兩年。
    
    > [!NOTE]
    > 在雲端連接器版本2.0 及更新版本中，CcServerCertificate Cmdlet 已變更為 Update-CcServerCertificate，而續租-CcCACertificate Cmdlet 已變更為 Update-CcCACertificate。 
  
    如果將內部憑證頒發給中央管理儲存體、中繼伺服器和 Edge 伺服器的到期或遭到破壞，請執行 CcServerCertificate 或更新 CcServerCertificate Cmdlet 來更新您的憑證。
    
    如果憑證授權單位憑證即將到期，請執行 CcCACertificate 或更新 CcCACertificate Cmdlet 來更新您的憑證。
    
    **如果憑證授權單位憑證遭到破壞，且網站中只有一個裝置，請**執行下列步驟：
    
1. 執行輸入 CcUpdate Cmdlet 來排出服務，並將裝置置於 [維護] 模式。
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 執行下列 Cmdlet 來重設及建立新的憑證授權單位憑證及所有內部伺服器憑證：
    
    在2.0 之前的雲端連接器版本：
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    或者，適用于雲端連接器版本2.0 及更新版本：
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. 如果在閘道與中繼伺服器之間使用 TLS，請從裝置執行 Export CcRootCertificate Cmdlet，然後將匯出的憑證安裝至 PSTN 閘道。 您可能也需要在閘道上重新頒發證書。

   ```powershell
   Export-CcRootCertificate
   ```

4. 執行 CcUpdate Cmdlet 以啟動服務並結束 [維護] 模式。

   ```powershell
   Exit-CcUpdate
   ```


    **如果憑證授權單位憑證遭到破壞，且網站中有多個裝置，請**在網站中的每個裝置上執行下列連續步驟。
    
    Microsoft 建議您在非高峰使用時間執行這些步驟。
    
1. 在第一個裝置上，執行 CcCertificationAuthorityFile Cmdlet，以清除\<SiteRoot\>目錄中的 CA 備份檔案。

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. 執行輸入 CcUpdate Cmdlet 來排出服務，並將每個裝置置於維護模式。

     ```powershell
     Enter-CcUpdate
     ```
    
3. 在第一個裝置上，執行下列 Cmdlet 來重設及建立新的憑證授權單位憑證及所有內部伺服器憑證：
    
     在2.0 之前的雲端連接器版本：
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     或者，適用于雲端連接器版本2.0 及更新版本：
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 在第一個裝置上，執行下列 Cmdlet，將 CA 檔案備份到\<SiteRoot\>資料夾。
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 在所有其他裝置的同一網站中，執行下列命令以使用 CA 備份檔案，讓裝置全都使用相同的根憑證，然後要求新的憑證。 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. 如果在閘道與中繼伺服器之間使用 TLS，請從網站中的任何裝置執行 Export CcRootCertificate Cmdlet，然後將匯出的憑證安裝至 PSTN 閘道。 您可能也需要在閘道上重新頒發證書。
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 執行 CcUpdate Cmdlet 以啟動服務並結束 [維護] 模式。 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **問題：您在雲端連接器管理服務記錄中收到下列錯誤訊息，"C:\Program Files\Skype for Business 雲端連接器 Edition\ManagementService\CceManagementService.log"： CceService 錯誤：0：將狀態報表給 online 時出現意外的例外狀況：系統管理。 CmdletInvocationException：登入使用者全域租\<使用者系統管理員\>失敗。請建立新的認證物件，確認您使用的是正確的使用者名稱和密碼。---\>**
    
    **解決方式：** Office 365 全域租使用者管理員認證已在註冊雲端連接器裝置之後進行變更。 若要在雲端連接器裝置上更新本機儲存的認證，請從主機裝置上的系統管理員 PowerShell 執行下列動作：
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **問題：在您針對部署所用的主機伺服器帳戶變更密碼之後，您會收到下列錯誤訊息：「ConvertTo-SecureString：不能在指定狀態中使用的金鑰」。商務用%ProgramFiles%\Skype 中的雲端連接器Edition\ManagementService\CceManagementService.log 或執行 CcCredential Cmdlet 時的狀態。**
    
    **解決方式：** 所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。 當主機伺服器上的密碼變更時，您將需要更新本機儲存的認證。
    
    **如果您執行的是雲端連接器版本1.4.2，請**依照下列步驟重新產生所有雲端連接器密碼：
    
  1. 重新開機主機伺服器。
    
  2. 刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。
    
  3. 以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，在描述之後重新輸入密碼。 輸入您在雲端連接器部署之前所輸入的密碼。
    
     **如果您執行的是雲端連接器版本2.0 或更新版本，請**遵循下列步驟來重新產生所有雲端連接器密碼：
    
  4. 重新開機主機伺服器。
    
  5. 刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。
    
  6. 以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，在描述之後重新輸入密碼。 
    
     如果使用雲端連接器版本1.4.2 產生快取的密碼檔，請在出現提示時，使用 CceService 密碼的 VMAdmin 密碼。 針對所有其他帳戶，輸入您在雲端連接器部署之前輸入的相同密碼。
    
     如果使用雲端連接器版本1.4.2 產生的快取密碼檔，且 DomainAdmin 和 VMAdmin 密碼不同，您必須執行下列步驟：
    
  7. 執行 CcCredential-AccountType DomainAdmin，如下所示：
    
  8. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
  9. 當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 DomainAdmin 密碼的密碼。
    
     如果使用雲端連接器版本2.0 或更新版本產生的快取密碼檔案，則根據預設，VmAdmin 和 DomainAdmin 使用與 CceService 相同的密碼。 如果您變更了 DomainAdmin 和 VMAdmin 密碼，您必須執行下列步驟：
    
  10. 執行 CcCredential-AccountType DomainAdmin，如下所示：
    
       1. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證
    
       2. 當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 DomainAdmin 密碼的密碼。
    
  11. 執行 CcCredential-AccountType VmAdmin，如下所示：
    
       1. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證
    
       2. 當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 VmAdmin 密碼的密碼。 
    
- **問題：使用雲端連接器版本2.1 及更新版本時，在裝置上執行寄存器 CcAppliance 或其他 Cmdlet 時，您會收到錯誤訊息，例如：「For Each 物件：在這個物件上找不到屬性 ' Common」。確認屬性存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1：681字元： 14 "**
    
    **解決方式：** 雲端連接器2.1 及更新版本需要 .NET Framework 4.6.1 或更新版本。 請將裝置上的 .NET Framework 更新為4.6.1 或更新版本，然後再次執行 Cmdlet。

- **問題：使用雲端連接器版本2.1 時，當您執行安裝 CcAppliance 時，您會收到錯誤訊息，例如：「無法安裝新實例，出現錯誤：無法設定「State」，因為只有字串可以做為值來設定 XmlNode 屬性」**

   **解決方式：** 在 Cloudconnector 的 [常見] 區段底下，請新增「State」 config，如下所示： CountryCode = 美國州 = WA 市 = 雷蒙德

   "State" 行將不是強制性的，但無法從 Cloudconnector 檔案中移除 [省/市/自治區] 行。

- **問題：您收到下列錯誤訊息：「卸載-WindowsImage：卸載-WindowsImage 失敗」。安裝或升級雲端連接器版本時，錯誤碼 = 0xc1550115 "。**
    
    **解決方式：** 以系統管理員身分啟動 PowerShell 主控台，請執行「DISM-清理-Wim」。 這將會清除所有 troubled 影像。 再次執行安裝-CcAppliance，或等待 bits 自動升級。
    
- **問題：在 HA 環境中部署第一個雲端連接器裝置失敗**
    
    **解決方式：** 您所採取的步驟取決於部署失敗的原因：
    
  - 如果第一個雲端連接器裝置發生故障，而且您無法判斷失敗的原因，您必須再次安裝裝置，直到部署成功為止，然後再安裝其他裝置。
    
  - 如果第一個雲端連接器裝置出現問題，例如外部憑證問題，您可能可以修正問題，而不需重新安裝裝置。 然後，您就可以使用租使用者遠端 PowerShell，將部署標示為成功，如下所示。 （如果第一次部署成功，您也可以使用下列步驟，但由於某種原因，雲端連接器無法成功報告部署。）
    
  - 若要取得第一個雲端連接器裝置的身分識別（GUID），請執行 CsHybridPSTNAppliance Cmdlet。
    
  - 若要將裝置標示為已成功部署，請執行設定 CsCceApplianceDeploymentStatus，如下所示：
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **問題：您需要在主機伺服器或虛擬機器上手動檢查並安裝 Windows 更新。**
    
   **解決方式：** 我們建議您利用商務用 Skype 雲端連接器版本所提供的自動作業系統更新。 在裝置註冊以進行線上管理且已啟用自動 OS 更新之後，主機伺服器和虛擬機器將根據 OS 更新時間視窗設定，自動檢查並安裝 Windows 更新。
    
   如果您需要手動檢查並安裝 Windows 更新，請按照本節中適用于您的部署類型的步驟進行。 您應該規劃同時更新主機伺服器與同時執行的虛擬機器，以將更新所需的停機時間降至最低。
    
   如果您想要的話，您可以使用 Windows Server Update Services （WSUS）伺服器來提供雲端連接器伺服器的更新。 只需確認將 Windows 更新設定為 [**不**自動安裝]。
    
   如需如何手動更新雲端連接器部署的相關資訊，請參閱下一節。
    
- **問題：雲端連接器更新至新組建時，不會更新雲端連接器 Cmdlet。** 當自動更新發生時，當 PowerShell 視窗保持開啟時，有時會發生這種情況。
    
  **解決方式：** 若要載入更新的 Cmdlet，您可以執行下列其中一項步驟：
    
   - 在雲端連接器裝置上關閉 PowerShell，然後重新開啟 PowerShell。
    
     - 或者，您可以執行匯入-模組 CloudConnector。 
 
-   **問題：「「Stop-CsWindowsService」這一詞無法辨識為 Cmdlet、函數、腳本檔案或可執行檔程式的名稱。嘗試執行 Enter-CcUpdate Cmdlet 時發生錯誤。**

    **解決方式：** 刪除 $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 檔案。
PowerShell 會將此檔案建立為一個由它所找到之模組的 Cmdlet 的快取，這樣就不必在每次重新分析所有模組，就是使其變得很慢。 很可能是部分檔案損壞，當它從快取回時，在 PowerShell 中提供誤導性的結果。

-   **問題：「匯入-模組 CloudConnector」產生錯誤「匯入-模組：由於在任何模組目錄中都找不到有效的模組檔案，因此無法載入指定的模組 "CloudConnector"**

    **解析**
    - 確認 [c:\Program Files\WindowsPowerShell\Modules] 底下確實存在 CloudConnector 模組
    
    - 在此位置下驗證 CloudConnector 模組之後，可以變更將路徑儲存至模組位置的 PSModulePath 環境變數：
    
     是. 暫時變更：以系統管理員身分啟動 Powershell，然後執行下列命令： $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"
        
     乙. 若要永久性變更，請以系統管理員的身分啟動 PowerShell，然後逐個執行下列命令： $CurrentValue = [環境]：： GetEnvironmentVariable （"PSModulePath"，"Machine"） SetEnvironmentVariable （"PSModulePath"，$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "，" 電腦 "）

    
## <a name="install-windows-updates-manually"></a>手動安裝 Windows 更新

如果您不想在您的環境中使用自動更新，請依照下列步驟手動檢查並套用 Windows 更新。 檢查並安裝 Windows 更新可能需要重新開機伺服器。 當主機伺服器重新開機時，使用者將無法使用雲端連接器來撥打或接聽電話。 您可以在更新進行時，手動檢查並安裝更新，然後在您選擇的時間內，根據需要重新開機電腦，以避免服務中斷。
  
若要手動檢查更新，請連線到每個主機伺服器，然後開啟 [**控制台**]。 選取 [**系統及\>安全性] 視窗更新**，然後根據您的環境管理更新和伺服器重新開機。
  
- 如果網站中只有一個裝置，請連線至每個虛擬機器，然後開啟 [**控制台**]。 選取 [**系統及\>安全性] 視窗更新**，然後視需要設定更新和伺服器重新開機。
    
- 如果網站中有一個以上的裝置，則在更新期間，使用者將無法存取要更新並重新啟動的實例。 使用者會連接到部署中的其他實例，直到所有的虛擬機器和所有的商務用 Skype 服務在更新完成之後，在虛擬機器上開始。 若要避免任何可能的服務中斷，您可以在套用更新時從 HA 中移除該實例，並在完成時將它還原。 若要執行此動作：
    
1. 在每個主機伺服器上，以系統管理員身分開啟 PowerShell 主控台。
    
2. 使用下列 Cmdlet 從 HA 中移除實例：
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    依照單一實例的步驟，手動套用更新並重新啟動虛擬機器。
    
4. 使用下列 Cmdlet，將實例設回 HA：
    
   ```powershell
   Exit-CcUpdate
   ```

針對多網站部署，請針對部署中的每個網站執行單一網站的步驟，一次將更新套用至一個網站。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>在雲端連接器主機電腦上安裝防毒軟體的秘訣

如果您需要在雲端連接器主機電腦上安裝防毒軟體，您必須新增下列排除專案：
  
- 每個電腦上的 [本機裝置目錄]。
    
- 每個電腦上的遠端網站目錄。
    
- 電腦上的本機網站目錄會託管共用網站根資料夾。
    
- 商務用雲端連接器版%ProgramFiles%\Skype
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- 處理常式 ManagementService 的程式。
