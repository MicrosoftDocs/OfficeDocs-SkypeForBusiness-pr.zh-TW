---
title: 商務用 Skype Server：規劃通話品質儀表板
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 摘要：瞭解在規劃通話品質儀表板時所應考慮的事項。
ms.openlocfilehash: 42b80c8e426f438a1608d3c71a41b20dd9d27a63
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777343"
---
# <a name="skype-for-business-server-plan-for-call-quality-dashboard"></a>商務用 Skype Server：規劃通話品質儀表板 
 
**摘要：** 深入瞭解當您規劃通話品質儀表板時應考慮的事項。
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>商務用 Skype Server 通話品質儀表板的概覽

商務用 Skype Server 通話品質儀表板 (CQD) 是商務用 Skype Server 之監控伺服器中的經驗品質資料庫之上的報表層。 CQD 使用 Microsoft SQL Server Analysis Services，提供匯總使用狀況及通話品質資訊，以及針對資料集進行篩選和旋轉。 CQD 的功能包括：
  
- **透過 CQD 的 QoE 封存元件 QoE 資料的歸檔儲存區。** QoE 的封存元件可將 QoE 資料儲存在比監控伺服器還多長的時間。 這可讓您一次對最多7個月的資料進行趨勢分析和報告，而且能夠將報表視窗滑動到盡可能後退的資料。
- **使用 Microsoft SQL Server analysis Services 的功能和速度來報告和分析。** CQD 利用 Microsoft SQL Analysis Services 提供快速的摘要、篩選和旋轉功能，以透過分析 Cube 來為儀表板供電。 報告執行速度及向下流覽資料的能力，可大幅減少分析時間。
- **針對通話品質報告優化的新資料架構。** Cube 具有設計用來進行語音品質報告和調查的架構。 入口網站使用者可以專注于報表工作，而不是判斷 QoE 度量資料庫架構如何對應至所需的視圖。 QoE 封存和 Cube 的組合提供了一個可透過 CQD 降低報告和分析複雜度的抽象性。 QoE 封存資料庫架構也包含可填入部署特有資料的資料表，以提升資料的整體價值。
- **內建的報表設計工具及就地報表編輯。** 入口網站元件隨附數個內建的報表，並在通話品質方法之後模仿。 入口網站使用者可以修改報告，並透過入口網站的編輯功能建立新的報告。
- **存取報表結構及分析 Cube 資料的 Web API。** 儀表板報表架構並非從 Cube 顯示資料的唯一方式。 CQD 提供數個使用 HTML 和 JavaScript 的範例，以從 CQD Web APIs 中取得資料，並以自訂格式轉譯資料。 報表編輯器和 CQD 網頁 APIs 的組合，可讓報表和自訂報表版面配置的快速原型。

> [!NOTE]
> 管理員現在可以使用[CQD 第3版](https://cqd.teams.microsoft.com) (以系統管理員認證) 來管理商務用 Skype Server 2019。 這需要混合式的實施，以及使用「呼叫資料連線器 (CDC) 。 如需啟用 CDC 的詳細資訊，請參閱 [規劃通話資料連線器](../../../SfbHybrid/hybrid/plan-call-data-connector.md) 。 如需 CQD 第3版的檔，請參閱[開啟和使用呼叫品質儀表板的 Microsoft Teams 和商務用 Skype 線上](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)，以取得更多有關 CQD 版本3的資訊。

## <a name="cqd-design-goals"></a>CQD 設計目標

CQD 可讓 IT 專業人員使用匯總資料來識別其環境中出現媒體質量問題的焦點區域。 它可讓 it Pro 比較不同使用者群組的統計資料，以及識別趨勢和模式。 這不會專注于解決個別通話問題，但識別將套用至指定環境中許多使用者的問題和解決方案。 
  
## <a name="call-quality-dashboard-components"></a>通話品質儀表板元件

通話品質儀表板包含數個資料庫、Microsoft SQL 代理程式工作、處理常式和 web 應用程式。 Microsoft SQL 代理程式工作定期將資料從 QoE 計量資料庫複製到 QoE 的封存資料庫，並以 QoE 封存資料庫中的資料處理 Cube。 存放庫資料庫可儲存為入口網站供電的報告定義。 入口網站提供瀏覽器存取 Cube 資料。 
  
CQD 元件（包括 QoE 封存、Cube 及存放庫資料庫）可安裝在監控伺服器上、安裝在自己的伺服器上，或安裝在多部伺服器上。 特定的安裝方法取決於 CQD 的效能需求，以及對相同伺服器上其他進程的影響。 如需詳細資訊，請參閱本文稍後的「CQD 元件及拓撲」一節。
  
### <a name="architectural-overview"></a>架構概觀

總而言之，CQD 需要下列元素：
  
- 兩個資料庫：封存資料庫及存放庫資料庫。
    
- 一個 SSAS Cube 會形象匯總的資料 
    
- IIS 主機 CQD 網頁入口網站
    
![CQD 元件。](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
同一個 CQD 架構支援 Lync Server 2013 和商務用 Skype。 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 和商務用 Skype 與 Lync 2013

 在商務用 Skype 環境中，可使用下列功能：
  
- Wi-Fi 的信號強度報告
    
- Wi-Fi 報告晶片組驅動程式
    
- 評估我的通話資料 
    
## <a name="information-available-through-cqd"></a>透過 CQD 提供的資訊

CQD 可顯示商務用 Skype Server 音訊、影片及應用程式共用資料流程計數和不良通話的計數，以及不良通話的比率。 這些視圖可以透過許多不同的維度進行切片及篩選。 CQD 會從監控伺服器中 QoE 度量資料庫繪製資料。 然後會將資料與客戶提供的任何資料合併，例如網路子網對組建對應，使報告如「每座通話的通話品質」。 
  
CQD 也會進一步摘要許多內部 QoE 資料特性，例如「來電者」和「被叫用方」，讓使用者能夠專注于「伺服器」和「用戶端」，以建立報表檢視。 遵循通話品質方法之後，CQD 會進行簡化，以協助識別少數的通話不足之情況：其中一個提高通話品質的原則。
  
## <a name="viewing-data-in-cqd"></a>在 CQD 中查看資料

CQD 資料可以透過 CQD 入口網站查看，並透過 REST API 通話存取。
  
### <a name="cqd-portal"></a>CQD 入口網站

入口網站是查看 Cube 中資料的最快方法。 入口網站隨附數個可立即使用的內建報告。 內建報告會以結構化方式連結，以引導使用者連續縮小或縮小通話資料的小扇面。 內建報告也會透過示範不同的旋轉、篩選及量值的圖表和資料表組合，強調可顯示資料的各種不同方式。 存取入口網站的每一位使用者都可以有自己的報表集合，而使用者可以修改和共用該集合。 如需 CQD 網頁入口網站用法的詳細資訊，請參閱[Use Call Quality 儀表板 for 商務用 Skype Server](use.md)。
  
CQD 入口網站支援的作業系統： Windows 8.1、Windows 8、Windows Server 2012 R2、Windows Server 2012 及 Windows Server 2016 (商務用 Skype Server 2019 CQD) 。
  
支援 CQD 入口網站的瀏覽器： internet explorer 11、Internet Explorer 10 和 Internet explorer 9。
  
### <a name="rest-apis"></a>REST API

您也可以透過 REST API 通話存取 Cube 資料。 透過 REST API 通話所找回的資料，可透過 HTML 頁面轉譯。 使用者可以利用 CQD 的查詢速度和高層級架構，同時仍建立適合其業務需求的自訂報告。 如需 API 和範例的詳細資訊，請參閱[開發通話品質儀表板以取得商務用 Skype Server](develop.md)。 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>定義組織的 CQD 需求

CQD 提供 QoE 資料封存，以及對通話品質資料的快速與深入分析。 下列指南可協助您決定部署 CQD 的時間與原因。
  
### <a name="when-to-deploy-cqd"></a>何時部署 CQD

 **即使組織未經歷通話品質問題，也可以部署 CQD，以建立基準通話品質度量。** 建立基準通話品質度量很重要，因為每個組織都有不同的 Wi-Fi 和有線和遠端與 office 工作者搭配使用。 當出現通話品質問題時，最新的通話品質測量值可與上一個時間間隔進行比較。 CQD 的趨勢功能可讓您輕鬆地偵測出通話品質隨時間變化的變化。
  
 **CQD 可部署，以主動尋找可能會影響通話品質的問題區域。** 即使組織的平均通話品質可能符合組織所設定的目標，也可能會有少數已隱藏的通話品質問題（平均計量）。 CQD 可讓樞紐分析表像是 QoEMetrics 資料庫中的多個維度的呼叫品質度量明細。 對等群組中的 Spotting 離群是一種可積極找到通話品質問題的快速方法。
  
 **如果組織中有通話品質問題，則應部署 CQD，以減少疑難排解問題所需的時間。** CQD 可提供快速報表效能及動態深入功能，以簡化現有通話品質調查。 CQD 是針對呼叫品質調查對環境所做的修復驗證所設計的許多工作流程。
  
### <a name="why-deploy-cqd"></a>為什麼要部署 CQD

 **如果需要針對超過3個月的資料執行 QoE 報告，則應該部署 CQD。** QoEMetrics 資料庫和監控伺服器報告的設計目的是要保留及報告一小部分資料集。 QoE 度量資料庫已針對快速插入進行優化，因此可透過大量通話或對資料庫的競爭性報表存取，下滑報表效能。 CQD 的 QoE 封存資料庫會提供第二個 QoE 計量資料複本，保留能力更長。 入口網站也經過優化，可一次顯示最多7個月的資料，而且可以視需要報告 QoE 封存中的所有資料。
  
 **如果需要自訂 QoE 報表，應部署 CQD。** 入口網站提供報表編輯器的功能，可快速且輕鬆地建立及建立報表的原型。 它也可讓您使用 REST APIs，以程式設計方式存取 Cube 資料，允許使用 HTML/JavaScript 或其他許多框架的自訂簡報。 為報告建立自訂資料檢視的目的，您不再需要編寫新的 SQL 查詢。
  
 **如果現有的 QoE 報告功能不符合組織所需的速度或深度，應部署 CQD。** CQD 附帶許多內建的報表。 報告立即有用，並示範逐步深入資料的方式可以在每個層級提供其他真知灼見。 報表階層也有助於以邏輯方式管理大量的報表，以及建立更容易存取和易於理解的報表。 CQD 不僅提供速度及彈性，還針對通話品質方法所開發的工作流程進行優化。
  
## <a name="components-and-topologies-for-cqd"></a>CQD 的元件與拓撲

CQD 附帶數個元件，而且可協助您瞭解每個元件的需求及其相互關聯，以取得最簡單且最適合的工具部署。 下表說明每個 CQD 元件的相依元件。
  

|元件名稱|相依元件|
|:-----|:-----|
|QoE 封存   |Microsoft SQL Server   |
|立方體   |Microsoft SQL ServerAnalysis Services   |
|入口網站   |Microsoft 資訊服務   |
|存放庫服務 (入口網站的部分安裝)    |Microsoft SQL Server   |
   
> [!NOTE]
> 針對 QoE 封存及 Cube，某些部署選項需要 Microsoft SQL Server 的商務智慧或 Enterprise 版本。 如需詳細資訊，請參閱下列的 [CQD 區段基礎結構需求](plan.md#Infrastructure_Req) 。
  
![CQD 元件。](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>單一伺服器設定

所有 CQD 元件和相依元件都可以安裝到一部機器上。 單一 box 設定是最簡單的設定，可讓 CQD 成為自包含的配置。 CQD 只需要存取監控伺服器上的 QoE 度量資料庫。 CQD 伺服器可以是獨立電腦、虛擬機器或虛擬機器，也可以是監控伺服器，視主機電腦的可用資源和效能需求而定。 
  
在安裝期間，執行安裝的使用者只需要提供先前在 CQD 要安裝的機器上設定的 Microsoft SQL Server 和 Microsoft SQL Server Analysis Services 實例。 如需詳細資訊，請參閱[部署通話品質儀表板的商務用 Skype Server](deploy-0.md) 。
  
### <a name="multiserver-configuration"></a>多伺服器設定

在多伺服器設定中，QoE 的封存、Cube 及入口網站都可以在不同的機器上。 有兩個主要用途用於多伺服器設定：
  
- 在不同的伺服器上主控 CQD 網頁入口網站和 CQD Cube。
    
- 主控「開發」入口網站，與「實際執行」入口網站分開。 
    
  **在不同的機器上主控 CQD 網頁入口網站和 CQD Cube。** 可能需要將 CQD 入口網站與 SQL Server 安裝分開的組織，或可能想要混合和符合 SQL Server 實例和 SQL Server Analysis Services 實例 SQL Server 版本的組織，可以選擇在不同的機器上安裝 CQD 入口網站和 CQD Cube。 如果組織只想要具有可持續的方法來封存 QoE 資料，而不會達到監控伺服器的效能限制，QoE 封存元件也可以是安裝的唯一 CQD 元件。
  
![單一伺服器 CQD。](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **主控「開發」入口網站，與「實際執行」入口網站分開。** 透過 REST APIs) 開發自己之自訂 (報告的組織，您可能傾向于在實際使用者存取通話品質監控或調查的實際執行入口網站上，部署其他 (CQD) 入口網站實例。 開發入口網站可以將任何對入口網站的修改與實際執行環境隔離。 其他的網頁入口網站可以部署在不同的機器上， (如下所示) 或部署在相同機器上的不同網頁目錄上 (不會顯示) 。 若要完成後者，必須手動將額外的 CQD 網頁入口網站複製到生產機器，因為 CQD 安裝程式會將 CQD 網頁入口網站部署至預設網站，且使用預先定義的 web 應用程式名稱。
  
![規劃 CQD 多伺服器。](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>支援的拓撲

CQD 不會合並多個 QoEMetrics 資料庫中的資料，就像在有多個商務用 Skype Server 拓撲的情況下，每個都有自己的監控伺服器。 每個 CQD 實例都必須指向一個 QoEMetrics 資料庫。 不過，因為 CQD 會將許多報表工作負載從監控伺服器移出，所以每個商務用 Skype Server 拓撲所需的監控伺服器必須針對所有拓撲使用一個監控伺服器。
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD 的基礎結構需求
<a name="Infrastructure_Req"> </a>

CQD，包括其所有元件和相依元件，都可以部署在虛擬機器、單一機器或跨多部機器上。 下表列出最低軟體和硬體需求。 資料可用性和查詢效能可能會根據使用中商務用 Skype Server 使用者與硬體及設定的數目而定，因此以下提供一些效能度量。
  

|針對 CQD 2015 |&nbsp;  |
|:-----|:-----|
|支援的作業系統   |WindowsServer 2008 r2，Windows Server 2012，Windows Server 2012 R2   |
|支援的 SQL Server   |SQL Server 2012 SQL Server 2014，SQL Server 2016   |


|針對 CQD 2019  |&nbsp;  |
|:-----|:-----|
|支援的作業系統   |Windows Server 2016，Windows Server 2019   |
|支援的 SQL Server   |SQL Server 2017，SQL Server 2019   |
   
CQD 利用 Microsoft SQL Server、Microsoft SQL Server Analysis Services 和 Microsoft Internet Information Services，因此 CQD 的硬體和軟體需求基本與從屬元件相同。 不過，根據組織對資料新鮮度的需求 (，取決於組織產生) 和部署成本的 QoE 資料量，應進行其他部署考慮。
  
CQD 中的資料處理分為兩個主要階段： 
  
- QoE 封存處理常式
    
- CQD Cube 處理
    
  **QoE 封存處理。** QoE 的封存處理工作會將資料從監控伺服器上的 QoE 計量資料庫複製到 QoE 封存資料庫。 在兩種情況下，任務的處理時間會有基本不同的效能特性。 第一種是在初次安裝 CQD 之後。 在進行全新安裝之後，第一次執行工作時，QoE 的封存處理工作會將 QoE 度量資料庫中的所有資料都複製到 QoE 封存資料庫中。 第二個是此初始迴圈之後的定期處理。 QoE 的封存處理工作每15分鐘會執行一次，並處理 QoE 計量資料庫中的任何新 QoE 記錄。 一般來說，初始處理時間不是問題，因為它只會在第一次安裝 CQD 時執行。 不過，如果 CQD 伺服器受到嚴格的布建，此工作可能需要數小時。 如需初始 QoE 的封存處理時間範例，請參閱下表。
  
  **CQD Cube 處理。** Cube 處理工作會將 QoE 封存資料庫中的資料匯總到 Cube。 初始 cube 處理時間及後續 cube 處理時間取決於用於 CQD cube 的 SQL Server Analysis Services edition。 如果使用 Standard edition，初始 cube 處理時間與後續 cube 處理時間之間並無差異，因為每次重新整理 Cube 資料時，它會永遠處理所有可用資料的完整處理。  (這表示當 QoE 封存資料庫中的資料量增加時，Cube 處理時間會增加。 ) 因為 SQL Server 的商務智慧 Edition 和 Enterprise Edition 有分割區支援，所以如果使用任一版本，則只有初始執行會處理 QoE 封存資料庫中的所有資料。 在後續的執行中，當每隔15分鐘觸發任務時，任務只會處理自上次執行工作後新增至 QoE 封存資料庫的新記錄。 一天一次，包含目前月份資料的磁碟分割上也會有完整的處理。
  
實體機器特徵可能會影響 CQD 效能，以及可從 SQL Server 元件取得的軟體功能。 與其他元件相比，QoE 的封存元件會比磁片更大量，但 Cube 元件的 CPU 和記憶體會更密集。 所有這些因素都會影響 CQD 的總資料處理時間，這會直接影響資料新鮮度和可用性。 組織應該根據組織的個別需求，對硬體和軟體進行決策。 
  
### <a name="tested-hardware-configurations"></a>測試的硬體設定

本節假設環境中有單一 QoEMetrics DB。 
  
**電腦設定檔**

|機器|CPU 核心|RAM|QoE 相同磁片上的封存和 Cube|在相同磁片上 QoE 封存及 SQL Temp DB|
|:-----|:-----|:-----|:-----|:-----|
|虛擬機器   |4    |7 GB   |是   |是   |
|4核心   |4    |20 GB   |是   |否   |
|8核心   |8    |32 GB   |是   |否   |
|16核心   |16    |128 GB   |否   |否   |
   
**效能結果**

|機器|QoE 度量 DB 大小|SQL 磁碟分割|磁片類型|資料流程數目|初始封存處理常式|初始 Cube 處理常式|後續的封存處理常式|後續 Cube 處理常式|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|虛擬機器   |900 MB   |單一   |VHD (可變大小)    |.5 M   |30 m   |2 m   |30秒   |1 m   |
|虛擬機器   |9 GB   |單一   |VHD (可變大小)    |5 M   |4 h   |15 m   |1 m   |5 m   |
|虛擬機器   |9 GB   |單一   | (固定大小的 VHD)    |5 M   |2 h   |5 m   |1 m   |5 m   |
|虛擬機器   |30 + GB   |單一   | (固定大小的 VHD)    |10 M   |15 h   |20 m   |2 m   |45 m   |
|8核心   |9 GB   |單一   |多個磁片   |5 M   |2 h   |5 m   |25 s   |5 m   |
|8核心   |9 GB   |多個   |多個磁片   |5 M   |2 h   |15 m   |35 s   |2 m   |
|8核心   |30 + GB   |單一   |多個磁片   |20 M   |9 h   |20 m   |1 m   |20 m   |
|8核心   |30 + GB   |多個   |多個磁片   |20 M   |9 h   |30 m   |2 m   |2 m   |
|4核心   |200 GB   |單一   |多個磁片   |125 M   |6 + 天   |7 h   |2 m   |6 h   |
|16核心   |500 GB   |多個   |多個主軸   |250 M   |8天   |2 h   |2 m   |10 m   |
   
\*這些不會在實際部署中遇到，因為 QoE 度量資料庫必須分別有9和18個月的資料，但在這裡提供這些資料是完整的。
  
### <a name="service-account-requirements"></a>服務帳戶需求

您將需要 (具有 QoEMetrics) 的帳戶，CQD Server 上的 SQL 代理程式才能用於將資料匯入 QoEArchiveDB。
  
您也可能需要為 SSAS 工作設定個別的帳戶，以從 QoEArchiveDB 提取資料 (這是選用的程式) 。
  
IIS 最常使用網路服務做為應用程式集區身分識別，但可以設定為服務帳戶。
  
### <a name="portal-access-control"></a>入口網站存取控制

根據預設，任何已驗證的使用者都可以存取。 您可以使用 IIS 授權規則來變更，以限制為特定群組。
  
### <a name="pre-install-requirements"></a>安裝前的需求

這些指示假設已安裝 QoE 度量值資料庫，且該資料庫在商務用 Skype Server 拓撲中的某處執行。
  
#### <a name="hardware-requirements"></a>硬體需求

CQD 使用 Microsoft SQL Server、microsoft SQL 分析伺服器及 microsoft Internet information server，因此 CQD 基本的硬體和軟體需求基本上與那些相依元件相同。 不過，根據組織對資料新鮮度的需求 (，取決於組織產生) 和部署成本的 QoE 資料量，應進行其他部署考慮。
  
#### <a name="software-requirements"></a>軟體需求

CQD 需要下列作業系統：
  
- Windows使用 IIS 7.5 的伺服器 2008 R2
    
- 使用 IIS 8.0 Windows Server 2012
    
- Windows Server 2012使用 IIS 8.5 的 R2

- Windows Server 2016 與 IIS 10.0 (商務用 Skype Server 2019 CQD 只有) 

- WindowsServer 2019 (僅限商務用 Skype Server 2019 CQD) 
    
以下是以階層順序) 所需的 IIS role services (：
  
- 網頁伺服器
    
  - 一般 HTTP 功能
    
  - 靜態內容
    
  - 預設文件
    
  - 應用程式開發
    
  - ASP.NET
    
  - ISAPI 篩選
    
  - 狀況 &amp; 診斷
    
  - HTTP 記錄
    
  - 安全性
    
  - URL 授權
    
  - Windows 驗證
    
  - 管理工具
    
  - IIS 管理主控台
    
> [!NOTE]
>  請注意上述需求的下列專案：您可以使用 .Net framework > 3.5 和4.5 版本的 .Net framework。 這兩者都是必要的 (更具體地說，) > 3.5 SP1。在部分系統中，如果在安裝 iis 之前設定 ASP.NET，則 ASP.NET 可能不會在 iis 中註冊。 問題是透過對應 .Net 版本的應用程式集區缺失，也不會在應用程式集區設定中遺漏 .NET CLR 版本。 若要修正 Windows Server 2008 R2 上的問題，請執行 `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` 。 在 Windows Server 2012 和 Windows Server 2012 R2 上執行 `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` 後，從 IIS 管理員的預設網站移除 "system.servicemodel" 模組。 > 管理工具為選用，但建議使用。
  
若要使用 PowerShell 來安裝這些需求，請執行下列作業：
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

支援下列 SQL Server 版本：

- CQD 2015： SQL Server 2012 SQL Server 2014，SQL Server 2016
- CQD 2019： SQL Server 2017，SQL Server 2019 
    
出於效能原因，建議使用商業智慧或 Enterprise edition。 這些版本允許使用可同時處理的多個分割檔，這對於處理跨越多個月或更長時間的資料非常有用。 
  
不建議同時支援 Standard edition。 處理會受限於單一分割區 (，在設定) 時，需要加以設定。 
  
在所有情況下，必須安裝「資料庫引擎服務」和「Analysis Services」。 建議您不要同時安裝「管理工具完成」功能，以新增 Analysis Services 的 SQL Server Management Studio 支援。 功能選取畫面的外觀應該如圖所示。
  
![SQL Server 功能需求。](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
設定 SSAS 安裝程式時，請在 Analysis Services 設定中，將「伺服器模式」設定為「維度和資料採礦模式」。 
  
如需安裝及設定 SQL Server 商務智慧功能的詳細說明，請參閱[Install Analysis Services in 多維及資料採礦模式](/previous-versions/sql/sql-server-2012/ms143708(v=sql.110))。
  
#### <a name="account-requirements"></a>帳戶需求

在最低許可權原則上，建議使用三個網域服務帳戶： 
  
- 一個已有 db_datareader 特權的 QoE 度量值資料庫 (的登入安全性主體，) QoE 封存 SQL Server 實例中的登入安全性主體， (在設定) 期間建立連結的伺服器物件。 此帳戶將用來執行 SQL Server 代理程式工作的「QoE 封存資料」步驟。
    
    > [!NOTE]
    > 如果您是在嚴重鎖定的環境中工作，您必須檢查此服務帳戶是否確實授與 QoE 度量監控資料庫 SQL Server 和 QoE 封存 SQL Server 上的「以批次登入工作」和「允許本機登入」使用者權限。
    
- 一種是用來執行 SQL Server 代理程式工作的「處理 Cube」步驟。 安裝程式會建立一個登入安全性主體，以使用「讀取和寫入」) 許可權 QoE 封存資料庫 (，也可以在 QoE 角色 (中，以 Cube 的「完全控制」許可權) 來建立成員。
    
- 一個用來為 web 入口網站和 web APIs 執行 IIS 工作者進程。 安裝程式會建立一個登入安全性主體，以 QoE 具有讀取權限的封存資料庫 () 、使用「讀取和寫入」許可權的存放庫資料庫 (的登入安全性主體) ，以及 Cube 的「完全控制」許可權 (的 QoERole) 中的成員。 
    
    > [!NOTE]
    > 當兩個 QoE 封存資料庫和存放庫資料庫裝載在相同 SQL Server 中時，只會建立一個具有兩個使用者對應的登入安全性主體。 
  
前兩個帳戶可以邏輯視為「後端服務帳戶」，而最後一個帳戶是「前端服務帳戶」。 不建議您在任何情況下都可以使用單一帳戶。
  
> [!NOTE]
> 啟動安裝的使用者帳戶除了具備 QoE 封存資料庫伺服器上的機器系統管理員許可權之外，還必須具有 QoE 計量 (DB 的讀取權，) 必須進行安裝。 
  
## <a name="capacity-planning"></a>容量規劃
<a name="Infrastructure_Req"> </a>

CQD 的設計是針對 QoEMetrics 的最小影響：此程式碼已優化為不鎖定資料，而匯入工作是可調式的。
  
使用的硬體類型取決於同步處理執行速度的需求。 磁片大小調整如下：
  
- QoEArchive 最初的大約 1.5 x 大於 QoEMetrics DB
    
- SSIS Cube 會將資料壓縮為與 DB 相比快 10 10。
    
- 資料每月分割;可刪除磁碟分割
