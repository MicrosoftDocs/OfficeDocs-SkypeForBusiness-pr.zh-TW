---
title: 在商務用 Skype Server 中安裝監視報告
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 摘要：瞭解如何在商務用 Skype Server 中安裝會產生監控報告的服務。
---

# <a name="install-monitoring-reports-in-skype-for-business-server"></a>在商務用 Skype Server 中安裝監視報告
 
**總結：** 瞭解如何在商務用 Skype Server 中安裝會產生監控報告的服務。
  
商務用 Skype Server 監視報告可為您提供組織中所發生之通訊會話品質與數量的大量資訊。 
  
## <a name="install-monitoring-reports"></a>安裝監視報告

當您安裝商務用 Skype Server 時，不會自動安裝監控報告，而是必須個別安裝監視報告，而且只有在電腦上安裝商務用 Skype Server 之後。
  
> [!NOTE]
> 建議您將監控報告安裝在已安裝監控資料庫之相同電腦上，如此可簡化存取報告的指派權限程序：將監控報告安裝在裝載監控存放區的電腦上，表示您不需要設定權限以允許某一台電腦上的資料庫與在第二台電腦執行的 Reporting Services 進行互動。 
  
商務用 Skype Server 監視報告包含超過30個報告，其設計目的是提供有關會議、對等 IM 會話、使用者註冊、回應群組應用程式以及其他許多方面的詳細資訊。 針對2013版本，商務用 Skype Server 監控報告包含一些增強功能：
  
- **新的語音品質報告**。 這些新的報表包括[商務用 Skype Server 中的媒體質量比較報告](../../manage/health-and-monitoring/comparison.md)，它會比較不同類型通話之間的品質 (例如，有線通話與無線) 通話之間的品質，以及[商務用 Skype Server 中會議加入時間報表](../../manage/health-and-monitoring/join-time-report.md)的相關資訊，其可提供使用者加入會議所需的時間量資訊。 
    
- **針對視訊與應用程式共用工作階段進行分析和疑難排解的改善報告。** [商務用 Skype Server 中的媒體質量摘要報告](../../manage/health-and-monitoring/summary.md)提供分析影片和應用程式共用呼叫的方法，而[商務用 Skype Server 中的伺服器效能報告](../../manage/health-and-monitoring/server-performance.md)會詳細說明產生這些呼叫之伺服器的效能。 影片和應用程式共用度量現在也是由[商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)和[商務用 Skype Server 中的會議詳細資料包告](../../manage/health-and-monitoring/detail-report.md)所報告。
    
- **改善報告效能**。包括加速回應與資料擷取時間，以及更迅速而簡便瀏覽報告。
    
有關個別報告的詳細資訊，可在監控報告文件中取得。
  
> [!NOTE]
> 商務用 Skype Server 中也包含另一個報告 QoE 詳細資料子報表。 但是，此報告主要用於內部，無法直接存取。 
  
有兩種方式可安裝商務用 Skype Server 監視報告：您可以使用商務用 Skype Server 部署嚮導，也可以使用商務用 Skype Server 安裝檔案隨附的 Windows PowerShell 腳本。 無論您使用哪一種方法安裝報告，都必須先確認您具備下列條件：
  
- 具備將資料庫角色新增至監控資料庫中使用者帳戶的權限。
    
- 在 SQL Server Reporting Services 中具有「內容管理員」角色。這個角色會賦予您將報告部署至 SQL Server Reporting Services 的權限。
    
若要使用部署精靈安裝監控報告，請完成下列步驟：
  
1. 依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 部署嚮導]**。
    
2. 在部署精靈中按一下 **[部署監控報告]** 以啟動「部署監控報告」精靈。
    
3. 在部署監控報告精靈中的 **[指定監控資料庫]** 頁面上，請確認裝載您監控存放區之電腦的完整網域名稱顯示於 **[監控資料庫]** 下拉式清單中。(如果您有多個監控存放區，則必須從下拉式清單選取適當的伺服器。) 確認正確的 SQL Server 執行個體顯示於 **[SQL Server Reporting Services (SSRS) 執行個體]** 方塊中 (例如 **atl-sql-001.litwareinc.com/archinst**)，然後按 **[下一步]**。
    
4. 在 **[指定認證]** 頁面的 **[使用者名稱]** 方塊中，輸入網域名稱及存取監控報告之時所使用的帳戶使用者名稱 (例如 **litwareinc\kenmyer**)。 如果您不使用此格式 (網域 \ 使用者名稱) 會發生錯誤。
    
    在 **[密碼]** 方塊中輸入使用者帳戶密碼，然後按 **[下一步]**。 請注意，此帳戶沒有必要的特殊權利。 安裝程式完成時，系統會自動授與帳戶所需的登入和資料庫許可權。
    
5. 在 **[指定唯讀群組]** 頁面上的使用者群組方塊中，輸入將授與 SQL Server Reporting Services 唯讀存取權的安全性群組名稱。例如，若要指定唯讀系統管理員存取報告，請輸入 **RTCUniversalReadOnlyAdmins**，然後按 **[下一步]**。
    
6. 在 **[執行命令]** 頁面上按一下 **[完成]**。
    
透過執行腳本 DeployReports.ps1，也可以從商務用 Skype Server 管理命令介面安裝監控報告; 此 Windows PowerShell 腳本可以位於 \ 商務用 Skype Server 2015 \ Deployment\Setup 資料夾中 \<install location\> 。 若要使用 DeployReports.ps1 安裝監控報告，請在管理介面提示中輸入類似下列命令：
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

用於以上命令的參數會在下表加以說明：
  
|**參數名稱**|**Required**|**描述**|
|:-----|:-----|:-----|
|storedUserName  <br/> |是  <br/> |用於存取監控存放區的使用者帳戶 (格式為網域\使用者名稱)；例如：  <br/> ```-storedUserName "litwareinc\kenmyer"```此帳戶必須具有先前指定的 SQL Server 和 SQL Server Reporting Services 許可權，否則腳本將會失敗。  <br/> |
|storedPassword  <br/> |是  <br/> |用於存取監控存放區的使用者帳戶密碼。  <br/> |
|readOnlyGroupName  <br/> |否  <br/> |授與成員監控報告唯讀權限的網域或本機安全性群組。 請注意，如果指定的群組不存在，指令碼就會失效。 如果您稍後決定撤銷這些權限，或是決定將權限授與其他使用者或群組，可使用 SQL Service Reporting Services 報表管理員執行這些動作。  <br/> |
|reportSqlServerInstance  <br/> |否  <br/> |託管 Reporting Service 的 SQL Server 執行個體。必須使用 Report Server 的完整網域名稱指定報告執行個體；例如：<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```若未加入此參數，腳本會假設報表服務是由主控監控資料庫的相同 SQL Server 實例所主控。  <br/> |
|monitoringDatabaseId  <br/> |否  <br/> |監控資料庫的服務識別。您可執行此命令返回監控資料庫的識別：<br/> ```Get-CsService -MonitoringDatabase```|
   
安裝監視報告之後，您必須使用 New-CsReportingConfiguration Cmdlet 來設定用來存取這些報告的 URL。 您可以執行下列 Windows PowerShell 命令，從商務用 Skype Server 管理命令介面執行此工作。 請注意，建議您在設定報告 URL 時使用 HTTPS 通訊協定 (非必要)：
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

以上的命令中，ReportingUrl 屬性應設為 SQL Server 2008 R2 Reporting Services 所使用的報表管理員 URL。您可在已安裝 SQL Server Reporting Services 的電腦上透過完成下列步驟來決定報表管理員 URL：
  
1. 依序按一下 [開始]、[所有程式]、[Microsoft SQL Server 2008 R2]、[組態工具]，然後按一下 [Reporting Services 組態管理員]。
    
2. 在 [Reporting Services 組態連接] 對話方塊中，請確定 Reporting Services 電腦名稱顯示於 [伺服器名稱] 對話方塊中。從 [報告伺服器執行個體] 下拉式清單中選取 SQL Server 執行個體，然後按一下 [連線]。
    
3. 在 [Reporting Services 組態管理員] 中，按一下 [報表管理員 URL]，[報表管理員 URL] 窗格應該會顯示一個以上的 URL。雖然其中任何 URL 皆可作為報告 URL 之用，再一次申明，建議您採用使用 HTTPS 通訊協定的 ReportingUrl 。
    
如果您已設定監控資料庫的鏡像資料庫，您也必須將監控報告與鏡像資料庫相關聯。 如需詳細資訊，請參閱[在商務用 Skype Server 中，將監控報告與鏡像資料庫相關聯](monitoring-reports-with-a-mirror-database.md)的文章。
  

