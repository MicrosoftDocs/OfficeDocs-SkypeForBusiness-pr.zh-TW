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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 疑難排解 Cloud Connector Edition 部署。
ms.openlocfilehash: 95a3a89e4ae593ffa972f7b5de3891ee94aaeff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623401"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>疑難排解您的 Cloud Connector 部署

> [!Important]
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。
 
疑難排解 Cloud Connector Edition 部署。
  
本主題說明 Cloud Connector Edition 部署常見問題的解決方案。 如果您在撥打/撥出公用交換電話網路 (PSTN) 時遇到問題，您可以遵循本主題中所述的解決方案來進行調查。
  
雲端連接器提供內建的機制，以自動解決某些問題。 自動偵測程式會尋找雲端連接器裝置的潛在問題，如果可能的話，請採取糾正動作來解決這些問題，而不需要系統管理員介入。 偵測過程的運作方式如下：
  
- **偵測順序：** 雲端連接器管理服務每60秒會執行一次處理常式，以偵測裝置是否已停機。 在雲端連接器版本2.0 和更新版本中，偵測程式會使用商務用 Skype 的企業版交換器，以進行 PowerShell 與雲端連接器電腦的連線;在2.0 之前的版本中，偵測程式會使用雲端連接器管理參數。
    
    > [!NOTE]
    > 若要讓自動復原成功，主機和虛擬機器之間的網路連線必須透過主機網路交換器。 請務必檢查網路連線，以確保自動偵測和復原能夠成功。 
  
- **監視：** 以下是在雲端連接器版本2.0 和更新版本中監控的服務：
    
  - 虛擬機器未連接至雲端連接器公司或網際網路虛擬交換器
    
  - 虛擬機器的狀態為已儲存或已停止
    
  - 中央管理伺服器服務：複本、主複本
    
  - 轉送伺服器服務：複本、RTCSRV 及 MEDSVC
    
  - Edge Server services： REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY
    
  - 在 Edge server 上的 CS RTCSRV （轉送伺服器上的 CS RTCMEDSRV）停用輸入防火牆規則
    
    在雲端連接器版本1.4.2 中，只會監控下列服務：
    
  - 轉送伺服器服務： RTCSRV 和 MEDSVC
    
  - Edge Server 服務： RTCSRV
    
- 復原 **處理常式：** 如果任何監控的服務已關機，裝置會標示為已關機，而且服務會停止並標示手動，直到解決所有問題為止。 這會使呼叫無法路由傳送至可能導致呼叫失敗的裝置。
    
    Cloud Connector Management service 會重試自動復原，如下所示
    
  - 初始重試間隔是每10秒，最大間隔時間為一小時。
    
  - 在前三個復原嘗試中，間隔時間為10秒。 從第四個重試開始，間隔時間會增加先前間隔時間的兩倍。 例如，第四次重試會在20秒內發生，第五次則是在40秒內，依此類推。 
    
  - 達到一小時的最大間隔時間時，每小時會繼續嘗試一次。
    
  - 復原成功時，間隔和重試次數會設定為其初始值。
    
  - 如果重新開機管理服務，則間隔和重試次數會重設為其初始值。
    
## <a name="troubleshooting"></a>疑難排解

以下是經常發生問題的解決方案：
  
- **問題：執行部署腳本時，部署失敗或停止回應。登入每個 VM 後，管理/內部/外部 NIC 的 IP 位址遺失或不正確。**
    
    **解決方法：** 無法自動解決此問題。 在執行中時，無法將 Nic 新增至 Vm。 請關閉並移除 hyper-v 管理員中的這些 Vm，然後執行下列 Cmdlet：
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **問題：安裝 Active Directory 伺服器和樹系之後，CMS 伺服器和（或）轉送伺服器並未正確加入網域。**
    
    **解決方法：** 若要解決此問題，請執行下列步驟：
    
  - 登入 Active Directory 伺服器，並確認已正確建立網域。
    
  - 登入 CMS/轉送伺服器，並確認已指派有效的 IP 位址的 [商業網路 NIC]，且有效的靜態 IP 和 DNS 已設定為 AD Server 的 IP 位址。
    
  - 登入 CMS/轉送伺服器，並開啟命令提示字元。 請確定您可以 ping Active Directory 伺服器的 FQDN 和 IP 位址。 否則，可能會發生 IP 位址衝突。 請嘗試為 Active Directory 指派新的 IP，並據此更新 CMS/轉送伺服器上的 DNS。
    
- **問題：您收到下列錯誤訊息：「Remove-VMSwitch：移除虛擬乙太網交換器時失敗。無法刪除虛擬交換器 ' Cloud Connector Management Switch '，因為它正由執行虛擬機器或指派給子集區使用。」**
    
    **解決方法：** 部署之後，「雲端連接器管理參數」並未刪除。 如果您擊中此錯誤，請移至 Hyper-v 管理員，並確認仍然沒有虛擬機器與其連線。 如果虛擬機器仍已連線，請將其中斷連線並刪除管理參數。 若仍無法刪除管理參數，請重新開機主機伺服器，然後再試一次。
    
- **問題：您收到下列錯誤訊息：「無法啟動服務 RTCMRAUTH。請確認服務未停用。**
    
    > [!NOTE]
    > 此問題只適用于1.4.2 之前的雲端連接器版本。 
  
    [無法啟動] 也可能是因為此前端伺服器先前利用電腦容錯移轉) 進行容錯移轉 (。 如果是這種情況，請使用電腦的容錯回復) 來呼叫回 (。
    
    **解決方法：** 當 Edge Server 未根信任 CA 憑證或中間 CA 憑證時，Edge Server 上便會發生此問題。 即使可匯入外部憑證，但憑證鏈中斷。 在此情況下，RTCMRAUTH 和/或 RTCSRV 服務無法啟動。
    
    請將外部憑證的根 CA 憑證和所有中間 CA 憑證，手動匯入 Edge Server，然後重新開機 Edge Server。 在 Edge Server 上看到 RTCMRAUTH 及 RTCSRV 服務後，請回到您的主機伺服器，以系統管理員身分啟動 PowerShell 主控台，然後執行下列 Cmdlet 以切換至新的部署：
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **問題：已套用 Windows 更新時，主伺服器已重新開機，且伺服器所提供的呼叫會失敗。**
    
    **解決方法：** 如果您部署的是高可用性環境，Microsoft 會提供一個 Cmdlet，協助您在手動檢查及安裝 Windows 更新時，將一部主機器 (部署實例) 移入或移出目前的拓撲。 請使用下列步驟來完成這項作業：
    
1. 在主伺服器上，以系統管理員身分啟動 PowerShell 主控台，然後執行：
    
   ```powershell
   Enter-CcUpdate
   ```

2. 檢查是否有更新，並安裝任何可用的。
    
3. 在 PowerShell 主控台中，執行下列 Cmdlet：
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **問題：從使用 PSTN 號碼的商務用 Skype 用戶端進行通話時，邀請其他 PSTN 號碼無法將通話呈報給會議。**
    
    **解決方法：** 若要解決此問題，請參閱 [設定線上混合轉送伺服器設定](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。
    
- **問題：當您安裝 Active Directory server 時，會顯示關於 Windows 更新的警告訊息-"Windows 自動更新未啟用。若要確定已自動更新新安裝的角色或功能，請開啟 Windows 更新]。**
    
    **解決方法：** 使用商務用 Skype 租使用者系統管理員認證啟動租使用者遠端 PowerShell 會話，然後執行下列 Cmdlet 以檢查網站的 _EnableAutoUpdate_ 設定：
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    如果 _EnableAutoUpdate_ 設定為 **True**，您就可以放心忽略此警告訊息，因為 CCEManagement 服務會同時處理針對虛擬機器及主機伺服器的下載及安裝 Windows 更新。 如果  _EnableAutoUpdate_ 設定為 **False**，請執行下列 Cmdlet 將它設定為 **True**。
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    或者，您也可以手動檢查並安裝更新。 請參閱下一節。
    
- **問題：您收到錯誤訊息：無法註冊裝置，因為您目前的輸入/ \<SiteName\> 設定 \<ApplianceName\> 或 \<Mediation Server FQDN\> \<Mediation Server IP Address\> 與現有裝置 (s) 有衝突。移除衝突裝置或更新輸入/設定資訊，然後再註冊一次。' 當執行 Register-CcAppliance，將目前的裝置登錄到線上。**
    
    **解決方法：** 的值 \<ApplianceName\> ， \<Mediation Server FQDN\> 且 \<Mediation Server IP Address\> 必須是唯一的，且僅適用于一個裝置註冊。 根據預設，來自 \<ApplianceName\> 主機名稱。 \<Mediation Server FQDN\> 和 \<Mediation Server IP Address\> 定義在設定 ini 檔案中。
    
    例如，使用 (ApplianceName = MyserverNew，轉送伺服器 FQDN = 10.10.10.10) 以登錄 SiteName = MySite，但是如果有已註冊的裝置 (ApplianceName = Myserver，轉送伺服器 FQDN =，轉送伺服器的 IP 位址 = 10.10.10.10) ，您就會發生衝突。。
    
    首先，請在 ApplianceRoot 目錄區段中檢查您的 CloudConnector.ini 檔案。 您將取得 \<SiteName\> 檔案 \<Mediation Server FQDN\> \<Mediation Server IP Address\> 中的和值。 \<ApplianceName\> 是您的主機伺服器名稱。
    
    其次，使用商務用 Skype 租使用者系統管理員認證來啟動租使用者遠端 PowerShell，然後執行下列 Cmdlet 以檢查已註冊的裝置)  (s。
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    在識別任何衝突之後，您可以使用符合註冊裝置的資訊來更新 CloudConnector.ini 檔案，或取消註冊現有裝置以解決衝突。
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **問題：如果主機上有已部署的裝置，則 Get-CcRunningVersion Cmdlet 會傳回空值。**
    
  **解決方法：** 當您從1.3.4 或1.3.8 升級至1.4.1 時，可能會發生這種情況。 在您使用 .msi 安裝版本1.4.1 之後，您必須先執行， `Register-CcAppliance` 再執行任何其他 Cmdlet。 `Register-CcAppliance` 會將 module.ini 檔案從%UserProfile%\CloudConnector 遷移至%ProgramData%\CloudConnector。 如果您錯過了它，將會在%ProgramData%\CloudConnector 資料夾中建立新的 module.ini，並取代1.3.4 或1.3.8 的執行/備份版本資訊。
    
  比較%UserProfile%\CloudConnector 和%ProgramData%\CloudConnector 資料夾中的 module.ini 檔案。 如果有差異，請刪除%ProgramData%\CloudConnector 中的 module.ini 檔案，然後重新執行  `Register-CcAppliance` 。 您也可以手動將檔案修改為正確的執行和備份版本。
    
- **問題：執行 Switch-CcVersion Cmdlet 以切換到與目前腳本版本不同的舊版本時，此舊版本沒有高可用性支援。**
    
    **解決方法：** 例如，您已從1.4.1 升級到1.4.2。 您目前的腳本版本（可以透過執行 `Get-CcVersion` ）和您的執行版本（這  `Get-CcRunningVersion` 兩種都是1.4.2）所決定。 在此情況下，如果您執行將執行 `Switch-CcVersion` 中的版本切換回1.4.1，則此舊版本將無法提供高可用性支援。
    
    若要取得完整的高可用性支援，請切換回舊版，使執行的版本和腳本版本相同。 如果您遇到1.4.2 部署的問題，請儘快卸載並重新安裝。
    
- **問題：對中央管理存放區、轉送伺服器和 Edge Server 發出的憑證授權憑證或內部憑證接近到期或遭到洩漏。**
    
    **解決方式：** 商務用 Skype 的憑證授權單位憑證是在五年內有效。 發佈至中央管理存放區、轉送伺服器和 Edge Server 的內部憑證是兩年有效。
    
    > [!NOTE]
    > 在雲端連接器版本2.0 和更新版本中，Renew-CcServerCertificate Cmdlet 已變更為 Update-CcServerCertificate，且 Renew-CcCACertificate Cmdlet 已變更為 CcCACertificate。 
  
    如果向中央管理存放區、轉送伺服器和 Edge Server 發行的內部憑證接近到期或遭到損害，請執行 Renew-CcServerCertificate 或 Update-CcServerCertificate Cmdlet 以更新憑證。
    
    如果憑證授權單位憑證接近到期，請執行 Renew-CcCACertificate 或 Update-CcCACertificate Cmdlet 以更新憑證。
    
    **如果憑證授權單位憑證遭到損害，且網站中只有一個裝置，請** 執行下列步驟：
    
1. 執行 Enter-CcUpdate Cmdlet 以排出服務，並將裝置置於維護模式。
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 執行下列 Cmdlet 以重設及建立新的憑證授權單位憑證和所有內部伺服器憑證：
    
    在2.0 之前的雲端連接器版本：
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    或適用于雲端連接器版本2.0 和更新版本：
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. 如果閘道和轉送伺服器之間使用 TLS，請從裝置執行 Export-CcRootCertificate Cmdlet，然後將匯出的憑證安裝到您的 PSTN 閘道。 您可能還需要重新簽發您的閘道上的憑證。

   ```powershell
   Export-CcRootCertificate
   ```

4. 執行 Exit-CcUpdate Cmdlet 以啟動服務並退出維護模式。

   ```powershell
   Exit-CcUpdate
   ```


    **如果憑證授權單位憑證遭到損害，且網站中有多個裝置，請** 在網站的每部裝置中執行下列順序步驟。
    
    Microsoft 建議您在非峰使用時間內執行這些步驟。
    
1. 在第一個裝置上，執行 Remove-CcCertificationAuthorityFile Cmdlet 以清除目錄中的 CA 備份檔案 \<SiteRoot\> 。

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. 執行 Enter-CcUpdate Cmdlet 以排出服務，並將每個裝置置於維護模式。

     ```powershell
     Enter-CcUpdate
     ```
    
3. 在第一個裝置上，執行下列 Cmdlet 以重設及建立新的憑證授權單位憑證和所有內部伺服器憑證：
    
     在2.0 之前的雲端連接器版本：
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     或適用于雲端連接器版本2.0 和更新版本：
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 在第一個裝置上，執行下列 Cmdlet，將 CA 檔案備份到 \<SiteRoot\> 資料夾。
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 在所有其他裝置的相同網站中執行下列命令，以使用 CA 備份檔案，讓裝置都使用相同的根憑證，然後要求新的憑證。 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. 如果閘道和轉送伺服器之間使用 TLS，請從網站中的任何裝置執行 Export-CcRootCertificate Cmdlet，然後將匯出的憑證安裝到您的 PSTN 閘道。 您可能還需要重新簽發您的閘道上的憑證。
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 執行 Exit-CcUpdate Cmdlet 以啟動服務並退出維護模式。 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **問題：您在雲端連接器管理服務記錄中收到下列錯誤訊息： "C:\Program Files \ 商務用 Skype Cloud Connector Edition \ManagementService\CceManagementService.log"： CceService 錯誤：0：向線上報告狀態時出現意外例外狀況： CmdletInvocationException：對使用者登入失敗 \<Global Tenant Admin\> 。請建立新的身分憑證物件，確定您已使用正確的使用者名稱和密碼。---\>**
    
    **解決方法：** 從雲端連接器裝置註冊後，Microsoft 365 或 Office 365 通用租使用者系統管理員認證已變更。 若要在雲端連接器裝置上更新本機儲存的認證，請從主機裝置上的系統管理員 PowerShell 執行下列作業：
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **問題：在您變更用於部署之主機伺服器帳戶的密碼之後，您會收到下列錯誤訊息：「ConvertTo-SecureString：機碼無法使用於指定的狀態」。在%ProgramFiles% \ 商務用 Skype Cloud Connector Edition \ManagementService\CceManagementService.log 或執行 Get-CcCredential 指令程式時。**
    
    **解決方法：** 所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "。 當主伺服器上的密碼變更時，您將需要更新本機儲存的認證。
    
    **如果您正在執行雲端連接器版本1.4.2，請** 遵循下列步驟重新產生所有雲端連接器密碼：
    
  1. 重新開機主機伺服器。
    
  2. 刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "。
    
  3. 以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，以在描述之後重新輸入密碼。 輸入您在雲端連接器部署之前輸入的相同密碼。
    
     **如果您正在執行 Cloud connector 版本2.0 或更新版本，請** 遵循下列步驟來重新產生所有雲端連接器密碼：
    
  4. 重新開機主機伺服器。
    
  5. 刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "。
    
  6. 以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，以在描述之後重新輸入密碼。 
    
     若快取密碼檔是以雲端連接器版本1.4.2 產生，請在提示時使用 CceService 密碼的 VMAdmin 密碼。 輸入您在雲端連接器部署之前輸入的相同密碼，供所有其他帳戶用。
    
     若快取密碼檔是以雲端連接器版本1.4.2 產生，且 DomainAdmin 和 VMAdmin 密碼不同，您必須執行下列步驟：
    
  7. 執行 Set-CcCredential AccountType DomainAdmin，如下所示：
    
  8. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。
    
  9. 當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 DomainAdmin 密碼的密碼。
    
     若快取密碼檔是以 Cloud Connector 版本2.0 或更新版本產生，則根據預設，VmAdmin 和 DomainAdmin 會使用與 CceService 相同的密碼。 如果您變更了 DomainAdmin 和 VMAdmin 密碼，您必須執行下列步驟：
    
  10. 執行 Set-CcCredential AccountType DomainAdmin，如下所示：
    
       1. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證
    
       2. 當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 DomainAdmin 密碼的密碼。
    
  11. 執行 Set-CcCredential AccountType VmAdmin，如下所示：
    
       1. 當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證
    
       2. 當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 VmAdmin 密碼的密碼。 
    
- **問題：使用雲端連接器版本2.1 和更新版本時，當您在裝置上執行 Register-CcAppliance 或其他 Cmdlet 時，會收到錯誤訊息，例如： "For Each-Object：無法在此物件上找到屬性「Common」。確認該屬性存在。C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1： 681 char： 14 "**
    
    **解決方法：** Cloud Connector 2.1 和更新版本需要 .NET Framework 4.6.1 或更新版本。 請將裝置上的 .NET Framework 更新為4.6.1 或更新版本，然後再次執行 Cmdlet () 。

- **問題：使用雲端連接器 Edition 2.1 時，當執行 CcAppliance 時，會收到錯誤訊息，例如：「未能安裝新的實例，錯誤：無法設定「狀態」，因為只有字串可以做為值以設定 XmlNode 屬性」**

   **解決方法：** 在 Cloudconnector.ini 中的 [通用] 區段下，請新增「State」 config，如下所示： CountryCode = US State = 華盛頓市 = Redmond

   「狀態」列必須具有值，但無法從 Cloudconnector.ini 檔移除「狀態」行。

- **問題：您收到下列錯誤訊息：「卸載-WindowsImage： Dismount-WindowsImage 失敗。在安裝或升級 Cloud Connector Edition 時，錯誤代碼 = 0xc1550115 "。**
    
    **解決方法：** 以系統管理員身分啟動 PowerShell 主控台，請執行「DISM-清除-Wim '」。 這會清除所有的 troubled 影像。 請再次執行 Install-CcAppliance，或等候 bits 自動升級。
    
- **問題：在 HA 環境中部署第一個雲端連接器裝置失敗**
    
    **解決方法：** 您採取的步驟取決於部署失敗的原因：
    
  - 如果第一個雲端連接器裝置失敗，而且您無法判斷失敗的原因，則必須重新安裝裝置，直到部署成功為止，然後再安裝其他裝置。
    
  - 如果第一個雲端連接器裝置因次要問題而失敗，例如外部憑證問題，您可能能夠修正問題，而不需重新安裝裝置。 然後，您可以使用租使用者 remote PowerShell，將部署標示為成功，如下所示。  (您也可以在第一次部署成功時使用下列步驟，但由於某些原因，Cloud Connector 無法報告部署成功。 ) 
    
  - 若要取得第一個雲端連接器裝置的身分識別 (GUID) ，請執行 Get-CsHybridPSTNAppliance Cmdlet。
    
  - 若要將裝置標示為已成功部署，請執行 Set-CsCceApplianceDeploymentStatus，如下所示：
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **問題：您需要在主伺服器或虛擬機器上手動檢查並安裝 Windows 更新。**
    
   **解決方法：** 我們建議您利用商務用 Skype Cloud Connector Edition 所提供的自動化作業系統更新。 在註冊裝置以供線上管理及自動作業系統更新啟用之後，主伺服器及虛擬機器將會根據作業系統更新時間視窗設定，自動檢查並安裝 Windows 更新。
    
   如果您需要手動檢查並安裝 Windows 更新，請遵循本節中適用于您的部署類型的步驟。 您應該同時規劃同時更新主機伺服器及同時在其上執行的虛擬機器，以將更新所需的停機時間降至最低。
    
   如果您願意，您可以使用 Windows Server Update Services (WSUS) 伺服器來提供雲端連接器伺服器的更新。 只須確定設定 Windows 更新，**否則不** 會自動安裝。
    
   如需如何手動更新雲端連接器部署的詳細資訊，請參閱下一節。
    
- **問題：當 Cloud Connector 更新至新的組建時，不會更新雲端連接器 Cmdlet。** 當自動更新發生時，當 PowerShell 視窗保持開啟狀態時，有時會發生這種情況。
    
  **解決方法：** 若要載入更新的 Cmdlet，您可以執行下列其中一個步驟：
    
   - 關閉雲端連接器裝置上的 PowerShell，然後重新開啟 PowerShell。
    
     - 或者，您可以 Import-Module CloudConnector-Force 執行。 
 
-   **問題：「字詞 ' Stop-CsWindowsService ' 不會被辨識為 Cmdlet、function、script file 或可執行檔程式的名稱。嘗試執行 Enter-CcUpdate 指令程式時發生錯誤。**

    **解決方法：** 刪除 $HOME \appdata\local\microsoft\ Windows \PowerShell\ModuleAnalysisCache 檔案。
PowerShell 會將此檔案建立為其所找到之模組的指令程式快取，這樣就不必每次重新分析所有的模組，這樣做會使事情變得非常緩慢。 在從該快取中讀取郵件時，可能會有一些檔案損毀，提供要 PowerShell 的誤導結果。

-   **問題： "Import-Module CloudConnector" 產生錯誤 "Import-Module：指定的模組" CloudConnector "未載入，因為在任何模組目錄中找不到有效的模組檔案"**

    **解決方法：**
    - 驗證 CloudConnector 模組是否確實存在於 c:\Program Files\WindowsPowerShell\Modules
    
    - 在驗證 CloudConnector 模組存在於此位置下之後，可以變更儲存模組位置路徑的 PSModulePath 環境變數：
    
     a. 暫時變更：以系統管理員身分啟動 Powershell，並執行下列命令： $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 針對持續變更，以系統管理員身分啟動 PowerShell，並執行下列命令之一： $CurrentValue = [環境]：： GetEnvironmentVariable ( "PSModulePath"，"Machine" ) SetEnvironmentVariable ( "PSModulePath"，$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "，" Machine ") 

    
## <a name="install-windows-updates-manually"></a>手動安裝 Windows 更新

如果您不想要在環境中使用自動更新，請遵循下列步驟，手動檢查並套用 Windows 更新。 檢查並安裝 Windows 更新可能需要重新開機伺服器。 當主機伺服器重新開機時，使用者將無法使用雲端連接器撥打或接聽電話。 您可以手動檢查並安裝更新，以控制更新何時進行，然後在您選擇避免服務中斷時，視需要重新開機電腦。
  
若要手動檢查更新，請連線至每個主機伺服器，然後開啟 [ **控制台**]。 選取 [**系統和安全性 \> Windows 更新**]，然後視您的環境，管理更新和伺服器重新開機。
  
- 如果網站中只有一個裝置，請連接到每一部虛擬機器，然後開啟 [ **控制台**]。 選取 [**系統和安全性 \> Windows 更新**]，然後視需要設定更新和伺服器重新開機。
    
- 如果網站中有多部裝置，則在更新期間，使用者無法存取已更新並重新啟動的實例。 使用者將會連線至部署中的其他實例，直到更新完成後，所有虛擬機器和所有的商務用 Skype 服務都會在虛擬機器上啟動。 若要避免任何可能中斷服務的情況，您可以在應用更新時從 HA 移除實例，然後在完成時還原。 若要這麼做︰
    
1. 在每一部主伺服器上，以系統管理員身分開啟 PowerShell 主控台。
    
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

針對多網站部署，針對部署中的每個網站執行單一網站的步驟，一次套用一個網站的更新。
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>在雲端連接器主機機器上安裝防毒軟體時的提示

如果您需要在雲端連接器主機機器上安裝防毒軟體，您必須新增下列排除專案：
  
- 在每個機器上的本機裝置目錄。
    
- 每個電腦上的遠端網站目錄。
    
- 電腦上的本機網站目錄會裝載共用網站根資料夾。
    
- %ProgramFiles% \ 商務用 Skype Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- 處理常式 Microsoft.Rtc.CCE.ManagementService.exe。