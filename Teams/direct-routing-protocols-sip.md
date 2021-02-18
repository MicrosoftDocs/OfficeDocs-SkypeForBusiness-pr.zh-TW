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
description: 直接路由通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fe636029c3a058dc1a8d33cc191d7654888ec5e
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278723"
---
# <a name="direct-routing---sip-protocol"></a>直接路由 - SIP 通訊協定

本文將說明直接路由如何將會話初始通訊協定 (SIP) 。 若要正確路由會話 Border Controller (SBC) 與 SIP Proxy 之間的流量，某些 SIP 參數必須具有特定值。 本文適用于負責在內部部署 SBC 與 SIP Proxy 服務之間設置連接的語音系統管理員。

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>處理傳入要求：尋找租使用者和使用者

在可以處理來電或外電通話之前，SIP Proxy 和 SBC 之間會交換 OPTIONS 訊息。 這些選項訊息允許 SIP Proxy 提供 SBC 允許的功能。 針對 200OK 回應 (選項交) ，允許 SBC 與 SIP Proxy 之間進一步溝通，以建立通話。 下列範例提供用於 SIP Proxy 之 OPTIONS 訊息中的 SIP 標頭：

| 參數名稱 | 值的範例 | 
| :---------------------  |:---------------------- |
| 要求-URI | OPTIONS sip：sip.pstnhub.microsoft.com：5061 SIP /2.0 |
| 透過頁眉 | Via： SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards頁眉 | Max-Forwards：68 |
| 從頁眉 | 從頁眉來源： <sip:sbc1.adatum.biz:5058> |
| 到頁眉 | 自： <sip:sip.pstnhub.microsoft.com:5061> |
| CSeq 標頭 | CSeq：1 INVITE | 
| 連絡人頁眉 | 聯繫： <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> SIP 標頭在使用的 SIP URI 中不包含使用者資訊。 根據 [RFC 3261，第 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1)節，URI 的使用者資訊部分為選擇性，而且當目的地主機沒有使用者概念，或當識別資源本身時，可能會缺少 URI 的使用者資訊部分。 如果 SIP URI 中出現 @ 符號，使用者欄位不能是空的。

在來電中，SIP Proxy 必須尋找該通話的目的地租使用者，並在此租使用者中尋找特定使用者。 租使用者系統管理員可能會在多個租使用者中設定非 DID 號碼，例如 +1001。 因此，尋找執行數位尋找的特定租使用者非常重要，因為在多個 Microsoft 365 或 Office 365 組織中，非 DID 號碼可能相同。  

本節說明 SIP Proxy 如何尋找租使用者和使用者，以及如何在傳入的連接上執行 SBC 驗證。

以下是來電的 SIP 邀請訊息範例：

| 參數名稱 | 值的範例 | 
| :---------------------  |:---------------------- |
| 要求-URI | 邀請sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| 透過頁眉 | Via： SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards頁眉 | Max-Forwards：68 |
| 從頁眉 | 從標頭來源：<sip：7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| 到頁眉 | To： sip:+183338006777@sbc1.adatum.biz | 
| CSeq 標頭 | CSeq：1 INVITE | 
| 連絡人頁眉 | 連絡人：<sip：68712781@sbc1.adatum.biz：5058;transport=tls> | 

在收到邀請時，SIP Proxy 會執行下列步驟：

1. 檢查憑證。 在初始連接上，直接路由服務會採用連絡人標頭中呈現的 FQDN 名稱，並比對到所呈現憑證的常見名稱或主體替代名稱。 SBC 名稱必須與下列其中一個選項相符：

   - 選項 1。 連絡人標題中顯示的完整 FQDN 名稱必須與所呈現憑證的常見名稱/Subject Alternative 名稱相符。  

   - 選項 2。 在連絡人標題中顯示 FQDN 名稱的網域部分 (例如 FQDN 名稱 adatum.biz 的 sbc1.adatum.biz) 必須與 Common Name/Subject Alternative Name (中的萬用字元值相符，例如 *.adatum.biz) 。

2. 嘗試使用連絡人標題中顯示的完整 FQDN 名稱來尋找租使用者。  

   檢查連絡人標頭中的 FQDN 名稱 (sbc1.adatum.biz) Microsoft 365 或 Office 365 組織中是否註冊為 DNS 名稱。 如果找到，使用者的查找會執行于將 SBC FQDN 註冊為功能變數名稱的租使用者中。 如果找不到，則適用步驟 3。   

3. 步驟 3 僅適用于步驟 2 失敗的情況。 

   移除主機部分 adatum.biz) 之後，從連絡人標題 (FQDN：sbc12.adatum.biz 中顯示之 FQDN 移除主機部分，並檢查此名稱是否在任何 Microsoft 365 或 Office 365 組織中註冊為 DNS 名稱。 如果找到，使用者會在此租使用者中執行查找。 如果找不到，通話會失敗。

4. 使用 Request-URI 中提供的電話號碼，在步驟 2 或 3 找到的租使用者中執行反向號碼尋找。 將呈現的電話號碼與上一個步驟所找到之租使用者中的使用者 SIP URI 相符。

5. 使用樹線設定。 尋找租使用者系統管理員為此 SBC 所設定的參數。

   Microsoft 不支援在 Microsoft SIP Proxy 與成對 SBC 之間建立協力廠商 SIP Proxy 或使用者代理伺服器，這可能會修改配對 SBC 所建立的要求 URI。

   本文稍後會說明兩個 (SBC 與許多租使用者 (電信者案例) 相互連接的案例所需的步驟 2 和 3) 。

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>連絡人標題和要求 URI 的詳細需求

#### <a name="contact-header"></a>連絡人標題

針對所有傳入的 SIP (選項，邀請) 到 Microsoft SIP Proxy，連絡人標頭必須在 URI 主機名稱中擁有配對的 SBC FQDN，如下所示：

語法：連絡人：<sip：phone 或 sip address@FQDN SBC;transport=tls> 

根據 [RFC 3261，第 11.1](https://tools.ietf.org/html/rfc3261#section-11.1)節，連絡人標題欄位可能會顯示于 OPTIONS 郵件中。 在直接路由中，需要連絡人標題。 對於上述格式的 INVITE 郵件，對於 OPTIONS 郵件，使用者資訊可以從 SIP URI 中移除，而且只有 FQDN 會以以下格式送出：

語法：連絡人：<sip：SBC 的 FQDN;transport=tls>

FQDN (名稱) 也必須在所呈現憑證的常見名稱或 (替代) 欄位。 Microsoft 支援在憑證的 (或) 名稱欄位使用名稱的萬用字元值。   

RFC [2818 第 3.1 節說明萬用字元的支援](https://tools.ietf.org/html/rfc2818#section-3.1)。 特別：

*「名稱可能包含萬用字元，該萬用字元可視為符合任何單一功能變數名稱 \* 元件或元件片段。例如，.a.com與 foo.a.com 不 \* bar.foo.a.com。 f \* .com foo.com但bar.com」。*

如果 SBC 在 SIP 訊息中呈現的連絡人標頭中，有一個值是由 SBC 所送出，則只會使用連絡人標題第一個值的 FQDN 部分。

根據直接路由的一般經驗，FQDN 必須用來填入 SIP URI，而不是 IP。 將傳入的 INVITE 或 OPTIONS 訊息傳入 SIP Proxy，其中連絡人標頭是由 IP 代表，而非 FQDN，因此會以 403 禁止拒絕此連接。

#### <a name="request-uri"></a>要求-URI 

針對所有來電，Request-URI 會用來將電話號碼與使用者相符。   

目前電話號碼必須包含加 (+) 如下列範例所示。 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>連絡人和Record-Route標題的考慮

SIP Proxy 需要針對新的對話方塊內用戶端交易計算下一個躍點 FQDN (例如 Bye 或重新邀請) ，以及回復 SIP 選項時。 使用連絡人Record-Route或連絡人。 

根據 [RFC 3261 第 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)節，任何可能導致新對話方塊的要求都需要連絡人標題。 只有Record-Route Proxy 想要留在對話方塊中未來要求的路徑時，才需要此要求。 如果 Proxy SBC 正與直接路由的 [當地媒體優化](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)一起使用，則記錄路由將需要進行配置，因為 Proxy SBC 必須留在路由中。 

若未使用 Proxy SBC，Microsoft 建議只使用連絡人標頭：

- 根據 [RFC 3261，第 20.30](https://tools.ietf.org/html/rfc3261#section-20.30)節 ，Record-Route 是當 Proxy 想要留在對話方塊中未來要求的路徑時，這不一定是必要的，因為所有流量都是在 Microsoft SIP Proxy 和配對的 SBC 之間。 

- Microsoft SIP Proxy 只會使用連絡人標頭 (記錄路由) 傳送出 ping 選項時決定下一個躍點。 在連絡人 (設定一個參數) 而非兩個 (連絡人和記錄路由) 可簡化不使用 Proxy SBC 時的管理程式。 

若要計算下一個躍點，SIP Proxy 會使用：

- 優先順序 1。 頂層記錄路由。 如果頂層Record-Route包含 FQDN 名稱，FQDN 名稱會用來建立出站對話方塊連接。

- 優先順序 2。 連絡人標題。 如果Record-Route，SIP Proxy 會尋找連絡人標頭的值，以建立外連。  (這是建議的組) 

如果同時使用連絡人Record-Route，SBC 系統管理員必須保持其值相同，這會造成系統管理負荷。 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>在連絡人或連絡人中使用 FQDN Record-Route

在連絡人或連絡人中不支援使用 IP 位址Record-Route。 唯一支援的選項是 FQDN，它必須與 SBC 憑證的共同名稱或主體替代名稱相符 (憑證中的萬用字元值) 。

- 如果 IP 位址以記錄路由或連絡人顯示，憑證檢查會失敗，且通話失敗。

- 如果 FQDN 與所呈現憑證中通用或主體替代名稱的值不相符，通話會失敗。 

## <a name="inbound-call-sip-dialog-description"></a>輸入通話：SIP 對話方塊描述

下表摘要列出非旁路和旁路模式之間的通話流程差異和相似點：

| 參數名稱 | 非旁路模式 | 旁路模式
| :---------------------  |:---------------------- |:----------------|
| 來自 183 和 200 個訊息的媒體候選人 | 媒體處理器 | 客戶 | 
| SBC 可接收的 183 個郵件數目 | 每個會話一個 | 多個 | 
| 通話可以使用 183 (的)  | 是 | 是 |
| 撥打 183 (無無)  | 是 | 是 |

###  <a name="non-media-bypass-flow"></a>非媒體旁路流程

Teams 使用者可能同時有多個端點。 例如，Windows 版 Teams 用戶端、iPhone 版 Teams 用戶端和 Teams Phone (Teams Android 用戶端) 。 每個端點可能會以以下方式發出 HTTP 休息訊號：

-   通話進度 – 由 SIP Proxy 轉換為 SIP 訊息 180。 收到郵件 180 時，SBC 必須產生本地響鈴。

-   媒體解答 – 由 SIP Proxy 轉換為訊息 183，在 SDP 的會話描述通訊協定或 SDP (媒體) 。 收到 183 訊息時，SBC 預期會連至 SDP 訊息中收到的媒體候選者。 

    > [!NOTE]
    > 在某些情況下，可能不會產生媒體答案，而結束點可能會以「已接受通話」訊息接聽。

-   已接受通話 - 由 SIP Proxy 轉換為 SIP 訊息 200 SDP。 收到訊息 200 後，SBC 預期會傳送和接收來自提供的 SDP 候選者媒體。

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>多個端點以答案響鈴

1.  SIP Proxy 在收到 SBC 的第一個邀請時，會傳送「SIP SIP/2.0 100 嘗試」訊息，並通知所有使用者端點有關來電。 

2.  通知後，每個端點都會開始響鈴，並傳送「通話進度」訊息到 SIP Proxy。 由於 Teams 使用者可以有多個結束點，因此 SIP Proxy 可能會收到多個通話進度訊息。

3.  對於從用戶端收到的每一則通話進度訊息，SIP Proxy 會將通話進度訊息轉換為 SIP 訊息「SIP SIP/2.0 180 嘗試」。 傳送這類訊息的間隔是由呼叫控制器接收郵件的間隔所定義。 在下列圖表中，SIP Proxy 產生兩則 180 則訊息。 這些訊息來自使用者的兩個 Teams 端點。 每個用戶端都有唯一的標記識別項。  每個來自不同端點的郵件都會是一個獨立的會話 (在 "To" 欄位中的參數 "tag" 會) 。 但端點可能不會立即產生訊息 180 並傳送訊息 183，如下圖所示。

4.  端點產生具有端點媒體候選者 IP 位址的 Media Answer 訊息後，SIP Proxy 會將收到的訊息轉換為「SIP 183 會話進度」訊息，而來自用戶端的 SDP 則由媒體處理器的 SDP 取代。 在下列圖表中，來自分叉 2 的端點已接電話。 如果系統未忽略中繼，則只會產生一次 183 SIP 訊息 (Ring Bot 或用戶端結束點) 。 183 可能位於現有的分叉上，或開始新的分叉。

5.  電話接受訊息會與接受通話之端點的最終候選者一起送出。 通話接受訊息會轉換為 SIP 訊息 200。 

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點以特定答案響鈴](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>多個端點在響鈴時沒有選擇答案

1.  SIP Proxy 在收到 SBC 的第一個邀請時，會傳送「SIP SIP/2.0 100 嘗試」訊息，並通知所有使用者端點有關來電。 

2.  通知後，每個端點都會開始響鈴，並傳送訊息「通話進度」到 SIP Proxy。 由於 Teams 使用者可以有多個結束點，因此 SIP Proxy 可能會收到多個通話進度訊息。

3.  對於從用戶端收到的每一則通話進度訊息，SIP Proxy 會將通話進度訊息轉換為 SIP 訊息「SIP SIP/2.0 180 嘗試」。  傳送郵件的間隔是由從呼叫控制器接收郵件的間隔所定義。 下圖顯示 SIP Proxy 產生的兩則 180 則訊息，這表示使用者登入三個 Teams 用戶端，且每個用戶端會傳送通話進度。 每封郵件都會是個別的會話， ("To" 欄位中參數 "tag" 是不同的) 

4.  電話接受訊息會與接受通話之端點的最終候選者一起送出。 通話接受訊息會轉換為 SIP 訊息 200。 

> [!div class="mx-imgBorder"]
> ![顯示多個端點響鈴且無特定答案的圖表](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>媒體旁路流程

媒體旁 (100 嘗試、180、183) 相同的訊息。 

以下架構顯示旁路通話流程的範例。 

> [!NOTE]
> 媒體候選者可能來自不同的端點。 

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點以特定答案響鈴](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>取代選項

SBC 必須支援使用取代邀請。

## <a name="size-of-sdp-considerations"></a>SDP 考慮的大小

直接路由介面可能會傳送超過 1，500 位元組的 SIP 訊息。  SDP 的大小主要會導致此原因。 不過，如果 SBC 後面有 UDP 中繼，如果郵件從 Microsoft SIP Proxy 轉往未修改的樹幹，則可能會拒絕該郵件。 Microsoft 建議在將郵件傳送至 UDP 中繼時，去除 SBC 上的 SDP 部分值。 例如，您可以移除 ICE 候選項目或未使用的編解碼器。

## <a name="call-transfer"></a>來電轉接

直接路由支援來電轉接的兩種方法：

- 選項 1。 SIP Proxy 程式從本地用戶端參照，並做為 RfC 3892 第 7.1 節所述的仲裁程式。

  使用此選項時，SIP Proxy 會終止傳輸並新增邀請。 


- 選項 2。 SIP Proxy 會傳送參照到 SBC，並做為 RFC 5589 第 6 節所述之傳輸程式。

  使用此選項時，SIP Proxy 會傳送參照到 SBC，並預期 SBC 會完全處理傳輸。

SIP Proxy 會根據 SBC 報告的功能來選取方法。 如果 SBC 表示它支援「參照」方法，SIP Proxy 會針對來電轉接使用選項 2。

以下是一個 SBC 傳送訊息的範例，指出支援參照方法：

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

如果 SBC 未指出參考為支援的方法，直接路由會使用選項 1，sip proxy (做為仲裁) 。 SBC 也必須表示它支援通知方法：

表示不支援參照方法的 SBC 範例：

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP Proxy 程式從本地用戶端參照，並做為仲裁者

如果 SBC 表示不支援參照方法，SIP Proxy 會做為仲裁者。 

來自用戶端的參考要求將在 SIP Proxy 上終止。  (下列圖表中，用戶端的來電轉接要求會顯示為「來電轉接給 Dave」。  詳細資訊請參閱 [RFC 3892 的第 7.1 節](https://www.ietf.org/rfc/rfc3892.txt)。 

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點以特定答案響鈴](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP Proxy 會傳送參照到 SBC，並做為傳輸者

這是來電轉接的偏好方法，對於尋求媒體旁路認證的裝置來說，這是強制性的。 媒體旁路模式不支援沒有 SBC 能夠處理引用的來電轉接。 

RFC 5589 的第 6 節說明標準。 相關的 RFC 為：

- [SIP 呼叫控制 (會話初始) 通訊協定 - 傳輸](https://tools.ietf.org/html/rfc5589)

- [SIP 標題 (會話) 初始通訊協定](https://tools.ietf.org/html/rfc3891)

- [會話初始通訊協定 (SIP) 「參考者」機制](https://tools.ietf.org/html/rfc3892)

此選項會假設 SIP Proxy 會做為傳輸器，並將參考訊息傳送給 SBC。 SBC 會做為受讓人，並處理參照以產生新的移轉優惠。 有兩種可能的情況：

- 通話會轉接給外部 PSTN 參與者。 
- 通話會透過 SBC 從一個 Teams 使用者轉接至同一租使用者中的另一個 Teams 使用者。 

如果通話是透過 SBC 從一個 Teams 使用者轉接到另一個，則預計 SBC 會使用 [參考訊息中的資訊 (針對移轉目標) 啟動新的對話方塊 (Teams 使用者) 。 

若要填入內部要求交易之 To/Transferor 欄位，SIP Proxy 需要在 REFER-TO/REFERRED-BY 標頭內傳達此資訊。 

SIP Proxy 會以 SIP URI 的形式形成 REFER-TO，由主機名稱中的 SIP Proxy FQDN 以及下列其中一項組成：

- URI 使用者名稱部分中的 E.164 電話號碼，以防傳輸目標為電話號碼，或

- 分別編碼完整傳輸目標 MRI 和租使用者識別碼的 x-m 和 x-t 參數 

REFERRED-BY 標頭是 SIP URI，其編碼為傳輸器 MRI，以及傳輸器租使用者識別碼和其他傳輸上下文參數，如下表所示：

| 參數 | 值 | 說明 |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | Mri | 由 CC 填出之傳輸器/傳輸目標的完整 MRI |
| x-t | 租用戶識別碼 | 由 CC 填送的 x-t 租使用者識別碼選擇性租使用者識別碼 |
| x-ti | 傳輸器相關識別碼 | 來電轉接者的相關識別碼 |
| x-tt | 轉接目標通話 URI | 編碼的呼叫取代 URI |

在這種情況下，參考頁眉的大小可高達 400 個符號。 SBC 必須支援處理大小最多 400 個符號的參考郵件。

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點以特定答案響鈴](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>會話計時器

SIP Proxy 支援 (非) 通話時提供會話計時器，但不在旁路通話時提供。 SBC 不一定使用會話計時器。

##  <a name="use-of-request-uri-parameter-userphone"></a>Request-URI 參數 user=phone 的使用

SIP Proxy 會分析 Request-URI，如果參數 user=phone 存在，服務會以電話號碼處理 Request-URI，將號碼與使用者配對。 如果參數不存在，SIP Proxy 會使用啟發式來判斷 Request-URI 使用者類型 (電話號碼或 SIP 位址) 。

Microsof 建議一直使用 user=phone 參數，以簡化通話設定程式。

## <a name="history-info-header"></a>History-Info頁眉

History-Info標題用於重新定目標 SIP 要求，並「提供 (s) 一個標準機制來記錄要求歷程記錄資訊，為網路和使用者啟用各種服務」。 詳細資訊請參閱 [RFC 4244 – 第 1.1 節](http://www.ietf.org/rfc/rfc4244.txt)。 針對 Microsoft Phone System，此標頭用於 Simulring 和呼叫轉包案例。  

如果傳送，History-Info啟用方式如下：

- SIP Proxy 將在個別專案插入包含相關聯電話號碼的參數History-Info組成要History-Info PSTN 控制器的標頭。  PSTN 控制器只會使用具有電話號碼參數History-Info，並透過 SIP Proxy 將標頭傳遞到 SIP 中繼提供者。

- History-Info同時撥打和呼叫呼叫轉譯案例時，會新增標題。

- History-Info轉接案例不會新增標題。

- 重新建立之 History-Info 標頭中的個別歷程記錄專案，會提供電話號碼參數與直接路由 FQDN (sip.pstnhub.microsoft.com) 設為 URI 的主機部分;'user=phone' 的參數會新增為 SIP URI 的一部分。  與原始頁眉關聯的任何其他History-Info除了電話內容參數以外，都會在重新建構的頁History-Info中傳遞。  

  > [!NOTE]
  > 由 RFC 4244 (3.3 中定義之機制所定義的私人專案將會轉) 因為 SIP 中繼提供者是信任的對等。

- 內History-Info會被忽略。

以下是 SIP Proxy 所送出之歷程記錄資訊標題的格式：

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

如果呼叫重新導向數次，每個重新導向的資訊會以時間順序包含適當的原因。


頁眉範例：

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

此History-Info受強制 TLS 機制保護。 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>直接路由與容錯移轉機制的 SBC 連接

請參閱直接路由規劃中 SIP 訊號的容錯移轉 [機制一節](direct-routing-plan.md#failover-mechanism-for-sip-signaling)。

## <a name="retry-after"></a>Retry-After

如果直接路由資料中心忙碌中，服務可以傳送一Retry-After一秒間隔的郵件給 SBC。 當 SBC 收到包含 Retry-After 標頭的 503 郵件以回應 INVITE 時，SBC 必須終止該連接，並嘗試下一個可用的 Microsoft 資料中心。 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE 重新開機：傳輸至不支援媒體旁路的端點的媒體旁路通話

SBC 必須支援 [RFC 5245 第 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)節中所述的 ICE 重新開機。

直接路由中的重新開機會根據 RFC 的下列段落來執行：

*若要重新開機 ICE，仲介人員必須同時變更優惠中的媒體串流之 ice-pwd 和 ice-ufrag。 請注意，在一個優惠中使用工作階段層級屬性是允許的，但提供與後續優惠中媒體層級屬性相同的 ice-pwd 或 ice-ufrag。 這不是密碼的變更，只是其表示方式的變更，也不會造成 ICE 重新開機。*

*代理程式會針對此媒體串流設定 SDP 中其餘的欄位，就像初次提供此媒體串流時一樣 (請參閱第 4.3 節) 。 因此，一組候選人可能包括該資料流程的部分、無或所有先前的候選人，而且可能會包含一組完全新的候選人，如第 4.1.1 節所述。*

如果通話最初是使用媒體旁路建立，且通話轉接至商務用 Skype 用戶端，則直接路由需要插入媒體處理器，這是因為直接路由無法與商務用 Skype 用戶端一起使用媒體旁路。 直接路由會變更 ice-pwd 和 ice-ufrag，並再次提供新的媒體候選項目，以啟動 ICE 重新開機程式。 


