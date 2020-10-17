---
title: 使用硬體負載平衡器的 DNS 摘要-調整式合併 edge
description: DNS 摘要-調整式合併 edge （使用硬體負載平衡器）。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59581f435267a7db607e03a8cbf52d21f70897f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570659"
---
# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-調整式合併 edge （使用硬體負載平衡器）

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-27_

對 Lync Server 2013 的遠端存取的 DNS 記錄需求，與憑證及埠的遠端存取非常直接。 此外，許多記錄是選用的，取決於如何設定執行 Lync 2013 的用戶端，以及是否啟用同盟。

如需 Lync 2013 DNS 需求的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。

如需設定如何設定 Lync 2013 用戶端自動設定的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)中的「自動設定沒有分割的大腦 dns」一節。

下表包含支援調整式合併 Edge 拓撲 (硬體負載平衡) 圖所需之 DNS 記錄的摘要。 請注意，只有 Lync 用戶端的自動設定需要某些 DNS 記錄。 如果您打算使用群組原則物件 (Gpo) 設定 Lync 用戶端，則不需要關聯的記錄。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要： Edge Server 網路介面卡需求

若要避免路由問題，請確認 Edge Server 中至少有兩個網路介面卡，且預設閘道只會在與外部介面相關聯的網路介面卡上設定。 例如，在 [調整式合併 edge 案例] 中，在 [Lync Server 2013 中使用硬體負載平衡器調整](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)式合併 edge 案例中所顯示的預設閘道會指向外部防火牆。

您可以在每一部 Edge Server 中設定兩個網路介面卡，如下所示：

  - **網路介面卡 1 (內部介面)**
    
    已指派 172.25.33.10 的內部介面。
    
    無預設閘道。
    
    請確定有從包含 Edge Server 內部介面的網路到包含 Lync Server 用戶端或執行 Lync Server 之伺服器的任何網路的路由 (例如，從172.25.33.0 到 192.168.10.0) 。

  - **網路介面卡 2 (外部介面)**
    
    三個公用 IP 位址會指派給此網路介面卡，例如131.107.155.10 用於 Access Edge service、131.107.155.20 for Web 會議 Edge service、131.107.155.30 for A/V Edge service。
    
    <div>
    

    > [!NOTE]
    > 指派給 Edge Server 實際外部網路介面的 IP 位址，可能取決於您所選擇的硬體負載平衡器。 請參閱硬體負載平衡器的檔，以瞭解實際的 IP 位址需求。<BR>將單一 IP 位址用於所有三個 Edge 服務介面是可行的，但不建議這麼做。 雖然這樣會儲存 IP 位址，但每個服務需要不同的連接埠號碼。 預設連接埠號碼為 443/TCP，可確保大部分遠端防火牆都允許該流量。 將埠值變更為 (例如，Access Edge service 的) 5061/tcp; A/V Edge service 的 Web 會議 Edge service 和443/TCP 的 444/TCP）可能會為遠端使用者造成問題，但這些使用者在其背後的防火牆不允許流量超過 5061/TCP 和 444/TCP。 此外，由於可以在 IP 位址上進行篩選，因此三個不同的 IP 位址會讓疑難排解較為容易。

    
    </div>
    
    Access Edge service 的 IP 位址為主要位址，且預設閘道設定為網際網路對向路由器 (131.107.155.1) 。
    
    Web 會議 Edge service 和 A/V Edge service IP 位址次要。

<div>


> [!TIP]
> 設定具有兩個網路介面卡的 Edge Server 是兩個選項之一。 另一種方法是針對 Edge Server 的外部端，使用一個網路介面卡作為內部端和三個網路介面卡。 此選項的主要優點是，每個 Edge Server 服務都有不同的網路介面卡，而且在進行疑難排解時，可能會有更簡明的資料收集方式。



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>調整式合併 Edge （硬體負載平衡 (範例）所需的 DNS 記錄) 

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
<td><p>Access Edge service 外部介面 (Contoso) 。 請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Web 會議 Edge service 外部介面</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>A/V Edge service 外部介面</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/SRV/443</p></td>
<td><p>_sip _sip._tls .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Access Edge service 外部介面。 自動設定 Lync 2013 和 Lync 2010 用戶端時必須執行，以供外部工作。 請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp .com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>需要 SIP Access Edge service 外部介面，以供同盟協力廠商（稱為「允許的 SIP 網域」）自動探索，但在先前版本) 中稱為「增強型同盟」 (。 針對具有啟用 Lync 功能之使用者的所有 SIP 網域和使用推播通知服務或 Apple Push Notification 服務的 Microsoft Lync 行動用戶端，重複此步驟。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>合併 Edge 內部介面</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

