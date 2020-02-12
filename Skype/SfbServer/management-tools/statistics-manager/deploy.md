---
title: 部署商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要：請閱讀本主題，以瞭解如何部署商務用 Skype Server 的統計資料管理器。
ms.openlocfilehash: 008e9d56dd4c795f7e524ac927402d99261f3e75
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888422"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>部署商務用 Skype Server 統計資料
 
**摘要：** 若要瞭解如何部署商務用 Skype Server 的統計資料管理器，請閱讀本主題。
  
 商務用 Skype Server 的 [統計資料管理員] 是一種強大的工具，可讓您即時查看商務用 Skype Server 健康情況和效能資料。 您可以每隔幾秒在數百個伺服器上輪詢效能資料，並立即在統計資料管理器網站上查看結果。
  
在您嘗試安裝 [統計資料管理器] 之前，請務必熟悉軟體、網路和硬體需求。 如需詳細資訊，請參閱[規劃商務用 Skype Server 的統計管理員方案](plan.md)。
  
> [!NOTE]
> 如果您是從舊版的統計資料管理員升級，請參閱[商務用 Skype Server 的升級統計資料管理器](upgrade.md)。 
  
> [!NOTE]
> [統計資料管理器] 網站已在 Internet Explorer 11 +、Edge 20.10240 + 和 Chrome 46 + （目前的長綠版本）上經過測試和正常運作。 
  
您可以在[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)下載 [統計資料管理器] 中找到。 
  
本主題包含下列各節：
  
- [部署統計資料管理員](deploy.md#BKMK_Deploy)
    
- [疑難排解您的部署](deploy.md#BKMK_Troubleshoot)
    
- [建立自我簽署憑證](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>部署統計資料管理員
<a name="BKMK_Deploy"> </a>

若要部署統計管理員，請遵循下列步驟：
  
1. 您可以安裝 Redis 的記憶體內部緩存系統，並確保您已安裝適當的憑證，以準備監聽器主機電腦。
    
2. 在主機電腦上安裝監聽器服務。 
    
3. 在主機電腦上安裝網站。
    
4. 在您想要監視的每個商務用 Skype 伺服器電腦上安裝代理程式。
    
5. 匯入您要監視之伺服器的拓撲。
    
> [!NOTE]
> Redis、監聽器服務和網站必須全部安裝在同一個主機電腦上。 確定主機電腦沒有安裝商務用 Skype 伺服器。 
  
### <a name="prepare-the-listener-host-machine"></a>準備監聽器主機機

若要準備主機機，您必須安裝 Redis 的記憶體內緩存系統，並確保電腦上有有效的憑證。 Microsoft 建議您安裝 Redis 3.0 的最新穩定組建。 已使用 Redis 3.2.100 測試統計資料管理員版本2.0。 
  
1. 從下列網站下載 Redis： [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)。 
    
    無法從下載未簽名的安裝程式[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    如有需要，可透過流行的套件管理員提供已簽署的二進位檔案： [Nuget](https://www.nuget.org/packages/Redis-64/)與[Choclatey](https://chocolatey.org/packages/redis-64)。
    
   - 執行提供的 msi，然後依照提示進行。
    
   - 請勿選取方塊來新增防火牆規則。
    
2. 監聽器服務需要證書。 Microsoft 強烈建議您擁有由受信任的憑證頒發機構簽署的憑證。 
    
    例如，如果您想要在 lab 中使用自我簽署憑證，以進行測試，請參閱[建立自我簽署憑證](deploy.md#BKMK_SelfCert)。
    
    請注意，代理程式會使用證書指紋驗證（而不是鏈式驗證）。 因為可以使用自我簽署的憑證，所以它不會進行完整的憑證驗證。
    
### <a name="install-the-listener-service"></a>安裝偵聽程式服務

若要在主機電腦上安裝監聽器服務，請執行 StatsManPerfAgentListener 並指定下列專案：
  
1. 查看授權協定，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 **[下一步]**。 
    
2. 在下一個頁面上，指定下列資訊：
    
   - **服務密碼：** 這是遠端代理程式將用來驗證監聽器服務的密碼。
    
   - **服務埠：** 這是監聽器將用來與 Agent 通訊的 HTTPS 埠號碼。 在安裝期間，系統會允許透過本機防火牆使用這個埠，將會建立 URL ACL，且 SSL 憑證會系結到這個埠。 預設值為8443。
    
   - **憑證指紋：** 這是監聽器將用來加密 HTTPS 通訊協定的憑證指紋。 網路服務必須擁有私密金鑰的讀取存取權。
    
     按一下 [**選取 ...** ] 按鈕來選擇指紋。
    
     您可以使用 [憑證管理員] 或使用下列 PowerShell 命令，找到證書指紋：
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **安裝目錄：** 這是將安裝二進位檔案的目錄。 您可以使用 [**流覽 ...]** 按鈕來變更預設值。
    
   - **AppData Dir：** 這是儲存 [記錄] 資料夾及其他資料的目錄。 您可以變更預設值。 卸載時不會刪除該檔案。
    
3. 按一下 [**安裝**]。
    
若要驗證安裝，請執行下列步驟：
  
1. 開啟瀏覽器並流覽至https://localhost:\<service-port\>/healthcheck/
    
    根據預設，服務埠是8443（除非您已指定另一個埠）。
    
2. 若要確保監聽器已正確安裝，請尋找下列各項：
    
   - 如果 healthcheck 頁面出現，表示已成功安裝監聽器。
    
   - 如果 KnownServerCount 是1或更新版本，就會建立與 Redis 的連線。
    
   - 在等待幾分鐘之後，且至少已安裝一個代理之後，請檢查 ValuesWritten 計數器是否為 [遞增]。
    
### <a name="install-the-website"></a>安裝網站

您可以執行 StatsManWebSite （隨附于[商務用 Skype Server、即時統計管理員（64位）](https://www.microsoft.com/en-in/download/details.aspx?id=57518)）並指定下列專案，在主機電腦上安裝網站：
  
1. 查看授權協定，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 **[下一步]**。 
    
2. 在下一個頁面上，指定下列資訊：
    
   - **服務埠：** 這是網站將接聽的埠號碼。 您可以稍後使用 IIS 管理器系結來變更它。 在安裝期間，系統會允許透過本機防火牆使用這個埠。
    
   - **安裝目錄：** 這是將安裝二進位檔案的目錄。 您可以使用 [**流覽 ...]** 按鈕來變更預設值。
    
   - **AppData Dir：** 這是儲存 [記錄] 資料夾及其他資料的目錄。 您可以變更預設值。 卸載時不會刪除該檔案。
    
3. 按一下 [**安裝**]。
    
若要查看網站，請開啟瀏覽器，然後流覽至http://localhost：，\>webport/。
  
若要只查看健康情況資訊，請開啟瀏覽器，然後http://localhost:\<webport\>/healthcheck/流覽至：。
  
根據預設，web 埠號碼是8080。 您可以使用 [IIS 管理器] 變更網站的埠系結。
  
Web 安裝程式會新增一個名為 StatsManWebSiteUsers 的本地安全性群組。 您可以將帳戶新增至此安全性群組，以授與網站的存取權。 
  
### <a name="install-the-agents"></a>安裝代理程式

透過執行 StatsManPerfAgent 並指定下列專案，在您想要監視的每個商務用 Skype 伺服器上安裝代理程式：
  
1. 查看授權協定，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 **[下一步]**。 
    
2. 在下一個頁面上，指定下列資訊：
    
   - **服務密碼：** 這是遠端代理程式將用來驗證監聽器服務的密碼。
    
   - **服務 URI：** 這是監聽器所駐留的 URI。 它應該使用https://name:port格式。
    
     您可以使用 NETBIOS 名稱或 FQDN。 您可以在偵聽程式服務上使用同時指定為**主題**或**消費者替換名稱**的名稱，但這不是必需的。
    
   - **服務指紋：** 這是監聽器所使用之 SSL 憑證的指紋。 代理程式將使用這個指紋來向監聽器進行驗證。 （它將不會執行完整的憑證驗證，因為可以使用自我簽署的憑證）。
    
   - **安裝目錄：** 這是將安裝二進位檔案的目錄。 您可以使用 [**流覽 ...]** 按鈕來變更預設值。
    
   - **AppData Dir：** 這是儲存 [記錄] 資料夾及加密的密碼 .txt 檔案的目錄。 您可能會感謝您將它變更為預設值。 卸載時不會刪除該檔案。
    
3. 按一下 [**安裝**]。
    
如果您要在許多電腦上安裝代理程式，您可能會想要在無人參與模式下執行。 例如： 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>匯入拓撲
<a name="BKMK_ImportTopology"> </a>

安裝並執行 [統計資料管理器] 之後，您必須匯入商務用 Skype Server 拓撲，以便統計資料管理員知道每個伺服器的網站、池和角色。 若要匯入商務用 Skype Server 拓朴，您將會使用[CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) Cmdlet 來檢索貴組織中使用的每個池的相關資訊，然後將此資訊匯入到 Statistics 管理員。
  
若要匯入商務用 Skype Server 拓撲，請依照下列步驟進行：
  
1. 在有商務用 Skype Server PowerShell Cmdlet 的主機上：
    
    是. 執行下列命令： 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    乙. 將 "mypoolinfo" 檔案複製到執行監聽程式的伺服器。
    
2. 在執行監聽程式的主機上：
    
   是. 執行 PowerShell。
    
   乙. 流覽至安裝監聽器的目錄。 預設值為： 
    
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

若要查看您目前已匯入的伺服器資訊，請執行下列腳本： 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

如果您想要監視不在商務用 Skype Server 拓撲中的伺服器（例如 Exchange 伺服器），您可以在執行監聽程式的主機上執行單一伺服器匯入。 若要執行單伺服器匯入，請依照下列步驟進行：
  
1. 流覽至安裝監聽器的目錄。 預設值為： 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 執行下列命令：
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>疑難排解您的部署
<a name="BKMK_Troubleshoot"> </a>

如果代理程式無法啟動，請檢查下列專案： 
  
- 代理程式是在 [統計資料管理器] 中註冊的嗎？
    
    1. 請確定您已按照匯入拓撲的指示進行。 請參閱匯[入拓撲](deploy.md#BKMK_ImportTopology)。
        
    2. 如果該代理位於拓撲中未列出的伺服器上（例如，SQL AlwaysOn 群集中的節點），您將需要按照匯[入拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增該代理程式。
    
- 工程師可以與監聽器聯繫嗎？
    
    1. 確認偵聽程式服務正在執行。 
        
        如果沒有執行，請確定 Redis 正在執行，然後嘗試重新開機偵聽程式。
        
    2. 確定該埠已開啟到監聽器服務，且代理程式電腦可以與該埠進行通訊。
    
- 若要確保統計資料管理員收集資料，您可以檢查 CSV 檔案，如下所示。 
    
    下列命令會檢索計數器儲存名稱： 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    下一個命令會檢索指定計數器的值： 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

如需您在應用程式事件日誌中可能會看到的所有事件的相關資訊，請參閱[疑難排解商務用 Skype Server 的統計資料管理員](troubleshoot.md)。
  
## <a name="create-a-self-signed-certificate"></a>建立自我簽署憑證
<a name="BKMK_SelfCert"> </a>

Microsoft 強烈建議您使用由受信任的憑證頒發機構簽署的憑證。 不過，如果您想要使用自行簽署式憑證來進行測試，請執行下列動作： 
  
1. 在以系統管理員身分登入的情況下，從 PowerShell 主控台輸入下列內容：
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 類型`certlm.msc`。 這將會開啟本機電腦的 [認證管理員]。
    
3. 流覽至 [**個人**]，然後開啟 [**憑證**]。
    
4. 以滑鼠右鍵按一下 [ **StatsManListener-\>所有\>任務-管理私人金鑰]。**
    
5. 按一下 [**新增**]。
    
6. 在 [**輸入要選取的物件名稱**] 方塊中，輸入下列內容： Network Service
    
7. 按一下 [確定]****。
    
8. 在 [**完全控制**] 底下，取消選取 [**允許**] 核取方塊。 （只需要 [讀取存取]。）
    
9. 按一下 [確定]****。
    
## <a name="for-more-information"></a>如需詳細資訊
<a name="BKMK_SelfCert"> </a>

如需詳細資訊，請參閱下列內容：
  
- [商務用 Skype Server 統計資料的規劃](plan.md)
    
- [升級商務用 Skype Server 統計資料](upgrade.md)
    
- [商務用 Skype Server ß的統計資料管理員疑難排解](troubleshoot.md)
