---
title: 為商務用 Skype Server 規劃行動性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: 為商務用 Skype Server 規劃行動的實施。
ms.openlocfilehash: 5c33c88d13dd3720d1526c1620f852fe176a9750
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096639"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>為商務用 Skype Server 規劃行動性
 
為商務用 Skype Server 規劃行動的實施。
  
在商務用 Skype Server 中，您可以部署行動功能，以在行動裝置上供應商務用 Skype Server 功能。 本文提供行動功能的詳細資料，並協助您規劃部署。
  
商務用 Skype Server 的行動功能可支援商務用 Skype 的行動裝置，以及 Lync 用戶端回到2010。 部署之後，您的使用者可以使用支援的 iOS、Android 和 Windows Phone mobile 裝置，連線至您的商務用 Skype 伺服器部署，以利用多種不同的功能，包括企業語音功能。 我們已包含下列部分清單，您也可以檢查商務用 [Skype 的桌面用戶端功能比較](clients-and-devices/desktop-feature-comparison.md) ，以取得詳細資訊：
  
- 傳送和接收郵件
    
- 查看目前狀態
    
- 查看連絡人
    
- 按一下以加入會議
    
- 從公司通話
    
- 單一號碼達到
    
- 語音信箱
    
- 未接來電通知
    
- Voice over IP (VoIP)
    
- 出席者影片 (H-p) 
    
- 查看會議內容 (PowerPoint 和桌面/應用程式共用) 
    
全部都透過整合通訊 Web API 或 UCWA 來完成。 UCWA 最初已引進 Lync Server 2013，它仍用於商務用 Skype Server。 還有其他功能可與 Lync 2010 用戶端進行通訊，而且其行動性服務 (MCX) 。 這些是免費服務，可讓 Lync Server 2010 和2013用戶端（以及商務用 Skype 用戶端）成功存取商務用 Skype Server 部署。
  
> [!NOTE]
> MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。 所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
請務必注意，在實施行動能力後，所有這些功能都能使用，但在某些裝置上的處理方式可能稍有不同。 在商務用 Skype 的行動 [用戶端功能比較](clients-and-devices/mobile-feature-comparison.md)上，我們有討論哪些功能可用於哪些裝置的網站。 在 [規劃用戶端和裝置](clients-and-devices/clients-and-devices.md)時，我們也會有一些極佳的裝置和作業系統資訊。
  
行動性利用自動探索功能，可讓用戶端自動找出商務用 Skype Server web 服務，而不需要使用者輸入任何 URLs (他們甚至不必知道) 。 如果您需要進行一些疑難排解，仍然支援手動輸入 URLs。
  
當商務用 Skype 應用程式未在後臺 (執行，或是不支援後臺) 中執行的應用程式的行動裝置，也支援推播通知。 將推播通知傳送給行動裝置，以瞭解裝置或應用程式處於非使用中時發生的事件。 當您的電話未使用中時，有一個很好的範例會遺失 IM 訊息，這樣會導致傳送推播通知 (此項會呈現為 toast 或通知，如應用程式是在背景) 中執行。 使用推播通知時，使用者將不會錯過 IM 或語音通話。
  
如需詳細資訊，我們有下列區段：
  
- [行動元件](mobility.md#MobilityComponents)
    
- [支援的拓撲](mobility.md#SupportedTopos)
    
- [技術需求](mobility.md#TechRequirements)
    
- [定義行動需求](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>行動元件
<a name="MobilityComponents"> </a>

商務用 Skype Server 有四種服務可共同作業：
  
- **Unified Communications Web API (UCWA)**
    
    為商務用 Skype Server 提供即時通訊的服務，與行動裝置和 web 用戶端通訊。 部署商務用 Skype Server 時，會在內部和外部 web 服務中建立 UCWA 虛擬目錄。 此虛擬目錄中的虛擬元件，可接受來自啟用 UCWA 之用戶端的呼叫。 用戶端應用程式會透過代表性狀態轉移進行通訊， (REST) 介面：
    
  - 存在
    
  - 接觸
    
  - 立即訊息 (IM) 
    
  - VoIP
    
  - 影片會議
    
  - 協作
    
    UCWA 使用 P-GET 通道，將事件（如來電、內送 IM）或郵件傳送至用戶端應用程式。
    
- **行動服務 (MCX)**
    
    支援行動裝置上的商務用 Skype 伺服器功能，例如 IM、目前狀態及連絡人。 行動服務安裝在每個集區中的每一部前端伺服器上，以支援行動裝置上的商務用 Skype Server 功能。 當您安裝商務用 Skype Server 2015 時，會在前端伺服器上的內部和外部網站下建立新的虛擬目錄 (Mcx) 。
    
    > [!NOTE]
    > MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。 所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
- **自動探索服務**
    
    識別使用者的位置，並可讓行動裝置和其他商務用 Skype 用戶端尋找資源 (例如商務用 Skype Server Web 服務的內部和外部 URL、Mcx URL 或 UCWA URL) 不論網路位置為何。 自動探索使用 lyncdiscoverinternal 網路內部使用者的硬編碼主機 (名，為網路內部的使用者) lyncdiscover，以及使用者的 SIP 網域。 它支援使用 HTTP 或 HTTPS 的用戶端連線。 
    
    自動探索服務會安裝在每個前端伺服器及每個集區中的每個 Director 上，以支援行動裝置上的商務用 Skype Server 功能。 當您安裝服務時，會在前端伺服器及 Director 上的內部和外部網站下建立新的虛擬目錄 (自動探索) 。
    
- **推播通知服務**
    
    位於商務用 Skype Online 資料中心的雲端式服務。 在沒有在後臺執行商務用 Skype 用戶端的電話，當發生新的事件時，會將錯過的事件通知 (稱為推播通知) 會傳送至行動裝置。 行動服務會將通知傳送至推播通知服務 (MPNS) ，然後將其傳送至行動裝置。 然後，使用者可以在其行動裝置上回應通知，以啟動應用程式。 這種功能需要 Edge Server。
    
## <a name="supported-topologies"></a>支援的拓撲
<a name="SupportedTopos"> </a>

針對您的拓撲規劃，我們有下列支援的商務用 Skype Server 應用程式：
  
- 行動 Standard Edition
    
- 行動企業版
    
您應該能夠搭配商務用 Skype Server Edge server 或 Lync Server 2013 Edge server 使用此功能。
  
當組合具有轉送伺服器角色的轉送伺服器角色，且有兩個網路介面，但您必須採取適當的步驟來設定這些介面時，前端伺服器便支援行動服務。 您必須將 IP 位址指派給將會以轉送伺服器通訊的特定介面，以及會以前端伺服器進行通訊的網路 IP 介面。 您可以在拓撲產生器中，為每個服務選取正確的 IP 位址，而不要使用預設值 [ **使用所有設定的 IP 位址** ] 選取範圍。
  
## <a name="technical-requirements"></a>技術需求
<a name="TechRequirements"> </a>

請務必規劃行動使用者可能會遇到的各種行動應用程式案例。 例如，某人可以透過3G 網路連接來開始使用工作以外的行動應用程式，然後在其接觸公司 Wi-Fi 網路時切換到公司的網路。 當您離開大樓時，他們可能會切換至4G。 現在規劃可讓您支援這些網路轉換，並保證一致的使用者體驗。
  
### <a name="dns-configuration"></a>DNS 設定

行動服務 Mcx 及 UCWA 使用 DNS 的方式相同。 使用自動探索時，行動裝置會使用 DNS 來尋找資源。 在 DNS 查閱期間，連接嘗試與內部 DNS 記錄相關聯的 FQDN (lyncdiscoverinternal。[internal domain name] ) 。 如果內部 DNS 記錄無法用來建立該連線，則會嘗試第二個連線，這次 (lyncdiscover 的外部 DNS 記錄。[microsoft.rtc.management.xds.sipdomain] ) 。 為什麼有兩個呢？ 網路內部的行動裝置將能夠使用內部自動探索 URL。 外部行動裝置會使用外部自動探索 URL。 在任何情況下，自動探索服務都會傳回使用者主集區的所有 Web 服務 URLs，包括行動服務 (Mcx 及 UCWA) 。
  
期望外部自動探索要求會透過您為商務用 Skype 伺服器設定的反向 proxy。 不過，內部行動服務 URL 與外部行動服務 URL 都與外部 Web 服務 FQDN 相關聯。 因此，不論行動裝置在網路內部或外部，裝置都永遠會透過反向 proxy 連線至外部的商務用 Skype 伺服器行動服務。
  
> [!NOTE]
> 如剛才所述，所有的行動服務流量 (內部及外部) 都會透過您的反向 proxy 進行。 但是有時候，當內部流量透過介面時，就會出現問題，只是在相同介面上再試一次。 這可能會違反您的欺騙 (正式稱為 TCP 資料包欺騙) 安全性規則。 您必須允許將「 **頭髮** 上的頭髮具有行動功能。
  
> [!NOTE]
> 如果您已準備好執行這項作業，您也可以選擇使用不同于防火牆 (的反向 proxy，出於安全性目的，在您的防火牆) 應一定強制進行欺詐防護。 如此一來，髮夾可能會發生在反向 proxy 的外部介面，而不是防火牆的外部介面。 這可讓您在您的反向 proxy 上放鬆規則時，在防火牆上正確偵測哄騙，而且您也可以取得行動能力。 
  
> [!NOTE]
> 如果您移至此路由，請務必使用 DNS 主機或 CNAME 記錄來定義髮夾行為的反向 proxy， (非防火牆) （如有可能）。 
  
您需要設定一些專案，以支援公司網路內部和外部的使用者。
  
以下是內部及外部 web Fqdn 的規則：
  
- 新的 CNAME 或 (主機，如果是 IPv6，AAAA) DNS 記錄，則會自動探索。
    
- 新增防火牆規則（如果您想要透過您的 Wi-Fi 網路支援推播通知）。
    
- 內部伺服器憑證和反向 proxy 憑證上的主體替代名稱，以進行自動探索。
    
- 前端伺服器硬體負載平衡設定會變更來源親近性。
    
以下是支援行動性服務和自動探索服務所需的拓撲需求：
  
- 前端集區內部 web FQDN 必須與前端集區外部 web FQDN 不同。
    
- 內部 web FQDN 必須僅解析至公司網路內，並可從公司網路存取。
    
- 外部 web FQDN 必須僅解析為網際網路，而且可以從網際網路存取。
    
- 對於公司網路內部的使用者，行動服務 URL 必須定為外部 web FQDN。 這項需求適用于行動服務，且僅適用于此 URL。
    
- 對於公司網路外部的使用者，要求必須移至前端集區或 Director 的外部 web FQDN。
    
如果您支援自動探索，您必須為每個 SIP 網域建立下列 DNS 記錄：
  
- 內部 DNS 記錄，以支援從組織網路內部連線的行動使用者。
    
- 外部或公開的 DNS 記錄，以支援從網際網路連線的行動使用者。
    
內部自動探索 URL 不應該從您的內部網路外部定址。 外部自動探索 URL 不應該從您的網路中可定址。 不過，如果這不可能是外部 URL，您的行動用戶端功能可能不會受到影響，因為會永遠先嘗試內部 URL。
  
### <a name="port-and-firewall-requirements"></a>埠和防火牆需求

我們已在其他檔中涵蓋大部分內容，但特別是針對行動性，如果您擁有位於 Survivable Branch 裝置上的任何使用者 (SBA) ，您就會想要在企業 Wi-Fi 網路上開啟下列埠：
  
- UcwaSipExternalListeningPort 需要5088。
    
- UcwaSipPrimaryListeningPort 需要5089。
    
### <a name="certificate-requirements"></a>憑證需求

如果您正在使用商務用 Skype 行動用戶端的自動探索，您需要在憑證上修改 SAN (主體替代名稱) 清單，以支援行動用戶端的安全連線。 如果您已有就地的憑證，則需要使用此處所述的 SAN 專案要求並指派新的憑證。 在執行自動探索服務的環境) 中，每個前端伺服器及 Director (都必須執行此操作。 我們也建議修改反向 proxy 憑證上的 SAN 清單，新增組織中每個 SIP 網域的 SAN 專案。
  
如果您要求新的憑證從內部 CA (憑證頒發機構) ，則這是一個簡單的程式，但公用憑證變得更複雜，而且重新要求的成本可能很高，但若要將大量 SIP 網域新增至新的公用憑證，則會有太高的代價。在這種情況下，有一種支援的方法，但 **不建議使用**。 您可以設定反向 proxy，透過埠80來進行初始自動探索服務要求，它會使用 HTTP，而不是埠443（即 HTTPS (，而443是預設設定) ）。 該傳入要求會重新導向至前端集區或 Director 上的埠8080。 這樣一來，您就不需要進行任何憑證變更，因為這種流量不會針對要求使用 HTTPS。 不過，我們不建議您這樣做，不過它會為您運作。
  
### <a name="windows-and-iis-requirements"></a>Windows 和 IIS 需求

您應具備商務用 Skype 伺服器環境支援的 Windows Server 版本。 因此，您也應該要有 IIS 8 或 IIS 8.5，以滿足您的行動需求。 您必須對預設的 ASP.NET 設定進行一些變更，但行動服務安裝程式會自動執行這項作業。
  
### <a name="hlb-requirements"></a>HLB 需求

如果您使用的是商務用 Skype Server 的拓撲，且其中包含一部前端) 伺服器 (集區的 HLB （該拓撲會包含多部前端伺服器的拓撲），則必須為來源設定 Web 服務流量的外部 Web 服務虛擬 IPs (VIPs) 。 來源相關性可協助確保將單一用戶端的多個連線傳送至相同的伺服器，以維護會話狀態。
  
如果您計畫只在內部 Wi-Fi 網路上支援商務用 Skype 行動用戶端，則應該針對 [外部 Web 服務] Vip 所述，設定來源的內部 Web 服務 VIPs。 在此情況下，您應該針對 HLB 上的內部 Web 服務 Vip，使用 source_addr (或 TCP) 親近性。
  
如需詳細資訊，請參閱商務用 [Skype 的負載平衡需求](network-requirements/load-balancing.md) 檔。
  
### <a name="reverse-proxy-requirements"></a>反向 Proxy 需求

為了支援商務用 Skype 行動用戶端的自動探索，您必須更新目前的發行規則，如下所示：
  
- 如果您決定更新反向 proxy 憑證上的 SAN 清單，而您要使用 HTTPS 來進行初始自動探索服務要求，您必須更新 lyncdiscover 的 web 發行 \<sipdomain\> 規則。 這通常會與前端集區上的外部 Web 服務 URL 的發佈 rul 合併。
    
- 如果您已決定使用 HTTP 來進行初始自動探索服務要求，以避免更新反向 proxy 憑證的 SAN 清單，但我們不建議您)  (，您必須為埠 HTTP/TCP 80 建立新的 web 發行規則（如果沒有的話）。 如果該規則存在，請將它更新為包含 lyncdiscover。\<sipdomain\> 進入。
    
## <a name="defining-your-mobility-needs"></a>定義行動需求
<a name="MobilityNeeds"> </a>

現在，我們已複習拓撲、元件及技術需求，讓我們看看您的組織可能需要在行動性實施方面的需求。
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>您是否要使用商務用 Skype mobile 用戶端的自動探索？

我們強烈建議您使用自動探索。 如以上的技術需求一節所述，它將需要建立新的內部和外部 DNS 記錄。 透過自動探索，商務用 Skype 用戶端可以從任何位置自動尋找商務用 Skype Server Web 服務，而不需要手動輸入 URL。
  
您可以視需要使用手動設定。 使用者必須將這些 URLs 輸入行動裝置：
  
- **Https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** 用於外部存取。
    
- **Https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** 用於內部存取。
    
再說一次，我們建議您使用自動探索。 您可能會發現手動設定對於疑難排解的目的很有説明。
  
### <a name="are-you-going-to-support-push-notifications"></a>您是否要支援推播通知？

推播通知用於支援此功能的行動應用程式，可在應用程式非使用中時通知使用者事件。 您的 Edge Server 需要與雲端式商務用 Skype Server 推播通知服務（位於商務用 Skype Online 資料中心的同盟關聯）。 您需要執行 Cmdlet 以啟用推播通知。
  
> [!NOTE]
> 如果您仍在使用 Lync Server 2010 用戶端，則必須在您的企業 WiFi 網路上，TCP 埠5223開啟輸出。 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>您是否要讓所有使用者都存取所有行動功能，或要指定可以存取這些功能的使用者嗎？

我們有一個表格可協助所有使用者使用的部分功能，以及這些功能是否是以預設值設定。 如需完整清單，請參閱 [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
  
> [!NOTE]
> 所有這些功能的範圍為全域/網站/使用者。 
  
|**功能**|**參數名稱**|**描述**|**預設設定**|
|:-----|:-----|:-----|:-----|
|啟用行動性  <br/> |EnableMobility  <br/> |控制已安裝商務用 Skype mobile 用戶端之指定範圍內的使用者。 若原則設定為 False，您的使用者將無法使用用戶端登入。  <br/> |對  <br/> |
|外語音  <br/> |EnableOutsideVoice  <br/> |可讓使用者使用「來電」功能，讓使用者可以使用其公司電話號碼，而不是其行動電話號碼來傳送和接收通話。 如果將其設為 False，使用者在使用其公司電話號碼時，將無法在行動電話上撥打或接聽電話。  <br/> |對  <br/> |
|啟用 IP 音訊和影片  <br/> |EnableIPAudioVideo  <br/> |設定為預設值，讓使用者可以使用 VoIP 在其行動裝置上撥打或接聽電話或視頻通話。 設為 False 時，您的使用者將無法使用行動裝置執行這兩項作業。  <br/> |對  <br/> |
|需要 IP 音訊的 WiFi  <br/> |RequireWiFiForIPAudio  <br/> |定義用戶端是否需要在 WiFi 上使用 VoIP，而不是行動電話資料網路，來撥打和接收通話。 如果設定為 True，您的使用者只會在透過 WiFi 連線時撥打和接收 VoIP 通話。  <br/> |False  <br/> |
|需要 IP 影片的 WiFi  <br/> |RequireWiFiForIPVideo  <br/> |定義用戶端是否需要在 WiFi，而不是行動電話資料網路上撥打和接收通話。 如果設定為 True，您的使用者只會在透過 WiFi 連線時撥打和接收 VoIP 通話。  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>是否應該未啟用 Enterprise Voice 的使用者可以使用按一下以加入加入會議？

若要讓使用者能夠存取行動功能及呼叫透過工作，必須啟用 Enterprise Voice。 不過，即使未啟用，仍然可以按一下行動裝置上的連結來加入會議，但只有在他們具有適當的語音原則時，才可以加入會議。 您可以：
  
- 將特定的語音原則指派給這些使用者，或
    
- 請確定全域原則或網站層級原則存在，且適用于。
    
無論是哪一種方式，您指派的語音原則都必須是公用交換電話網路 (PSTN) 流量記錄和路由，以定義使用者可以撥出以加入會議的位置。
  
> [!NOTE]
> 想要使用 [按一下以加入] 的行動使用者需要語音原則，以及相關的 PSTN 使用方式記錄和語音路由，因為當他們在行動裝置上按一下該連結時，就會產生來自商務用 Skype 伺服器的撥出電話。 
