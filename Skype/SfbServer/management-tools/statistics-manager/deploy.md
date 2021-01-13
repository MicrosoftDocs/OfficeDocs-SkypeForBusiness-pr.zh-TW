---
title: 部署商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要：閱讀此主題以瞭解如何部署商務用 Skype Server 的統計資料管理員。
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814813"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>部署商務用 Skype Server 統計資料
 
**摘要：** 閱讀此主題以瞭解如何部署商務用 Skype Server 的統計資料管理員。
  
 商務用 Skype Server 的統計資料管理員是一種強大的工具，可讓您即時查看商務用 Skype 伺服器的健康情況和效能資料。 您可以每隔幾秒輪詢每數百部伺服器上的效能資料，並在統計資料管理員網站上立即查看結果。
  
在您嘗試安裝統計資料管理員之前，請確定您已熟悉軟體、網路及硬體需求。 如需詳細資訊，請參閱 [規劃商務用 Skype Server 的統計資料管理員](plan.md)。
  
> [!NOTE]
> 若要從舊版的統計資料管理員升級，請參閱 [升級統計資料管理員以取得商務用 Skype Server](upgrade.md)。 
  
> [!NOTE]
> 在 Internet Explorer 11 +、Edge 20.10240 + 和 Chrome 46 + (目前的長綠版本) 上，已測試並正確地處理統計資料管理員網站。 
  
您可以在中找到 [統計資料管理員] [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 。 
  
本主題包含下列各節：
  
- [部署統計資料管理員](deploy.md#BKMK_Deploy)
    
- [疑難排解您的部署](deploy.md#BKMK_Troubleshoot)
    
- [建立自我簽署憑證](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>部署統計資料管理員
<a name="BKMK_Deploy"> </a>

若要部署統計資料管理員，請遵循下列步驟：
  
1. 安裝 Redis 的記憶體中快取系統，並確認您已安裝適當的憑證，以準備監聽器主機電腦。
    
2. 在主機機器上安裝監聽器服務。 
    
3. 在主機電腦上安裝網站。
    
4. 在您想要監視的每一部商務用 Skype Server 電腦上安裝代理人。
    
5. 匯入所監控之伺服器的拓撲。
    
> [!NOTE]
> Redis、攔截器服務和網站必須全部安裝在相同的主機電腦上。 請確定主機電腦沒有安裝商務用 Skype 伺服器。 
  
### <a name="prepare-the-listener-host-machine"></a>準備監聽器主機電腦

若要準備主機機，您需要安裝 Redis 的記憶體中快取系統，並確認電腦上有有效的憑證。 Microsoft 建議您安裝 Redis 3.0 的最新穩定組建。 統計資料管理員版本2.0 已透過 Redis 3.2.100 進行測試。 
  
1. 從下列網站下載 Redis： [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) 。 
    
    未簽署的安裝程式可從 [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    如有需要，可透過流行的套件管理員取得已簽署的二進位檔案： [Nuget](https://www.nuget.org/packages/Redis-64/) 和 [Choclatey](https://chocolatey.org/packages/redis-64)。
    
   - 執行提供的 msi 並依照提示執行。
    
   - 請勿勾選 [新增防火牆規則] 方塊。
    
2. 監聽器服務需要憑證。 Microsoft 強烈建議您擁有由受信任的憑證授權單位單位簽署的憑證。 
    
    如果您想要使用自我簽署的憑證，以在實驗室中進行測試，例如，請參閱 [建立自我簽署憑證](deploy.md#BKMK_SelfCert)。
    
    請注意，代理程式會使用憑證指紋驗證 (，而不是鏈式驗證) 。 因為可能會使用自我簽署的憑證，所以不會執行完整的憑證驗證。
    
### <a name="install-the-listener-service"></a>安裝攔截器服務

執行 StatsManPerfAgentListener.msi，並指定下列專案，以在主機機器上安裝監聽器服務：
  
1. 請參閱授權合約，如果同意，請選取 [ **我接受授權合約中的條款**]，然後按 **[下一步]**。 
    
2. 在下一個頁面上，指定下列資訊：
    
   - **服務密碼：** 這是遠端代理程式將用來驗證監聽器服務的密碼。
    
   - **服務埠：** 這是攔截器將用來與代理程式通訊的 HTTPS 埠號碼。 在安裝期間，將會允許透過本機防火牆的埠，建立 URL ACL，並將 SSL 憑證系結至此埠。 預設值為8443。
    
   - **憑證指紋：** 這是監聽器將用來加密 HTTPS 通訊協定的憑證指紋。 網路服務必須具有私密金鑰的讀取權限。
    
     按一下 [ **選取 ...** ] 按鈕，選擇指紋。
    
     您可以使用 [憑證管理員] 或使用下列 PowerShell 命令，找到憑證指紋：
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **安裝目錄：** 這是二進位檔案安裝所在的目錄。 您可以使用 [ **流覽 ...]** 按鈕，將其變更為預設值。
    
   - **AppData 目錄：** 這是用來儲存記錄檔資料夾及其他資料的目錄。 您可以從預設值變更它。 卸載時不會將其刪除。
    
3. 按一下 **安裝**。
    
若要驗證安裝，請執行下列步驟：
  
1. 開啟瀏覽器並流覽至 https://localhost: \<service-port\> /healthcheck/
    
    除非您指定另一個埠) ，否則服務埠預設為 8443 (。
    
2. 若要確定監聽器已正確安裝，請尋找下列專案：
    
   - 如果出現 [healthcheck] 頁面，表示監聽器安裝成功。
    
   - 如果 KnownServerCount 是1或更高版本，就會建立與 Redis 的連接。
    
   - 等候幾分鐘後，至少安裝了一個代理程式之後，請檢查 ValuesWritten 計數器是否為增量。
    
### <a name="install-the-website"></a>安裝網站

執行 StatsManWebSite.msi (隨附于 [商務用 Skype Server，Real-Time 統計資料管理員 (64 位) ](https://www.microsoft.com/en-in/download/details.aspx?id=57518) ，並指定下列專案，以在主機機器上安裝網站：
  
1. 請參閱授權合約，如果同意，請選取 [ **我接受授權合約中的條款**]，然後按 **[下一步]**。 
    
2. 在下一個頁面上，指定下列資訊：
    
   - **服務埠：** 這是網站會接聽的埠號碼。 您可以稍後使用 IIS 管理員系結變更。 在安裝期間，將允許透過本機防火牆的埠。
    
   - **安裝目錄：** 這是二進位檔案安裝所在的目錄。 您可以使用 [ **流覽 ...]** 按鈕，將其變更為預設值。
    
   - **AppData 目錄：** 這是用來儲存記錄檔資料夾及其他資料的目錄。 您可以從預設值變更它。 卸載時不會將其刪除。
    
3. 按一下 **安裝**。
    
若要查看網站，請開啟瀏覽器，然後流覽至： http://localhost ，webport \> /。
  
若只要查看健康資訊，請開啟瀏覽器，然後流覽至： http://localhost: \<webport\> /healthcheck/。
  
網頁埠號碼預設為8080。 您可以使用 IIS 管理員變更網站的埠系結。
  
Web 安裝程式會新增稱為 StatsManWebSiteUsers 的本機安全性群組。 您可以將帳戶新增至此安全性群組，以授與網站的存取權。 
  
### <a name="install-the-agents"></a>安裝代理程式

執行 StatsManPerfAgent.msi 並指定下列專案，以在每個要監視的商務用 Skype 伺服器上安裝代理程式：
  
1. 請參閱授權合約，如果同意，請選取 [ **我接受授權合約中的條款**]，然後按 **[下一步]**。 
    
2. 在下一個頁面上，指定下列資訊：
    
   - **服務密碼：** 這是遠端代理程式將用來驗證監聽器服務的密碼。
    
   - **服務 URI：** 這是攔截器所在的 URI。 它應該使用此 https://name:port 格式。
    
     您可以使用 NETBIOS 名稱或 FQDN。 您可以在監聽器服務上使用同時指定為 **主題** 或 **主體替代名稱** 的名稱，但這不是必要條件。
    
   - **服務指紋：** 這是監聽器所使用之 SSL 憑證的指紋。 代理程式會使用此指紋向監聽器進行驗證。  (因為可能使用自我簽署的憑證，所以不會執行完整的憑證驗證。 ) 
    
   - **安裝目錄：** 這是二進位檔案安裝所在的目錄。 您可以使用 [ **流覽 ...]** 按鈕，將其變更為預設值。
    
   - **AppData 目錄：** 這是儲存 Logs 資料夾及加密 password.txt 檔案的目錄。 您可能會多謝從預設值變更。 卸載時不會將其刪除。
    
3. 按一下 **安裝**。
    
若要在許多機器上安裝代理程式，您可能想要在自動模式中執行這項作業。 例如： 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>匯入拓撲
<a name="BKMK_ImportTopology"> </a>

在安裝並執行統計資料管理員之後，您必須匯入商務用 Skype 伺服器拓撲，使統計資料管理員知道每一部伺服器的網站、集區和角色。 若要匯入商務用 Skype 伺服器拓撲，您將會使用 [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) Cmdlet，以取得組織中所使用之每個集區的相關資訊，然後將此資訊匯入至統計資料管理員。
  
若要匯入商務用 Skype 伺服器拓撲，請遵循下列步驟：
  
1. 在具有商務用 Skype 伺服器的主機上 PowerShell Cmdlet：
    
    a. 執行下列命令： 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. 將 "mypoolinfo.xml" 檔複製到執行監聽器的伺服器。
    
2. 在執行攔截器的主機上：
    
   a. 執行 PowerShell。
    
   b. 流覽至安裝攔截器的目錄。 預設值為： 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. 若要確認要新增及更新的伺服器，請執行下列命令：
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

下列命令可讓您查看所有選項：
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

若要查看您目前匯入的伺服器資訊，請執行下列腳本： 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

如果您想要監視不在商務用 Skype 伺服器拓撲中的伺服器--Exchange 伺服器，您可以在執行監聽器的主機上進行單一伺服器匯入。 若要進行單一伺服器匯入，請遵循下列步驟：
  
1. 流覽至安裝攔截器的目錄。 預設值為： 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 執行下列命令：
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>疑難排解您的部署
<a name="BKMK_Troubleshoot"> </a>

若代理程式無法啟動，請檢查下列事項： 
  
- 代理程式是在統計資料管理員中註冊嗎？
    
    1. 請確認您已遵循匯入拓撲的指示。 請參閱匯 [入拓撲](deploy.md#BKMK_ImportTopology)。
        
    2. 如果代理程式位於拓撲中未列出的伺服器上 (例如，SQL AlwaysOn 叢集中的節點) ，您必須遵循匯 [入拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增代理程式。
    
- 代理程式是否可以與監聽器聯繫？
    
    1. 請確定監聽器服務正在執行中。 
        
        若未執行，請確定 Redis 正在執行，然後嘗試重新開機監聽器。
        
    2. 請確定監聽器服務已開啟埠，且代理人電腦可以與埠通訊。
    
- 若要確定統計資料管理員正在收集資料，您可以檢查 CSV 檔案，如下所示。 
    
    下列命令會檢索計數器儲存名稱： 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    下一個命令會為指定的計數器檢索值： 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

如需您可能會在應用程式事件記錄檔中看到之所有事件的詳細資訊，請參閱 [統計資料管理員以取得商務用 Skype 伺服器的疑難排解](troubleshoot.md)。
  
## <a name="create-a-self-signed-certificate"></a>建立自我簽署憑證
<a name="BKMK_SelfCert"> </a>

Microsoft 強烈建議您使用受信任的憑證授權單位單位所簽署的憑證。 不過，如果您想要使用自我簽署憑證以進行測試，請執行下列操作： 
  
1. 從 PowerShell 主控台，以系統管理員身分登入時，輸入下列專案：
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 類型  `certlm.msc` 。 這會開啟本機電腦的憑證管理員。
    
3. 流覽至 [ **個人**]，然後開啟 [ **憑證**]。
    
4. 以滑鼠右鍵按一下 [ **StatsManListener- \> 所有工作- \> 管理私密金鑰]。**
    
5. 按一下 **[新增]**。
    
6. 在 [ **輸入物件名稱來選取** ] 方塊中，輸入下列專案：網路服務
    
7. 按一下 **[確定]**。
    
8. 在 [ **完全控制**] 底下，取消勾選 [ **允許** ] 核取方塊。 只需要 (讀取權。 ) 
    
9. 按一下 **[確定]**。
    
## <a name="for-more-information"></a>相關資訊
<a name="BKMK_SelfCert"> </a>

如需詳細資訊，請參閱下列各主題：
  
- [商務用 Skype Server 統計資料的規劃](plan.md)
    
- [升級商務用 Skype Server 統計資料](upgrade.md)
    
- [商務用 Skype Server β的統計資料管理員疑難排解](troubleshoot.md)
