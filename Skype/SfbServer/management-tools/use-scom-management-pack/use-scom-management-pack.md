---
title: 使用 SCOM 管理元件管理商務用 Skype Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 摘要：瞭解如何設定您的商務用 Skype Server 2015 基礎結構，以與 System Center Operations Manager 搭配使用。
ms.openlocfilehash: 0349949afe27c5351f9eefda7a5cc5f44a0a072d
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014937"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>使用 SCOM 管理元件管理商務用 Skype Server 2015
 
**摘要：** 瞭解如何設定商務用 Skype Server 2015 基礎結構，以與 System Center Operations Manager 搭配使用。
  
在理想的世界中，您絕對不會遇到商務用 Skype Server 2015 的問題。 不過，商務用 Skype Server 可能會受到外部因素的影響，例如網路損毀和硬體失敗。 透過使用商務用 Skype Server 2015 管理元件，您可以主動識別並處理潛在的問題。 如此一來，商務用 Skype Server 2015 管理元件會擴充 System Center Operations Manager 的功能。
  
此資訊是根據商務用 Skype Server 2015 通訊軟體之監控套件的版本9319.0 所撰寫。
  
## <a name="configuration-overview"></a>設定概述

 若要設定商務用 Skype Server 2015 基礎結構與 System Center Operations Manager 搭配使用，您必須執行下列三項操作：
  
識別及  [設定主要管理伺服器](configure-the-primary.md)。 若要這麼做，您必須安裝 System Center Operations Manager 2012 SP1 或 R2。 
  
 識別及[設定要監視的商務用 Skype Server 電腦](configure-computers-to-monitor.md)。 若要使用 System Center Operations manager 監視商務用 Skype Server 電腦，您必須安裝 System Center Operations manager 代理程式檔案，並設定每一部伺服器充當 proxy。 
  
 識別及 [安裝及設定監視程式節點](watcher-nodes.md)。 監看員節點是定期執行商務用 Skype Server 綜合交易的電腦-Windows PowerShell 指令程式會驗證金鑰商務用 Skype Server 元件（例如，登入系統的功能，或 exchange 立即訊息的功能）如預期般運作。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System CenterOperations Manager 根管理伺服器和代理程式支援

管理套件可以搭配 System Center Operations manager 2007 R2 (64-位)  (支援遷移，只) 或 System Center operations manager 2012 SP1 &amp; R2 (64 位) 或 System Center operations manager 2016 (64-位) 。 下表顯示商務用 Skype Server 2015 的管理元件支援的設定： 
  
|設定|支援？|
|:-----|:-----|
|Windows Server 2008 R2 operating system  <br/> Windows Server 2012R2 作業系統   |是。 在商務用 Skype Server 2015 伺服器及綜合交易觀察程式節點上。   |
|聚簇伺服器   |不支援。   |
|無代理監控   |不支援。   |
|虛擬環境   |是。   |
|加入網域的伺服器角色   |所有內部商務用 Skype Server 2015 伺服器角色必須已加入網域。   |
|獨立伺服器角色   |商務用 Skype Server 2015 Edge server 不一定要加入網域。   |
|拓撲限制   |部署中的所有伺服器角色都必須從相同的 Operations Manager 管理群組進行監視。   |
|綜合交易觀察程式節點   |支援使用綜合交易記錄觀察器節點的監控案例， (需要) 其他設定。 不需要以加入網域的觀察者節點。   |
   
下表顯示綜合交易觀察器節點的容量及作業系統需求：
  
|硬體元件|基本需求|
|:-----|:-----|
|CPU   |下列其中之一：  <br/> 64位處理器、四核心2.33GHz 或更高版本  <br/> 64位2路處理器、雙核2.33GHz 或更高版本   |
|記憶體   |8 GB   |
|作業系統   |Windows Server 2008 R2  <br/> Windows Server 2012 R2   |
|網路   |1 Gbps 的網路介面卡   |
   
## <a name="prerequisites"></a>必要條件

若要執行綜合交易觀察程式節點，您必須先安裝下列專案：
  
- System CenterOperations Manager 代理程式 
    
-  Microsoft .NET Framework 4.5
    
- 商務用 Skype Server 核心安裝檔 (OcsCore.msi) 和整合通訊 Managed API (UCMA)  (版本必須符合商務用 Skype Server WatcherNode.msi 版本) 
    
## <a name="files-in-this-monitoring-pack"></a>此監控套件中的檔案

商務用 Skype Server 2015 的監控套件包含下列檔案：
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>新增功能

下列功能是商務用 Skype Server 2015 管理套件的新功能。

- **在 [9 月2019更新](https://www.microsoft.com/en-in/download/details.aspx?id=47364)中所做的變更** 有些警示已移除特殊字元。 在某些情況下，特殊字元會干擾 SCOM 命令通道通知功能。

- **用戶端 Sign-In 的自動探索** 登入商務用 Skype Server 2015 的用戶端應用程式通常會自動探索要登入的伺服器。 綜合交易現在支援已正確設定自動探索的驗證。
    
- **自訂的綜合交易執行間隔** 為了簡化觀察程式節點的設定程式，綜合交易可共用使用者帳戶。 這會在測試進行序列化時，減慢測試執行的頻率，以避免衝突。 根據預設，綜合交易會每隔15分鐘執行一次，以確保所有測試都有時間執行。 選擇對每位使用者使用更多使用者或較少測試的系統管理員，現在也可以減少執行間隔。
    
- **影片 Interop 服務綜合交易** 從其他廠商解決方案遷移至商務用 Skype Server 2015 的客戶，通常需要繼續使用影片電話會議裝置 (VTCs) 其他廠商。 Video Interop 伺服器是新的商務用 Skype Server 2015 伺服器角色，可讓客戶透過視頻 SIP 主幹連線到 cisco CUCM，繼續使用其會議室中的 cisco VTCs。 這項功能也會新增綜合交易，以協助確認影片 Interop 伺服器是否已開啟，並可以處理透過視頻 SIP 主幹的傳入連線。
    
- **應用程式共用會議綜合交易** 現在支援應用程式共用會議的端對端案例驗證。
    
## <a name="monitoring-scenarios"></a>監視案例

商務用 Skype Server 2015 管理元件利用多種功能來協助您偵測和診斷問題。 這些功能可讓您即時看到商務用 Skype Server 2015 環境的健康情況。
  
|監控案例|描述|
|:-----|:-----|
|綜合交易   | Windows PowerShell Cmdlet，以測試及協助確保案例的高可用性，例如登入、目前狀態、IM 和會議的使用者。 <br/> 綜合交易可以從任何地理位置執行（包括企業內部、企業外及分支辦公室）。  <br/> 當綜合交易失敗時，會建立 HTML 記錄檔，以協助判斷失敗的確切性質。 這包括瞭解哪些動作失敗、每個動作的延遲、用來執行測試的命令列，以及所發生的特定錯誤。   |
|通話可靠性警示   |商務用 Skype Server 2015 server 寫入的詳細通話記錄 (cdr) 會反映使用者是否可以連線至通話或終止通話的原因。 通話可靠性警示會查詢 CDR 資料庫，以產生警示，指出當高數目的使用者遇到對等通話或基本會議功能的連線問題時。  <br/> 案例覆蓋範圍包括音訊通話、對等立即訊息 (IM) 及其他會議功能。   |
|媒體質量警示   |查看經驗品質 (QoE) 在每次通話結束時商務用 Skype Server 2015 用戶端所發佈的報表的資料庫查詢。 這些查詢會產生警示，以找出使用者最可能經歷通話和會議期間受損媒體質量的情況。 資料是以重要的度量單位（例如資料包延遲和遺失）為基礎，其可直接促進使用者經驗的品質。   |
|元件狀況警示   |個別的伺服器元件會透過事件記錄檔和效能計數器來引發警示，以指出可能會對使用者案例產生重大影響的失敗條件。 這些警示指出各種情況，例如未執行的服務、高失敗率、高郵件延遲或連線問題。   |
|依賴性狀況監控   |由於各種外部原因，商務用 Skype Server 可能會失敗。 管理元件會監視及收集可能表示嚴重問題的重要外部相依性資料。 這些相依性包括 Internet Information Services (IIS) 可用性及商務用 Skype Server 所用伺服器的 CPU。   |

   
### <a name="alert-prioritization"></a>警示優先順序

提醒分為下列類別： 
  
 **高優先順序警示：** 這些警示表示的情況會導致大量使用者的服務中斷，而且需要立即採取行動。 綜合交易和離線服務所偵測到的中斷 (例如商務用 Skype Server Audio/Video 會議) 資格為高優先順序警示。 相反地，單一機器上的元件失敗不是高優先順序的警示。 商務用 Skype Server 2015 在這些情況下具有內建的高可用性功能，例如，在負載平衡器背後的多部前端伺服器。
  
 **中優先順序警示：** 這些警示會指出會影響使用者子集的條件，或指出通話品質中的問題，例如元件失敗、通話中的延遲或通話中較低的音訊品質。 此類別中的警示是有狀態的 (也就是說，根據網路連線的狀態，警示變更的性質。 ) 例如，如果通話建立時間指出延遲，但接著又回到一般臨界值，System Center Operations Manager 中將會自動解決這種媒體優先順序警示，而管理員不需要採取動作。 不能自動解決的警示，通常是由系統管理員在同一部商務日的位址。
  
 **其他警示：** 這些警示會從可能會影響特定使用者或使用者子集的元件產生。 例如，一般警示是通訊錄服務無法為 user： testuser@contoso.com 分析 Active Directory®網域服務 (AD DS) 專案。 當系統管理員有可用時間時，就可以處理這些警示。
  
### <a name="synthetic-transactions"></a>綜合交易

商務用 Skype Server 2015 管理元件會透過綜合交易，提供更高的警示覆蓋範圍。 綜合交易是與 Operations Manager 管理元件整合的 Windows PowerShell Cmdlet，用來測試端對端使用者案例。 當您指定伺服器以執行綜合交易時，這些指令程式會定期由管理套件觸發。 綜合交易產生的失敗會產生狀態警示。 以下是商務用 Skype Server 2015 支援的綜合交易：
  


|註冊、目前狀態及連絡人支援的綜合交易|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|1   |註冊 (使用者登入)    |可用的 Lync Server 2010 及以上   |
|第   |通訊錄服務 (檔案下載)    |可用的 Lync Server 2010 及以上   |
|3    |通訊錄 Web 查詢   |可用的 Lync Server 2010 及以上   |
|4    |目前狀態   |可用的 Lync Server 2010 及以上   |
|5   |整合聯絡資料儲存   |可用的 Lync Server 2013 及以上   |

  

|Peer-to-Peer 服務支援的綜合交易|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|6    |Peer-to-Peer 立即訊息   |可在 Lync Server 2010 和之後使用   |
|7    |Peer-to-Peer 音訊影片   |可在 Lync Server 2010 和之後使用   |
|8    |MCX Peer-to-Peer 立即訊息 (mobile)    |可在2011年9月發行的 Lync Server 2010 中取得，以商務用 Skype 2015   |
 
> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。


|支援的會議和持續聊天的綜合交易|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|9    |音訊和視訊會議   |可在 Lync Server 2010 和之後使用   |
|10    |資料會議   |可在 Lync Server 2013 和之後使用   |
|11    |立即訊息會議   |可在 Lync Server 2010 和之後使用   |
|12    | 常設聊天室  |可在 Lync Server 2013 和之後使用   |
|13   |加入 Launcher (排程的會議)    |可在 Lync Server 2013 和之後使用   |
|14    |電話撥入式會議   |商務用 Skype Server 2015 的新功能   |
|15    |應用程式共用會議   |商務用 Skype Server 2015 的新功能   |
|16    |UCWA 會議 (web 會議加入)    |商務用 Skype Server 2015 的新功能   |


|網路和夥伴相依性支援的綜合交易|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|17    |AV Edge Connectivity   |可在 Lync Server 2013 和之後使用   |
|18    |AV Edge connectivity Exchange 整合郵件連線 (語音信箱)    |可在 Lync Server 2013 和之後使用   |
|19   |PSTN Peer-to-Peer 通話   |可在 Lync Server 2010 和之後使用   |
|共   |XMPP 立即訊息 (同盟)    |可在 Lync Server 2013 和商務用 Skype 2015 中使用   |
| 21   |視訊互通性伺服器   |商務用 Skype Server 2015 的新功能   |

   
## <a name="how-health-rolls-up"></a>狀況匯總的方式

下表顯示商務用 Skype Server 監視套件之物件的健康狀態。
  
|Management Pack 物件|描述|
|:-----|:-----|
|商務用 Skype Server部署   |代表組織中商務用 Skype Server 2015 的部署。   |
|商務用 Skype Server網站   |代表部署服務的不同地理位置。   |
|商務用 Skype Server池   |為使用者提供通訊服務（如立即訊息和會議）的網站) 中的集區 (。 適用于前端集區、Edge 集區和 Director 集區，即使指定集區中只有一部電腦。   |
|商務用 Skype Server作用   |主控商務用 Skype Server 服務的伺服器角色。   |
|商務用 Skype Server服務   |代表在特定電腦上部署的功能 (例如，fp01.contoso.com) 上的 user service。   |
|商務用 Skype Server元件   |服務的元件 (例如，通訊錄下載元件是 Web 服務) 的一部分。   |
|商務用 Skype Server集區觀察程式   |針對一個集區執行的綜合交易的實例。   |
|商務用 Skype Server註冊器觀察程式   |針對一個註冊集區執行之綜合交易的實例。   |
|商務用 Skype Server使用者服務集區觀察程式   |針對一個使用者服務集區執行之綜合交易的實例。   |
|商務用 Skype Server語音集區觀察程式   |在一個語音集區上執行之綜合交易的實例。   |
|商務用 Skype Server埠觀察程式   |針對一個集區執行的埠檢查實例。   |
|簡易 URL 觀察程式   |在部署中執行已設定的簡易 URLs HTTPS 探查。   |
   
![SCOM 匯總。](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
商務用 Skype Server 集區可以包含多個個別商務用 Skype Server 系統 (具有一個以上商務用 Skype Server 角色、商務用 Skype Server 服務，以及商務用 Skype Server 元件) 。 因此，個別伺服器或元件的失敗對商務用 Skype Server 集區的整體健康情況而言並不很重要，因為相同集區中的其他伺服器也可以為用戶端提供應用程式服務。 健康情況會在百分比層級上向上翻轉至商務用 Skype Server 集區。 
  
商務用 Skype Server 集區觀察程式會針對商務用 Skype Server 集區執行綜合交易。 連續失敗一或多個綜合交易 (稱為「連續輪詢間隔」的處理常式) 會將嚴重健康狀態狀態累加至集區層級 (最糟的所有綜合交易) ，如下圖所示。 
  
![SCOM 匯總連續輪詢。](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>最佳作法：建立自訂的管理套件

依預設，Operations Manager 會儲存所有自訂專案，例如對預設管理套件的覆寫。 最佳作法是針對您要自訂的每個密封管理套件建立個別的管理套件。 
  
當您建立用來儲存密封管理套件之自訂設定的管理元件時，建議您適當地命名新的管理套件，例如「商務用 Skype Server 2015 自訂」。 
  
建立新的管理套件以儲存每個密封管理套件的自訂，讓從測試環境將自訂匯出至實際執行環境變得更容易。 這也會使刪除管理元件變得更容易，因為您必須先刪除任何相依性，才能刪除管理元件。 若所有管理套件的自訂專案儲存在預設管理元件中，且您需要刪除單一管理元件，您必須先刪除預設管理套件，也就是刪除其他管理元件的自訂專案。 
  
## <a name="links"></a>連結

下列連結會連線至與 System Center 2012 監視套件相關聯的常見工作相關資訊：
  
- [管理套件生命週期](/previous-versions/system-center/system-center-2012-R2/hh212732(v=sc.12))
    
- [如何在 Operations Manager 中匯入管理套件2012](/previous-versions/system-center/system-center-2012-R2/hh212691(v=sc.12))
    
- [如何覆寫規則或監視器](/previous-versions/system-center/system-center-2012-R2/hh212869(v=sc.12))
    
- [如何在 Operations Manager 中建立執行身分帳戶2012](/previous-versions/system-center/system-center-2012-R2/hh321655(v=sc.12))
    
- [管理執行方式帳戶和設定檔](/previous-versions/system-center/system-center-2012-R2/hh212714(v=sc.12))
    
- [如何匯出 Operations Manager 管理元件](/previous-versions/system-center/system-center-2012-R2/hh320149(v=sc.12))
    
- [如何移除 Operations Manager 管理元件](/previous-versions/system-center/system-center-2012-R2/hh230746(v=sc.12))
    
下列連結會連線至與 System Center 2007 監視套件相關聯的常見工作相關資訊：
  
- [管理套件生命週期](/previous-versions/system-center/operations-manager-2007-r2/cc974486(v=technet.10))
    
- [如何在 Operations Manager 中匯入管理套件2007](/previous-versions/system-center/operations-manager-2007-r2/cc974494(v=technet.10))
    
- [如何使用覆寫進行監視](/previous-versions/system-center/operations-manager-2007-r2/bb309719(v=technet.10))
    
- [如何在 Operations Manager 中建立執行身分帳戶2007](/previous-versions/system-center/operations-manager-2007-r2/bb309445(v=technet.10))
    
- [如何修改現有的執行方式設定檔](/previous-versions/system-center/operations-manager-2007-r2/dd891202(v=technet.10))
    
- [如何匯出管理套件自訂](/previous-versions/system-center/operations-manager-2007-r2/cc974487(v=technet.10))
    
- [如何移除管理套件](/previous-versions/system-center/operations-manager-2007-r2/cc974489(v=technet.10))
    
如需 Operations manager 和監控套件的相關問題，請參閱[System Center Operations manager 社區論壇](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
有用的資源是[System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/)博客，包含特定監控套件的「範例」公告。
  
如需 Operations Manager 的其他資訊，請參閱下列博客： 
  
- [Operations Manager 小組博客](https://blogs.technet.com/momteam/default.aspx)
    
- [OpsMgr 上的想法](https://thoughtsonopsmgr.blogspot.com/)
    
   
> [!IMPORTANT]
> 非 Microsoft 網站上的所有資訊和內容都是由網站的擁有者或使用者所提供。 Microsoft 對本網站的資訊不做任何擔保、明確、暗示或法令。 
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 2015 管理工具](../../management-tools/management-tools.md)