---
title: 新式天運算 Lync Server 2013： 常見安全性威脅
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb78e03f67f7ceffbbfc401403f4025d3004fb00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>新式天運算的常見安全性威脅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-09-10_

由於 Lync Server 2013 是企業層級通訊系統，您應該要知道其基礎結構和通訊可能會影響的常見安全性攻擊。

<div>

## <a name="compromised-key-attack"></a>洩漏金鑰攻擊

金鑰是用來加密、解密或驗證秘密資訊的秘密代碼或數字。 有兩個機密機碼中使用中公開金鑰基礎結構 (PKI) 也必須納入考量:。

  - 每個憑證持有者具有私密金鑰

  - 工作階段識別碼，是使用後成功的識別資料及工作階段 exchange 通訊的協力廠商

當攻擊者判斷出私密金鑰或工作階段金鑰時，即發生洩漏金鑰攻擊。 當攻擊者成功判斷出金鑰後，就可以在傳送者不知情的情況下，使用金鑰將加密的資料解密。

Lync Server 2013 的 Windows Server 作業系統中使用 PKI 功能，來保護用於加密的傳輸層安全性 (TLS) 連線的索引鍵資料。 所用的媒體加密金鑰會透過 TLS 連線交換。

</div>

<div>

## <a name="network-denial-of-service-attack"></a>網路拒絕服務攻擊

一般網路使用與函式的有效使用者，可防止攻擊者時，就會發生*拒絕服務攻擊*。 這是當攻擊者塞爆使癱瘓使用服務的合法要求服務合法的使用者。 藉由使用拒絕服務攻擊，攻擊者可以執行下列動作：

  - 傳送無效的資料給受攻擊網路中執行的應用程式和服務，干擾其正常功能。

  - 傳送大量流量使系統超載，直到系統停止回應或是對合法要求回應變慢。

  - 隱藏攻擊證據。

  - 阻止使用者存取網路資源。

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>竊聽 （竊聽，側錄）

當攻擊者後所提升的網路中的資料路徑的存取權，且能夠監視及讀取流量時，就會發生*竊聽*。 這也稱為*探查*或*側錄*。 如果流量是純文字，則攻擊者取得路徑存取權之後就可以讀取流量。 例如，控制資料路徑上的路由器，就是進行這類攻擊的方式。

Microsoft Lync Server 2013 內的流量的設定與預設的建議作法是使用相互 TLS (MTLS) 之間信任的伺服器與 TLS 從用戶端到伺服器。 此措施會使攻擊，很難或無法達到指定的交談會發生的期間內。 TLS 會驗證所有相關人員並加密所有流量。 雖然這無法阻止竊聽，卻能讓攻擊者無法讀取流量，除非加密被破解。

周遊使用轉送 NAT （開啟） 通訊協定並未受命進行加密的流量，它傳送資訊會受到訊息完整性。 雖然開啟竊聽，資訊它傳送直接透過只要查看封包的來源和目的地位址，則可以擷取 （也就是 IP 位址和連接埠）。 A / V Edge service 可確保資料是否有效，藉由使用衍生自幾項目，包括開啟密碼，永遠不會以純文字傳送的機碼檢查郵件訊息完整性。 如果使用安全即時通訊協定 (SRTP)，則也加密的媒體流量。

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>身分詐騙 （IP 位址詐騙）

攻擊者決定並沒有正在授權使用 IP 位址為網路、 電腦或網路元件，若要這麼做時，就會發生*詐騙*。 成功的攻擊允許操作時是否攻擊者通常的 IP 位址所識別的實體攻擊者。 在 Microsoft Lync Server 2013 的內容，這種情況而重新列入播放只有當系統管理員已完成下列兩項：

  - 設定支援僅傳輸控制通訊協定 (TCP) （這不建議使用，因為 TCP 通訊未經過加密） 的連線。

  - 將這些連線的 IP 位址標記為信任的主機。

這是小於問題進行傳輸層安全性 (TLS) 連線，因為 TLS 驗證所有方並加密的所有流量。 使用 TLS，可防止攻擊者執行詐騙在某特定連線 （例如，相互 TLS 連線） 上的 IP 位址。 但攻擊者可能仍會詐騙的 Lync Server 2013 使用的 DNS 伺服器位址。 不過，因為憑證執行 Lync 中的驗證，攻擊者將不會包含需要下列其中一個通訊中的各方負責詐騙的有效憑證。

</div>

<div>

## <a name="man-in-the-middle-attack"></a>攔截攻擊

攻擊變更路徑透過攻擊者電腦的兩個通訊使用者不知情的情況下的兩個使用者之間的通訊時發生攔截攻擊。 攻擊者可以監視及傳送入預定的收件者之前，請先閱讀流量。 通訊中的每位使用者不知情的情況下傳送的流量，並從攻擊者，所有時考慮進行通訊，但只會與預期的使用者接收流量。 如果攻擊者可以修改將他/她伺服器新增為信任的伺服器，或修改網域名稱系統 (DNS) 來取得用戶端能夠連線至伺服器的路上攻擊者透過 Active Directory 網域服務，這可能會發生。 攔截攻擊可能也會發生兩個用戶端之間的媒體流量。 不過，在 [Microsoft Lync Server 2013 點對點音訊、 視訊及應用程式共用，資料流是使用 SRTP，使用交涉會使用透過 TLS 的工作階段初始通訊協定 (SIP) 對等之間的密碼編譯金鑰加密。 例如 Group Chat 伺服器進行強化安全性的網頁流量使用 HTTPS。

</div>

<div>

## <a name="rtp-replay-attack"></a>RTP 重播攻擊

*重新執行攻擊*發生於兩方有效的媒體傳輸會攔截和重新傳輸的惡意的用途。 與安全信號通訊協定使用 SRTP 會重新執行攻擊傳輸保護藉由啟用維護已收到 RTP 封包的索引，並比較與索引中已列出每個新的封包收件者。

</div>

<div>

## <a name="spim"></a>垃圾訊息

*垃圾訊息*是來路不明的商業立即訊息或目前狀態訂閱要求。 而不是依本身，而危害的網路，請它很煩人中最少資源可用性和實際執行環境，可以減少，可能導致網路的危害。 例如，這是使用者 spimming 彼此藉由傳送要求。 使用者可以封鎖彼此避免發生這樣，但使用同盟時，如果在建立協調的垃圾攻擊時，這可能很難克服除非您停用同盟協力廠商。

</div>

<div>

## <a name="viruses-and-worms"></a>病毒和蠕蟲

*病毒*是程式碼的目的，是以重現額外類似的程式碼單位的單位。 病毒需要宿主才能運作，檔案、電子郵件或程式都可能成為宿主。 *蠕蟲*單位程式碼的目的，是以重現額外類似的程式碼單位，但它不需要主應用程式。 病毒和蠕蟲常出現在用戶端之間的檔案傳輸期間或是其他使用者送出的 URL 中。 舉例來說，如果病毒存在您的電腦中，它就能夠使用您的身分識別並代您傳送立即訊息。

</div>

<div>

## <a name="personally-identifiable-information"></a>個人識別資訊

Microsoft Lync Server 2013 有可能會透過公用網路，或許可以都連結至個人透露資訊。 資訊類型可以是分解以兩個特定類別：

  - **增強顯示狀態資料**增強顯示狀態資料是使用者可以選擇要共用的或不共用透過連結給同盟協力廠商或與組織內的連絡人的資訊。 此資料不會共用與公用 IM 網路上的使用者。 用戶端原則及其他用戶端組態可能會讓某些控制項與系統管理員。 在 Lync Server 2013 中，增強型目前狀態隱私權模式可針對個別使用者可防止不是在使用者的連絡人清單上的 Lync 使用者看見使用者的目前狀態資訊。 增強型目前狀態隱私權模式無法防止使用者的 Microsoft Office Communicator 2007 與 Microsoft Office Communicator 2007 R2 看見使用者的目前狀態資訊。 如需詳細資訊，請參閱[什麼是新的 Lync Server 2013 中的用戶端](lync-server-2013-what-s-new-for-clients.md)中的快速入門 > 文件和[Lync Server 2013 中設定增強的目前狀態隱私權模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)部署文件中。

  - **必要資料**必要資料是必要的伺服器或用戶端的正常運作，且無法控制的用戶端或系統管理。 這是所需的路由、 狀態維護的目的伺服器或網路層級和訊號的資訊。

下表列出公開在公用網路上的資料。

### <a name="enhanced-presence-data"></a>增強顯示狀態資料

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>資料外洩</th>
<th>可能的設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>個人資料</p></td>
<td><p>名稱、 職稱、 公司、 電子郵件地址、 時區</p></td>
</tr>
<tr class="even">
<td><p>電話號碼</p></td>
<td><p>工作、 手機、 住家</p></td>
</tr>
<tr class="odd">
<td><p>行事曆資訊</p></td>
<td><p>空閒/忙碌，Out-Of-Town 通知、 會議詳細資料 （對象存取您行事曆）</p></td>
</tr>
<tr class="even">
<td><p>目前狀態</p></td>
<td><p>離開、 線上、 忙碌、 請勿打擾、 離線</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>必要資料

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>資料外洩</th>
<th>範例資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IP 位址</p></td>
<td><p>實際的電腦或經過 nat 處理地址的地址</p></td>
</tr>
<tr class="even">
<td><p>SIP URI</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

