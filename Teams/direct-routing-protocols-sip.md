---
title: 電話系統直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由式通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: a66213214457648ec0b699d77bdadc96113fba27
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780682"
---
# <a name="direct-routing---sip-protocol"></a>直接路由 SIP 通訊協定

本文說明直接路由如何實現會話初始通訊協定（SIP）。 若要在會話邊界控制器（SBC）與 SIP proxy 之間正確路由流量，某些 SIP 參數必須有特定的值。 本文適用于負責設定內部部署 SBC 與 SIP proxy 服務之間的連線的語音系統管理員。

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>處理傳入要求：尋找租使用者和使用者

在撥入通話中，SIP proxy 需要尋找通話是目的地的租使用者，並在這個租使用者中找到特定使用者。 租使用者管理員可能會在多個租使用者中設定非已執行的號碼（例如 + 1001）。 因此，請務必找出要在其上執行數位查閱的特定租使用者，因為在多個 Office 365 組織中，非使用中的號碼可能是相同的。  

本節將說明 SIP proxy 如何找到租使用者與使用者，以及如何在傳入連線上執行 SBC 驗證。

下列是撥入電話的 SIP 邀請訊息範例：

| 參數名稱 | 值的範例 | 
| :---------------------  |:---------------------- |
| 要求 URI | 邀請 sip:+18338006777@sip.pstnhub.microsoft.com SIP/2。0 |
| Via 頁首 | Via： SIP/2.0/TLS sbc1 biz： 5058; 別名; 分支 = z9hG4bKac2121518978 | 
| Max-轉寄頁首 | 最大轉寄：68 |
| 從頁首 | 從頁首開始： <sip： 7168712781@sbc1. biz; 傳輸 = udp; tag = 1c747237679 |
| 移至頁首 | 至： sip:+183338006777@sbc1.adatum.biz | 
| CSeq 頁首 | CSeq：1個邀請 | 
| 連絡人標題 | 連絡人： <sip： 68712781@sbc1 biz; transport = tls> | 

在收到邀請時，SIP proxy 會執行下列步驟：

1. 檢查憑證。 在初始連線中，直連路由服務會取得連絡人標頭中所提供的 FQDN 名稱，並將其與所提供憑證的通用名稱或消費者替換名稱相符。 SBC 名稱必須符合下列其中一個選項：

   - 選項1。 在連絡人標題中提供的完整 FQDN 名稱，必須符合所提供憑證的通用名稱/消費者替換名稱。  

   - 選項2。 在連絡人標題中顯示的 FQDN 名稱網域部分（例如，FQDN 名稱 sbc1.adatum.biz 的 adatum.biz），必須符合常見名稱/消費者替換名稱（例如 *. adatum.biz）中的萬用字元值。

2. 嘗試使用在連絡人標題中提供的完整 FQDN 名稱尋找租使用者。  

   檢查連絡人標題（sbc1.adatum.biz）的 FQDN 名稱是否已在任何 Office 365 組織中註冊為 DNS 名稱。 如果找到，則會在已將 SBC FQDN 註冊為功能變數名稱的租使用者中執行使用者查閱。 如果找不到，則會套用步驟3。   

3. 步驟3只有在步驟2失敗時才適用。 

   從 FQDN 中移除主機部分（FQDN： sbc12.adatum.biz，在移除主機部分： adatum.biz）後，檢查是否已在任何 Office 365 組織中將此名稱註冊為 DNS 名稱。 如果找到，則會在此租使用者中執行使用者查閱。 如果找不到，通話就會失敗。

4. 使用在 Request URI 中所提供的電話號碼，在步驟2或3中發現的租使用者中執行反向號碼查閱。 在上一個步驟中找到的租使用者內，將所提供的電話號碼與使用者 SIP URI 相符。

5. 套用主幹設定。 尋找此 SBC 的租使用者管理員所設定的參數。

   Microsoft 不支援在 Microsoft SIP proxy 與成對式 SBC 之間擁有協力廠商 SIP proxy 或使用者代理伺服器，這可能會修改成對 SBC 所建立的要求 URI。

   這兩個查閱（步驟2和3）的需求，在這篇文章的稍後部分中，您需要有一個 SBC 互相連接到許多租使用者的情形（載波案例）。

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>連絡人標題與要求 URI 的詳細需求

#### <a name="contact-header"></a>連絡人標題

針對所有來電至 Microsoft SIP proxy，連絡人報頭在 URI 主機名稱中必須有成對的 SBC FQDN，如下所示：

語法： Contact： <sip： SBC 的電話或 sip address@FQDN; transport = tls> 

此名稱也必須在所提供之憑證的 [通用名稱] 或 [消費者替換名稱] 欄位中。 Microsoft 支援在憑證的 [通用名稱] 或 [Subject 替換名稱] 欄位中，使用名稱的萬用字元。   

在[RFC 2818 （section 3.1）](https://tools.ietf.org/html/rfc2818#section-3.1)中描述了萬用字元支援。 說

*[名稱可能包含要與任何\*單一網功能變數名稱稱元件或元件片段相符的萬用字元字元。例如，a.com \*會比對 foo.a.com，但不符合 bar.foo.a.com。\*[.com] 符合 foo.com，而不是 bar.com。」*

如果由 SBC 傳送 SIP 訊息中的連絡人標頭中有多個值，則只會使用連絡人標題第一個值的 FQDN 部分。

#### <a name="request-uri"></a>要求 URI 

針對所有來電，要求 URI 是用來將電話號碼與使用者進行相符。   

目前電話號碼必須包含加號（+），如下列範例所示。 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>連絡人與記錄-路由標題考慮

SIP proxy 需要針對新的對話用戶端事務（例如再見或重新邀請），以及在回復 SIP 選項時，計算下一個躍點 FQDN。 使用連絡人或記錄-路線。 

根據 RFC 3261，任何可能會產生新對話方塊的要求中，都必須有連絡人標頭。 只有在 proxy 想要在對話方塊中保留未來要求的路徑時，才需要記錄路由。 

Microsoft 建議只使用連絡人標頭的原因如下：

- 根據 RFC 3261，如果 proxy 想要在對話方塊中保留未來要求的路徑，這並不重要，就是 Microsoft SIP proxy 與成對的 SBC 之間的所有流量都不是必要的。 在 SBC 與 Microsoft SIP proxy 之間，不需要使用中間 proxy 伺服器。

- Microsoft SIP proxy 只會使用連絡人頭（而非記錄路由）來決定傳送輸出 ping 選項時的下一個躍點。 只設定一個參數（連絡人），而不是兩個（連絡人與記錄-路線），可簡化管理。

若要計算下一個躍點，SIP proxy 會使用：

- 優先順序1。 頂層記錄-路線。 如果頂層記錄-路由包含 FQDN 名稱或 IP，則會使用 FQDN 名稱或 IP 來產生輸出的內連接對話方塊連線。

- [優先順序 2]。 連絡人標頭。 如果記錄-路由不存在，SIP proxy 會查詢連絡人標頭的值，以產生輸出連線。 （這是建議的配置。）

如果使用了連絡人與記錄路線，則 SBC 管理員必須讓其值保持相同，這會造成系統管理的額外負荷。 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>在連絡人或記錄-路線中使用 FQDN 名稱

不論是記錄-路由或連絡人，都不支援 IP 位址的使用。 唯一受支援的選項是 FQDN，必須符合 SBC 憑證的通用名稱或消費者替換名稱（在憑證中支援通配值）。

- 如果您的 IP 位址是記錄-路由或連絡人，則憑證檢查失敗且通話失敗。

- 如果 FQDN 不符合所提供憑證中常見或消費者備用名稱的值，通話就會失敗。 

## <a name="inbound-call-sip-dialog-description"></a>入站通話： SIP 對話方塊描述

下表摘要列出非旁路及旁路模式之間的通話流程差異與相似性：

| 參數名稱 | 非旁路模式 | 旁路模式
| :---------------------  |:---------------------- |:----------------|
| 183和200訊息中的媒體候選人來自 | 媒體處理器 | 台 | 
| SBC 可以接收的183訊息數 | 每個會話一個 | 條 | 
| 通話可以是臨時的答案（183） | 是 | 是 |
| 通話可能不會有臨時答案（183） | 是 | 是 |

###  <a name="non-media-bypass-flow"></a>非媒體旁路流程

團隊使用者可能同時擁有多個端點。 例如，Windows 用戶端、iPhone 版團隊用戶端和團隊手機（團隊 Android 用戶端）的團隊。 每個端點可能會以下列方式通知 HTTP rest：

-   呼叫進度–由 SIP proxy 將其轉換成 SIP 訊息180。 在接收郵件180時，SBC 必須產生本機響鈴。

-   媒體答案–由 SIP proxy 轉換成在會話描述通訊協定（SDP）中有媒體候選人的訊息183。 在接收郵件183時，SBC 預期會連線至在 SDP 訊息中收到的媒體候選人。 請注意，在某些情況下，可能不會產生媒體答案，而且終點可能會以「已接受通話」訊息回答。

-   呼叫已接受–由 SIP proxy 轉換為 SIP 訊息200與 SDP。 在接收郵件200時，SBC 預期會在所提供的 SDP 候選人中傳送和接收媒體。

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>使用臨時應答的多個端點

1.  收到 SBC 中的第一個邀請之後，SIP proxy 就會傳送「SIP SIP/2.0 100 嘗試」訊息，並將有關來電的所有最終使用者端點通知給所有。 

2.  收到通知時，每個端點都會開始響鈴並傳送「呼叫進度」訊息給 SIP proxy。 因為團隊使用者可以有多個端點，所以 SIP proxy 可能會收到多個呼叫進度訊息。

3.  針對從用戶端收到的每個呼叫進度訊息，SIP proxy 會將呼叫進度訊息轉換為 SIP 訊息 "SIP SIP/2.0 180 嘗試"。 傳送這類訊息的間隔是由從呼叫控制器接收郵件的間隔所定義。 在下圖中，SIP proxy 產生 2 180 的訊息。 這些訊息來自使用者的兩個團隊端點。 用戶端每個都有唯一的標記識別項。  來自不同端點的每一封郵件都將是一個獨立的會話（[至] 欄位中的參數「標記」會不同）。 但端點可能不會產生訊息180並立即傳送訊息183，如下列圖表所示。

4.  當端點使用端點媒體候選人的 IP 位址產生媒體答案訊息時，SIP proxy 會將收到的訊息轉換為「SIP 183 會話進度」訊息，並將來自用戶端的 SDP 從媒體處理器取代。 在下圖中，分叉2的端點已接聽通話。 如果主幹是非繞過的，183 SIP 訊息只會產生一次（Ring Bot 或用戶端結束點）。 183可能會出現在現有的分叉或開始新的物件。

5.  來電接受訊息會與接受通話之端點的最終候選人一起傳送。 [通話接受] 訊息會轉換為 SIP 訊息200。 

![顯示多個端點與臨時應答鈴聲的圖表](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>多個端點鈴聲沒有臨時答案

1.  收到 SBC 中的第一個邀請之後，SIP proxy 就會傳送「SIP SIP/2.0 100 嘗試」訊息，並將有關來電的所有最終使用者端點通知給所有。 

2.  收到通知時，每個端點都會開始響鈴，並將「通話進度」訊息傳送給 SIP proxy。 因為團隊使用者可以有多個端點，所以 SIP proxy 可能會收到多個呼叫進度訊息。

3.  針對從用戶端收到的每個呼叫進度訊息，SIP proxy 會將呼叫進度訊息轉換為 SIP 訊息 "SIP SIP/2.0 180 嘗試"。  傳送訊息的間隔是由從呼叫控制器接收郵件的間隔所定義。 在下圖中，有 SIP proxy 產生的 2 180 郵件，這表示使用者登入三個小組用戶端，而每個用戶端都會傳送呼叫進度。 每封郵件都將是一個單獨的會話（[至] 欄位中的參數 "標記" 不一樣）

4.  來電接受訊息會與接受通話之端點的最終候選人一起傳送。 [通話接受] 訊息會轉換為 SIP 訊息200。 

![圖表顯示多個端點的響鈴，沒有臨時答案](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>媒體旁路流程

媒體略過案例中會使用相同的訊息（100嘗試、180、183）。 

下面的架構顯示旁路通話流程的範例。 請注意，媒體候選人可能來自不同的端點。 

![顯示多個端點與臨時應答鈴聲的圖表](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>[取代] 選項

SBC 必須支援以 replace 取代的邀請。

## <a name="size-of-sdp-considerations"></a>SDP 考慮的大小

直接路由介面可能會傳送超過1500個位元組的 SIP 訊息。  SDP 的大小主要會造成這個問題。 不過，如果在 SBC 後有 UDP 幹線，可能會在從 Microsoft SIP proxy 轉寄到不修改中繼的情況下，拒絕該訊息。 Microsoft 建議您在將訊息傳送至 UDP trunks 時，在 SBC 上去除一些值。 例如，您可以移除 ICE 候選或未使用的編解碼器。

## <a name="call-transfer"></a>來電轉接

直接路由支援兩種來電轉接方法：

- 選項1。 SIP proxy 進程會從本機參照用戶端，並做為 Referee，如 RFC 3892 的7.1 一節所述。

  使用此選項時，SIP proxy 會終止傳輸並新增邀請。 


- 選項2。 SIP proxy 會傳送參照給 SBC 並充當 Transferor，如 RFC 5589 的第6節所述。

  使用此選項時，SIP proxy 會傳送對 SBC 的參照，並預期 SBC 完全處理傳輸。

SIP proxy 會根據 SBC 所報告的功能，選取該方法。 如果 SBC 指出它支援「參考」這個方法，SIP proxy 將會使用 Option 2 進行來電轉接。

下列是一個 SBC 範例，該範例會傳送支援 method 方法的訊息：

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

如果 SBC 不指出該參照為支援的方法，直連路由將使用選項1（SIP proxy 充當 Referee）。 SBC 也必須發出支援 Notify 方法的信號：

指示不支援此參考方法的 SBC 範例：

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP proxy 進程是從本機引用用戶端，並做為 Referee

如果 SBC 指出不支援 method 方法，SIP proxy 就會充當 Referee。 

來自用戶端的參考要求將會在 SIP proxy 上終止。 （來自用戶端的參照要求在下圖中顯示為「來電轉接至 Dave」。  如需詳細資訊，請參閱[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)的7.1 節。 

![顯示多個端點與臨時應答鈴聲的圖表](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP proxy 傳送參照給 SBC 並充當 Transferor

這是來電轉接的首選方法，對於尋找媒體略過認證的裝置是強制性的。 在媒體旁路模式中不支援不含 SBC 即可處理引用的來電轉接。 

標準將在 RFC 5589 的第6節中說明。 相關 Rfc 包括：

- [會話初始通訊協定（SIP）通話控制-轉移](https://tools.ietf.org/html/rfc5589)

- [會話初始通訊協定（SIP）「取代」標頭](https://tools.ietf.org/html/rfc3891)

- [會話初始通訊協定（SIP）「參照者」機制](https://tools.ietf.org/html/rfc3892)

此選項假設 SIP proxy 充當 Transferor，並將 [參閱] 訊息傳送給 SBC。 SBC 是作為 Transferee，並處理參考以產生新的傳送優惠。 可能有兩種情況：

- 通話會轉接至外部 PSTN 參與者。 
- 通話是透過 SBC 從某個團隊使用者轉接給同一個租使用者中的另一個小組使用者。 

如果通話是透過 SBC 從某個團隊使用者轉接到另一個，則 SBC 預期會使用參考訊息中接收的資訊，為傳輸目標（團隊使用者）發出新的邀請（開始新的對話方塊）。 

若要在內部填入要求交易的 [To/Transferor] 欄位，SIP proxy 需要在 [參考資料]/[參照者] 標頭內傳達這項資訊。 

SIP proxy 會將「參考」視為 SIP URI，由主機名稱中的 SIP proxy FQDN 以及下列其中一項：

- 如果傳輸目標是電話號碼，則是 URI 的使用者名稱部分中的 E. 164 電話號碼，或者

- 分別對完整轉接目標 MRI 與租使用者識別碼進行編碼的 x-y 和 x-y 參數 

[被參照] 標頭是一個 SIP URI，其上有 transferor MRI，以及 transferor 租使用者識別碼和其他傳輸內容參數，如下表所示：

| 參數 | 值 | 描述 |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | 以 [抄送] 填充的 transferor/轉讓目標的完整 MRI |
| x-y | 租使用者識別碼 | x-y 的租使用者識別碼（由 CC 填入）選用的租使用者識別碼 |
| x-ti | Transferor 相關識別碼 | 呼叫 transferor 的相關識別碼 |
| x-tt | 傳輸目標通話 URI | 已編碼的呼叫取代 URI |

在這種情況下，[參考頁首] 的大小最多可以為400符號。 SBC 必須支援使用大小最大至400符號的資訊來處理參考訊息。

![顯示多個端點與臨時應答鈴聲的圖表](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>會話計時器

SIP proxy 支援（永遠提供）非旁路呼叫中的會話計時器，但不會在旁路呼叫中提供。 由 SBC 使用會話計時器並不是強制性的做法。

##  <a name="use-of-request-uri-parameter-userphone"></a>使用 Request-URI 參數 user = phone

SIP proxy 會分析要求-URI，如果參數使用者 = phone 存在，服務會將要求 URI 處理為電話號碼，並將該號碼與使用者進行相符。 如果參數不存在，SIP proxy 會套用啟發式來判斷要求 URI 使用者類型（電話號碼或 SIP 位址）。

Microsof [建議] 請務必套用 user = 電話參數，以簡化通話設定處理常式。

## <a name="history-info-header"></a>[歷程記錄-資訊] 標題

[歷程記錄-資訊] 標頭是用來 retargeting SIP 要求，而「提供（s）可捕獲要求歷程記錄資訊以針對網路和使用者提供多種服務的標準機制」。 如需詳細資訊，請參閱[RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt)。 針對 Microsoft Phone System，此標頭是用於 Simulring 和來電轉接案例中。  

如果傳送，則會啟用 [歷程記錄] 資訊，如下所示：

- SIP proxy 會在個別的歷程記錄資訊專案中插入一個包含相關電話號碼的參數，這些內容包含傳送至 PSTN 控制器的歷程記錄資訊標頭。  PSTN 控制器只使用具有電話號碼參數的專案，會重建新的歷程記錄資訊標頭，並透過 SIP proxy 將它傳送給 SIP 中繼提供者。

- [歷程記錄-資訊] 標題會新增至同時撥打及來電轉接的情況。

- 將不會針對來電轉接案例新增 [歷程記錄-資訊] 標題。

- 已重建歷程記錄資訊標題中的個別歷程記錄專案會將電話號碼參數與直接路由 FQDN （sip.pstnhub.microsoft.com）組合在一起，並設為 URI 的主機元件;[user = phone "的參數會新增為 SIP URI 的一部分。  與原始歷程記錄-資訊頭相關聯的任何其他參數（除了電話內容參數之外），都將會在重新構造的歷程記錄資訊標頭中傳遞。  請注意，只有當 SIP 幹線提供者是受信任的對等專案時，才能轉寄私人（由 RFC 4244 的3.3 區段中定義的機制所決定）。

- [入站記錄]-資訊將會被忽略。

以下是 SIP proxy 傳送之歷程記錄資訊標頭的格式：

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

如果呼叫重新導向數次，則每次重新導向的相關資訊都會隨附適當的原因（依時間順序排列）。


頁首範例：

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

[歷程記錄]-資訊受到強制 TLS 機制的保護。 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>指向直接路由與容錯移轉機制的 SBC 連接

請參閱[直接路由規劃](direct-routing-plan.md#failover-mechanism-for-sip-signaling)中 SIP 信號的容錯移轉機制區段。

## <a name="retry-after"></a>Retry-在

如果直接路由資料中心處於忙碌狀態，則服務可以在 SBC 中以一秒的間隔傳送一個 Retry 訊息。 當 SBC 收到503訊息，並以重試標頭回應邀請之後，SBC 必須終止該連線，然後嘗試下一個可用的 Microsoft 資料中心。 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE 重新開機：媒體旁路來電轉接到不支援媒體旁路的端點

SBC 必須支援以[RFC 5245 （章節9.1.1.1）](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)所述的 ICE 重新開機。

[直接路由] 中的 [重新開機] 是根據 RFC 的下列幾個段落來實現：

*若要重新開機 ICE，工程師必須在優惠中變更媒體資料流程的 ice 密碼和 ice ufrag。 請注意，您可以在一個優惠中使用會話階層屬性，但在後續優惠中提供相同的 ice 密碼或 ice ufrag 做為媒體層級屬性。 這不會變更密碼，只會變更其表示形式，也不會導致 ICE 重新開機。*

*代理程式會將此媒體資料流程的其他欄位設定為在這個媒體資料流程的初始提供（請參閱4.3 節）。 因此，候選人集合可能包含部分、無或所有舊版的候選人，而且可能會包含一組全新的候選項目，如4.1.1 一節所述。*

如果通話是使用媒體略過建立，且通話是傳送到商務用 Skype 用戶端，則直接傳送必須插入媒體處理器，這是因為直接路由無法與使用媒體旁路的商務用 Skype 用戶端搭配使用。 直接傳送：透過變更冰密碼和冰 ufrag，並在 reinvite 中提供新的媒體候選人，以開始 ICE 重新開機程式。 


