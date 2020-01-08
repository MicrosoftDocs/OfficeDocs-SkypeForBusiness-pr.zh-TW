---
title: DNS 摘要 - 調整式合併 Edge (利用硬體負載平衡器)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d411b004edde96314e3c06d7f28a9f9d294688ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (利用硬體負載平衡器)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-27_

對 Lync Server 2013 進行遠端存取的 DNS 記錄需求與憑證和埠的遠端存取是相當直接的。 此外，許多記錄都是選擇性的，視您如何設定執行 Lync 2013 的用戶端以及是否啟用同盟而定。

如需有關 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。

如需有關設定 Lync 2013 用戶端的自動設定的詳細資料，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)（不含分割大腦 dns）一節。

下表包含支援經過調整的合併邊緣拓朴（硬體負載平衡）圖所需的 DNS 記錄摘要。 請注意，只有 Lync 用戶端的自動設定需要特定的 DNS 記錄。 如果您打算使用群組原則物件（Gpo）來設定 Lync 用戶端，則不需要相關聯的記錄。

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>重要： Edge 伺服器網路介面卡需求

若要避免路由問題，請確認 Edge 伺服器中至少有兩個網路介面卡，且 [預設閘道] 只在與外部介面相關聯的網路介面卡上設定。 例如，如在 Lync Server 2013 中以縮放的合併邊緣案例中所示，在[使用硬體負載平衡器調整合並邊緣](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)的情況圖中，預設閘道會指向外部防火牆。

您可以在每個邊緣伺服器中設定兩個網路介面卡，如下所示：

  - **網路介面卡1（內部介面）**
    
    已指派172.25.33.10 的內部介面。
    
    沒有預設閘道。
    
    請確定有來自網路的路由，包含 Edge 伺服器內部介面至任何包含 Lync Server 用戶端或執行 Lync Server 之伺服器的網路（例如從172.25.33.0 到192.168.10.0）。

  - **網路介面卡2（外部介面）**
    
    系統會將三個公用 IP 位址指派給這個網路介面卡，例如 131.107.155.10 [存取邊緣服務]，131.107.155.20 [網路會議 Edge 服務]，131.107.155.30 提供 A/V 邊緣服務。
    
    <div>
    

    > [!NOTE]
    > 指派給 Edge 伺服器實際外部網路介面的 IP 位址，可能會視您選擇的硬體負載平衡器而定。 請參閱硬體負載平衡器的相關檔，瞭解實際的 IP 位址需求。<BR>如果不建議這樣做，您可以針對所有三個邊緣服務介面使用單一 IP 位址。 雖然這會儲存 IP 位址，但是它需要每個服務有不同的埠號碼。 預設埠號碼為 443/TCP，可確保大多數的遠端防火牆都能允許流量。 將埠值變更為（例如） [存取邊緣] 服務的 [5061/TCP]、[網路會議邊緣] 服務的 [444/tcp] 和 [A/V 邊緣] 服務的 443/TCP，可能會導致遠端使用者發生問題，而這些使用者的防火牆不允許使用 5061/TCP 和 444/TCP 的流量。 此外，三個不同的 IP 位址可讓疑難排解變得更容易，因為能夠篩選 IP 位址。

    
    </div>
    
    [存取邊緣服務 IP 位址] 是主要的，預設閘道設定為 [面向網際網路的路由器] （131.107.155.1）。
    
    Web 會議 Edge 服務和 A/V 邊緣服務 IP 位址是副。

<div>


> [!TIP]
> 將 Edge 伺服器設定成兩個網路介面卡是其中一個選項。 另一個選項是將一個網路介面卡用於內部端，而將三個網路介面卡用於邊緣伺服器的外部端。 此選項的主要優點是每 Edge 伺服器服務有一個獨特的網路介面卡，而且在需要疑難排解時也可能更簡明地收集資料



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>已調整的合併邊緣所需的 DNS 記錄，以及硬體負載平衡（範例）

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
<td><p>Access Edge 服務外部介面（Contoso）。 在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>網路會議 Edge 服務外部介面</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
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
<td><p>SIP 存取邊緣服務外部介面需要聯盟夥伴的自動 DNS 探索（稱為「允許 SIP 網域」（在舊版發行中稱為「已允許 SIP 網域」）。 在已啟用 Lync 功能的使用者以及使用推播通知服務或 Apple 推播通知服務的 Microsoft Lync 行動用戶端的情況下，對所有 SIP 網域重複上述步驟。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>整合的邊緣內部介面</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

