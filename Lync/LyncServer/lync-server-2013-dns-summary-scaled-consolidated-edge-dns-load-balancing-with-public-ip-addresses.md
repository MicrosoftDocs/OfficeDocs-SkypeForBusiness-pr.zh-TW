---
title: Lync Server 2013：DNS 摘要 - 調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f748f8107e4d1c0da41a07285eb61e4a3149551
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-09_

對 Lync Server 2013 進行遠端存取的 DNS 記錄需求與憑證和埠的遠端存取是相當直接的。 此外，許多記錄都是選擇性的，視您如何設定執行 Lync 2013 的用戶端以及是否啟用同盟而定。

如需有關 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。

如需有關設定 Lync 2013 用戶端的自動設定的詳細資料，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)（不含分割大腦 dns）一節。

下表包含支援單一合併邊緣拓朴圖中所顯示之單一整合邊緣拓朴所需的 DNS 記錄摘要。 請注意，只有在自動設定 Lync 2013 用戶端時，才需要特定的 DNS 記錄。 如果您打算使用群組原則物件（Gpo）來設定 Lync 用戶端，則不需要相關聯的記錄。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要： Edge 伺服器網路介面卡需求

若要避免路由問題，請確認 Edge 伺服器中至少有兩個網路介面卡，且 [預設閘道] 只在與外部介面相關聯的網路介面卡上設定。 例如，在經過[調整的合併邊緣（在 Lync Server 2013 中，使用公用 IP 位址進行 DNS 負載平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)）中，預設閘道會指向外部防火牆，如此圖中所示。

您可以在每個邊緣伺服器中設定兩個網路介面卡，如下所示：

  - **網路介面卡 1-節點1（內部介面）**
    
    已指派172.25.33.10 的內部介面。
    
    未定義預設閘道。
    
    請確定您的網路有一個路由，其中包含邊緣內部介面到任何網路，包括執行 Lync Server 2013 或 Lync Server 2013 用戶端的伺服器（例如從172.25.33.0 到192.168.10.0）。

  - **網路介面卡 1-節點2（內部介面）**
    
    已指派172.25.33.11 的內部介面。
    
    未定義預設閘道。
    
    請確定您的網路有一個路由，其中包含邊緣內部介面到任何網路，包括執行 Lync Server 2013 或 Lync Server 2013 用戶端的伺服器（例如從172.25.33.0 到192.168.10.0）。

  - **網路介面卡2節點1（外部介面）**
    
    系統會將三個私人 IP 位址指派給這個網路介面卡，例如 131.107.155.10 [存取邊緣服務]，131.107.155.20 [網路會議 Edge 服務]，131.107.155.30 提供 A/V 邊緣服務。
    
    存取邊緣服務公用 IP 位址是主要，且預設閘道設定為公用路由器（131.107.155.1）。
    
    網路會議 Edge 服務與 A/V 邊緣服務私人 IP 位址是 Windows Server 中的 [**網際網路通訊協定版本4（tcp/IPv4）** ] 和 [**局域網****協定版本6（tcp/IPv6）** ] 屬性的 [**高級**] 區段中的其他 IP 位址。
    
    <div>
    

    > [!NOTE]  
    > 如果不建議這樣做，您可以針對所有三個邊緣服務介面使用單一 IP 位址。 雖然這會儲存 IP 位址，但是它需要每個服務有不同的埠號碼。 預設埠號碼為 443/TCP，可確保大多數的遠端防火牆都能允許流量。 將埠值變更為（例如） [存取邊緣] 服務的 [5061/TCP]、[網路會議邊緣] 服務的 [444/tcp] 和 [A/V 邊緣] 服務的 443/TCP，可能會導致遠端使用者發生問題，而這些使用者的防火牆不允許使用 5061/TCP 和 444/TCP 的流量。 此外，三個不同的 IP 位址可讓疑難排解變得更容易，因為能夠篩選 IP 位址。

    
    </div>

  - **網路介面卡2節點2（外部介面）**
    
    系統會將三個私人 IP 位址指派給這個網路介面卡，例如 131.107.155.11 [存取邊緣服務]，131.107.155.21 [網路會議 Edge 服務]，131.107.155.31 提供 A/V 邊緣服務。
    
    存取邊緣服務公用 IP 位址是主要，且預設閘道設定為公用路由器（131.107.155.1）。
    
    網路會議 Edge 服務與 A/V 邊緣服務私人 IP 位址是 Windows Server 中的 [**網際網路通訊協定版本4（tcp/IPv4）** ] 和 [**局域網****協定版本6（tcp/IPv6）** ] 屬性的 [**高級**] 區段中的其他 IP 位址。

<div>


> [!TIP]  
> 將 Edge 伺服器設定成兩個網路介面卡是其中一個選項。 另一個選項是將一個網路介面卡用於內部端，而將三個網路介面卡用於邊緣伺服器的外部端。 此選項的主要優點是每 Edge 伺服器服務有一個獨特的網路介面卡，而且在需要疑難排解時也可能更簡明地收集資料



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>已調整合並的邊緣所需的 DNS 記錄，以及使用公用 IP 位址的 DNS 負載平衡（範例）

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/類型/埠</th>
<th>FQDN/DNS 記錄</th>
<th>IP 位址/FQDN</th>
<th>地圖/批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 和131.107.155.11</p></td>
<td><p>在已啟用 Lync 功能的使用者的所有 SIP 網域中，請根據需要，為存取邊緣服務外部介面（Contoso）重複進行</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 和131.107.155.21</p></td>
<td><p>網路會議 Edge 服務外部介面</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 和131.107.155.31</p></td>
<td><p>A/V 邊緣服務外部介面</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip. _tls. .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge 服務外部介面。 需要自動設定 Lync 2013 和 Lync 2010 用戶端才能在外部作業。 在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述步驟。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>存取邊緣服務外部介面需要聯盟夥伴的自動 DNS 探索（稱為「允許 SIP 網域」（在舊版發行中稱為「已允許 SIP 網域」）。 在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 和172.25.33.11</p></td>
<td><p>整合的邊緣內部介面</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>同盟所需的記錄


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/類型/埠</th>
<th>稱</th>
<th>IP 位址/FQDN 主機記錄</th>
<th>地圖/批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP 存取邊緣服務外部介面需要將同盟自動 DNS 探索到其他潛在的同盟夥伴，且稱為「允許的 SIP 網域」（在先前的版本中稱為「增強聯盟」）。</p>
<div>

> [!IMPORTANT]  
> 在已啟用 Lync 功能的使用者以及使用推播通知服務或 Apple 推播通知服務的 Microsoft Lync 行動用戶端的情況下，對所有 SIP 網域重複上述步驟。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>可擴展訊息和目前狀態通訊協定的 DNS 摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/類型/埠</th>
<th>稱</th>
<th>IP 位址/FQDN 主機記錄</th>
<th>地圖/批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-_tcp. .com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>XMPP [存取邊緣服務] 或 [Edge] 池中的 [proxy 外部介面]。在已啟用 Lync 功能的使用者中，針對所有內部 SIP 網域重複上述步驟，可透過全域原則、使用者所處的網站原則，或套用使用者原則來設定外部存取原則。啟用 Lync 的使用者。 您也必須在 XMPP 聯盟夥伴原則中設定允許的 XMPP 網域。 如需其他詳細資料，請參閱另<strong>請</strong>參閱中的主題</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com （例如）</p></td>
<td><p>Edge 伺服器或邊緣池託管 XMPP proxy 的存取邊緣服務的 IP 位址</p></td>
<td><p>指向託管 XMPP proxy 服務的存取邊緣服務或 Edge 池。 通常，您所建立的 SRV 記錄會指向這個主機（A 或 AAAA）記錄</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

