---
title: 部署商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要：閱讀本主題以瞭解如何部署適用于 商務用 Skype Server 的統計資料管理員。
ms.openlocfilehash: 1debe0c38b3e3df0b6be193e892991c09e15fb61
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675985"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>部署商務用 Skype Server 統計資料

**總結：** 請閱讀本主題以瞭解如何部署適用于 商務用 Skype Server 的統計資料管理員。

 適用于 商務用 Skype Server 的統計資料管理員是功能強大的工具，可讓您即時檢視商務用 Skype Server健康情況和效能資料。 您可以每隔幾秒輪詢數百部伺服器的效能資料，並立即在統計資料管理員網站上檢視結果。

嘗試安裝統計資料管理員之前，請確定您已熟悉軟體、網路和硬體需求。 如需詳細資訊，請參閱[Plan for Statistics Manager for 商務用 Skype Server](plan.md)。

> [!NOTE]
> 如果您要從舊版的統計資料管理員升級，請參閱[Upgrade Statistics Manager for 商務用 Skype Server](upgrade.md)。

> [!NOTE]
> 統計資料管理員網站已經過測試，並可在 Internet Explorer 11+、Edge 20.10240+ 和 Chrome 46+ (目前的常青版本) 上正確運作。

您可以在 找到可下載的 [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 統計資料管理員。

本主題包含下列各節：

- [部署統計資料管理員](deploy.md#BKMK_Deploy)

- [針對您的部署進行疑難排解](deploy.md#BKMK_Troubleshoot)

- [建立自我簽署憑證](deploy.md#BKMK_SelfCert)

## <a name="deploy-statistics-manager"></a>部署統計資料管理員
<a name="BKMK_Deploy"> </a>

若要部署統計資料管理員，請遵循下列步驟：

1. 安裝 Redis 記憶體內部快取系統，並確定您已安裝適當的憑證，以準備接聽程式主機電腦。

2. 在主機電腦上安裝接聽程式服務。

3. 在主機電腦上安裝網站。

4. 在您想要監視的每個商務用 Skype Server電腦上安裝代理程式。

5. 匯入您要監視之伺服器的拓撲。

> [!NOTE]
> Redis、接聽程式服務和網站都必須安裝在同一部主機電腦上。 請確定主機電腦未安裝商務用 Skype Server。

### <a name="prepare-the-listener-host-machine"></a>準備接聽程式主機電腦

若要準備主機電腦，您必須安裝 Redis 記憶體內部快取系統，並確保機器上有有效的憑證。 Microsoft 建議您安裝 Redis 3.0 的最新穩定組建。 統計資料管理員 2.0 版已使用 Redis 3.2.100 進行測試。

1. 從下列網站下載 Redis： [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) 。

    您可以從下載未簽署的安裝程式 [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)

    已簽署的二進位檔可透過熱門套件管理員取得： [Nuget](https://www.nuget.org/packages/Redis-64/) 和 [Choclatey](https://chocolatey.org/packages/redis-64)。

   - 執行提供的 msi 並遵循提示。

   - 請勿核取方塊以新增防火牆規則。

2. 接聽程式服務需要憑證。 Microsoft 強烈建議您擁有受信任憑證授權單位單位所簽署的憑證。

    如果您想要使用自我簽署憑證，例如實驗室中的測試用途，請參閱 [建立自我簽署憑證](deploy.md#BKMK_SelfCert)。

    代理程式會使用憑證指紋驗證 (，而不是鏈結驗證) 。 它不會執行完整憑證驗證，因為可以使用自我簽署憑證。

### <a name="install-the-listener-service"></a>安裝接聽程式服務

執行StatsManPerfAgentListener.msi並指定下列專案，以在主機電腦上安裝接聽程式服務：

1. 檢閱授權合約，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 [ **下一步]**。

2. 在下一個頁面上，指定下列資訊：

   - **服務密碼：** 遠端代理程式會使用此密碼向接聽程式服務進行驗證。

   - **服務埠：** 接聽程式會使用此 HTTPS 埠號碼來與代理程式通訊。 在安裝期間，將允許此埠通過本機防火牆、建立 URL ACL，並將 SSL 憑證系結至此埠。 預設值為 8443。

   - **憑證指紋：** 接聽程式會使用此憑證來加密 HTTPS 通訊協定。 網路服務必須具有私密金鑰的讀取權限。

     按一下 [ **選取...]** 按鈕以選擇指紋。

     您可以使用憑證管理員或使用下列 PowerShell 命令來尋找憑證指紋：

      ```PowerShell
      Get-ChildItem -path cert:\LocalMachine\My
      ```

   - **安裝 Dir：** 此目錄是將安裝二進位檔的位置。 您可以使用 [ **流覽...** ] 按鈕，將它從預設值變更。

   - **AppData Dir：** 此目錄是 Logs 資料夾和其他資料的儲存位置。 您可以將它從預設值變更。 卸載時不會刪除它。

3. 按一下 **安裝**。

若要驗證安裝，請執行下列步驟：

1. 開啟瀏覽器並瀏覽至 `https://localhost:<service-port>/healthcheck/`

    除非您指定另一個埠) ，否則服務埠預設為 8443 (。

2. 若要確保接聽程式已正確安裝，請尋找下列專案：

   - 如果 [健康情況檢查] 頁面出現，接聽程式安裝會成功。

   - 如果 KnownServerCount 為 1 或更高版本，則會建立與 Redis 的連線。

   - 等候幾分鐘之後，在至少安裝一個 Agent 之後，請檢查 ValuesWritten 計數器是否正在遞增。

### <a name="install-the-website"></a>安裝網站

執行 商務用 Skype Server 隨附的StatsManWebSite.msi (，在主機電腦上安裝網站[，Real-Time統計資料管理員 (64 位) ](https://www.microsoft.com/download/details.aspx?id=57518)) ：

1. 檢閱授權合約，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 [ **下一步]**。

2. 在下一個頁面上，指定下列資訊：

   - **服務埠：** 此 TCP 埠是網站將接聽的位置。 您可以稍後使用 IIS 管理員系結來變更它。 在安裝期間，將允許此埠通過本機防火牆。

   - **安裝 Dir：** 此目錄是將安裝二進位檔的位置。 您可以使用 [ **流覽...** ] 按鈕，將它從預設值變更。

   - **AppData Dir：** 此目錄是 Logs 資料夾和其他資料的儲存位置。 您可以將它從預設值變更。 卸載時不會刪除它。

3. 按一下 **安裝**。

若要檢視網站，請開啟瀏覽器，然後流覽至： `http://<localhost:webport/>` 。

若只要檢視健康情況資訊，請開啟瀏覽器，然後流覽至： `http://localhost:<webport>/healthcheck/` 。

根據預設，Web 埠號碼為 8080。 您可以使用 IIS 管理員來變更網站的埠系結。

Web 安裝程式會新增名為 StatsManWebSiteUsers 的本機安全性群組。 您可以將帳戶新增至此安全性群組，以授與網站的存取權。

### <a name="install-the-agents"></a>安裝代理程式

執行 StatsManPerfAgent.msi，在您想要監視的每個商務用 Skype Server上安裝代理程式：

1. 檢閱授權合約，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 [ **下一步]**。

2. 在下一個頁面上，指定下列資訊：

   - **服務密碼：** 遠端代理程式會使用此密碼向接聽程式服務進行驗證。

   - **服務 URI：** 此 URL 是接聽程式所在的位置。 `https://name:port`使用 格式。

     您可以使用 NETBIOS 名稱或 FQDN。 您可以在接聽程式服務上使用也指定為憑證 **主體或****主體別名** 的名稱，但這並非必要。

   - **服務指紋：** 此 SS：接聽程式會使用憑證。 代理程式會使用此指紋向接聽程式進行驗證。 它不會執行完整憑證驗證，因為可以使用自我簽署憑證。

   - **安裝 Dir：** 此目錄是將安裝二進位檔的位置。 您可以使用 [ **流覽...** ] 按鈕，將它從預設值變更。

   - **AppData Dir：** 此目錄是 Logs 資料夾和加密password.txt檔案的儲存位置。 您可以感謝您將它從預設值變更。 卸載時不會刪除它。

3. 按一下 **安裝**。

如果您要在許多機器上安裝代理程式，您可能會想要在自動模式中執行此動作。 例如：

```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>匯入拓撲
<a name="BKMK_ImportTopology"> </a>

安裝並執行統計資料管理員之後，您必須匯入商務用 Skype Server拓撲，讓統計資料管理員知道每部伺服器的月臺、集區和角色。 若要匯入商務用 Skype Server拓撲，您將使用[Get-CsPool](/powershell/module/skype/get-cspool) Cmdlet 來擷取組織中每個使用中集區的相關資訊，然後將此資訊匯入統計資料管理員。

若要匯入商務用 Skype Server拓撲，請遵循下列步驟：

1. 在具有 商務用 Skype Server PowerShell Cmdlet 的主機上：

    a. 執行下列命令：

   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```

    b. 將 「mypoolinfo.xml」 檔案複製到執行接聽程式的伺服器。

2. 在執行接聽程式的主機上：

   a. 執行 PowerShell。

   b. 流覽至安裝接聽程式的目錄。 預設值為：

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. 若要確認要新增和更新哪些伺服器，請執行下列命令：

   ```console
   .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

下列命令可讓您檢視所有選項：

```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed
```

若要查看您目前匯入的伺服器資訊，請執行下列腳本：

```powershell
.\Get-StatsManServerInfo.ps1
```

如果您想要監視不在商務用 Skype Server拓撲中的伺服器，例如Exchange Server，您可以在執行接聽程式的主機上執行單一伺服器匯入。 若要執行單一伺服器匯入，請遵循下列步驟：

1. 流覽至安裝接聽程式的目錄。 預設值為：

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 執行下列命令：

   ```powershell
   .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>針對您的部署進行疑難排解
<a name="BKMK_Troubleshoot"> </a>

如果 Agent 無法啟動，請檢查下列問題：

- 代理程式是否已在統計資料管理員中註冊？

   1. 請確定您已遵循匯入拓撲的指示。 請參閱 [匯入拓撲](deploy.md#BKMK_ImportTopology)。

   2. 例如，如果 Agent 位於未列在拓撲 (的伺服器上，SQL AlwaysOn 叢集中的節點) ，您必須依照匯入[拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增代理程式。

- 代理程式可以連絡接聽程式嗎？

   1. 請確定接聽程式服務正在執行。

      如果未執行，請確定 Redis 正在執行，然後嘗試重新開機接聽程式。

   2. 請確定接聽程式服務已開啟埠，且 Agent 電腦可以與埠通訊。

- 若要確保統計資料管理員正在收集資料，您可以檢查 CSV 檔案，如下所示。

    下列命令會擷取計數器儲存體名稱：

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    下一個命令會擷取指定計數器的值：

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

如需您可能會在應用程式事件記錄檔中看到之所有事件的資訊，請參閱[針對商務用 Skype Server的統計資料管理員進行疑難排解](troubleshoot.md)。

## <a name="create-a-self-signed-certificate"></a>建立自我簽署憑證
<a name="BKMK_SelfCert"> </a>

Microsoft 強烈建議您使用受信任憑證授權單位單位所簽署的憑證。 不過，如果您想要使用自我簽署憑證進行測試，請執行下列步驟：

1. 以系統管理員身分登入時，從 PowerShell 主控台執行下列命令：

   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 輸入  `certlm.msc` 。 這會開啟本機電腦的憑證管理員。

3. 流覽至 **[個人**]，然後開啟 **[憑證]**。

4. 以滑鼠右鍵按一下 **StatsManListener - \> 所有工作 - \> 管理私密金鑰...**

5. 按一下 **[新增]**。

6. 在 [ **輸入要選取的物件名稱** ] 方塊中，輸入下列文字：網路服務

7. 按一下 **[確定]**。

8. 在 [ **完全控制]** 下，取消核取 [ **允許]** 核取方塊。  (唯讀存取權是必要的。) 

9. 按一下 **[確定]**。

## <a name="for-more-information"></a>相關資訊
<a name="BKMK_SelfCert"> </a>

如需詳細資訊，請參閱下列主題：

- [商務用 Skype Server 統計資料的規劃](plan.md)

- [升級商務用 Skype Server 統計資料](upgrade.md)

- [疑難排解商務用 Skype Server 統計資料](troubleshoot.md)
