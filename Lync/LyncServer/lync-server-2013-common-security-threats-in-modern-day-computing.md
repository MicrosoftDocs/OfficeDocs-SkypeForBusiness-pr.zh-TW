---
title: Lync Server 2013：現代計算中常見的安全性威脅
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
ms.openlocfilehash: 60197a65bb0362b1bbdcf3fee779ed503af00eb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526130"
---
# <a name="common-security-threats-in-modern-day-computing"></a>現代的日期計算中的常見安全性威脅

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-10_

因為 Lync Server 2013 是企業級的通訊系統，所以應注意可能影響其基礎結構和通訊的常見安全性攻擊。

<div>

## <a name="compromised-key-attack"></a>洩漏金鑰攻擊

金鑰是用來加密、解密或驗證秘密資訊的秘密代碼或數字。 在公開金鑰基礎結構中使用的機密機碼有兩個 (必須考慮的 PKI) ：。

  - 每個憑證持有者所擁有的私密金鑰

  - 通訊夥伴成功識別與會話金鑰交換之後所使用的工作階段金鑰

當攻擊者判斷出私密金鑰或工作階段金鑰時，即發生洩漏金鑰攻擊。 當攻擊者成功判斷出金鑰後，就可以在傳送者不知情的情況下，使用金鑰將加密的資料解密。

Lync Server 2013 使用 Windows Server 作業系統中的 PKI 功能來保護用於加密傳輸層安全性 (TLS) 連線的金鑰資料。 媒體加密所用的按鍵會透過 TLS 連接進行交換。

</div>

<div>

## <a name="network-denial-of-service-attack"></a>網路拒絕服務攻擊

當攻擊者禁止正常網路使用和有效使用者運作時，就會發生 *拒絕服務攻擊* 。 當攻擊者利用合法的使用者利用服務的合法要求來淹沒服務時，這是很好的做法。 攻擊者使用拒絕服務攻擊可執行下列作業：

  - 傳送無效的資料給受攻擊網路中執行的應用程式和服務，干擾其正常功能。

  - 傳送大量流量使系統超載，直到系統停止回應或是對合法要求回應變慢。

  - 隱藏攻擊證據。

  - 阻止使用者存取網路資源。

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>偷聽 (探查、窺探) 

當攻擊者存取網路中的資料路徑，並且具備監控和讀取流量的能力時，可能會發生*偷聽*。 這也稱為 *嗅探* 或 *窺探*。 如果流量是純文字，則攻擊者取得路徑存取權之後就可以讀取流量。 例如，控制資料路徑上的路由器，就是進行這類攻擊的方式。

Microsoft Lync Server 2013 內之流量的預設建議和設定是使用來自用戶端與伺服器之間的信任伺服器與 TLS 之間的相互 TLS (MTLS) 。 這項保護措施會使攻擊非常困難，甚至無法在指定交談發生的時段內達到。 TLS 會驗證所有相關人員並加密所有流量。 雖然這無法阻止竊聽，卻能讓攻擊者無法讀取流量，除非加密被破解。

使用轉送 NAT 的遍歷 (關閉) 通訊協定不會要求加密流量，而且傳送的資訊會受到郵件完整性的保護。 雖然它是開放的，但是它所傳送的資訊 (也就是說，您只需查看封包的來源和目的地位址，即可直接解壓縮 IP 位址和通訊埠) 。 A/V Edge service 會使用衍生自少數專案的金鑰（包括密碼，也就是永不以明文形式傳送）來檢查郵件的郵件完整性，以確保資料有效。 如果使用安全即時通訊協定 (SRTP) ，媒體流量也會加密。

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>身分識別哄騙 (IP 位址欺騙) 

當攻擊者判斷並使用網路、電腦或網路元件的 IP 位址但未獲授權時，就會發生*欺騙*。 成功的攻擊可讓攻擊者像是由 IP 位址一般識別的實體一樣運作。 在 Microsoft Lync Server 2013 的內容中，只有當系統管理員已執行下列兩項作業時，才會進入播放狀態：

  - 設定只支援傳輸控制通訊協定 (TCP)  (但不建議使用的連線，因為 TCP 通訊未加密) 。

  - 將那些連線的 IP 位址標記為受信任的主機。

這不是傳輸層安全性 (TLS) 連線的問題，因為 TLS 會驗證所有的各方，並加密所有流量。 使用 TLS 可防止攻擊者在特定的連接上執行 IP 位址欺騙 (例如，相互 TLS 連線) 。 但是，攻擊者仍然可以哄騙 Lync Server 2013 所用的 DNS 伺服器位址。 不過，因為 Lync 的驗證是以憑證執行，所以攻擊者不會有必要的有效憑證，以哄騙通訊中的一方。

</div>

<div>

## <a name="man-in-the-middle-attack"></a>干預中間人攻擊

當攻擊者透過攻擊者的電腦來重排兩位使用者之間的通訊時，就會發生中間人攻擊，而不會知道兩個通訊使用者的知識。 攻擊者可以在將流量傳送給預定收件者之前，監控並讀取流量。 通訊中的每一位使用者都會在不知情的情況下傳送流量，並接收來自攻擊者的流量，所有的情況都是在思考他們只與預定的使用者進行通訊。 如果攻擊者可以修改 Active Directory 網域服務，將其伺服器新增為受信任的伺服器或修改網域名稱系統 (DNS) ，以取得用戶端透過攻擊者以其方式連線至伺服器，便會發生這種情況。 在兩個用戶端間的媒體流量也會發生中間人攻擊。 不過，在 Microsoft Lync Server 2013 點對點音訊、影片和應用程式共用中，資料流程會以 SRTP 加密，使用在使用會話初始通訊協定的對等 (SIP) over TLS 之間協商的加密金鑰。 群組聊天等伺服器會使用 HTTPS，以加強網頁流量的安全性。

</div>

<div>

## <a name="rtp-replay-attack"></a>RTP 重放攻擊

當雙方之間的有效媒體傳輸因惡意目的而截取和重新傳輸時，就會發生重新顯示 *攻擊* 。 SRTP 與安全信號通訊協定搭配使用，可讓接收器維護已接收的 RTP 封包的索引，並將每個新的資料包與索引中已列出的資料包進行比較，以保護傳輸免受重新顯示攻擊。

</div>

<div>

## <a name="spim"></a>Spim

*Spim* 是未經要求的商業立即訊息或顯示狀態訂閱要求。 雖然它本身不是網路遭到損害，但卻令人討厭的是，它可能會降低資源的可用性和生產，而且可能會導致網路受損。 例如，使用者會傳送要求來 spimming 對方。 使用者可以彼此封鎖，以防止發生這種情況，但在同盟中，如果已建立協調的 spim 攻擊，則除非您停用夥伴的同盟，否則這可能會很難克服。

</div>

<div>

## <a name="viruses-and-worms"></a>病毒和蠕蟲

*病毒*是其用途的程式碼單位，可再現其他類似的代碼單位。 病毒需要宿主才能運作，檔案、電子郵件或程式都可能成為宿主。 *Worm*是一個程式碼單位，其用途是複製其他類似的代碼單位，但不需要主機。 病毒和蠕蟲常出現在用戶端之間的檔案傳輸期間或是其他使用者送出的 URL 中。 舉例來說，如果病毒存在您的電腦中，它就能夠使用您的身分識別並代您傳送立即訊息。

</div>

<div>

## <a name="personally-identifiable-information"></a>個人身分識別資訊

Microsoft Lync Server 2013 可能會透過可以連結到個人的公用網路洩漏資訊。 資訊類型可分為兩個特定類別：

  - **增強顯示狀態資料** 增強型顯示狀態資料是使用者可選擇共用或不共用的資訊，供同盟合作夥伴或組織內的連絡人連結。 此資料與公用 IM 網路上的使用者不共用。 用戶端原則和其他用戶端設定可能會對系統管理員帶來一些控制權。 在 Lync Server 2013 中，可為個別使用者設定增強的目前狀態隱私權模式，以避免使用者的連絡人清單中的 Lync 使用者看到使用者的目前狀態資訊。 增強型目前狀態隱私權模式不會防止 Microsoft Office Communicator 2007 和 Microsoft Office Communicator 2007 R2 的使用者看到使用者的目前狀態資訊。 如需詳細資訊，請參閱部署檔中的「入門檔」和「[在 Lync server 2013 中設定增強型目前狀態隱私權」模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)中的[客戶2013端新增功能](lync-server-2013-what-s-new-for-clients.md)。

  - **必要資料** 必要的資料是伺服器或用戶端的適當運作所需的，且不受用戶端或系統管理的控制。 這是伺服器或網路層級必要的資訊，目的是用於路由、狀態維護和信號。

下表列出透過公用網路公開的資料。

### <a name="enhanced-presence-data"></a>增強顯示狀態資料

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>資料洩漏</th>
<th>可能的設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>個人資料</p></td>
<td><p>名稱、職稱、公司、電子郵件地址、時區</p></td>
</tr>
<tr class="even">
<td><p>電話號碼</p></td>
<td><p>Work，Mobile，Home</p></td>
</tr>
<tr class="odd">
<td><p>行事曆資訊</p></td>
<td><p>Free/Busy、不在城鎮的通知、會議詳細資料 (有權存取您的行事曆) </p></td>
</tr>
<tr class="even">
<td><p>顯示狀態</p></td>
<td><p>離開，可用，忙碌，請勿打擾，離線</p></td>
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
<th>資料洩漏</th>
<th>範例資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IP 位址</p></td>
<td><p>電腦或 NATed 位址的實際位址</p></td>
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

