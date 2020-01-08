---
title: Lync Server 2013：現代的日期計算中的常見安全性威脅
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2446ee0755f4544f17f6c04c6059d70576a466f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "40982757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>現代的日期計算中的常見安全性威脅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-10_

由於 Lync Server 2013 是企業級通訊系統，因此您應該注意到可能會影響其基礎結構和通訊的常見安全性攻擊。

<div>

## <a name="compromised-key-attack"></a>受害金鑰攻擊

金鑰是用來加密、解密或驗證機密資訊的秘密代碼或數位。 在公開金鑰基礎結構（PKI）中，有兩個要使用的機密金鑰必須考慮：。

  - 每個證書持有者所擁有的私人金鑰

  - 通訊合作夥伴成功識別與會話金鑰交換之後所使用的工作階段金鑰

當攻擊者決定私密金鑰或工作階段金鑰時，就會發生受害金鑰攻擊。 當攻擊者成功判斷金鑰之後，攻擊者就可以使用金鑰來解密加密的資料，而不需要寄件者的知識。

Lync Server 2013 使用 Windows Server 作業系統中的 PKI 功能，來保護用於傳輸層安全性（TLS）連線之加密的金鑰資料。 媒體加密所用的金鑰會經由 TLS 連線進行交換。

</div>

<div>

## <a name="network-denial-of-service-attack"></a>網路拒絕服務攻擊

當攻擊者防止正常網路使用及由有效的使用者運作時，就會發生*拒絕服務攻擊*。 當攻擊者利用合法的使用者大量使用服務的合法要求時，就會完成這項工作。 攻擊者可以使用拒絕服務攻擊來執行下列動作：

  - 傳送不正確資料給受攻擊的網路中執行的應用程式和服務，以中斷其正常運作。

  - 傳送大量的流量，在系統停止回應或緩慢回應合法要求之前，將系統超載。

  - 隱藏攻擊的證據。

  - 防止使用者存取網路資源。

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>竊聽（嗅探、窺探）

*竊聽*可能會在攻擊者取得網路中資料路徑的存取權，並具備監視及讀取流量的能力時發生。 這也稱為*嗅探*或*窺探*。 如果流量是純文字，攻擊者就可以在取得路徑存取權時，閱讀流量。 例如，您可以透過控制資料路徑上的路由器來執行攻擊。

在 Microsoft Lync Server 2013 中，針對通訊的預設建議和設定是在受信任的伺服器之間使用相互 TLS （MTLS），而從用戶端到伺服器的 TLS 則是。 這個保護措施會使攻擊在指定交談發生的時段內變得非常困難或無法完成。 TLS 會驗證所有雙方，並加密所有通訊。 這不會防止竊聽，但除非加密遭到破壞，否則攻擊者無法讀取流量。

使用中繼 NAT （TURN）通訊協定的遍歷不會要求加密通信量，且傳送的資訊會受到郵件完整性的保護。 雖然它是以竊聽的方式開啟，但是它所傳送的資訊（也就是 IP 位址和埠）可以直接提取，只要查看資料包的來源和目的地位址即可。 A/V Edge 服務使用從幾個專案衍生的金鑰來檢查郵件的完整性，以確保資料有效，包括 [密碼]，此密碼決不會以明文傳送。 如果使用安全即時通訊協定（SRTP），媒體流量也會經過加密。

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>身分識別欺騙（IP 位址欺騙）

如果攻擊者決定並使用網路、電腦或網路元件的 IP 位址，而不需要執行此動作，就會發生*哄騙*情況。 成功的攻擊可讓攻擊者進行操作，就像是 IP 位址通常會識別的實體一樣。 在 Microsoft Lync Server 2013 的內容中，只有當系統管理員已完成下列兩項作業時，才會播放此情況：

  - 已設定僅支援傳輸控制通訊協定（TCP）的連線（不建議使用），因為 TCP 通訊未加密。

  - 已將這些連線的 IP 位址標示為受信任的主機。

這不是傳輸層安全性（TLS）連線的問題，因為 TLS 會驗證所有參與方，並加密所有通訊。 使用 TLS 可防止攻擊者在特定連線（例如相互 TLS 連線）上執行 IP 位址欺騙。 但是，攻擊者仍可欺騙 Lync Server 2013 使用的 DNS 伺服器位址。 不過，因為 Lync 中的驗證是透過憑證來執行，所以攻擊者沒有假冒通訊中的其中一個參與方所需的有效證書。

</div>

<div>

## <a name="man-in-the-middle-attack"></a>中間人攻擊（中間人）

當攻擊者透過攻擊者的電腦傳送兩個使用者之間的通訊時，就會發生中間人攻擊，而不需要兩個通訊使用者的知識。 攻擊者可以在將通信量傳送給預定的收件者前，進行監控並閱讀。 通訊中的每位使用者都會在不知情的情況下傳送流量，並接收來自攻擊者的流量，同時認為他們只與預期的使用者通訊。 如果攻擊者可以修改 Active Directory 網域服務將其伺服器作為受信任的伺服器加入，或修改網域名稱系統（DNS），以讓用戶端透過攻擊者連線到伺服器，就會發生這種情況。 中間人攻擊也會在兩個用戶端之間的媒體流量中發生。 不過，在 Microsoft Lync Server 2013 的點對端音訊、影片和應用程式共用中，資料流程是使用 SRTP 來加密的，這些金鑰是在使用經由 TLS 的會話初始通訊協定（SIP）的對等。 伺服器（例如群組聊天）使用 HTTPS 來加強網頁流量的安全性。

</div>

<div>

## <a name="rtp-replay-attack"></a>RTP 重播攻擊

當雙方之間的有效媒體傳輸遭到攔截並重新傳輸以進行惡意時，就會發生*重播攻擊*。 SRTP 與安全的信號通訊協定搭配使用，可讓接收器維持已收到的 RTP 資料包的索引，並將每個新的資料包與已列在索引中的新資料包加以比較，以保護傳輸。

</div>

<div>

## <a name="spim"></a>Spim

*Spim*是未經請求的商業立即訊息或目前狀態訂閱要求。 雖然不只是網路遭到破壞，但卻不令人討厭，但可能會降低資源的可用性與生產，而且可能會造成網路遭到破壞。 例如，使用者可以傳送要求來 spimming 對方。 使用者可以彼此封鎖來避免這種情況，但使用同盟時，如果已建立共同的 spim 攻擊，除非您為合作夥伴停用同盟，否則可能難以解決。

</div>

<div>

## <a name="viruses-and-worms"></a>病毒與蠕蟲

[*病毒*] 是一個程式碼單位，其目的是要再現其他類似的代碼單位。 若要發揮作用，病毒需要有主機（例如檔案、電子郵件或程式）。 *蠕蟲*是一種程式碼單位，其用途是要再現其他類似的程式碼單位，但不需要主機。 病毒和蠕蟲主要會在用戶端之間的檔案傳輸期間，或從其他使用者傳送 Url 時顯示。 例如，如果您的電腦上有病毒，就可以使用您的身分識別和代表您傳送即時消息。

</div>

<div>

## <a name="personally-identifiable-information"></a>個人辨識資訊

Microsoft Lync Server 2013 有可能在可連結至個人的公用網路上洩漏資訊。 資訊類型可以分為兩個特定類別：

  - **增強的目前狀態資料**[增強的目前狀態資料] 是使用者可以選擇共用或不共用至同盟夥伴或組織內部連絡人之連結的資訊。 此資料不會與公用 IM 網路上的使用者共用。 用戶端原則和其他用戶端設定可能會讓系統管理員進行一些控制。 在 Lync Server 2013 中，您可以針對個別使用者設定增強的目前狀態隱私權模式，避免 Lync 使用者不在使用者的連絡人清單中，而不會看到使用者的目前狀態資訊。 增強的目前狀態隱私權模式不會防止 Microsoft Office Communicator 2007 和 Microsoft Office Communicator 2007 R2 的使用者看到使用者的目前狀態資訊。 如需詳細資訊，請參閱適用[于 Lync server 2013 中的用戶端的新功能](lync-server-2013-what-s-new-for-clients.md)在「快速入門」檔中，以及在 [部署] 檔的 [ [lync server 2013]](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)中設定增強的目前狀態隱私權

  - **強制資料**伺服器或用戶端的正常運作需要必要的資料，而且不受用戶端或系統管理的控制。 這是伺服器或網路層級所需的資訊，用於路由、狀態維護和傳送信號。

下表列出在公用網路公開的資料。

### <a name="enhanced-presence-data"></a>增強的目前狀態資料

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>已披露資料</th>
<th>可能的設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>個人資料</p></td>
<td><p>名稱、標題、公司、電子郵件地址、時區</p></td>
</tr>
<tr class="even">
<td><p>電話號碼</p></td>
<td><p>公司、行動裝置、家用版</p></td>
</tr>
<tr class="odd">
<td><p>行事曆資訊</p></td>
<td><p>空閒/忙碌、不在城鎮通知、會議詳細資料（針對有權存取您行事曆的人員）</p></td>
</tr>
<tr class="even">
<td><p>目前狀態</p></td>
<td><p>離開、可用、忙碌、[請勿打擾]、[離線]</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>強制資料

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>已披露資料</th>
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

