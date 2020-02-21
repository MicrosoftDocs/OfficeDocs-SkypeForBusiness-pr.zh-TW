---
title: Lync Server 2013： 設定邊際伺服器的網路介面
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
ms.openlocfilehash: 267db7062c19a0b1344d11f27205a51bf1e750ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>設定 Lync Server 2013 中的 Edge server 的網路介面

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

在每部 Edge Server 是多重主機電腦與外部及內部對外的介面。 介面卡的網域名稱系統 (DNS) 設定值取決於是否在周邊網路中有 DNS 伺服器。 如果周邊網路中 DNS 伺服器，則必須區域，其中包含一或多個 DNS A 記錄下, 一個躍點伺服器或集區 （也就是 Director 或指定的前端集區），且外部查詢其參照至其他公用 DNS 伺服器的名稱查閱。 如果沒有 DNS 伺服器周邊網路中，Edge server 使用的外部 DNS 伺服器來解析網際網路名稱查閱，並在每部 Edge Server 使用主機來解析成 IP 位址的下一個躍點伺服器名稱。

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" />安全性附註：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>基於安全性考量，建議您不需要 Edge Server 存取位於內部網路的 DNS 伺服器。</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>若要設定的介面與周邊網路中的 DNS 伺服器

1.  每個 Edge Server，一個用於向內介面，另一個用於向外介面安裝兩個網路介面卡。
    
    <div>
    

    > [!IMPORTANT]  
    > 內部和外部子網路必須不是路由傳送給對方。

    
    </div>

2.  在外部介面，設定 [外部周邊網路 （也稱為 DMZ、 非軍事區和遮蔽式子網路） 上的三個靜態 IP 位址子網路及外部防火牆的點至內部介面的預設閘道。 設定介面卡的 DNS 設定以指向周邊 DNS 伺服器的一組。
    
    <div>
    

    > [!NOTE]  
    > 就此介面中，使用最少一個 IP 位址，不過，若要這麼做您需要變更連接埠指派為非標準的值。 在拓撲產生器建立拓撲時，判斷這。

    
    </div>

3.  在內部介面，設定一個靜態 IP 位址內部周邊網路子網路上並沒有設定預設閘道。 設定介面卡的 DNS 設定以指向至少一部 DNS 伺服器，最好是一組的周邊 DNS 伺服器。

4.  在用戶端、 Lync Server 2013 和 Exchange 整合通訊 (UM) 伺服器所在的內部介面所有內部網路上建立持續性靜態路由。

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>若要設定周邊網路中沒有 DNS 伺服器的介面

1.  每個 Edge Server，一個用於向內介面，另一個用於向外介面安裝兩個網路介面卡。
    
    <div>
    

    > [!IMPORTANT]  
    > 內部和外部子網路必須不是路由傳送給對方。

    
    </div>

2.  在外部介面，設定外部周邊網路子網路上的三個靜態 IP 位址。 您也可以設定預設閘道上的外部介面。 例如，定義為網際網路對向路由器或外部防火牆作為預設閘道。 設定 DNS 以指向 DNS 伺服器上，preferably to 一組的外部 DNS 伺服器。
    
    <div>
    

    > [!NOTE]  
    > 它是可行的但不是建議使用，以使用最少一個 IP 位址的外部介面。 若要允許此功能才能運作，您需要變更連接埠指派，為非標準的值，及開通常是 「 易記 」 的防火牆用戶端通訊的預設連接埠 443。 當您在拓撲產生器建立拓撲時決定的 IP 位址設定及連接埠設定。

    
    </div>

3.  在內部介面，設定一個靜態 IP 位址內部周邊網路子網路上並沒有設定預設閘道。 配接器 DNS 設定保留空白。

4.  在 Lync 用戶端或執行 Lync Server 2013 的伺服器所在的內部介面到所有的內部網路上建立持續性靜態路由。

5.  編輯主機上的檔案包含的下一個躍點伺服器的記錄每部 Edge Server 或虛擬 IP (VIP) （Director、 Standard Edition server 或前端集區已設定為在拓撲產生器中的 Edge Server 下一個躍點地址，可能會記錄）。 如果您使用 DNS 負載平衡，包括行的下一個躍點集區的每個成員。

</div>

</div>

<span> </span>

</div>

</div>

</div>

