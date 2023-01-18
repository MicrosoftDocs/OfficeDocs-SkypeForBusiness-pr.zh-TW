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
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cf7bf4040a75e59518312edd32c9c4e77f11728
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812710"
---
# <a name="direct-routing---sip-protocol"></a>直接路由 - SIP 通訊協定

本文說明直接路由如何實作會話初始通訊協定 (SIP) 。 若要在會話框線控制器 (SBC) 和 SIP Proxy 之間正確路由流量，某些 SIP 參數必須具有特定值。 本文適用于負責設定內部部署 SBC 與 SIP Proxy 服務之間連線的語音系統管理員。

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>處理傳入要求：尋找租使用者和使用者

在處理來電或撥出電話之前，SIP Proxy 和 SBC 之間會交換 OPTIONS 訊息。 這些選項訊息可讓 SIP Proxy 為 SBC 提供允許的功能。 請務必交涉 OPTIONS，以成功 (200OK 回應) ，以便在 SBC 和 SIP Proxy 之間進一步溝通，以建立通話。 下列範例提供選項訊息至 SIP Proxy 的 SIP 標頭：

| 參數名稱 | 值的範例 | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONS sip：sip.pstnhub.microsoft.com：5061 SIP /2.0 |
| 透過頁首 | Via：SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards頁首 | Max-Forwards：68 |
| 從頁首 | 從頁首： <sip:sbc1.adatum.biz:5058> |
| 移至頁首 | 自： <sip:sip.pstnhub.microsoft.com:5061> |
| CSeq 標頭 | CSeq：1 邀請 | 
| 連絡頁首 | 聯繫： <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> SIP 標頭在所使用的 SIP URI 中不包含 userinfo。 根據 [RFC 3261，區段 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1)，URI 的 userinfo 部分是選用的，當目的地主機沒有使用者概念或主機本身為識別資源時，可能會遺失。 如果 @ 符號出現在 SIP URI 中，則使用者欄位不得為空白。
> 請注意，SIPS URI 不應與直接路由搭配使用，因為它不受支援。
> 檢查會話框線控制器設定，並確認您未在 SIP 要求中使用「取代」標頭。 直接路由會拒絕已定義取代標頭的 SIP 要求。

在來電中，SIP Proxy 必須尋找來電目的地的租使用者，並在此租使用者中尋找特定使用者。 租使用者系統管理員可能會在多個租使用者中設定非 DID 號碼，例如 +1001。 因此，請務必尋找要執行數位查閱的特定租使用者，因為非 DID 的數位在多個 Microsoft 365 或Office 365組織中可能相同。  

本節說明 SIP Proxy 如何尋找租使用者和使用者，並在傳入連線上執行 SBC 驗證。

以下是來電上的 SIP 邀請訊息範例：

| 參數名稱 | 值的範例 | 
| :---------------------  |:---------------------- |
| Request-URI | 邀請 sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| 透過頁首 | Via：SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards頁首 | Max-Forwards：68 |
| 從頁首 | 從頁首：<sip：+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| 移至頁首 | To：sip:+183338006777@sbc1.adatum.biz | 
| CSeq 標頭 | CSeq：1 邀請 | 
| 連絡頁首 | 聯繫： <sip:+17168712781@sbc1.adatum.biz:5058;transport=tls> | 

收到邀請時，SIP Proxy 會執行下列步驟：

1. 檢查憑證。 在初始連線上，直接路由服務會採用連絡人標頭中顯示的 FQDN 名稱，並將其與所呈現憑證的通用名稱或主旨替代名稱相符。 SBC 名稱必須符合下列其中一個選項：

   - 選項 1. 在連絡人標頭中顯示的完整 FQDN 名稱必須符合所呈現憑證的通用名稱/主旨替代名稱。  

   - 選項 2. 在連絡人標頭 (顯示之 FQDN 名稱的網域部分，例如 FQDN 名稱 sbc1.adatum.biz) adatum.biz 必須符合常見名稱/主旨替代名稱 (例如 *.adatum.biz) 中的萬用字元值。

2. 嘗試使用連絡人標頭中顯示的完整 FQDN 名稱尋找租使用者。  

   檢查連絡人標題 (sbc1.adatum.biz) 的 FQDN 名稱是否在任何 Microsoft 365 或Office 365組織中註冊為 DNS 名稱。 如果找到，使用者的查閱會在已註冊為功能變數名稱的 SBC FQDN 租使用者中執行。 如果找不到，則適用步驟 3。   

3. 步驟 3 僅適用于步驟 2 失敗時。 

   移除 FQDN 中的主機部分，此部分會在 [連絡人] 標題 (FQDN 中顯示：移除主機部分之後 sbc12.adatum.biz：adatum.biz) ，並檢查此名稱是否在任何 Microsoft 365 或Office 365組織中註冊為 DNS 名稱。 如果找到，使用者查閱會在此租使用者中執行。 如果找不到，通話會失敗。

4. 使用 Request-URI 中顯示的電話號碼，在步驟 2 或 3 找到的租使用者內執行反向號碼查閱。 將呈現的電話號碼與上一個步驟找到之租使用者內的使用者 SIP URI 相符。

5. 套用主幹設定。 尋找此 SBC 租使用者系統管理員所設定的參數。

   Microsoft 不支援在 Microsoft SIP Proxy 與配對 SBC 之間擁有協力廠商 SIP Proxy 或使用者代理伺服器，這可能會修改由配對 SBC 建立的要求 URI。

   這兩個查閱的需求 (本文稍後所說明的一個 SBC 與許多租使用者相互連線至許多租使用者 (電信業者案例時，所需步驟 2 和 3) ) 步驟 2 和 3。

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>連絡人標頭和要求 URI 的詳細需求

#### <a name="contact-header"></a>連絡頁首

針對 [選項] (所有內送 SIP 訊息，邀請) 至 Microsoft SIP Proxy，連絡人標頭必須在 URI 主機名稱中擁有配對的 SBC FQDN，如下所示：

語法：連絡人：<SBC 的 sip：phone 或 sip address@FQDN;transport=tls> 

根據 [RFC 3261 區段 11.1](https://tools.ietf.org/html/rfc3261#section-11.1)，[選項] 訊息中可能會出現 [連絡人標題] 欄位。 在 [直接路由] 中，必須有連絡人標頭。 對於上述格式的 INVITE 郵件，您可以從 SIP URI 移除使用資訊給選項訊息，而且只能從以下格式傳送 FQDN：

語法：連絡人：<SBC 的 sip：FQDN;transport=tls>

此名稱 (FQDN) 也必須位於通用名稱或主旨替代名稱欄位 (所呈現憑證的) 。 Microsoft 支援在憑證的 [通用名稱] 或 [主旨替代名稱] 欄位中使用名稱 () 的萬用字元值。   

[RFC 2818，第 3.1 節](https://tools.ietf.org/html/rfc2818#section-3.1)說明萬用字元的支援。 特別：

*「名稱可能包含萬用字元 \* ，其視為符合任何單一功能變數名稱元件或元件片段。例如， \* .a.com 比對 foo.a.com 但 bar.foo.a.com 不相符。f.com \* 比對 foo.com 但不 bar.com」。*

如果 SBC 傳送 SIP 郵件中的連絡人標頭中超過一個值，則只會使用連絡人標頭第一個值的 FQDN 部分。

作為直接路由的拇指規則，使用 FQDN 來填入 SIP URI 而非 IP 是很重要的。 內送 INVITE 或 OPTIONS 訊息至 SIP Proxy 與連絡人標頭，其中 hostname 以 IP 表示，而非 FQDN，連線將拒絕 403 禁止。

#### <a name="request-uri"></a>Request-URI 

針對所有來電，會使用 Request-URI 來比對使用者的電話號碼。   

目前電話號碼必須包含加號 (+) ，如下列範例所示。 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>從頁首

針對所有來電，[寄件者頁首] 會用來比對來電者的電話號碼與來電者的封鎖電話號碼清單。

電話號碼必須包含 +，如下列範例所示。

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>連絡和Record-Route標頭考慮

SIP Proxy 需要針對新的對話方塊用戶端交易計算下一個躍點 FQDN (例如 Bye 或重新邀請) ，以及回復 SIP 選項時。 使用連絡人或Record-Route。 

根據 [RFC 3261，區段 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)，任何可能導致新對話方塊的要求中都必須有連絡人標頭。 只有 Proxy 想要維持在對話方塊中未來要求的路徑時，才需要Record-Route。 如果 Proxy SBC 正與 [「本機媒體優化」搭配直接路由](./direct-routing-media-optimization.md)使用，記錄路由就必須設定為 Proxy SBC 需要留在路由中。 

如果不使用 Proxy SBC，Microsoft 建議您只使用連絡人標頭：

- 根據 [RFC 3261，區段 20.30](https://tools.ietf.org/html/rfc3261#section-20.30)，如果 Proxy 想要維持在對話方塊中未來要求的路徑，則會使用Record-Route。如果沒有設定 Proxy SBC，因為 Microsoft SIP Proxy 和配對 SBC 之間的流量都沒關係。 

- Microsoft SIP Proxy 只會使用連絡人標頭 (而非 Record-Route) 來判斷傳送輸出 ping 選項時的下一個躍點。 只要設定一個參數 (連絡人) ，而不是兩個 (連絡人和 Record-Route) 簡化不使用 Proxy SBC 的系統管理。 

若要計算下一個躍點，SIP Proxy 會使用：

- 優先順序 1. 頂層記錄路由。 如果頂層Record-Route包含 FQDN 名稱，則會使用 FQDN 名稱來建立輸出對話方塊連線。

- 優先順序 2. 連絡頁首。 如果Record-Route不存在，SIP Proxy 會查閱連絡人標頭的值，以建立輸出連線。  (這是建議的設定。) 

如果同時使用 [連絡人] 和 [Record-Route]，則 SBC 系統管理員必須保持其值的相同，因而導致系統管理負荷過重。 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>在連絡人或Record-Route中使用 FQDN 名稱

Record-Route或連絡人不支援使用 IP 位址。 唯一支援的選項是 FQDN，必須符合 SBC 憑證的通用名稱或主旨替代名稱 (憑證中的萬用字元值) 支援。

- 如果在 [記錄路由] 或 [連絡人] 中顯示 IP 位址，憑證檢查會失敗且通話失敗。

- 如果 FQDN 不符合所呈現憑證中 [通用名稱] 或 [主旨替代名稱] 的值，通話便會失敗。 

## <a name="inbound-call-sip-dialog-description"></a>撥入通話：SIP 對話方塊描述

下表摘要列出非略過和略過模式之間的通話流程差異和相似處：

| 參數名稱 | 非略過模式 | 略過模式
| :---------------------  |:---------------------- |:----------------|
| 來自 183 和 200 封郵件的媒體候選字 | 媒體處理器 | 用戶端 | 
| SBC 可接收的 183 封郵件數目 | 每個會話一個 | 多個 | 
| 通話可以與接聽的接聽 (183)  | 是 | 是 |
| 183 (183) 通話不含任何答案 | 是 | 是 |

###  <a name="non-media-bypass-flow"></a>非媒體略過流程

Teams 使用者可能同時有多個端點。 例如，Windows 用戶端 Teams、iPhone 版 Teams 用戶端和 Teams Phone (Teams Android 用戶端) 。 每個端點可能會發出 HTTP 休憩訊號，如下所示：

-   通話進度 – 由 SIP Proxy 轉換為 SIP 訊息 180。 在收到郵件 180 時，SBC 必須產生本機響鈴。

-   媒體答案 – 在 SDP) 的會話描述通訊協定 (中，由 SIP Proxy 轉換為訊息 183 與媒體候選字。 在收到訊息 183 時，SBC 預期會連線到 SDP 訊息中收到的媒體候選字。 

    > [!NOTE]
    > 在某些情況下，可能不會產生媒體接聽，端點可能會以「通話已接受」訊息來接聽。

-   已接受通話 ： 使用 SIP 將 SIP Proxy 轉換為 SIP 訊息 200。 在收到訊息 200 時，SBC 預期會傳送和接收所提供 SDP 候選字的媒體。

    > [!NOTE]
    > 直接路由不支援沒有 SDP) 的延遲優惠邀請 (邀請。

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>多個端點隨著附著答案響鈴

1.  收到 SBC 的第一次邀請時，SIP Proxy 會傳送「SIP SIP/2.0 100 試用」訊息，並通知所有使用者端點與來電有關。 

2.  收到通知時，每個端點都會開始響鈴，並傳送「通話進度」訊息到 SIP Proxy。 由於 Teams 使用者可以有多個端點，SIP Proxy 可能會收到多個通話進度訊息。

3.  針對從用戶端收到的每一封通話進度訊息，SIP Proxy 會將通話進度訊息轉換為 SIP 訊息「SIP SIP/2.0 180 響鈴」。 傳送這類訊息的間隔是根據從呼叫控制器接收郵件的時間間隔所定義。 在下列圖表中，有兩封由 SIP Proxy 產生的 180 封郵件。 這些訊息來自使用者的兩個 Teams 端點。 每個用戶端都有唯一的標籤識別碼。  每個來自不同端點的郵件都會是個別的會話， (「收件者」欄位中的參數「標籤」會不同) 。 但端點可能不會產生訊息 180，並立即傳送郵件 183，如下圖所示。

4.  當端點產生含有端點媒體候選字 IP 位址的 Media Answer 訊息後，SIP Proxy 會將收到的郵件轉換為「SIP 183 會話進度」訊息，而來自用戶端的 SDP 由媒體處理器的 SDP 取代。 在下列圖表中，Fork 2 的端點已接聽來電。 如果未略過主幹，183 SIP 訊息只會在通道機器人或用戶端端點)  (產生一次。 183 可能在現有的筆跡上，或是開始新的一個。

5.  通話接受訊息會傳送至接受通話之端點的最後候選字。 通話接受訊息會轉換為 SIP 訊息 200。 

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點在鈴聲中帶有解答。](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>多個端點響鈴而不傳入解答

1.  收到 SBC 的第一次邀請時，SIP Proxy 會傳送「SIP SIP/2.0 100 試用」訊息，並通知所有使用者端點與來電有關。 

2.  收到通知時，每個端點都會開始響鈴，並傳送「通話進度」訊息至 SIP Proxy。 由於 Teams 使用者可以有多個端點，SIP Proxy 可能會收到多個通話進度訊息。

3.  針對從用戶端收到的每一封通話進度訊息，SIP Proxy 會將通話進度訊息轉換為 SIP 訊息「SIP SIP/2.0 180 試用」。  傳送郵件的間隔是根據從呼叫控制器接收郵件的時間間隔所定義。 在下圖中，SIP Proxy 產生兩則 180 封郵件，表示使用者登入三個 Teams 用戶端，而每個用戶端都會傳送通話進度。 每封郵件都會是個別的會話， ([收件者] 欄位中的參數 「tag」 是不同的) 

4.  通話接受訊息會傳送至接受通話之端點的最後候選字。 通話接受訊息會轉換為 SIP 訊息 200。 

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點響鈴而不包含解答。](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>媒體略過流程

相同的訊息 (100 試用、180、183) 用於媒體略過案例。 

下列架構顯示略過通話流程的範例。 

> [!NOTE]
> 媒體候選字可以來自不同的端點。 

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點在鈴聲中帶有解答。](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>[取代] 選項

SBC 必須支援 [以取代邀請]。

## <a name="size-of-sdp-considerations"></a>SDP 考慮的大小

直接路由介面可能會傳送超過 1，500 位元組的 SIP 訊息。  SDP 的大小主要會導致此問題。 不過，如果 SBC 後方有 UDP 主幹，如果郵件從 Microsoft SIP Proxy 轉寄到未修改的主幹，可能會拒絕該郵件。 Microsoft 建議您在將郵件傳送到 UDP 主幹時，在 SBC 上的 SDP 中去除某些值。 例如，可以移除 ICE 候選字或未使用的編解碼器。

## <a name="call-transfer"></a>來電轉接

直接路由支援兩種來電轉接方法：

- 選項 1. SIP Proxy 程式：從本機用戶端進行參考，並依照 RFC 3892 第 7.1 節所述做為[裁判員]。

  使用此選項時，SIP Proxy 會終止移轉，並新增新的邀請。 


- 選項 2. SIP Proxy 會傳送參考 SBC，並做為轉接器，如 RFC 5589 第 6 節所述。

  使用此選項時，SIP Proxy 會傳送 [參考至 SBC]，並預期 SBC 會完整處理傳輸。

SIP Proxy 會根據 SBC 回報的功能來選取該方法。 如果 SBC 表示它支援「推薦」方法，則 SIP Proxy 會使用選項 2 進行來電轉接。

下列是 SBC 傳送郵件的範例，該訊息支援 [參考] 方法：

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

如果 SBC 不指出「參考為支援的方法」，直接路由會使用選項 1 (SIP Proxy 做為「裁判員」) 。 SBC 也必須表示它支援[通知] 方法：

表示不支援參照方法的 SBC 範例：

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP Proxy 程式 從本機用戶端推薦並做為裁判員

如果 SBC 指出不支援 [參考] 方法，SIP Proxy 會做為 [裁判員]。 

來自用戶端的 「參考」要求將會在 SIP Proxy 上終止。  (在下列圖表中，用戶端的 [推薦] 要求顯示為「來電轉接給 Dave」。  如需詳細資訊，請參閱 [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)第 7.1 節。 

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點在鈴聲中帶有解答。](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP Proxy 會傳送 [參照至 SBC]，並做為移轉者

這是來電轉接的慣用方法，對於尋求媒體略過認證的裝置而言是必要的。 媒體旁路模式不支援沒有 SBC 處理 [推薦] 的來電轉接。 

此標準會在 RFC 5589 的第 6 節中說明。 相關的 RFC 為：

- [SIP) 撥號控制 (會話初始通訊協定 - 轉接](https://tools.ietf.org/html/rfc5589)

- [SIP (會話初始通訊協定) 「取代」標頭](https://tools.ietf.org/html/rfc3891)

- [SIP) 「參照者」機制 (會話初始通訊協定](https://tools.ietf.org/html/rfc3892)

此選項假設 SIP Proxy 做為轉接器，並傳送 [參考] 訊息至 SBC。 SBC 會做為轉接者，並處理 [參考] 以產生新的傳輸優惠。 有兩種可能的情況：

- 通話會轉接給外部 PSTN 參與者。 
- 通話會透過 SBC 從一個 Teams 使用者轉移到同一租使用者中的另一個 Teams 使用者。 

如果通話是透過 SBC 從一個 Teams 使用者轉接至另一個使用者，則預期 SBC 會發出新的邀請 (啟動轉接目標的新對話方塊) ， (Teams 使用者) 使用 [參考] 訊息中收到的資訊。 

若要在內部填入要求交易的 To/Transferor 欄位，SIP Proxy 必須在 REFER-TO/REFER-BY 標頭內傳達此資訊。 

SIP Proxy 會將 REFER-TO 形成為 SIP URI，包含主機名稱中的 SIP Proxy FQDN，以及下列其中一項：

- URI 使用者名稱部分中的 E.164 電話號碼，以防移轉目標為電話號碼或

- x-m 和 x-t 參數分別編碼完整傳輸目標 MRI 和租使用者識別碼 

REFERRED-BY 標頭是 SIP URI，其中包含編碼的移轉器 MRI，以及移轉器租使用者識別碼和其他傳輸上下文參數，如下表所示：

| 參數 | 值 | 描述 |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | Mri | CC 填入之傳輸器/傳輸目標的完整 MRI |
| x-t | 租用戶識別碼 | x-t 租使用者識別碼 選擇性租使用者識別碼由 CC 填入 |
| x-ti | 傳輸器相互關聯識別碼 | 來電轉接器的相互關聯識別碼 |
| x-tt | 轉接目標通話 URI | 編碼呼叫取代用 URI |

在此情況下，[推薦頁首] 的大小最多可以是 400 個符號。 SBC 必須支援處理最多 400 個符號大小的 [參考] 郵件。

> [!div class="mx-imgBorder"]
> ![圖表顯示多個端點在鈴聲中帶有解答。](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>會話計時器

SIP Proxy 支援 (一律在非略過的通話上提供) 會話計時器，但不會在略過的通話時提供。 SBC 並不強制使用會話計時器。

##  <a name="use-of-request-uri-parameter-userphone"></a>使用 Request-URI 參數 user=phone

SIP Proxy 會分析 Request-URI，如果出現參數 user=phone，服務會以電話號碼處理 Request-URI，與使用者的號碼相符。 如果參數不存在，SIP Proxy 會套用語言來判斷電話號碼或 SIP 位址)  (Request-URI 使用者類型。

Microsoft 建議一律套用 user=phone 參數，以簡化通話設定程式。

## <a name="history-info-header"></a>History-Info頁首

History-Info標頭用於重新設定 SIP 要求，以及「提供 () 擷取要求歷程記錄資訊的標準機制，以便為網路和使用者啟用各種服務」。 如需詳細資訊，請參閱 [RFC 4244 – 節 1.1](http://www.ietf.org/rfc/rfc4244.txt)。 對於 Microsoft Phone System，此標頭用於 Simulring 和來電轉接案例。  

如果傳送，History-Info會以下列方式啟用：

- SIP Proxy 會在個別History-Info專案中插入包含相關聯電話號碼的參數，該專案包含傳送到 PSTN 控制器的History-Info標頭。  PSTN 控制器只會使用具有電話號碼參數的專案，重建新的History-Info標頭，並透過 SIP Proxy 將它傳遞給 SIP 主機提供者。

- 系統會針對同時撥打和來電轉接案例新增History-Info標頭。

- History-Info來電轉接案例將不會新增標頭。

- 重新建立History-Info頁首中的個別歷程記錄專案會將提供的電話號碼參數與直接路由 FQDN (sip.pstnhub.microsoft.com) 設為 URI 的主機部分;系統會將 'user=phone' 的參數新增為 SIP URI 的一部分。  除了手機上下文參數以外，與原始History-Info頁首相關的任何其他參數都會在重新建構的History-Info頁首中傳遞。  

  > [!NOTE]
  > 由 RFC 4244) 第 3.3 節定義的私密 (專案會轉寄，因為 SIP 主幹提供者是受信任的對等。

- 啟用 ForwardCallHistory 參數時，會保留輸入History-Info。 保留History-Info可用於防迴圈防護。

以下是 SIP Proxy 所傳送之歷程記錄資訊標頭的格式：

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

如果重新導向通話數次，每個重新導向的相關資訊會依時間順序包含在適當的原因中。


頁首範例：

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

History-Info受到強制性 TLS 機制保護。 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>SBC 與直接路由和容錯移轉機制的連線

請參閱規劃 [直接路由中的](direct-routing-plan.md#failover-mechanism-for-sip-signaling)SIP 訊號容錯移轉機制一節。

## <a name="retry-after"></a>Retry-After

如果直接路由資料中心忙碌中，服務可以將間隔一秒的Retry-After郵件傳送到 SBC。 當 SBC 收到含有Retry-After標頭的 503 郵件以回應 INVITE 時，SBC 必須終止該連線，並嘗試下一個可用的 Microsoft 資料中心。

## <a name="handling-retries-603-response"></a>處理 603 回應 (重述) 
如果使用者在拒絕來電後觀察到多個未接來電，表示 SBC 或 PSTN 主幹提供者的重試機制設定錯誤。 SBC 必須重新設定，才能停止 603 回應的重試。

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE 重新開機：媒體略過來電轉接至不支援媒體略過的端點

SBC 必須支援 [如 RFC 5245 章節 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)中所述的 ICE 重新開機。

直接路由中的重新開機會根據 RFC 的下列段落實作：

*若要重新開機 ICE，專員必須變更優惠中媒體串流的 ice-pwd 和 ice-ufrag。 請注意，在一個優惠中使用工作階段層級屬性是允許的，但若要在後續優惠中提供與媒體層級屬性相同的 ice-pwd 或 ice-ufrag。 這不是密碼變更，只是變更其表示方式，也不會造成 ICE 重新開機。*

*代理程式會針對此媒體串流設定 SDP 中其餘的欄位，就像此媒體串流的初始優惠一樣， (請參閱第 4.3 節) 。 因此，該候選字組可能包含該串流和 MAY 的部分、無或所有先前的候選字，並包含一組全新的候選字，如第 4.1.1 節所述。*

如果通話最初是在媒體略過的情況下建立，且來電轉接至商務用 Skype用戶端，則直接路由必須插入媒體處理器，這是因為直接路由無法與媒體略過商務用 Skype用戶端搭配使用。 直接路由會變更冰塊和 ice-ufrag 並提供重新邀請中的新媒體候選字，以啟動 ICE 重新開機程式。
