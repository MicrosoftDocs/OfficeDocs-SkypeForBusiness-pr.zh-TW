---
title: 部署商務用 Skype Server 的通話品質儀表板
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
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 摘要：瞭解通話品質儀表板的部署程式。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: ccfb19bf8069bf72d52d7399b012d81af72e4110
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816852"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>部署商務用 Skype Server 的通話品質儀表板
 
**摘要：** 瞭解通話品質儀表板的部署程式。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
## <a name="deployment-overview"></a>部署概述

通話品質儀表板（CQD）包含三個主要元件：
  
- [封存**資料庫**]，其中會複製並儲存 [經驗] （QoE）資料的品質。
    
- **多維資料集**，其中 QoE 封存資料庫的資料會根據優化和快速存取進行匯總。
    
- **入口網站**，使用者可以在此輕鬆地查詢及視覺化 QoE 資料。
    
![CQD 元件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
QoE 封存的設定程式會涉及建立 QoE 封存資料庫、部署 SQL Server 儲存程式，以將來源 QoE 指標資料庫中的資料移至 QoE 封存資料庫，並設定 SQL Server 代理程式作業來執行已儲存的檔案定期間隔的程式。 
  
多維資料集部署會取得使用者在 QoE 封存所在位置的資訊、部署立方體，並設定一般的 SQL Server 代理程式作業，以便定期重新整理立方體。
  
[入口網站安裝] 會建立儲存 CQD 使用者與每個使用者的報表/查詢對應的知識庫資料庫。 接著，它會設定 IIS web 應用程式，讓使用者可以查看預先定義的報告集，以及自訂和建立自己的查詢，以視覺化立方體中的資料。 入口網站安裝會建立兩個額外的 web 應用程式，讓使用者以程式設計方式存取儲存庫和立方體。 （這些 Api 也是由儀表板內部使用。）
  

|**分**|**步驟**|**角色與群組成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|安裝必備的硬體和軟體。  <br/> |決定 CQD 設定，然後選擇要執行安裝的 SQL Server。  <br/> |屬於本機管理員群組成員的網域使用者。  <br/> |部署檔中的「安裝前需求」一節。  <br/> |
|安裝 CQD。  <br/> |在部署檔後執行 MSI。  <br/> |若要執行設定，安裝帳戶必須是本機系統管理員群組成員的網域使用者，以及在監視伺服器上擁有 QoE 度量值資料庫的讀取權限。  <br/> |[部署] 檔中的 [帳戶和部署步驟] 區段。  <br/> |
|授與使用者存取權。  <br/> |若要管理使用者對入口網站的授權，我們建議使用 IIS 7.0 中引入的 URL 授權。 如需詳細資訊，請參閱[瞭解 IIS 7.0 URL 授權](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。  <br/> |屬於本機管理員群組成員的網域使用者。  <br/> |在部署檔中管理入口網站區段的使用者存取權。  <br/> |
|[選用]：提供子網對應資訊。  <br/> |在 QoE 封存資料庫中填入網路及建立對應資料表。  <br/> |具有 QoE 封存資料庫寫入存取權的帳戶。  <br/> |使用者檔中的「提供子網資訊」一節。  <br/> |
   


部署通話品質儀表板涉及設定基礎結構及安裝軟體。 下列程式會概述此程式。
  
## <a name="deployment-steps"></a>部署步驟

1. 將 CallQualityDashboard 複製到要安裝 CQD 封存資料庫元件的電腦（這是安裝了 SQL Server 的電腦）。 
    
2. 執行 MSI （Windows 會提示您使用系統管理員許可權執行）。 
    
3. 接受 EULA。
    
4. 選取與通話品質儀表板元件相關的檔案所在的目的地資料夾，或接受預設位置。
    
5. 選取 [所有功能]。
    
6. 在 [QoE 封存設定] 頁面上，提供下列資訊：
    
   - **QoE 度量值 SQL Server：** QoE 度量資料庫所在位置的 SQL Server 實例名稱（這將是資料來源）。
    
   - **QoE 封存 SQL Server 名稱：** 這是唯讀欄位，且已修正本機電腦的完整功能變數名稱。 封存資料庫只能安裝在本機電腦上。
    
   - **QoE 封存 SQL Server 實例：** 要在其中建立封存資料庫的本機 SQL Server 實例名稱。 若要使用預設的 SQL Server 實例，請將此欄位留白。 若要使用命名的 SQL Server 實例，請指定實例名稱（例如，在 ""\"之後的名稱）。
    
   - **QoE 封存資料庫：** 根據預設，此選項會設定為 [建立新資料庫]。 由於不支援封存資料庫升級，因此如果現有封存資料庫的架構與要安裝的組建相同，就可以使用 [使用現有的資料庫] 選項的唯一情況。
    
   - **資料庫檔案目錄：** 存放封存資料庫之資料庫檔案（.mdf 和 .ldf）的路徑。 這應該是與作業系統分開的磁片磁碟機（建議的硬體設定中的 HDD2）。 請注意，因為檔案名已在安裝中修正，所以建議您不要使用沒有檔案的空白目錄。
    
   - **使用多個分區：** 預設值會設定為 [多個分區]，這需要商務智慧版本或企業版的 SQL Server。 針對標準版，請選取 [單一分區] 選項。 請注意，如果使用單一分區，cube 處理效能可能會受到影響。
    
     > [!NOTE]
     > 安裝程式完成後，就無法變更 [使用多重分區的選取範圍] 選項。 若要變更它，需要先卸載立方體功能，然後使用 [控制台] 中的 [變更] 選項重新安裝。 
  
   - [分區] 檔案**目錄：** 要放置 QoE 封存資料庫分區的路徑。 這應該是在磁碟機上（建議的硬體設定中的 HDD3），與 OS 磁片磁碟機及 SQL 資料庫記錄檔磁碟機不同。 請注意，因為檔案名已在安裝中修正，所以建議您不要使用沒有檔案的空白目錄。
    
   - **SQL 代理作業使用者-使用者名稱&amp;密碼：** 網域服務帳戶名稱和密碼（遮罩），會用來執行 SQL Server 代理作業的「QoE 封存資料」步驟（這會執行儲存程式，以將資料從 QoE 量度 DB 提取到封存資料庫），因此，此帳戶必須具備對 QoE 公制 DB 的讀取存取權，如 [帳戶] 區段中所述。 這個帳戶也需要在 QoE 封存 SQL Server 實例中擁有登入。
    
     > [!NOTE]
     > 運行 SQL Server 實例的帳戶（例如 NT SERVICE\MSSQLSERVER）必須具備上述所給之目錄的存取/許可權，才能成功安裝。 如需詳細資訊，請參閱[設定資料庫引擎存取的檔案系統許可權](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. 按一下 [下一步] 時，安裝程式將執行必要的檢查，並在遇到任何問題時報告。 當所有的先決條件檢查完成時，安裝程式會移至 [立方體設定] 頁面。 
    
    > [!NOTE]
    > 如果安裝程式顯示警告訊息，指出 QoE 封存 SQL Server 實例的 SQL Server 代理服務目前未執行，則可以繼續安裝，但請確定 SQL Agent 服務正在執行，並將啟動類型設定為[自動]，讓排程的作業執行。 
  
8. 在 [立方體設定] 頁面上，提供下列資訊：
    
   - **QoE 封存 SQL Server 名稱：** 這是唯讀欄位，且已修正本機電腦的完整功能變數名稱。 只能從擁有 QoE 封存資料庫的電腦（注意）安裝 Cube。 立方體本身可能已安裝在遠端電腦上。 請參閱下圖）
    
   - **QoE 封存 SQL Server 實例：** QoE 封存資料庫所在位置的 SQL Server 實例名稱。 若要指定預設的 SQL Server 實例，請將此欄位留白。 若要指定命名的 SQL Server 實例，請輸入實例名稱（例如，在 ""\"之後的名稱）。 如果已選取 [QoE 封存元件] 進行安裝，此欄位將會預先填入 [QoE 封存設定] 頁面上提供的值。
    
   - **立方體分析伺服器：** 要在其中建立多維資料集的 SQL Server Analysis Services 實例名稱。 這可以是不同的電腦，但安裝使用者必須是目標 SQL Server Analysis Service 實例之伺服器系統管理員的成員。
    
     > [!NOTE]
     >  如需有關設定 Analysis Services Server 系統管理員許可權的詳細資訊，請參閱[授與伺服器管理員許可權（Analysis Services）](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **使用多個分區：** 預設值會設定為 [多個分區]，這需要商務智慧版本或企業版的 SQL Server。 針對標準版，請選取 [單一分區] 選項。 請注意，如果使用單一分區，cube 處理效能可能會受到影響。
    
     > [!NOTE]
     >  安裝程式完成後，就無法變更 [使用多重分區的選取範圍] 選項。 若要變更它，需要先卸載立方體功能，然後使用 [控制台] 中的 [變更] 選項重新安裝。
  
   - **立方體使用者-使用者名稱&amp;密碼：** 將觸發 cube 處理的網域服務帳戶名稱和密碼（遮罩）。 如果您已選取安裝的 QoE 封存元件，此欄位將會預先填入 SQL 代理作業使用者的 [封存設定] 頁面上提供的值，但我們建議您指定不同的網域服務帳戶，以便讓安裝程式能夠授與所需的許可權最低。
    
9. 按一下 [下一步] 時，將會執行另一輪驗證，且會報告任何問題。 成功完成驗證之後，安裝程式會移至入口網站設定頁面。 
    
10. 在入口網站設定頁面上，提供下列資訊：
    
    - **QoE 封存 SQL Server：** QoE 封存資料庫所在位置的 SQL Server 實例名稱。 請注意，與 [QoE 封存配置] 頁面和 [立方體設定] 頁面不同，電腦名稱稱並未修正且必須提供。 如果已選取 [QoE 封存元件] 進行安裝，此欄位將會預先填入 [QoE 封存設定] 頁面上提供的值。
    
    - **立方體分析伺服器：** 多維資料集所在位置的 SQL Server Analysis 服務實例名稱。 如果已為安裝選取 [Cube 元件]，此欄位將會預先填入 [Cube 設定] 頁面上提供的值。
    
    - **知識庫 SQL Server：** 要建立知識庫資料庫的 SQL Server 實例名稱。 如果 QoE 封存資料庫所在位置的 SQL Server 實例名稱是在設定（在其他元件中）之前提供，此欄位將會預先填入 QoE 封存資料庫 SQL Server 實例名稱。 這可以是任何 SQL Server 實例。
    
    - **知識庫資料庫：** 根據預設，此選項會設定為 [建立新資料庫]。 由於知識庫 DB 升級不受支援，因此，使用 [使用現有的資料庫] 選項的唯一情況是，如果現有的知識庫資料庫的架構與您要安裝的組建相同。
    
    - **IIS 應用程式池使用者-使用者&amp;名稱密碼：** IIS 應用程式池應該在其下執行的帳戶。 如果已選取內建的系統帳戶，[使用者名稱] 和 [密碼] 欄位就會呈現灰色。 只有在下拉式方塊中選取了 [其他] 時，才會啟用這些欄位，讓使用者可以輸入網域服務帳戶資訊。
    
11. 按一下 [下一步] 時，將會完成最後一輪驗證，以確保使用所提供的認證和電腦上提供的 IIS 來存取 SQL Server 實例。 成功完成驗證之後，安裝程式將會繼續進行設定。 
    
安裝程式完成後，最可能的原因是 SQL Server 代理程式作業將在進行中，執行 QoE 資料的初始載入和 cube 處理。 根據 QoE 中的資料量，入口網站將沒有可供查看的資料。 若要查看資料載入與 cube 處理的狀態，請移至`http://<machinename>/CQD/#/Health`。 
> [!NOTE]
> 請注意，檢查下載 cube 處理狀態的 URL 會區分大小寫。 如果您輸入「健康情況」，URL 將無法運作。 您必須在 URL 結尾處輸入 "Health"，並加上大寫的 H。 
  
如果啟用 [偵錯模式]，就會顯示詳細的記錄訊息。 若要啟用 [偵錯模式]，請移至 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**，並更新下列行，以將此值設定為**True**：

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

您可以透過存取主要入口網站`http://<machinename>/CQD`頁面。 
## <a name="managing-user-access-for-the-portal"></a>管理入口網站的使用者存取權

若要管理使用者對入口網站的授權，我們建議使用 IIS 7.0 中引入的 URL 授權。 如需有關 IIS 安全性的詳細資訊，請參閱[瞭解 iis 7.0 URL 授權](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。
  
任何網站或 web 應用程式都會繼承針對整個 IIS 所設定的預設 URL 授權，通常是「允許所有使用者」。 如果存取入口網站需要更嚴格的限制，系統管理員可以編輯「授權規則」，只授與特定使用者群組的存取權。
  
![部署通話品質-IIS 中的授權規則](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> [授權規則] 圖示不會與 [ASP.NET] 區段下的 [.NET 授權] 混淆，這是一種不同的授權機制。 
  
系統管理員應該先移除繼承的 [允許所有使用者] 規則。 這可防止任何非授權的使用者存取入口網站。
  
![部署 CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
接著，系統管理員應該新增「允許」規則，並給予特定使用者存取入口網站的許可權。 建議建立名為 "CQDPortalUsers" 的本機群組來管理使用者。
  
![部署通話品質儀表板](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
配置詳細資料儲存在位於入口網站物理目錄的 web.config 中。
  
```XML
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

下一步是設定 CQD 的儀表板。 當使用者由 IIS 驗證之後，他們將必須擁有 CQD 目錄的檔案許可權，才能存取網頁入口網站內容。 您可以透過 CQD 目錄屬性的 [安全性] 索引標籤變更 Acl，以新增個別的使用者或群組;不過，建議的方法是讓檔案許可權保持不變。 相反地，請將 IIS 設定變更為使用 IIS 輔助進程來存取 CQD 目錄，不論驗證哪個使用者。 
  
> [!IMPORTANT]
> 請務必為 CQD 應用程式變更此設定，而不是針對兩個 API 應用程式： QoEDataService 和 QoERepositoryService。 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>為 CQD 設定檔案存取（儀表板）

1. 開啟 CQD 的 [設定編輯器]。
    
     ![部署通話品質儀表板](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. 在 [節] 底下，選擇 [ **system.webserver/serverRuntime**]。
    
     ![部署通話品質儀表板](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. 將 authenticatedUserOverride 變更為**UseWorkerProcessUser**。
    
     ![部署通話品質儀表板-配置編輯器](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. 按一下**頁面**右側的 [套用]。
    
## <a name="known-issues"></a>已知問題

### <a name="the-cqd-shows-no-data-after-deployment"></a>部署之後，CQD 不會顯示任何資料

您可能會收到下列錯誤：

*我們無法在多維資料集中執行查詢。使用 [查詢編輯器] 修改查詢並修正任何問題。此外，請確定多維資料集可以存取。*

這表示在 CQD 中使用多維資料集之前，必須先在 SQL Server Analysis Services 中處理。 您可以遵循下列步驟來解決此問題：

1. 開啟 SQL Management Studio，然後選取 [ **Analysis Services**]。

2. 展開**QoECube**物件，選取 [ **QoE 公制**]，以滑鼠右鍵按一下，然後選擇 **[流覽]**。 

    如果這會傳回空白瀏覽器，則該立方體尚未繼續進行。

3. 以滑鼠右鍵按一下 [ **QoE 公制**angain]，然後選擇 [**處理**]。

4. 處理完成時，請再次以滑鼠右鍵按一下物件，然後選擇 **[流覽]** ，確認瀏覽器頁面現在顯示資料。 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>使用者無法登入，因為安裝程式無法在 IIS 中建立正確的設定

在少數情況下，安裝程式無法在 IIS 中建立正確的設定。 若要允許使用者登入 CQD，必須進行手動變更。 如果使用者無法登入，請依照下列步驟進行：
  
1. 開啟 [啟動 IIS 管理員]，然後流覽至 [預設網站]。
    
     ![部署通話品質儀表板](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. 按一下 [驗證]。 如果「匿名驗證」、「ASP.NET 模擬」、「表單驗證」和「Windows 驗證」與下列設定不符，請手動變更這些設定，以符合以下設定。 所有其他的驗證機制都應該停用。
    
     ![部署通話品質儀表板](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. 針對「Windows 驗證」，請按一下右側的 [高級設定]。
    
     ![部署通話品質儀表板](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. 將 [延伸保護] 設定為接受並核取 [啟用核心模式驗證] 方塊。
    
     ![部署通話品質儀表板](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. 針對「預設網站」底下的每個「CQD」、「QoEDataService」和「QoERepositoryService」專案，重複上述步驟。
    
針對 HTTP 和 HTTPS 埠系結，安裝程式將會在預設埠號碼（HTTP 的埠80，以及 HTTPS 的埠443）上建立埠系結。 如果電腦上有另一個網站使用這些系結，就會發生衝突，且無法預測 IIS 行為。 避免這個問題的最佳方式，就是在安裝 CQD 之前，先確定沒有任何其他網站對應到埠80和443。 
  
若要在 IIS 中啟用 SSL/TLS，並強迫使用者透過安全的 HTTPS （而不是 HTTP）連線：
  
1. 在 IIS 中設定安全通訊端層，請參閱[在 iis 7 中配置安全通訊端層](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx)。 完成後，[ `http`取代`https`為]。
    
2. 如需在 SQL Server 連線中啟用 TLS 的指示，請參閱[如何使用 Microsoft 管理主控台針對 SQL Server 實例啟用 SSL 加密](https://support.microsoft.com/en-us/kb/316898/)。
    
## <a name="cube-sync-fails"></a>Cube 同步處理失敗

QoEMetrics 可能會包含一些以使用者時鐘為基礎的無效記錄。 如果時間偏差大於 60 yrs，立方體匯入將會失敗。
  
 使用下列選取範圍，查看最小和最大 StartTime/EndTime。 在過去和遙遠的未來，尋找並刪除記錄，可能會被忽視，而且會中斷同步處理常式。
  
- 從 CqdPartitionedStreamView 選取 [最小值] （StartTime）
    
- 從 CqdPartitionedStreamView 選取 [最大值] （StartTime）
    
- 從 CqdPartitionedStreamView 選取 [最小值] （EndTime）
    
- 從 CqdPartitionedStreamView 選取 [最大值] （EndTime）
    
## <a name="post-install-tasks"></a>安裝後的工作

### <a name="importing-buildings-and-networks"></a>匯入建築物和網路

安裝 CQD 之後，請執行下列配置工作：
  
1. 定義建築物類型（建議使用）
    
2. 定義建築物擁有權類型（建議使用）
    
3. 定義網路類型（強烈建議）
    
4. 匯入建築物（建議使用）
    
5. 匯入子網（建議使用）
    
### <a name="define-building-types"></a>定義建築物類型

建築物類型是用來描述您組織內的不同建築物定義或類型。 
  
> [!NOTE]
> 此步驟是選擇性的，但建議使用。 
  
範例
  
- 設
    
- 遠端辦公室
    
- 共同冒險的位置
    
  **範例 SQL 語法**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

BuildingTypeId 和 BuildingTypeDesc 參數是必要的。
  
### <a name="define-building-ownership-types"></a>定義建築物擁有權類型

擁有權類型是用來區分擁有的與租用的資產。
  
> [!NOTE]
> 此步驟是選擇性的，但建議使用。 
  
範例
  
- Contoso 租您的非&amp;RE F
    
- Contoso 租賃 RE&amp;F
    
- Contoso 擁有
    
- 子公司租
    
  **範例 SQL 語法**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

OwnershipTypeId 和 OwnershipTypeDesc 參數是必要的。 
  
### <a name="define-network-names"></a>定義網路名稱

網路類型是用來描述組織內部不同類型的網路。 這可讓您篩選（或篩選掉）特定的網路類型。
  
> [!NOTE]
> 強烈建議定義網路名稱，但它是選擇性的。 如果您決定不定義網路名稱，請確定每個 CqdNetwork 專案都有 BuildingId 0。 
  
範例
  
- 點對點
    
- 實驗
    
  **範例 SQL 語法**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

NetworkNameID 和 NetworkName 參數是必要的，NetworkType 參數是選擇性的，但建議使用。
  
### <a name="import-buildings"></a>匯入建築物

匯入建築物可讓您取得建立特定深入見解（WiFi/有線等的每個建築物較差的通話）。 
  
> [!NOTE]
> 此步驟是選擇性的，但建議使用。 
  
在匯入新的組建之前，您應該已經識別出預先定義的 BuildingKey。 若要這樣做，請發出 [從 CqdBuilding 中選取 MAX （BuildingKey）] SQL 命令，以找出目前的值，並將1加到結果中。
  
 **範例 SQL 語法**
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId 參數是必要的，其他參數是選擇性的。
  
### <a name="import-subnets"></a>匯入子網

匯入建築物可讓您取得建立特定深入見解（WiFi/有線等的每個建築物較差的通話）。 
  
> [!NOTE]
> 此步驟是選擇性的，但建議使用。 
  
匯入子網並將其對應至在上一個步驟中匯入的建築物。 如果您決定不要填入 NetworkName，請確定此表格中的每個專案都使用0的 NetworkNameID。
  
 **範例 SQL 語法**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

Network 及 UpdatedDate 參數是必要的，其他參數則是選用的。
  
### <a name="optional-bssid"></a>選用： BSSID

填入 BSSID 資訊後，您可以透過控制器或無線電提供額外的 WiFi 資料流程關聯。 這與透過組建或子網進行篩選之外。 
  
 **範例 SQL 語法**
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**CqdBssidTable 詳細資料**

|**如 CQD 所示**|**CQDBssid 資料表**|**輸入範例**|
|:-----|:-----|:-----|
|Ap NName  <br/> |應付  <br/> |AP1  <br/> |
|BBssid  <br/> |面臨  <br/> |00-00-00-00-00-00 （您必須使用分隔符號 fformat）  <br/> |
|審計員  <br/> |創建  <br/> |Aruba AP 7  <br/> |
|裝置  <br/> |員工  <br/> |Controller1  <br/> |
|收發  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>處理匯入的資料

根據預設，在您匯入建立/網路資料之後，只會套用到在該時間點之後產生的記錄。 
  
若要使用這個新資料來標記所有先前的記錄，您必須執行 CqdUpdateBuilding 的儲存程式，如下所示： 
  
賦予它您第一筆記錄的日期（找出在 CqdPartitionedStreamView SQL 命令中使用 Select MIN （StartTime））、明天的結束時間，最後兩個值為 Null。
  
資料與資料流程資料關聯之後，SSIS 立方體需要重新處理所有記錄。 大量新增 BSSID/ISP 資料時，也會套用這種情況。 確認已選取 [程式已滿]。
  

