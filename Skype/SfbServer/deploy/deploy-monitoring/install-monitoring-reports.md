---
title: 在商務用 Skype Server 中安裝監視報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 摘要：瞭解如何在商務用 Skype Server 中安裝會產生監視報告的服務。
ms.openlocfilehash: 6c8b7089a66abc3e0b1dcacb4bfa5c840f57ed36
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41789991"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>在商務用 Skype Server 中安裝監視報告
 
**摘要：** 瞭解如何在商務用 Skype Server 中安裝會產生監視報告的服務。
  
商務用 Skype Server 監視報告提供大量有關貴組織中所發生之通訊會話品質和數量的資訊。 
  
## <a name="install-monitoring-reports"></a>安裝監視報告

當您安裝商務用 Skype Server 時，系統不會自動安裝監視報告;相反地，您必須單獨安裝監視報告，而且只有在電腦上安裝商務用 Skype Server 之後才能進行。
  
> [!NOTE]
> 建議您在安裝監視資料庫的同一部電腦上安裝監視報告。 這簡化了指派許可權以存取報表的程式：在託管監視存放區的電腦上安裝監視報表，意味著您不需要設定允許一部電腦上的資料庫互動的許可權在另一部電腦上執行 Reporting Services。 
  
商務用 Skype Server 監視報告包含30個以上的報告，旨在提供會議、對等 IM 會話、使用者註冊、回應群組應用程式的詳細資訊，以及更多相關資訊。 針對2013版本，商務用 Skype Server 監視報告包含許多增強功能：
  
- **新的語音品質報告**。 這些新報告包含[商務用 Skype Server 中的 [媒體質量比較] 報告](../../manage/health-and-monitoring/comparison.md)，該報告會比較不同類型的通話（例如有線通話和無線通話之間）之間的品質。[在商務用 Skype Server 中的 [會議加入時間] 報告](../../manage/health-and-monitoring/join-time-report.md)，可提供使用者加入會議所需的時間量資訊。 
    
- **改善了分析和疑難排解影片與應用程式共用會話的報表。** [商務用 Skype server 中的 [媒體質量摘要] 報告](../../manage/health-and-monitoring/summary.md)提供一種分析視頻與應用程式共用通話的方式，而[商務用 skype server 中的 [伺服器效能] 報告](../../manage/health-and-monitoring/server-performance.md)則會詳細說明產生這些呼叫的伺服器效能。 透過商務用 skype server 的 [對[等會話詳細資料] 報告](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)以及[商務用 skype server 中的 [會議詳細](../../manage/health-and-monitoring/detail-report.md)資料] 報告，現在也會報告影片和應用程式共用度量值。
    
- **改善報表效能**。 這包括更快速的回應與資料檢索時間，以及更快速且更輕鬆地流覽報表的功能。
    
您可以在 [監視報告] 檔中找到個別報告的詳細資訊。
  
> [!NOTE]
> 有另一個報表 QoE 通話詳細資料子報表，包含在商務用 Skype 伺服器中。 不過，此報告主要供內部使用，且不應直接存取。 
  
有兩種方式可以安裝商務用 Skype Server Monitoring 報告：您可以使用商務用 Skype Server 部署嚮導，或者您可以使用隨附于商務用 Skype Server 安裝盤案中的 Windows PowerShell 腳本。 無論您使用何種方法來安裝報表，您必須先確定：
  
- 有權將資料庫角色新增到監視資料庫中的使用者帳戶。
    
- 在 SQL Server Reporting Services 中保留內容管理員角色。 這個角色提供將報表部署至 SQL Server Reporting Services 的權利。
    
若要使用 [部署嚮導] 安裝監視報告，請完成下列步驟：
  
1. 按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype server**]，然後按一下 [**商務用 skype server 部署嚮導]**。
    
2. 在 [部署嚮導] 中，按一下 [**部署監視報表**]，以啟動 [部署監視報表] 嚮導。
    
3. 在 [部署監視報表] 嚮導中的 [**指定監視資料庫**] 頁面上，確認 [**監視資料庫**] 下拉式清單中顯示的是託管監視存放區之電腦的完整功能變數名稱。 （如果您有多個監視儲存區，您將需要從下拉式清單中選取適當的伺服器）。確認**Sql Server Reporting Services （SSRS） [實例**] 方塊（例如**atl-sql-001.litwareinc.com/archinst**）中出現正確的 sql server 實例，然後按 **[下一步]**。
    
4. 在 [**指定認證**] 頁面上的 [**使用者名稱**] 方塊中，輸入存取監視報告時要使用之帳戶的功能變數名稱和使用者名稱（例如， **litwareinc\kenmyer**）。 如果您不使用此格式（domain\user name），就會發生錯誤。
    
    在 [**密碼**] 方塊中輸入使用者帳戶密碼，然後按一下 **[下一步]**。 請注意，此帳戶不需要特殊許可權。 安裝程式完成時，系統會自動授與帳戶所需的登入和資料庫許可權。
    
5. 在 [**指定唯讀群組**] 頁面上，在 [使用者群組] 方塊中，輸入將被授與 SQL Server Reporting Services 唯讀存取權的安全性群組名稱。 例如，若要賦予唯讀管理員對報表的存取權，請輸入**RTCUniversalReadOnlyAdmins**。 按一下 **[下一步]**。
    
6. 在 [**執行命令**] 頁面上，按一下 **[完成]**。
    
您也可以透過執行腳本 DeployReports. ps1; 來從商務用 Skype Server Management Shell 安裝監視報告。您可以在 [安裝位置\< \>\Skype] 中的 [商務伺服器 2015 \ Deployment\Setup] 資料夾中找到這個 Windows PowerShell 腳本。 若要使用 DeployReports 安裝監視報表，請在管理命令介面提示處輸入類似以下的命令：
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

下表說明前面命令中使用的參數：
  
|**參數名稱**|**必要**|**說明**|
|:-----|:-----|:-----|
|storedUserName  <br/> |是  <br/> |用來存取監視存放區之使用者帳戶（格式為 [域 \ 使用者名]）;例如：  <br/> ```-storedUserName "litwareinc\kenmyer"```這個帳戶必須擁有先前指定的 SQL Server 和 SQL Server Reporting Services 許可權，否則腳本將會失敗。  <br/> |
|storedPassword  <br/> |是  <br/> |用來存取監視存放區之使用者帳戶的密碼。  <br/> |
|readOnlyGroupName  <br/> |否  <br/> |網域或本機安全性群組，其成員將被授與監控報告的唯讀存取權。 請注意，如果指定的群組不存在，腳本將會失敗。 如果您稍後決定要撤銷這些許可權，或者如果您決定要授與其他使用者或其他群組的存取權限，您可以使用 SQL 服務 Reporting Services 報表管理員來執行此動作。  <br/> |
|reportSqlServerInstance  <br/> |否  <br/> |託管報表服務的 SQL Server 實例。 報告實例必須使用報表伺服器的完整功能變數名稱來指定;例如：  <br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```如果此參數未包含，腳本將假設報表服務是由託管監視資料庫的相同 SQL Server 實例所託管。  <br/> |
|monitoringDatabaseId  <br/> |否  <br/> |監視資料庫的服務身分識別。 您可以執行下列命令，以傳回監視資料庫的身分識別：  <br/> ```Get-CsService -MonitoringDatabase```|
   
在已安裝監視報告之後，您必須使用 CsReportingConfiguration Cmdlet 來設定用來存取這些報告的 URL。 您可以執行下列 Windows PowerShell 命令，從商務用 Skype Server Management Shell 執行此工作。 請注意，建議您在設定報表 URL 時，使用 HTTPS 通訊協定，但這不是必要的。
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

在上述命令中，ReportingUrl 屬性應該設定為 SQL Server 2008 R2 Reporting Services 所使用的報表管理員 URL。 您可以在已安裝 SQL Server Reporting Services 的電腦上完成下列步驟，以判斷報表管理員 URL：
  
1. 按一下 [開始]，按一下 [所有程式]，按一下 [Microsoft SQL Server 2008 R2]，按一下 [設定工具]，然後按一下 [Reporting Services Configuration Manager]。
    
2. 在 [Reporting Services 配置連線] 對話方塊中，確認 [伺服器名稱] 方塊中出現 [報表服務] 電腦的名稱。 從 [報表伺服器實例] 下拉式清單中選取 [SQL Server 實例]，然後按一下 [連線]。
    
3. 在 Reporting Services 組態管理員中，按一下 [報表管理員 URL]。 一個或多個 Url 應該出現在 [報表管理員 URL] 窗格中。 您也可以將這些 Url 作為報告 URL 使用，但建議您再次使用 HTTPS 通訊協定 ReportingUrl。
    
如果您已為監視資料庫設定鏡像資料庫，您也必須將監視報告與鏡像資料庫建立關聯。 如需詳細資訊，請參閱[在商務用 Skype 伺服器中將 [監視報告] 與 [鏡像資料庫] 關聯](monitoring-reports-with-a-mirror-database.md)。
  

