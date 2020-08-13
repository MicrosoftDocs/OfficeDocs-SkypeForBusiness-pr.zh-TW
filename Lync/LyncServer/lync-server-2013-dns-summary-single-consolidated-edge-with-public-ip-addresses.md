---
title: DNS 摘要-單一合併 edge （利用公用 IP 位址）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 622cb9811e33762bf40c05dfa5e5f0ab644b51aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-單一合併 edge （利用公用 IP 位址）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-09_

對 Lync Server 2013 的遠端存取的 DNS 記錄需求，與憑證及埠的遠端存取非常直接。 此外，許多記錄是選用的，取決於如何設定執行 Lync 2013 的用戶端，以及是否啟用同盟。

如需 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。

如需有關執行 Lync 2013 之用戶端自動設定的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)中的「沒有 Split-Brain DNS 的自動設定」。

下表包含用以支援單一合併 Edge 拓撲 (如單一合併 Edge 拓撲圖表中所示) 所需的 DNS 記錄摘要。 請注意，只有在自動設定 Lync 2013 和 Lync 2010 用戶端時，才需要特定的 DNS 記錄。 如果您打算使用群組原則物件 (Gpo) 設定 Lync 用戶端，則不需要關聯的自動設定記錄。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要： Edge Server 網路介面卡需求

若要避免路由問題，請確認 Edge Server 中至少有兩個網路介面卡，且預設閘道只會在與外部介面相關聯的網路介面卡上設定。 例如，在[Lync Server 2013 的單一合併](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)edge 拓撲中，如使用公用 ip 位址的單一合併 edge 拓撲，使用公用 ip 位址的單一合併 edge 拓撲，預設閘道會指向您網際網路周邊或防火牆上的外部路由器，可提供公用 ip 位址。 Edge Server 介面的網路關聯性是路由關聯，而不是 NAT 關聯。

您可以在 Edge Server 中設定兩個網路介面卡，如下所示：

  - **網路介面卡 1 (內部介面)**
    
    已指派 172.25.33.10 的內部介面。
    
    未定義預設閘道。
    
    確定有從包含 Edge 內部介面的網路，路由傳送至任何包含執行 Lync Server 2013 或 Lync Server 2013 用戶端之伺服器的網路 (例如，從172.25.33.0 至 192.168.10.0) 。

  - **網路介面卡 2 (外部介面)**
    
    將三個公開 IP 位址指派給這個網路介面卡，例如，131.107.155.10 指派給 Access Edge、131.107.155.20 指派給 Web Conferencing Edge，而 131.107.155.30 指派給 AV Edge。
    
    <div>
    

    > [!NOTE]
    > 對於所有三個 Edge 服務介面使用相同的 IP 位址，不過不建議這麼做。雖然這確實能夠節省 IP 位址，不過對於各個服務仍然需要不同的連接埠編號。預設的連接埠編號是 443/TCP，這能夠確保大多數遠端防火牆將允許流量。例如，將連接埠值變更為 5061/TCP (Access Edge)、 444/TCP (Web Conferencing Edge) 和 443/TCP (AV Edge)，可能導致遠端使用者發生問題，以致其使用的防火牆埠不允許透過 5061/TCP 和 444/TCP 的流量。此外，由於能夠篩選 IP 位址，所以三個不同的 IP 位址比較容易進行疑難排解。

    
    </div>
    
    Access Edge 公開 IP 位址為主要位址，且其預設閘道將設為公開路由器 (131.107.155.1)。
    
    Web 會議和 A/V Edge 公開 IP 位址是 Windows Server 的**本機區域連線內容**中**網際網路協定第 4 版 (TCP/IPv4)** 和**網際網路通訊協定第 6 版(TCP/IPv6)** 所出現的**進階**區段中額外的 IP 位址。

<div>


> [!TIP]
> 設定具有兩個網路介面卡的 Edge Server 是兩個選項之一。 另一種方法是針對 Edge Server 的外部端，使用一個網路介面卡作為內部端和三個網路介面卡。 此選項的主要優點是，每個 Edge Server 服務都有不同的網路介面卡，而且在進行疑難排解時，可能會有更簡明的資料收集方式。



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>含有公開 IP 位址的單一合併 Edge 所需的 DNS 記錄 (範例)

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
<td><p>131.107.155.10</p></td>
<td><p>Access Edge 外部介面 (Contoso) 對於存在 Lync 啟用的使用者在其中的所有 SIP 網路進行必要的重複</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Web Conferencing Edge 外部介面</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V Edge 外部介面</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip _tls .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge 外部介面。 自動設定 Lync 2013 和 Lync 2010 用戶端時必須執行，以供外部工作。 請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>DNS 自動探索同盟合作夥伴 (亦稱為「允許的 SIP 網域」，先前版本稱為增強型同盟) 需要 SIP Access Edge 外部介面。對於存在 Lync 啟用的使用者在其中的所有 SIP 網路必須重複</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>合併 Edge 內部介面</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> 上表所列記錄內含 <EM>.net</EM> 延伸網址或 <EM>.com</EM> 延伸網址，以強調在您未使用 split-brain DNS 時這些項目應該歸屬的區域。 如果您使用 split-brain DNS，則所有記錄將位於相同區域，唯一區別在於該記錄的版本 (內部或外部)。 如需詳細資訊，請參閱<A href="lync-server-2013-determine-dns-requirements.md">決定 Lync Server 2013 的 dns 需求</A>中的「Split-Brain DNS」。



</div>

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
<td><p>SIP Access Edge 外部介面。DNS 自動探索同盟至其他潛在同盟協力廠商 (亦稱為「允許的 SIP 網域」，先前版本稱為增強型同盟) 所需。請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</p>



> [!IMPORTANT]
> 行動性及推播通知結算所需要此 SRV 記錄

</td>
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

