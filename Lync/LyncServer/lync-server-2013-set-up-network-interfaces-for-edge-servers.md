---
title: Lync Server 2013：設定 Edge server 的網路介面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7eee448ffd5176797ebfbb0fb43afc4c9e41a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509820"
---
# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Edge server 的網路介面

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

每一部 Edge Server 都是具有外部及內部介面的多主機電腦。 DNS) 設定 (的「配接器網域名稱系統」，取決於周邊網路中是否有 DNS 伺服器。 如果周邊中已存在 DNS 伺服器，則他們必須具有一個區域，其中包含下一個躍點伺服器或集區 (的一個或多個 DNS A 記錄，也就是 Director 或指定的前端集區) ，以及它們參照其他公用 DNS 伺服器名稱查閱的外部查詢。 若周邊中沒有 DNS 伺服器，Edge Server (s) 使用外部 DNS 伺服器來解析網際網路名稱查閱，而每個 Edge Server 會使用主機將下一個躍點伺服器名稱解析為 IP 位址。

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全性附注：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>基於安全性考慮，建議您不要讓 Edge Server 存取位於內部網路中的 DNS 伺服器。</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>在周邊網路中使用 DNS 伺服器設定介面

1.  為每一部 Edge Server 安裝兩個網路介面卡，一個用於內部對向介面，另一個用於外部介面。
    
    <div>
    

    > [!IMPORTANT]  
    > 內部和外部子網不得彼此路由傳送。

    
    </div>

2.  在外部介面上，設定外部周邊網路上的三個靜態 IP 位址 (也稱為 DMZ、隔離區域和遮罩式子網) 子網，然後將預設閘道指向外部防火牆的內部介面。 設定介面卡 DNS 設定，以指向一對周邊 DNS 伺服器。
    
    <div>
    

    > [!NOTE]  
    > 您可以只使用此介面的一個 IP 位址，但若要這麼做，您必須將埠指派變更為非標準值。 您可以在拓撲產生器中建立拓撲時加以判斷。

    
    </div>

3.  在 internal 介面上，在內部周邊網路子網上設定一個靜態 IP 位址，而不要設定預設閘道。 設定介面卡 DNS 設定，使其指向至少一部 DNS 伺服器，最好是一對周邊 DNS 伺服器。

4.  在內部介面上建立持續性靜態路由，以傳送用戶端、Lync Server 2013 和 Exchange 整合通訊 (UM) 伺服器所在的所有內部網路。

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>在周邊網路中設定沒有 DNS 伺服器的介面

1.  為每一部 Edge Server 安裝兩個網路介面卡，一個用於內部對向介面，另一個用於外部介面。
    
    <div>
    

    > [!IMPORTANT]  
    > 內部和外部子網不得彼此路由傳送。

    
    </div>

2.  在外部介面上，設定外部周邊網路子網上的三個靜態 IP 位址。 您也可以在外部介面上設定預設閘道。 例如，將網際網路對向路由器或外部防火牆定義為預設閘道。 設定 DNS 設定以指向 DNS 伺服器，最好是一對外部 DNS 伺服器。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用但不建議使用，只使用外部介面的一個 IP 位址。 若要讓這種方式可以運作，您必須將埠指派變更為非標準值，並從預設埠443（通常為「防火牆友好」）變更為用戶端通訊。 您可以在拓撲產生器中建立拓撲時決定 IP 位址設定及埠設定。

    
    </div>

3.  在 internal 介面上，在內部周邊網路子網上設定一個靜態 IP 位址，而不要設定預設閘道。 將配接器 DNS 設定保留空白。

4.  在內部介面上建立持續性靜態路由，以傳送 Lync 用戶端或執行 Lync Server 2013 之伺服器所在的所有內部網路。

5.  編輯每一部 Edge Server 上的主機檔案，以包含下一個躍點伺服器或虛擬 IP (VIP) 的記錄， (該記錄將是 Director、Standard Edition Server 或前端集區，其設定為拓撲產生器) 中已設定為 Edge Server 下一個躍點位址的前端集區。 如果您使用 DNS 負載平衡，請在下一個躍點集區的每個成員中包含一行。

</div>

</div>

<span> </span>

</div>

</div>

</div>

