---
title: DNS 摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156757dbb3afd671d15618e8d3fceb0dfa7a04ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-09_

對 Lync Server 2013 進行遠端存取的 DNS 記錄需求與憑證和埠的遠端存取是相當直接的。 此外，許多記錄都是選擇性的，視您如何設定執行 Lync 2013 的用戶端以及是否啟用同盟而定。

如需有關 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。

如需有關執行 Lync 2013 之用戶端的自動設定的詳細資料（如果未設定 split 大腦 DNS），請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)（不含分裂

下表包含支援單一合併邊緣拓朴圖中所顯示之單一整合邊緣拓朴所需的 DNS 記錄摘要。 請注意，只有 Lync 2013 和 Lync 2010 用戶端自動進行設定時，才需要特定的 DNS 記錄。 如果您打算使用群組原則物件（Gpo）來設定 Lync 用戶端，則不需要相關聯的自動設定記錄。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要： Edge 伺服器網路介面卡需求

若要避免路由問題，請確認 Edge 伺服器中至少有兩個網路介面卡，且 [預設閘道] 只在與外部介面相關聯的網路介面卡上設定。 例如，如單一整合邊緣拓朴中，在[Lync Server 2013 中有私人 IP 位址和 NAT](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)的單一合併邊緣拓撲圖所示，預設閘道會指向外部防火牆（10.45.16.1）。

您可以在 Edge 伺服器中設定兩個網路介面卡，如下所示：

  - **網路介面卡1（內部介面）**
    
    已指派172.25.33.10 的內部介面。
    
    未定義預設閘道。
    
    請確定您的網路有一個路由，其中包含邊緣內部介面到任何網路，包括執行 Lync Server 2013 或 Lync Server 2013 用戶端的伺服器（例如從172.25.33.0 到192.168.10.0）。

  - **網路介面卡2（外部介面）**
    
    系統會將三個私人 IP 位址指派給這個網路介面卡，例如10.45.16.10 存取邊緣、10.45.16.20 網頁會議邊緣、AV 邊緣10.45.16.30
    
    <div>
    

    > [!NOTE]
    > 如果不建議這樣做，您可以針對所有三個邊緣服務介面使用單一 IP 位址。 雖然這會儲存 IP 位址，但是它需要每個服務有不同的埠號碼。 預設埠號碼為 443/TCP，可確保大多數的遠端防火牆都能允許流量。 若要將埠值變更為（例如）存取邊緣的 5061/TCP，對於網路會議邊緣的 444/tcp，以及 AV 邊緣的 443/TCP，可能會導致遠端使用者發生問題，使得其背後的防火牆無法透過 5061/TCP 與 444/TCP 進行通訊。 此外，三個不同的 IP 位址可讓疑難排解變得更容易，因為能夠篩選 IP 位址。

    
    </div>
    
    存取邊緣 IP 位址是主要，且預設閘道設定為整合路由器（10.45.16.1）。
    
    [Web 會議] 和 [A/V 邊緣 IP 位址-次要]。

<div>


> [!TIP]
> 將 Edge 伺服器設定成兩個網路介面卡是其中一個選項。 另一個選項是將一個網路介面卡用於內部端，而將三個網路介面卡用於邊緣伺服器的外部端。 此選項的主要優點是每 Edge 伺服器服務有一個獨特的網路介面卡，而且在需要疑難排解時也可能更簡明地收集資料



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a>使用 NAT （範例）使用私人 IP 位址的單一合併邊緣所需的 DNS 記錄（範例）

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
<td><p>131.107.155.10</p></td>
<td><p>在已啟用 Lync 功能的使用者的情況中，對於所有 SIP 網域，都必須重複使用 [存取邊緣外部介面]</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>網路會議 Edge 外部介面</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V 邊緣外部介面</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip. _tls. .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>[存取邊緣外部介面]。 需要自動設定 Lync 2013 和 Lync 2010 用戶端才能在外部作業。 在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述步驟。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>需要 SIP 存取邊緣外部介面，才能自動 DNS 發現聯盟夥伴（稱為「允許 SIP 網域」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>整合的邊緣內部介面</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> 如上表所列的記錄會以<EM>.net</EM>副檔名或<EM>.com</EM>副檔名顯示，以強調您不使用分割大腦 DNS 時所需駐留的區域。 如果您使用的是分割大腦 DNS，所有記錄都將位於同一個<EM>.com</EM>區域中，唯一的區別就是它們位於內部或外部 DNS 區域版本中。 如需詳細資訊，請參閱<A href="lync-server-2013-determine-dns-requirements.md">決定 Lync Server 2013 的 DNS 需求</A>中的「分割大腦 DNS」。



</div>

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
<td><p>SIP 存取邊緣外部介面需要將同盟自動 DNS 探索到其他潛在的同盟夥伴，且稱為「允許的 SIP 網域」（在先前的版本中稱為「增強聯盟」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</p>



> [!IMPORTANT]
> 行動與推播通知結算所需要這個 SRV 記錄

</td>
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

