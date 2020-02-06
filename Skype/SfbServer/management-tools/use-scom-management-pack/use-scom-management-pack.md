---
title: 使用 SCOM 管理套件管理商務用 Skype Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 摘要：瞭解如何設定您的商務用 Skype Server 2015 基礎結構，以搭配 System Center Operations Manager 使用。
ms.openlocfilehash: 7982cd26b512574864e2d53d9c8ef771781348f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816102"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>使用 SCOM 管理套件管理商務用 Skype Server 2015
 
**摘要：** 瞭解如何設定您的商務用 Skype Server 2015 基礎結構，以搭配 System Center Operations Manager 使用。
  
在理想世界中，您不會在商務用 Skype Server 2015 中遇到問題。 不過，商務用 Skype Server 可能受外部因素影響，例如網路故障和硬體失敗。 透過使用商務用 Skype Server 2015 管理套件，您可以預先找出並解決可能的問題。 如此一來，商務用 Skype Server 2015 管理套件延伸了 System Center Operations Manager 的功能。
  
此資訊是根據商務用 Skype Server 2015 通訊軟體之監視套件版本9319.0 撰寫。
  
## <a name="configuration-overview"></a>配置概覽

 若要設定您的商務用 Skype Server 2015 基礎結構以搭配 System Center Operations Manager 使用，您必須執行下列三項操作：
  
找出並[設定主要管理伺服器](configure-the-primary.md)。 若要這樣做，您必須安裝 System Center Operations Manager 2012 SP1 或 R2。 
  
 找出並[設定要監視的商務用 Skype 伺服器電腦](configure-computers-to-monitor.md)。 若要使用 System Center Operations Manager 監視商務用 Skype Server 電腦，您必須安裝 System Center Operations Manager 代理檔案，並將每個伺服器設定為使用 proxy。 
  
 識別及[安裝及設定觀察程式節點](watcher-nodes.md)。 [觀察程式] 節點是定期執行商務用 Skype Server 綜合交易的電腦，這些 Cmdlet 會驗證該重要的商務用 Skype Server 元件，例如登入系統或 exchange 立即功能的功能。訊息會如預期的方式運作。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>系統中心作業管理員根管理伺服器與代理程式支援

管理套件可與 System Center Operations Manager 2007 R2 （64位）搭配使用（僅適用于遷移）或 System Center Operations Manager 2012 SP1 &amp; R2 （64）或 System Center operations manager 2016 （64位）。 下表顯示商務用 Skype Server 2015 的管理套件支援的設定： 
  
|Configuration|受?|
|:-----|:-----|
|Windows Server 2008 R2 作業系統  <br/> Windows Server 2012 R2 作業系統  <br/> |是。 在商務用 Skype Server 2015 server 和綜合交易觀察程式節點上。  <br/> |
|叢集服務器  <br/> |不支援。  <br/> |
|無代理監視  <br/> |不支援。  <br/> |
|虛擬環境  <br/> |是。  <br/> |
|加入網域的伺服器角色  <br/> |所有內部商務用 Skype Server 2015 伺服器角色都必須加入網域。  <br/> |
|獨立伺服器角色  <br/> |商務用 Skype Server 2015 Edge 伺服器不需要加入網域。  <br/> |
|拓撲限制  <br/> |部署中的所有伺服器角色，都必須從同一個 Operations Manager 管理群組監視。  <br/> |
|綜合交易觀察程式節點  <br/> |支援使用 [綜合交易觀察程式] 節點監視案例可用性（需要其他設定）。 不需要將觀察程式節點加入網域。  <br/> |
   
下表顯示綜合交易觀察程式節點的容量及作業系統需求：
  
|硬體元件|最低需求|
|:-----|:-----|
|CPU  <br/> |下列其中一項：  <br/> 64-位處理器、四核、2.33 GHz 或更新版本  <br/> 64位雙路處理器、雙核、2.33 GHz 或更新版本  <br/> |
|儲存體  <br/> |8 GB  <br/> |
|作業系統  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|網路  <br/> |1 Gbps 的1個網路介面卡  <br/> |
   
## <a name="prerequisites"></a>先決條件

若要執行綜合交易觀察程式節點，您必須先安裝下列各項：
  
- System Center Operations Manager 代理 
    
-  Microsoft .NET Framework 4。5
    
- 商務用 skype Server 核心安裝檔案（OcsCore）和整合通訊管理 API （UCMA）（版本必須符合商務用 Skype Server WatcherNode .msi 版本）
    
## <a name="files-in-this-monitoring-pack"></a>此監視套件中的檔案

商務用 Skype Server 2015 的監視套件包含下列檔案：
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode
    
## <a name="whats-new"></a>新增功能

下列功能是商務用 Skype Server 2015 管理套件的新增功能。

- **2019 年[9 月更新](https://www.microsoft.com/en-in/download/details.aspx?id=47364)中的變更**部分警示已移除特殊字元。 在某些情況下，特殊字元會干擾 SCOM 命令通道通知功能。

- **用戶端登入的自動探索**登入商務用 Skype Server 2015 的用戶端應用程式通常會自動探索要登入的伺服器。 綜合交易立即支援驗證正確設定自動探索。
    
- **自訂的綜合交易執行間隔**為了簡化觀察程式節點的設定程式，綜合交易可以共用使用者帳戶。 這會降低測試執行的頻率，因為測試是系列化的，以避免發生衝突。 根據預設，綜合交易會每隔15分鐘執行一次，以確保所有測試都有時間執行。 針對每個使用者選擇使用更多使用者或較少測試的系統管理員，現在也可以減少執行時間間隔。
    
- **影片交互操作服務綜合交易**從其他供應商解決方案遷移到商務用 Skype Server 2015 的客戶，通常想要繼續使用來自這些其他廠商的視頻 teleconferencing 裝置（VTCs）。 影片交互操作伺服器是新的商務用 Skype Server 2015 伺服器角色，可讓客戶透過視頻 SIP 幹線連線至 Cisco CUCM，繼續使用其會議室中的 Cisco VTCs。 此功能也會新增綜合交易，以協助驗證視頻互通性伺服器是否已啟動，並可在視頻 SIP 主幹上處理傳入的連線。
    
- **應用程式共用會議綜合交易**現在支援適用于應用程式共用會議的端對端案例驗證。
    
## <a name="monitoring-scenarios"></a>監控案例

商務用 Skype Server 2015 管理套件利用各種功能來協助您偵測及診斷問題。 這些功能可讓您即時看到商務用 Skype Server 2015 環境的健康情況。
  
|監控案例|說明|
|:-----|:-----|
|綜合交易  <br/> | Windows PowerShell Cmdlet 以進行測試，並協助確保案例的高可用性，例如登入、目前狀態、IM 和會議供使用者查看。 <br/> 綜合交易可以從任何地理位置執行，包括企業外部與分支辦公室以外的企業內部。  <br/> 當綜合交易失敗時，系統會建立 HTML 記錄 s 來協助判斷失敗的確切性質。 這包括瞭解哪個動作失敗、每個動作的延遲、用於執行測試的命令列，以及所發生的特定錯誤。  <br/> |
|通話可靠性警報  <br/> |商務用 Skype Server 2015 伺服器所撰寫的通話詳細資料記錄（CDRs）反映使用者是否可以連線到通話或來電終止的原因。 [通話可靠性警報] 會查詢 CDR 資料庫，以產生警示，指出當大量使用者遇到對等通話或基本會議功能的連接問題時。  <br/> 案例覆蓋範圍包括音訊通話、對等立即訊息（IM）及其他會議功能。  <br/> |
|媒體質量警示  <br/> |在每次通話結束時，會查看商務用 Skype Server 2015 用戶端所發佈的經驗品質（QoE）報告的資料庫查詢。 這些查詢會產生警示，以找出使用者在通話和會議期間最有可能遇到受損媒體質量的情況。 資料是根據主要度量單位（例如 [資料包延遲] 和 [遺失]）來建立，這會直接影響使用者的使用體驗品質。  <br/> |
|元件健康情況警示  <br/> |個別伺服器元件會透過事件日誌和效能計數器產生警示，以指出可能會對使用者案例產生嚴重影響的失敗情況。 這些警示會指出各種情況，例如未執行的服務、高失敗率、高資訊延遲或連線問題。  <br/> |
|相依性狀況監視  <br/> |商務用 Skype 伺服器可能會因為各種外部原因而失敗。 管理套件會監視和收集資料，以尋找可能表示嚴重問題的重要外部相依性。 這些相依性包括網際網路資訊服務（IIS）可用性，以及適用于商務用 Skype Server 的伺服器 CPU。  <br/> |
|||
   
### <a name="alert-prioritization"></a>警示優先順序

警報分為下列類別： 
  
 **高優先順序警示：** 這些警示代表會針對大型使用者群組造成服務中斷的情況，且需要立即採取行動。 綜合交易和離線服務（例如商務用 Skype Server 音訊/視訊會議）檢測到的中斷是合格的高優先順序警示。 相反地，單一電腦上的元件失敗不是高優先順序的警示。 商務用 Skype Server 2015 在這些情況下具有內建的高可用性功能，例如，在負載平衡器背後有多個前端伺服器。
  
 **中等優先順序警示：** 這些警示代表會影響使用者子集的條件，或代表通話品質問題，例如元件失敗、通話中的延遲，或通話中的音訊品質降低。 此類別中的警示是全狀態的（也就是根據網路連線的狀態，通知的性質變更。）例如，如果通話建立時間指出延遲，但接著又回到正常閾值，此媒體優先順序通知將在 System Center Operations Manager 中自動解決，而管理員則不需要採取動作。 無法自動解析的警示，通常是由系統管理員在同一個工作日中解決。
  
 **其他通知：** 這些警示是從可能會影響特定使用者或使用者子集的元件產生的。 例如，「通訊錄服務」可能無法分析使用者： testuser@contoso.com 的 Active Directory®網域服務（AD DS）專案。 當使用者有可用的時間時，系統管理員可以處理這些通知。
  
### <a name="synthetic-transactions"></a>綜合交易

商務用 Skype Server 2015 管理套件可透過綜合交易，為警報增加覆蓋範圍。 綜合交易是集成到 Operations Manager 管理套件中以測試端對端使用者案例的 Windows PowerShell Cmdlet。 當您指派伺服器來執行綜合交易時，系統會定期由管理套件觸發這些 Cmdlet。 綜合交易產生全狀態報警時產生的失敗。 以下是商務用 Skype Server 2015 支援的綜合交易：
  


|登記、目前狀態和連絡人支援的綜合交易|||
|:-----|:-----|:-----|
|1  <br/> |註冊（使用者登入）  <br/> |可用的 Lync Server 2010 及以上版本  <br/> |
|2  <br/> |通訊錄服務（檔案下載）  <br/> |可用的 Lync Server 2010 及以上版本  <br/> |
|3  <br/> |通訊錄 Web 查詢  <br/> |可用的 Lync Server 2010 及以上版本  <br/> |
|4  <br/> |目前狀態  <br/> |可用的 Lync Server 2010 及以上版本  <br/> |
|500  <br/> |整合連絡人存放區  <br/> |可用的 Lync Server 2013 及以上版本  <br/> |
||||   

|對等服務支援的綜合交易|||
|:-----|:-----|:-----|
|6  <br/> |對等立即訊息  <br/> |適用于 Lync Server 2010 及以上版本  <br/> |
|utf-7  <br/> |對等音訊影片  <br/> |適用于 Lync Server 2010 及以上版本  <br/> |
|型  <br/> |MCX 對等立即訊息（行動電話）  <br/> |在2011年9月發行的 Lync Server 2010 發佈至商務用 Skype 2015  <br/> |
 
> [!NOTE]
> MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。


|支援的會議和持續聊天的綜合交易|||
|:-----|:-----|:-----|
|9  <br/> |音訊和視訊會議  <br/> |適用于 Lync Server 2010 及以上版本  <br/> |
|第  <br/> |資料會議  <br/> |適用于 Lync Server 2013 及以上版本  <br/> |
|11  <br/> |立即訊息會議  <br/> |適用于 Lync Server 2010 及以上版本  <br/> |
|之間  <br/> | 常設聊天室 <br/> |適用于 Lync Server 2013 及以上版本  <br/> |
|合  <br/> |加入啟動器（排程的會議）  <br/> |適用于 Lync Server 2013 及以上版本  <br/> |
|4  <br/> |電話撥入式會議  <br/> |商務用 Skype Server 2015 中的新功能  <br/> |
|工資  <br/> |應用程式共用會議  <br/> |商務用 Skype Server 2015 中的新功能  <br/> |
|位  <br/> |UCWA 會議（網路會議加入）  <br/> |商務用 Skype Server 2015 中的新功能  <br/> |
||||

|網路與合作夥伴相依性支援的綜合交易|||
|:-----|:-----|:-----|
|11x17  <br/> |AV 邊緣連接  <br/> |適用于 Lync Server 2013 及以上版本  <br/> |
|滿  <br/> |AV 邊緣連通性 Exchange 整合郵件連線（語音信箱）  <br/> |適用于 Lync Server 2013 及以上版本  <br/> |
|合  <br/> |PSTN 對等通話  <br/> |適用于 Lync Server 2010 及以上版本  <br/> |
|20  <br/> |XMPP 立即訊息（同盟）  <br/> |在 Lync Server 2013 和商務用 Skype 2015 中提供  <br/> |
|日前  <br/> |視訊互通性伺服器  <br/> |商務用 Skype Server 2015 中的新功能  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>健康情況匯總

下表顯示商務用 Skype Server monitoring pack 物件的健康狀態。
  
|管理套件物件|說明|
|:-----|:-----|
|商務用 Skype Server 部署  <br/> |代表組織中商務用 Skype Server 2015 的部署。  <br/> |
|商務用 Skype Server 網站  <br/> |代表部署服務的不同地理位置。  <br/> |
|商務用 Skype 伺服器池  <br/> |在網站內提供通訊服務（例如立即訊息和會議）給使用者的文件庫。 適用于前端池、邊緣池及控制器池，即使在指定的池中只有一台電腦也一樣。  <br/> |
|商務用 Skype Server 角色  <br/> |主持商務用 Skype Server 服務的伺服器角色。  <br/> |
|商務用 Skype Server 服務  <br/> |代表在特定電腦上部署的功能（例如，fp01.contoso.com 上的使用者服務）。  <br/> |
|商務用 Skype Server 元件  <br/> |服務的元件（例如，通訊錄下載元件是 Web 服務的一部分）。  <br/> |
|商務用 Skype Server Pool 觀察程式  <br/> |針對一個池執行的綜合交易實例。  <br/> |
|商務用 Skype 伺服器註冊程式觀察程式  <br/> |針對單一註冊機構池執行的綜合交易的實例。  <br/> |
|商務用 Skype Server 使用者服務池觀察程式  <br/> |針對單一使用者服務池執行的綜合交易實例。  <br/> |
|商務用 Skype Server 語音信箱觀察程式  <br/> |在單一語音池中執行的綜合交易的實例。  <br/> |
|商務用 Skype 伺服器埠觀察程式  <br/> |針對一個池執行埠檢查的實例。  <br/> |
|簡單的 URL 觀察程式  <br/> |在部署中執行已設定的簡單 Url 的 HTTPS 探測。  <br/> |
   
![SCOM 匯總](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
商務用 Skype 伺服器池可以包含多個個別的商務用 Skype 伺服器系統（有一個以上的商務用 skype 伺服器角色、商務用 Skype Server 服務，以及商務用 Skype Server 元件）。 因此，個別伺服器或元件的失敗對商務用 Skype 伺服器池的整體健康情況不太重要，因為相同池中的其他伺服器可以為用戶端提供應用程式服務。 [健康情況] 會將百分比階層累加到商務用 Skype 伺服器池。 
  
商務用 Skype 伺服器池觀察程式會針對商務用 Skype 伺服器池執行綜合交易。 一或多個綜合交易連續失敗（稱為連續輪詢間隔的程式）會將重要健康情況狀態累加至池層級（任何綜合交易的最差），如下圖所示。 
  
![SCOM 匯總連續輪詢](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>最佳做法：建立自訂的管理套件

根據預設，Operations Manager 會儲存所有自訂專案，例如對預設管理套件的覆寫。 最佳做法是，針對您要自訂的每個密封管理套件建立一個單獨的管理套件。 
  
當您建立用來儲存密封管理套件之自訂設定的管理套件時，建議您適當地命名新的管理套件，例如「商務用 Skype Server 2015 自訂」。 
  
建立新的管理套件來儲存每個密封管理套件的自訂，讓您可以更輕鬆地將自訂從測試環境匯出到生產環境。 這也可以讓您更容易刪除管理套件，因為您必須先刪除任何相依性，才能刪除管理套件。 如果所有管理套件的自訂都儲存在預設的管理套件中，而且您需要刪除單一管理套件，您必須先刪除預設管理套件，這也會刪除其他管理套件的自訂專案。 
  
## <a name="links"></a>鏈路

下列連結可將您連線至與 System Center 2012 監視套件相關聯之一般工作的相關資訊：
  
- [管理套件生命週期](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [如何在 Operations Manager 2012 中匯入管理套件](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [如何覆寫規則或監視器](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [如何在 Operations Manager 2012 中建立執行方式帳戶](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [管理執行方式帳戶和設定檔](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [如何匯出 Operations Manager 管理套件](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [如何移除 Operations Manager 管理套件](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
下列連結可將您連線至與 System Center 2007 監視套件相關聯之一般工作的相關資訊：
  
- [管理套件生命週期](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [如何在 Operations Manager 2007 中匯入管理套件](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [如何使用覆寫進行監視](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [如何在 Operations Manager 2007 中建立執行方式帳戶](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [如何修改現有的執行方式設定檔](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [如何匯出管理套件自訂](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [如何移除管理套件](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
如需 Operations Manager 及監視套件的相關問題，請參閱[System Center Operations Manager 社區論壇](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
「[系統中心」作業管理員 Unleashed](https://opsmgrunleashed.wordpress.com/)博客是一種有用的資源，其中包含特定監視套件的「依範例」文章。
  
如需有關 Operations Manager 的其他資訊，請參閱下列博客： 
  
- [Operations Manager 團隊博客](https://blogs.technet.com/momteam/default.aspx)
    
- [古柯 Holman 的 OpsMgr 博客](https://blogs.technet.com/kevinholman/default.aspx)
    
- [OpsMgr 上的想法](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael Burri 的博客](https://rburri.wordpress.com/)
    
- [BWren 的管理空間](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> 非 Microsoft 網站上的所有資訊和內容都是由網站的擁有者或使用者所提供。 Microsoft 不會針對此網站上的資訊，進行任何明示、默示或法定保證。 
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 2015 管理工具](../../management-tools/management-tools.md)
