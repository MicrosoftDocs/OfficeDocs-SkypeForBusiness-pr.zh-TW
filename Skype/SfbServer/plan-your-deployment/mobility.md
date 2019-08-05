---
title: 針對商務用 Skype Server 進行行動規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: 規劃商務用 Skype Server 的行動方案實施方案。
ms.openlocfilehash: 8b0ba8dd4ae07d3330a8ca722a1101c6b41a7cec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192984"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>針對商務用 Skype Server 進行行動規劃
 
規劃商務用 Skype Server 的行動方案實施方案。
  
在商務用 Skype Server 中, 您可以部署行動裝置功能, 以便在行動裝置上供應商務用 Skype Server 的功能。 本文提供行動功能的詳細資料, 並協助您規劃部署。
  
商務用 Skype Server 的行動功能可支援商務用 Skype 的行動用戶端, 以及要傳回2010的 Lync 用戶端。 部署之後, 您的使用者就可以使用支援的 iOS、Android 和 Windows Phone 行動裝置連線到您的商務用 Skype Server 部署, 以利用幾個不同的功能, 包括企業語音功能。 我們已包含下列部分清單, 您也可以查看商務用[Skype 的桌面用戶端功能比較](clients-and-devices/desktop-feature-comparison.md), 以取得詳細資訊:
  
- 傳送及接收郵件
    
- 查看目前狀態
    
- [查看連絡人]
    
- 按一下以加入會議
    
- 透過公司通話
    
- 一個數位達到
    
- 語音信箱
    
- 未接來電通知
    
- [語音 over IP (VoIP)]
    
- 出席者影片 (H-p)
    
- 查看會議內容 (PowerPoint 和桌面/應用程式共用)
    
所有這些都是透過整合通訊 Web API 來完成, 或 UCWA。 UCWA 是在 Lync Server 2013 中第一次推出, 且仍在適用于商務用 Skype Server。 還有其他功能可與 Lync 2010 用戶端通訊, 並提供行動服務 (MCX)。 這些是免費的服務, 可讓 Lync Server 2010 和2013用戶端以及商務用 Skype 用戶端順利地存取商務用 skype 伺服器部署。
  
> [!NOTE]
> MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
請務必注意, 雖然所有這些功能都是在行動完成後才提供, 但在某些裝置上, 它們的運作方式可能稍有不同。 我們在商務用 Skype 的行動[用戶端功能比較](clients-and-devices/mobile-feature-comparison.md)中, 有一個討論哪些功能適用于哪些裝置的網站。 我們也會在[規劃用戶端與裝置](clients-and-devices/clients-and-devices.md)時有一些很棒的裝置和作業系統資訊。
  
行動性利用自動探索功能, 可讓用戶端自動找出商務用 Skype Server web 服務, 而不需要輸入任何 Url (甚至不需要知道它們)。 如果您需要進行一些疑難排解, 仍支援手動輸入 Url。
  
如果商務用 Skype app 不是在背景中執行 (或針對不支援在背景執行的應用程式的行動裝置), 也支援推播通知。 當裝置或應用程式處於非使用中時, 會傳送推播通知給行動裝置。 當您的手機不在使用中時, 可能會遺失 IM 訊息, 而這會導致傳送推播通知 (這會在應用程式在背景執行時顯示為快顯或通知)。 有了推播通知, 使用者就不會錯過 IM 或語音通話。
  
如需詳細資訊, 我們提供下列各節:
  
- [行動元件](mobility.md#MobilityComponents)
    
- [支援的拓撲](mobility.md#SupportedTopos)
    
- [技術需求](mobility.md#TechRequirements)
    
- [定義行動需求](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>行動元件
<a name="MobilityComponents"> </a>

商務用 Skype Server 有四種服務可共同作業:
  
- **整合通訊 Web API (UCWA)**
    
    針對商務用 Skype Server 提供與行動與 web 用戶端即時通訊的服務。 部署商務用 Skype Server 時, 在內部和外部 web 服務中建立的 UCWA 虛擬目錄。 此虛擬目錄中的虛擬元件, 可接受從 UCWA 啟用的用戶端的呼叫。 用戶端應用程式使用 representational 狀態傳輸 (REST) 介面進行通訊, 以進行下列作業:
    
  - 平臺
    
  - 聯絡
    
  - 立即訊息 (IM)
    
  - VoIP
    
  - 視訊會議
    
  - 共同作業
    
    UCWA 使用 P 形式的通道來傳送事件, 例如傳入通話、內送 IM 或訊息到用戶端應用程式。
    
- **行動服務 (MCX)**
    
    支援行動裝置上的商務用 Skype 伺服器功能, 例如 IM、目前狀態及連絡人。 行動服務是安裝在每個需要在行動裝置上支援商務用 Skype Server 功能之每個池的每個前端伺服器上。 當您安裝商務用 Skype Server 2015 時, 會在您的前端伺服器上的內部和外部網站底下建立新的虛擬目錄 (Mcx)。
    
    > [!NOTE]
    > MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。 所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。 使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。
  
- **自動探索服務**
    
    識別使用者的位置, 並讓行動裝置和其他商務用 Skype 用戶端找出資源 (例如商務用 Skype Server Web 服務的內部和外部 URL、Mcx URL 或 UCWA URL), 而不論網路位置為何。 自動搜尋使用硬式編碼主機名稱 (lyncdiscoverinternal 網路中的使用者、lyncdiscover 網路以外的使用者), 以及使用者的 SIP 網域。 它支援使用 HTTP 或 HTTPS 的用戶端連線。 
    
    自動探索服務會安裝在每個前端伺服器上, 以及每個要支援行動裝置上的商務用 Skype Server 功能的每個泳池中的每個控制器上。 當您安裝服務時, 會在您的前端伺服器與控制器上的內部和外部網站下建立新的虛擬目錄 (自動探索)。
    
- **推播通知服務**
    
    位於商務用 Skype Online 資料中心的雲端服務。 在沒有在背景中執行商務用 Skype 用戶端的手機上, 當發生新事件時, 錯過事件的通知 (稱為推播通知) 會改為傳送至行動裝置。 行動服務會傳送通知給推播通知服務 (MPNS), 然後將它傳送到行動裝置。 然後, 使用者就可以在行動裝置上回應通知, 以啟動應用程式。 此功能需要 Edge 伺服器。
    
## <a name="supported-topologies"></a>支援的拓撲
<a name="SupportedTopos"> </a>

針對您的拓撲規劃, 我們有下列支援的商務用 Skype Server 應用程式:
  
- 行動標準版
    
- 行動企業版
    
您應該可以在商務用 Skype Server Edge 伺服器或 Lync Server 2013 Edge 伺服器中使用這種功能。
  
當 collocated 使用中繼伺服器角色 (具有兩個網路介面) 的情況下, 前端伺服器支援行動服務, 但您必須採取適當的步驟來設定這些介面。 您必須將 IP 位址指派給將會以中繼伺服器通訊的特定介面, 以及將通訊為前端伺服器的網路 IP 介面。 您可以在拓撲建立器中, 為每個服務選取正確的 IP 位址, 而不是使用預設的 [**使用所有已設定的 ip 位址**] 選取專案。
  
## <a name="technical-requirements"></a>技術需求
<a name="TechRequirements"> </a>

規劃行動使用者可能會遇到的各種行動應用程式案例, 這一點非常重要。 例如, 某些人可能會在工作以外的地方開始使用行動裝置應用程式, 只要透過3G 網路連線, 就能在公司的 Wi-fi 網路達到工作時切換。 在離開建築物時, 他們可能會切換到4G。 規劃現在可讓您支援這些網路轉換, 並保證一致的使用者體驗。
  
### <a name="dns-configuration"></a>DNS 設定

行動服務 Mcx 和 UCWA 使用 DNS 的方式相同。 使用自動搜尋, 行動裝置會使用 DNS 來找出資源。 在 DNS 查詢期間, 連線嘗試與內部 DNS 記錄 (lyncdiscoverinternal) 相關聯的 FQDN。 [內部網功能變數名稱稱])。 如果內部 DNS 記錄無法用來建立該連線, 則會嘗試第二次連線至外部 DNS 記錄 (lyncdiscover. [sipdomain]). 為什麼有兩個？ 您網路內部的行動裝置將能夠使用內部自動探索 URL。 外部行動裝置將會使用外部自動探索 URL。 不論是哪一種情況, 自動探索服務都會傳回使用者 [家用] 池的所有 Web 服務 Url, 包括行動服務 (Mcx 和 UCWA)。
  
外部自動探索要求將會透過您針對商務用 Skype Server 所設定的反向 proxy 進行。 不過, 內部行動服務 URL 與外部行動服務 URL 都與外部 Web 服務 FQDN 相關聯。 因此, 無論行動裝置是在您的網路內部或外部, 該裝置都會透過您的反向 proxy 連線至外部的商務用 Skype Server 行動裝置服務。
  
> [!NOTE]
> 正如我們剛才所說, 所有行動服務流量 (內部和外部) 都將透過您的反向 proxy 進行。 但有時候, 當內部流量透過介面時, 就會出現問題, 只是在同一個介面上再試一次。 這可能會違反您的欺騙 (正式稱為 TCP 資料包欺騙) 安全性規則。 您必須允許**頭髮釘**選, 才能進行行動函式功能。
  
> [!NOTE]
> 如果您已準備好這樣做, 您也可以選擇使用獨立于防火牆的反向 proxy (出於安全性考慮, 請務必在防火牆上強制進行欺騙防範)。 如此一來, hairpin 可能會在反向 proxy 的外部介面 (而非防火牆的外部介面) 發生。 這可讓您在您在反向 proxy 中放鬆規則時, 在防火牆上正確偵測到欺騙, 而且您可以取得行動功能。 
  
> [!NOTE]
> 如果您移至此路線, 請務必使用 DNS 主機或 CNAME 記錄來定義 hairpin 行為的反向 proxy (而非防火牆) (如果可能的話)。 
  
您需要設定一些專案來支援公司網路內部和外部的使用者。
  
以下是內部和外部 web Fqdn 的規則:
  
- 針對自動探索的新 CNAME 或 A (IPv6、AAAA) DNS 記錄。
    
- 如果您想要透過 Wi-fi 網路支援推播通知, 請選擇 [新增防火牆規則]。
    
- 內部伺服器憑證上的消費者替代名稱和反向 proxy 憑證, 用於自動搜尋。
    
- 前端伺服器硬體載入平衡的設定變更來源關聯性。
    
以下是支援行動服務與自動探索服務所需的拓撲需求:
  
- 前端池內部網站 FQDN 必須與前端池外部 web FQDN 不同。
    
- 內部網站 FQDN 必須只能解析為商業網路內且可供存取。
    
- 外部 web FQDN 必須只能解析為網際網路, 且可從網際網路存取。
    
- 對於公司網路內部的使用者, 行動服務 URL 必須定址至外部 web FQDN。 此需求適用于行動服務, 且僅適用于此 URL。
    
- 對於公司網路以外的使用者, 要求必須移至前端池或主管的外部 web FQDN。
    
如果您支援自動探索, 您將需要針對每個 SIP 網域進行下列 DNS 記錄:
  
- 內部 DNS 記錄可支援從貴組織的網路內部連線的行動使用者。
    
- 外部或公用的 DNS 記錄, 可支援從網際網路連線的行動使用者。
    
內部自動探索 URL 不應來自內部網路外部。 外部自動探索 URL 無法從您的網路中定址。 但如果外部 URL 無法這樣做, 您的行動用戶端功能可能不會受到影響, 因為內部 URL 將永遠先嘗試。
  
### <a name="port-and-firewall-requirements"></a>埠和防火牆需求

我們在其他檔中已涵蓋大部分的功能, 但特別是行動裝置, 如果您有任何使用者都駐留在 Survivable 分支裝置 (SBA) 上, 您就會想要在企業 Wi-fi 網路上開啟下列埠:
  
- UcwaSipExternalListeningPort 需要5088。
    
- UcwaSipPrimaryListeningPort 需要5089。
    
### <a name="certificate-requirements"></a>證書需求

如果您使用的是商務用 Skype mobile 用戶端的自動探索, 您必須在您的憑證上修改 SAN (subject 備用名稱) 清單, 以支援行動用戶端的安全連線。 如果您已經有現成的憑證, 您將需要用 SAN 專案 (如下所述) 要求並指派新的憑證。 在執行自動探索服務的每個前端伺服器和主管 (如果在您的環境中), 都必須執行這個動作。 我們也建議您在反向 proxy 憑證上修改 SAN 清單, 新增您組織中每個 SIP 網域的 SAN 專案。
  
如果您是從內部 CA (憑證授權單位) 要求新的認證, 但公用憑證較複雜, 而且可能需要重新要求的費用較高, 所以這應該是一個簡單的程式, 而不是提及可能需要增加大量 SIP 才能花費太高的費用網域新增至新的公用證書。在這種情況下, 有一個支援但**不建議**的方法。 您可以設定您的反向 proxy, 透過埠80進行初始自動探索服務要求, 這將會使用 HTTP, 而不是埠 443 (以及443是預設設定)。 該傳入要求將會重新導向至您的前端池或控制器上的埠8080。 如此一來, 您就不需要進行任何憑證變更, 因為這種流量不會對要求使用 HTTPS。 不過, 我們不建議這樣做, 雖然它會適合您。
  
### <a name="windows-and-iis-requirements"></a>Windows 與 IIS 需求

您的商務用 Skype Server 環境必須具備支援的 Windows Server 版本。 因此, 您也應該使用 IIS 8 或 IIS 8.5 來滿足行動需求。 預設 ASP.NET 設定需要進行一些變更, 但行動服務安裝程式會自動執行此動作。
  
### <a name="hlb-requirements"></a>HLB 需求

如果您使用的是商務用 Skype Server 的拓朴, 且包含您的前臺端池 HLB (這會是包含多個前端伺服器的任何拓撲), 則必須設定適用于 Web 服務流量的外部 Web 服務虛擬 Ip (Vip)。針對來源。 來源關聯有助於確保將來自單一用戶端的多個連線傳送到同一個伺服器, 以維持會話狀態。
  
如果您打算只支援將商務用 Skype 行動用戶端僅限在您的內部 Wi-fi 網路上, 請按照外部 Web 服務 Vip 的說明, 設定來源的內部 Web 服務 Vip。 在這種情況下, 您應該針對 HLB 上的內部 Web 服務 Vip 使用 source_addr (或 TCP) 關聯。
  
如需所有這些內容的詳細資料, 請參閱商務用 Skype 檔的[負載平衡需求](network-requirements/load-balancing.md)。
  
### <a name="reverse-proxy-requirements"></a>反向 Proxy 需求

為了支援商務用 Skype 行動用戶端的自動探索, 您需要更新目前的發佈規則, 如下所示:
  
- 如果您決定要更新您的反向 proxy 憑證上的 SAN 清單, 且您在初始自動探索服務要求中使用 HTTPS, 您需要更新 lyncdiscover 的 web 發佈規則。\<sipdomain\>。 這通常與前端池上的外部 Web 服務 URL 的發佈 rul 結合。
    
- 如果您決定將 HTTP 用於初始自動探索服務要求, 以避免必須更新您的反向 proxy 憑證的 SAN 清單 (我們不建議這麼做), 您必須為埠 HTTP/TCP 80 建立新的 web 發佈規則 (如果沒有的話)。已. 如果該規則存在, 請將其更新為包含 lyncdiscover。\<sipdomain\>專案。
    
## <a name="defining-your-mobility-needs"></a>定義行動需求
<a name="MobilityNeeds"> </a>

現在我們已經回顧了拓撲、元件和技術需求, 讓我們來看看您的組織可能需要行動實現。
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>您想要使用商務用 Skype mobile 用戶端的自動探索嗎？

我們強烈建議您使用自動搜尋。 這將需要建立新的內部和外部 DNS 記錄, 如上述技術需求一節所述。 透過自動搜尋, 商務用 Skype 用戶端可以自動找出任何位置的商務用 Skype Server Web 服務, 而不需要手動輸入 URL。
  
如有需要, 您可以使用手動設定。 這些 Url 將需要由使用者輸入至其行動裝置:
  
- **Https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root**以進行外部存取。
    
- **Https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root**以取得內部存取。
    
同樣地, 我們建議您使用自動探索。 您可能會發現手動設定適用于疑難排解的目的。
  
### <a name="are-you-going-to-support-push-notifications"></a>您打算支援推播通知嗎？

推播通知是用來支援此功能的行動應用程式, 以在 app 不在使用中時通知事件使用者。 您的邊緣伺服器必須與您雲端的商務用 Skype Server 推播通知服務 (在商務用 Skype Online 資料中心中找到) 有一個同盟關聯。 您必須執行一個 Cmdlet, 才能啟用推播通知。
  
> [!NOTE]
> 如果您仍在使用 Lync Server 2010 用戶端, 他們將需要在您的企業 WiFi 網路上開啟 TCP 埠5223。 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>您是否要讓所有使用者都能存取所有行動功能, 或您想要指定可存取這些功能的使用者嗎？

我們有一個可協助所有使用者使用的功能, 以及是否依預設設定為這種方式的表格。 若要取得完整清單, 請複習 [[新增-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)]。
  
> [!NOTE]
> 所有這些功能的範圍為 [全域]/[網站/使用者]。 
  
|**功能**|**參數名稱**|**說明**|**預設設定**|
|:-----|:-----|:-----|:-----|
|啟用行動性  <br/> |EnableMobility  <br/> |在已安裝商務用 Skype mobile 用戶端的指定範圍內, 控制使用者。 如果原則設定為 False, 您的使用者將無法使用其用戶端登入。  <br/> |滿足  <br/> |
|外語音  <br/> |EnableOutsideVoice  <br/> |讓使用者能夠透過 [工作] 使用通話, 讓使用者可以使用自己的公司電話, 而不是行動電話號碼來傳送和接收通話。 如果將其設為 False, 您的使用者在使用其公司電話號碼時將無法撥打或接聽其行動電話。  <br/> |滿足  <br/> |
|啟用 IP 音訊和影片  <br/> |EnableIPAudioVideo  <br/> |設為預設值, 可讓使用者在行動裝置上使用 VoIP 撥打或接聽電話或視頻通話。 當設為 False 時, 您的使用者將無法使用其行動裝置來執行其中一項操作。  <br/> |滿足  <br/> |
|需要 IP 音訊的 WiFi  <br/> |RequireWiFiForIPAudio  <br/> |定義用戶端是否需要透過 VoIP (而不是行動電話資料網路) 撥打和接聽 VoIP 的通話。 如果是設定為 True, 您的使用者將只能在連線到 WiFi 時撥打及接聽 VoIP 通話。  <br/> |虛假  <br/> |
|IP 視頻需要 WiFi  <br/> |RequireWiFiForIPVideo  <br/> |定義用戶端是否需要在 WiFi (而非行動資料網路) 上撥打及接聽視頻通話。 如果是設定為 True, 您的使用者將只能在連線到 WiFi 時撥打及接聽 VoIP 通話。  <br/> |虛假  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>如果沒有已啟用企業語音的使用者可以使用「按一下」加入會議嗎？

若要讓使用者能夠存取行動功能, 以及透過公司通話, 必須為企業語音啟用這些功能。 但即使尚未啟用, 他們還是可以按一下行動裝置上的連結來加入會議, 但必須有指派適當的語音原則。 您可以執行下列其中一項操作:
  
- 將特定的語音原則指派給這些使用者, 或者,
    
- 確定全域原則或網站層級原則存在並套用至它們。
    
不論是哪一種方式, 您指派的語音原則都需要有公用的交換電話網絡 (PSTN) 使用記錄和路由, 以定義使用者可以撥出加入會議的位置。
  
> [!NOTE]
> 想要使用 [按一下以加入] 的行動使用者以及相關的 PSTN 使用記錄和語音路由, 因為當他們按一下行動裝置上的該連結時, 會產生來自商務用 Skype 伺服器的出站通話。 
  

