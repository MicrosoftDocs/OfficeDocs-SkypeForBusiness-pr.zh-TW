---
title: Lync Server 2013： DNS 摘要-調整式合併 edge （利用公用 IP 位址進行 DNS 負載平衡）
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
ms.openlocfilehash: 48dab867ac7ae408f544e4dbc6bc55ff555e20a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-09_

對 Lync Server 2013 的遠端存取的 DNS 記錄需求，與憑證及埠的遠端存取非常直接。 此外，許多記錄是選用的，取決於如何設定執行 Lync 2013 的用戶端，以及是否啟用同盟。

如需 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。

如需設定如何設定 Lync 2013 用戶端自動設定的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)中的「自動設定沒有分割的大腦 dns」一節。

下表包含用以支援單一合併 Edge 拓撲 (如單一合併 Edge 拓撲圖表中所示) 所需的 DNS 記錄摘要。 請注意，只有在自動設定 Lync 2013 用戶端時，才需要特定的 DNS 記錄。 如果您打算使用群組原則物件 (Gpo) 設定 Lync 用戶端，則不需要關聯的記錄。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要： Edge Server 網路介面卡需求

若要避免路由問題，請確認 Edge Server 中至少有兩個網路介面卡，且預設閘道只會在與外部介面相關聯的網路介面卡上設定。 例如，如調整式合併 edge 案例中的調整式合併 Edge 案例中所示，在[Lync Server 2013 中使用公用 IP 位址進行 DNS 負載平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)，預設閘道會指向外部防火牆。

您可以在每部 Edge Server 中設定兩個網路介面卡，如下所示：

  - **網路介面卡 1 - 節點 1 (內部介面)**
    
    已指派 172.25.33.10 的內部介面。
    
    未定義預設閘道。
    
    確定有從包含 Edge 內部介面的網路，路由傳送至任何包含執行 Lync Server 2013 或 Lync Server 2013 用戶端之伺服器的網路 (例如，從172.25.33.0 至 192.168.10.0) 。

  - **網路介面卡 1 - 節點 2 (內部介面)**
    
    已指派 172.25.33.11 的內部介面。
    
    未定義預設閘道。
    
    確定有從包含 Edge 內部介面的網路，路由傳送至任何包含執行 Lync Server 2013 或 Lync Server 2013 用戶端之伺服器的網路 (例如，從172.25.33.0 至 192.168.10.0) 。

  - **網路介面卡 2 - 節點 1 (外部介面)**
    
    三個私人 IP 位址會指派給此網路介面卡，例如131.107.155.10 用於 Access Edge service、131.107.155.20 for Web 會議 Edge service、131.107.155.30 for A/V Edge service。
    
    Access Edge service 公用 IP 位址為主要位址，且其預設閘道設定為公用路由器 (131.107.155.1) 。
    
    Web 會議 Edge service 和 A/V Edge service 私人 IP 位址是在 [**網際網路通訊協定第4版**的屬性] 的 [**高級**] 區段中的其他 IP 位址 (TCP/IPv4) 及**網際網路通訊協定第6版** (TCP/IPv6 Windows Server 中的**局域連線屬性**。
    
    <div>
    

    > [!NOTE]  
    > 將單一 IP 位址用於所有三個 Edge 服務介面是可行的，但不建議這麼做。 雖然這樣會儲存 IP 位址，但每個服務需要不同的連接埠號碼。 預設連接埠號碼為 443/TCP，可確保大部分遠端防火牆都允許該流量。 將埠值變更為 (例如，Access Edge service 的) 5061/tcp; A/V Edge service 的 Web 會議 Edge service 和443/TCP 的 444/TCP）可能會為遠端使用者造成問題，但這些使用者在其背後的防火牆不允許流量超過 5061/TCP 和 444/TCP。 此外，由於可以在 IP 位址上進行篩選，因此三個不同的 IP 位址會讓疑難排解較為容易。

    
    </div>

  - **網路介面卡 2 - 節點 2 (外部介面)**
    
    三個私人 IP 位址會指派給此網路介面卡，例如131.107.155.11 用於 Access Edge service、131.107.155.21 for Web 會議 Edge service、131.107.155.31 for A/V Edge service。
    
    Access Edge service 公用 IP 位址為主要位址，且其預設閘道設定為公用路由器 (131.107.155.1) 。
    
    Web 會議 Edge service 和 A/V Edge service 私人 IP 位址是在 [**網際網路通訊協定第4版**的屬性] 的 [**高級**] 區段中的其他 IP 位址 (TCP/IPv4) 及**網際網路通訊協定第6版** (TCP/IPv6 Windows Server 中的**局域連線屬性**。

<div>


> [!TIP]  
> 設定具有兩個網路介面卡的 Edge Server 是兩個選項之一。 另一種方法是針對 Edge Server 的外部端，使用一個網路介面卡作為內部端和三個網路介面卡。 此選項的主要優點是，每個 Edge Server 服務都有不同的網路介面卡，而且在進行疑難排解時，可能會有更簡明的資料收集方式。



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>調整式合併 Edge （透過公用 IP 位址進行 DNS 負載平衡）所需的 DNS 記錄 (範例) 

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
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 及 131.107.155.11</p></td>
<td><p>Access Edge service 外部介面 (Contoso) 針對所有具有 Lync 啟用使用者的 SIP 網域，依需要重複</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 及 131.107.155.21</p></td>
<td><p>Web 會議 Edge service 外部介面</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 及 131.107.155.31</p></td>
<td><p>A/V Edge service 外部介面</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip _tls .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge service 外部介面。 自動設定 Lync 2013 和 Lync 2010 用戶端時必須執行，以供外部工作。 請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>「Access Edge service」的自動 DNS 探索（稱為「允許的 SIP 網域」）所需的外部介面，稱為「允許的 SIP 網域」 (稱為「增強型同盟」) 。 請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 及 172.25.33.11</p></td>
<td><p>合併的 Edge 內部介面</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>進行同盟所需的記錄


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
<th>FQDN</th>
<th>IP 位址/FQDN 主機記錄</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>SIP Access Edge service 外部介面，可自動將同盟的 DNS 探索至其他潛在同盟協力廠商，也稱為「允許的 SIP 網域」 (在舊版版本) 中稱為「增強型同盟」。</p>
<div>

> [!IMPORTANT]  
> 針對具有啟用 Lync 功能之使用者的所有 SIP 網域和使用推播通知服務或 Apple Push Notification 服務的 Microsoft Lync 行動用戶端，重複此步驟。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>可延伸訊息和目前狀態通訊協定的 DNS 摘要


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
<th>FQDN</th>
<th>IP 位址/FQDN 主機記錄</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-_tcp .com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Access Edge service 或 Edge 集區上的 XMPP proxy 外部介面。針對所有內部 SIP 網域，針對所有內部 SIP 網域，依需要重複此步驟：透過全域原則、使用者所在的網站原則，或套用到啟用 Lync 功能之使用者的使用者原則，可透過外部存取原則的設定允許與 XMPP 聯繫。 您也必須在 XMPP 同盟協力廠商原則中設定允許的 XMPP 網域。 如需其他詳細資料，請參閱另<strong>請</strong>參閱主題</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (範例)</p></td>
<td><p>Edge Server 或 Edge 集區上主控 XMPP proxy 的 Access Edge service 的 IP 位址</p></td>
<td><p>指向主控 XMPP proxy 服務的 Access Edge service 或 Edge 集區。 一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

