---
title: 規劃商務用 Skype Server 的通話品質儀表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 摘要：在您規劃通話品質儀表板時，瞭解要考慮的事項。
ms.openlocfilehash: 3a0982f565495740887b6da07dd802de1205dcf8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991408"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>規劃商務用 Skype Server 的通話品質儀表板 
 
**摘要：** 瞭解當您規劃 [通話品質] 儀表板時要考慮的事項。
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>商務用 Skype Server 通話品質儀表板概覽

商務用 Skype Server 通話品質儀表板（CQD）是 [商務用 Skype 伺服器] 的 [監視伺服器] 中的 [體驗品質] 資料庫上方的報告層。 CQD 使用 Microsoft SQL Server Analysis Services 來提供匯總使用量和通話品質資訊，以及在資料集中進行篩選與旋轉。 CQD 功能包括：
  
- **透過 CQD 的 QoE 封存元件，儲存 QoE 資料的檔案。** QoE 封存元件可儲存超過監視伺服器所能長的 QoE 資料。 這可讓您一次最多七個月的資料進行趨勢分析及報告，且能夠將 [報告] 視窗滑動到最新的資料。
- **使用 Microsoft SQL Server Analysis Services 的電源和速度進行報告和分析。** CQD 利用 Microsoft SQL Analysis Services 來提供快速的摘要、篩選及旋轉功能，以透過分析立方體來為儀表板加上電源。 報告執行速度與向下切入資料的能力可以大大減少分析時間。
- **針對通話品質報告優化的新資料架構。** 此多維資料集具有專為語音品質報告和調查設計的架構。 入口網站使用者可以將焦點放在報告工作上，而不是找出 QoE 規格資料庫架構對應至所需的視圖。 QoE 封存與立方體的組合提供可減少透過 CQD 進行報告和分析的複雜性的抽象。 QoE 封存資料庫架構也包含可填入部署特定資料的資料表，以增強資料的整體值。
- **內建報表設計工具和就地報表編輯。** 入口網站元件隨附幾個內建的報表，並類比通話品質方法。 入口網站使用者可以修改報告，並透過入口網站的編輯功能建立新報表。
- **可存取報表結構及分析 Cube 資料的 Web API。** 儀表板報告架構不是顯示立方體資料的唯一方式。 CQD 提供數個使用 HTML 和 JavaScript 從 CQD Web Api 中取得資料，並以自訂格式轉譯資料的範例。 [報表編輯器] 和 [CQD 網頁 Api] 的組合可讓您快速建立報表和自訂報表的版面配置。

> [!NOTE]
> 系統管理員現在可以使用[CQD 版本 3](https://cqd.teams.microsoft.com)管理商務用 Skype Server 2019 （以管理員認證登入）。 這需要混合式實現，以及使用通話資料連線器（CDC）。 如需啟用 CDC 的詳細資訊，請參閱[規劃通話資料連線器](/SkypeForBusiness/hybrid/plan-call-data-connector)。 如需 CQD 版本3的檔，請參閱[開啟及使用 Microsoft 團隊和商務用 Skype Online 的通話品質儀表板](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)，以取得更多關於 CQD 版本3的資訊。

## <a name="cqd-design-goals"></a>CQD 設計目標

CQD 可讓 IT 專業人員使用匯總資料來找出遇到媒體質量問題之環境中的焦點區域。 它可讓 IT 專業人員比較不同使用者群組的統計資料，並識別趨勢和模式。 它不是針對個別呼叫問題的重點，而是針對在指定環境中針對許多使用者所套用的問題與解決方案。 
  
## <a name="call-quality-dashboard-components"></a>通話品質儀表板元件

[通話品質] 儀表板由數個資料庫、Microsoft SQL 代理程式作業、進程及 web 應用程式組成。 Microsoft SQL 代理作業會定期將資料從 QoE 量度資料庫複製到 QoE 封存資料庫，並使用 QoE 封存資料庫中的資料處理多維資料集。 知識庫資料庫會儲存為入口網站加電的報表定義。 入口網站提供瀏覽器存取多維資料集資料的許可權。 
  
CQD 元件（包括 QoE 封存、Cube 及知識庫資料庫）可以安裝在監視伺服器上、安裝在自己的伺服器上，或安裝在多個伺服器上。 具體的安裝方式取決於 CQD 的效能需求，以及對相同伺服器上的其他進程所造成的影響。 如需詳細資訊，請參閱本文稍後的「CQD 元件與拓撲」一節。
  
### <a name="architectural-overview"></a>結構概述

總之，CQD 需要下列元素：
  
- 兩個資料庫： [封存資料庫] 和 [知識庫資料庫]。
    
- 一個 SSAS 立方體視覺化匯總的資料 
    
- IIS 主機 CQD 網頁入口網站
    
![CQD 元件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
相同的 CQD 架構支援 Lync Server 2013 和商務用 Skype。 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 及商務用 Skype 與 Lync 2013

 在商務用 Skype 環境中，您可以使用下列功能：
  
- 信號強度的 wi-fi 報告
    
- 晶片組驅動程式的 wi-fi 報告
    
- 評價我的通話資料 
    
## <a name="information-available-through-cqd"></a>透過 CQD 提供的資訊

CQD 可以顯示商務用 Skype Server 音訊、影片及應用程式共用資料流程數量及良好的通話計數，以及不正確的通話比率。 您可以透過許多不同的尺寸來對視圖進行切片與篩選。 CQD 會從監視伺服器中的 [QoE 度量] 資料庫繪製資料。 然後，就會將資料與任何客戶提供的資料（例如網路子網間的對應）合併，以製作諸如「每個建築物的通話品質」等報告。 
  
CQD 也會抽象化許多內部 QoE 資料特性（例如「來電者」和「被叫方」），讓使用者能夠將精力集中在「伺服器」和「用戶端」上建立報表檢視。 遵循通話品質方法之後，CQD 會簡化，以協助找出少數不佳通話的條件，其中一個改善通話品質的原則。
  
## <a name="viewing-data-in-cqd"></a>在 CQD 中查看資料

CQD 資料可透過 CQD 入口網站查看，並透過 REST API 呼叫存取。
  
### <a name="cqd-portal"></a>CQD 入口網站

入口網站是查看多維資料集中資料最快的方法。 入口網站隨附數個可立即使用的內建報告。 內建的報告是以結構化的方式連結，可引導使用者在通話資料中連續減少或較小的磁區。 內建的報告也會透過示範不同的旋轉、篩選及量值的圖表與表格組合，來醒目提示資料的不同顯示方式。 存取入口網站的每個使用者都可以有自己的一組報表，供他/她修改和共用。 如需 CQD 網頁入口網站用法的詳細資訊，請參閱[使用商務用 Skype Server 的通話品質儀表板](use.md)。
  
支援的 CQD 入口網站： Windows 8.1、Windows 8、Windows Server 2012 R2、Windows Server 2012 及 Windows Server 2016 （僅適用于商務用 Skype Server 2019 CQD）。
  
CQD 入口網站支援的瀏覽器： Internet Explorer 11、Internet Explorer 10 和 Internet Explorer 9。
  
### <a name="rest-apis"></a>REST Api

您也可以透過 REST API 呼叫來存取立方體資料。 透過 REST API 呼叫檢索的資料，可以透過 HTML 頁面來轉譯。 使用者可以利用查詢速度和高層級架構 CQD，同時仍建立適合其業務需求的自訂報表。 如需 API 與範例的詳細資訊，請參閱[開發商務用 Skype Server 的通話品質儀表板](develop.md)。 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>定義貴組織的 CQD 需求

CQD 提供 QoE 資料封存及快速及深入的通話品質資料分析。 下列指南可協助您決定何時以及為什麼要部署 CQD。
  
### <a name="when-to-deploy-cqd"></a>部署 CQD 的時機

 **您可以部署 CQD 來建立比較基準通話品質測量，即使組織不會遇到通話品質問題也一樣。** 建立比較基準通話品質測量很重要，因為每個組織都有不同的 Wi-fi 與有線與遠端與 office 工作人員的混合。 出現通話品質問題時，最新的通話品質測量可以與之前的時間間隔進行比較。 CQD 的趨勢分析功能可在一段時間內輕鬆地偵測通話品質的變更。
  
 **您可以部署 CQD，以前瞻性地找出可能會影響通話品質的問題區域。** 即使組織的平均通話品質可能符合組織所設定的目標，也可能會有少數的通話品質問題，這些問題不會出現在平均指標中。 CQD 可讓樞紐分析表與 QoEMetrics 資料庫中的多個維度的通話品質指標分類。 Spotting 對等群組中的 [離群離群] 是快速找出通話品質問題的快速方法。
  
 **如果組織中有通話品質問題，則應部署 CQD，以減少疑難排解問題所需的時間。** CQD 可以提供快速報告效能和動態向下功能，以簡化現有的通話品質調查。 CQD 是針對在通話品質調查中針對環境修復進行驗證所設計的許多類型的工作流程而設計。
  
### <a name="why-deploy-cqd"></a>為什麼要部署 CQD

 **如果需要針對3個月以上的資料進行 QoE 報告，請部署 CQD。** QoEMetrics 資料庫與監視伺服器報表的設計目的是保留並報告一小組資料。 QoE 度量資料庫已針對快速插入進行優化，因此，您可以透過大量的通話或對資料庫進行競爭性報表存取的方式來 impeded 報表效能。 CQD 的 QoE 封存資料庫提供一份 QoE 指標資料的第二個複本，且保留能力較長。 入口網站也經過優化，可一次顯示多達7個月的資料，並視需要在 QoE 封存中報告所有資料。
  
 **如果需要自訂 QoE 報告，則應部署 CQD。** 入口網站擁有 [報表編輯器] 的功能，可讓您快速且輕鬆地建立及建立報表原型。 它也可讓您以程式設計方式存取多維資料集資料，並允許使用 HTML/JavaScript 或許多其他架構進行自訂簡報。 您不再需要撰寫新的 SQL 查詢，目的是為了建立報告的自訂資料檢視。
  
 **如果現有的 QoE 報告功能不符合組織所需的速度或深度，就應該部署 CQD。** CQD 隨附許多內建的報表。 報告會立即起作用，並示範如何逐步深化資料，在每個層級中都能提供其他見解。 [報表階層] 也可協助以邏輯方式管理大量報表，並讓建立更多易於存取且易於理解的報表。 CQD 並不只提供速度與靈活性，也會針對通話品質方法所開發的工作流程進行優化。
  
## <a name="components-and-topologies-for-cqd"></a>CQD 的元件與拓撲

CQD 隨附數個元件，並有助於瞭解各個元件的需求，以及它們彼此之間的關聯，以取得該工具最簡單且最佳的部署。 下表說明每個 CQD 元件的相依元件。
  

|**元件名稱**|**相依元件**|
|:-----|:-----|
|QoE 封存  <br/> |Microsoft SQL Server  <br/> |
|Cube  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|門戶  <br/> |Microsoft 資訊服務  <br/> |
|知識庫服務（入口網站安裝的一部分）  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> 針對 QoE 封存和 Cube，某些部署選項需要 Microsoft SQL Server 的商務智慧或企業版。 如需詳細資訊，請參閱下方的[CQD 區段基礎結構需求](plan.md#Infrastructure_Req)。
  
![CQD 元件](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>單一伺服器設定

所有 CQD 元件和相依元件都可以安裝在一部電腦上。 [單方塊設定] 是最簡單的設定，可讓 CQD 自行包含。 CQD 只需要存取監視伺服器上的 QoE 指標資料庫即可。 CQD 伺服器可以是獨立電腦（虛擬機器），也可以是監視伺服器（視主機電腦的可用資源和效能需求而定）。 
  
在安裝期間，執行安裝的使用者只需要提供 Microsoft SQL Server 以及先前在安裝 CQD 的電腦上設定的 Microsoft SQL Server Analysis Services 實例。 如需詳細資訊，請參閱[部署商務用 Skype Server 的通話品質儀表板](deploy-0.md)。
  
### <a name="multiserver-configuration"></a>多伺服器設定

在多伺服器設定中，QoE 封存、Cube 及入口網站都可以在不同的電腦上。 多伺服器設定主要有兩種用途：
  
- 在不同的伺服器上託管 CQD 網頁入口網站和 CQD Cube。
    
- 裝載與「生產」入口網站不同的「開發」入口網站。 
    
  **在不同的電腦上託管 CQD 網頁入口網站和 CQD Cube。** 可能需要將 CQD 入口網站與 SQL Server 安裝分開或想要混合與搭配 sql server 實例與 SQL server Analysis Services 實例之 SQL Server 版本的組織，可以選擇安裝 CQD 入口網站，並在不同的電腦上 CQD 立方體。 如果組織只想要使用可持續方法來封存 QoE 資料，而不會在監視伺服器上達到效能限制，則 QoE 封存元件也可以是您所安裝的唯一 CQD 元件。
  
![單一伺服器 CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **裝載與「生產」入口網站不同的「開發」入口網站。** 開發自己的自訂報表（透過 REST Api）的組織，可能比較喜歡在正式使用者存取通話品質監控或調查時，在生產入口網站上部署其他（CQD）入口網站實例。 開發入口網站可以將任何對入口網站的修改從生產環境中隔離。 您可以在不同的電腦（如下所示）上部署其他網頁入口網站，或將它部署到同一部電腦上的不同網頁目錄（未顯示）。 若要完成後一個步驟，必須手動將額外的 CQD 網頁入口網站複製到生產電腦，因為 CQD 設定處理常式總是使用預先定義的 web 應用程式名稱將 CQD Web 入口網站部署到預設的網站。
  
![規劃 CQD 多重伺服器](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>支援的拓撲

CQD 不會合並來自多個 QoEMetrics 資料庫的資料，就像在有多個商務用 Skype 伺服器拓撲結構一樣，每個都有自己的監視伺服器的情況。 每個 CQD 實例都必須指向一個 QoEMetrics 資料庫。 不過，因為 CQD 會將許多報告工作負荷從監視伺服器移出，所以針對每個商務用 Skype Server 拓撲所需部署一個監視伺服器的大型組織，應該考慮使用單一監視伺服器來進行所有拓撲。
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD 的基礎結構需求
<a name="Infrastructure_Req"> </a>

CQD （包括其所有元件和相依元件）可以在虛擬機器、單一電腦或跨多台電腦部署。 最低的軟體和硬體需求如下所示。 根據使用中的商務用 Skype 伺服器使用者和硬體及設定的數量，資料的可用性與查詢效能可能會不同到幾個小時，因此以下提供一些效能測量。
  
|||
|:-----|:-----|
|針對 CQD 2015 <br/> |  <br/> |
|支援的作業系統  <br/> |Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2  <br/> |
|支援的 SQL Server  <br/> |SQL Server 2012、SQL Server 2014、SQL Server 2016  <br/> |

|||
|:-----|:-----|
|針對 CQD 2019 <br/> |  <br/> |
|支援的作業系統  <br/> |Windows Server 2016、Windows Server 2019  <br/> |
|支援的 SQL Server  <br/> |SQL Server 2017、SQL Server 2019  <br/> |
   
CQD 利用 Microsoft SQL Server、Microsoft SQL Server Analysis Services 及 Microsoft 網際網路資訊服務，因此 CQD 最低的硬體和軟體需求基本與那些相依元件完全相同。 不過，根據組織對資料新鮮度的需求（取決於組織產生的 QoE 資料量）和部署成本，也應該進行其他部署考慮。
  
CQD 中的資料處理分為兩個主要階段： 
  
- QoE 封存流程
    
- CQD Cube 處理
    
  **QoE 封存處理。** QoE 封存處理任務會將資料從監視伺服器上的 QoE 度量資料庫複製到 QoE 封存資料庫。 在兩種情況下，任務的處理時間會有基本不同的效能特性。 第一次是在初次安裝 CQD 之後。 當您在全新安裝之後第一次執行工作時，QoE 封存處理工作會將 QoE 度量資料庫中的所有資料複製到 QoE 封存資料庫。 第二個是在這個初始迴圈之後的定期處理。 QoE 封存處理工作將會每隔15分鐘執行一次，然後處理 QoE 度量資料庫中的任何新 QoE 記錄。 一般來說，最初的處理時間並不是要考慮的問題，因為它只會在第一次安裝 CQD 時執行。 不過，如果 CQD 伺服器嚴格受置備，此工作可能需要幾個小時的時間。 請參閱下表，以取得初始 QoE 封存處理時間的範例。
  
  **CQD Cube 處理。** 多維資料集處理工作會將 QoE 封存資料庫中的資料匯總至立方體。 初始的立方體處理時間與後續的 cube 處理時間是由用於 CQD Cube 的 SQL Server Analysis Services 版本所決定。 如果使用標準版，則初始的 cube 處理時間與後續的立方體處理時間之間沒有任何差異，因為每次重新整理立方體資料時，都會完全處理所有可用的資料。 （這表示隨著 QoE 封存資料庫中的資料量增加，Cube 處理時間會增加。）因為商務智慧版本和企業版的 SQL Server 都有分區支援，所以只要使用其中一個版本，只有初始執行就會處理 QoE 封存資料庫中的所有資料。 在後續執行中，當任務每15分鐘觸發一次時，任務只會處理自上次執行任務之後新增至 QoE 封存資料庫的新記錄。 一天一次，包含當月資料的分區也會有完整的處理。
  
物理電腦特徵可能會影響 CQD 效能，以及 SQL Server 元件提供的軟體功能。 與其他元件相比，QoE 封存元件會比其他元件更大量佔用磁碟空間，而 Cube 元件則需要大量的 CPU 和記憶體。 所有這些因素都會影響 CQD 的總資料處理時間，這會直接影響資料的新鮮度和可用性。 組織應該根據組織的個別需求，在硬體和軟體上做出決策。 
  
### <a name="tested-hardware-configurations"></a>已測試的硬體設定

本節假設環境中有單一的 QoEMetrics 資料庫。 
  
**電腦設定檔**

|**加工**|**CPU 核心**|**RAM**|**在同一磁片上 QoE 封存與立方體**|**在同一磁片上 QoE 封存與 SQL Temp 資料庫**|
|:-----|:-----|:-----|:-----|:-----|
|虛擬機器  <br/> |4  <br/> |7 GB  <br/> |是  <br/> |是  <br/> |
|4核  <br/> |4  <br/> |20 GB  <br/> |是  <br/> |否  <br/> |
|8核  <br/> |型  <br/> |32 GB  <br/> |是  <br/> |否  <br/> |
|16核  <br/> |位  <br/> |128 GB  <br/> |否  <br/> |否  <br/> |
   
**效能結果**

|**加工**|**QoE 度量資料庫大小**|**SQL 分區**|**磁片類型**|**串流數**|**初始封存處理常式**|**初始 Cube 進程**|**後續的封存處理常式**|**後續 Cube 進程**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|虛擬機器  <br/> |900 MB  <br/> |通過  <br/> |VHD （可變大小）  <br/> |. 5 M  <br/> |30 m  <br/> |2 m  <br/> |30秒  <br/> |1 m  <br/> |
|虛擬機器  <br/> |9 GB  <br/> |通過  <br/> |VHD （可變大小）  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|虛擬機器  <br/> |9 GB  <br/> |通過  <br/> |VHD （固定大小）  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|虛擬機器  <br/> |30 + GB  <br/> |通過  <br/> |VHD （固定大小）  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8核  <br/> |9 GB  <br/> |通過  <br/> |多個磁片  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8核  <br/> |9 GB  <br/> |條  <br/> |多個磁片  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8核  <br/> |30 + GB  <br/> |通過  <br/> |多個磁片  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8核  <br/> |30 + GB  <br/> |條  <br/> |多個磁片  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4核  <br/> |200 GB  <br/> |通過  <br/> |多個磁片  <br/> |125 M  <br/> |6天  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16核  <br/> |500 GB  <br/> |條  <br/> |多個心軸  <br/> |250 M  <br/> |8天  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*我們不會在實際部署中遇到這些錯誤，因為 QoE 指標資料庫必須分別有9和18個月的資料，但此處提供的內容是完整的。
  
### <a name="service-account-requirements"></a>服務帳戶需求

您需要在 CQD 伺服器上的 SQL 代理程式可以用來匯入資料至 QoEArchiveDB 的帳戶（具有 QoEMetrics 的讀取存取權）。
  
您可能也需要為 SSAS 作業設定個別的帳戶，以從 QoEArchiveDB 拉入資料（這是選擇性程式）。
  
IIS 最常使用網路服務做為應用程式池身分識別，但可以設定為服務帳戶。
  
### <a name="portal-access-control"></a>入口網站存取控制

根據預設，任何經過驗證的使用者都可以存取。 您可以使用 IIS 授權規則來變更，以限制使用特定的群組。
  
### <a name="pre-install-requirements"></a>安裝前的需求

這些指示會假設已安裝 QoE 度量值資料庫，且它正在商務用 Skype Server 拓撲結構中執行。
  
#### <a name="hardware-requirements"></a>硬體需求

CQD 利用 Microsoft SQL Server、Microsoft SQL 分析伺服器及 Microsoft Internet Information Server，讓 CQD 的硬體和軟體需求的最低程度與那些相依元件基本相同。 不過，根據組織對資料新鮮度的需求（取決於組織產生的 QoE 資料量）和部署成本，也應該進行其他部署考慮。
  
#### <a name="software-requirements"></a>軟體需求

CQD 需要下列作業系統：
  
- Windows Server 2008 R2 （含 IIS 7.5）
    
- Windows Server 2012 與 IIS 8。0
    
- Windows Server 2012 R2 （含 IIS 8.5）

- Windows Server 2016 （含 IIS 10.0）（僅適用于商務用 Skype Server 2019 CQD）

- Windows Server 2019 （僅適用于商務用 Skype Server 2019 CQD）
    
下列是所需的 IIS 角色服務（以層次結構順序排列）：
  
- 網頁伺服器
    
  - 常見的 HTTP 功能
    
  - 靜態內容
    
  - 預設檔
    
  - 應用程式開發
    
  - ASP.NET
    
  - ISAPI 篩選
    
  - 健康&amp;狀況診斷
    
  - HTTP 記錄
    
  - 安全性
    
  - URL 授權
    
  - Windows 驗證
    
  - 管理工具
    
  - IIS 管理主控台
    
> [!NOTE]
>  請注意，以下是上述需求：有可用的 .Net framework > 3.5 和4.5 版本。 兩者都是必要的（特別是需要 3.5 SP1） >。在部分系統中，如果 ASP.NET 是在安裝 IIS 前進行設定，則 ASP.NET 可能不會在 IIS 中註冊。 問題會透過對應 .Net 版本的應用程式池缺失，而且在應用程式池設定中也缺少 .NET CLR 版本。 若要修正 Windows Server 2008 R2 上的這類問題`%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`，請執行。 在 Windows Server 2012 和 Windows Server 2012 R2 上， `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45`執行後接著從 IIS 管理器中的預設網站移除 "system.servicemodel" 模組。 > 管理工具是選擇性的，但建議使用。
  
若要使用 PowerShell 安裝這些需求，請執行下列動作：
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

支援下列版本的 SQL Server：
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 （僅適用于商務用 Skype Server 2019 CQD）
    
出於效能考慮，建議使用商務智慧或企業版。 這些版本可讓您使用多個可以並行處理的分區檔案，這對於處理橫跨多個月或更長的資料很有用。 
  
雖然不建議這樣做，但也支援標準版。 處理將會受限於單一磁碟分割（需要在安裝期間進行設定）。 
  
在任何情況下，都必須安裝「資料庫引擎服務」和「分析服務」。 建議您，但不需要安裝「管理工具-完成」功能，這會新增 SQL Server Management Studio 對 Analysis Services 的支援。 [功能選取] 畫面看起來應該像是圖。
  
![SQL Server 功能需求](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
配置 SSAS 設定時，請在 Analysis Services 設定中，將 "伺服器模式" 設為 "多維與資料採礦模式"。 
  
如需安裝及設定 SQL Server 商務智慧功能的其他說明，請參閱[在多維和資料採礦模式中安裝 Analysis Services](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx)。
  
#### <a name="account-requirements"></a>帳戶需求

針對最低許可權的原則，建議使用三個網域服務帳戶： 
  
- 在 QoE 封存 SQL Server 實例（在安裝期間建立連結的伺服器物件）中，已有 QoE 量度資料庫的登入安全性主體（具有 db_datareader 許可權）和登入安全性主體的一個。 這個帳戶將用來執行 SQL Server 代理程式作業的「QoE 封存資料」步驟。
    
- 一種將用來執行 SQL Server 代理作業的「處理 Cube」步驟。 安裝程式將會建立登入安全性原則，以 QoE 封存資料庫（具有讀取和寫入權限），同時也會在多維資料集的 QoE 角色（具有完全控制許可權）中建立成員。
    
- 一個用來針對網頁入口網站和 web Api 執行 IIS 輔助進程。 安裝程式將會建立一個登入安全性原則，以 QoE 封存資料庫（具有 [讀取] 許可權）、[知識庫資料庫] （具有 [讀取及寫入] 許可權）以及 [QoERole （具有完全控制許可權）] 的成員。 
    
    > [!NOTE]
    > 當 QoE 封存資料庫與知識庫資料庫都裝載于同一個 SQL Server 中時，只會建立一個具有兩個使用者對應的登入安全主體。 
  
前兩個帳戶可以邏輯視為「後端服務帳戶」，而最後一個帳戶則是「前端服務帳戶」。 雖然不建議這樣做，但在任何情況下都可以使用單一帳戶。
  
> [!NOTE]
> 啟動安裝的使用者帳戶必須具備 QoE 量度 DB 的讀取存取權（除了必須在進行安裝的 QoE 封存資料庫伺服器上擁有電腦系統管理員許可權）。 
  
## <a name="capacity-planning"></a>容量規劃
<a name="Infrastructure_Req"> </a>

CQD 的設計是針對 QoEMetrics 的最低影響：程式碼已優化為不鎖定資料，且匯入作業是可調式的。
  
要使用的硬體類型，取決於您對同步處理執行速度的需求。 磁片大小調整如下所示：
  
- QoEArchive 的大約 1.5 x 大於 QoEMetrics DB
    
- SSIS 立方體將資料壓縮到資料庫幾乎10倍
    
- 資料每月分區;可以刪除分區
    

