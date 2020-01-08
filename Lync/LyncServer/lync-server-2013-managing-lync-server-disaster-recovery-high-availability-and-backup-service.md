---
title: 管理 Lync Server 災害復原、高可用性及備份服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>管理 Lync Server 2013 災害復原、高可用性及備份服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-12_

本節包含災害復原作業的程式，以及維護備份服務以同步處理成對的前端池中的資料。

容錯移轉和回切的災害復原程式都是手動的。 如果發生災難，系統管理員必須手動喚醒呼叫容錯移轉程式。 在修復池之後，回切會有同樣的作用。

本節其餘部分中的災難復原程式是假設下列事項：

  - 您的部署具有成對的前端池（位於不同的網站中），如在[Lync Server 2013 規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原中所述。 備份服務已在這些成對的池中執行，以讓它們保持同步處理。

  - 如果中央管理儲存體是裝載在任何一個 pool，則會在兩個配對的池子上安裝並執行，而其中一個池則是裝載作用中主機，另一個裝載備用的池。

<div>


> [!IMPORTANT]
> 在下列程式中， <EM>PoolFQDN</EM>參數會參照受災難影響之池的 FQDN，而不是重新導向受影響的使用者的池。 針對同一組受影響的使用者，它會參照容錯移轉與回切的 Cmdlet 中的同一個池（也就是在容錯移轉前先駐留使用者的池）。<BR>例如，假設駐留在 pool P1 上的所有使用者都已容錯移轉到備份池（P2）。 如果系統管理員想要將所有目前由 P2 提供服務的使用者移至 P1，系統管理員必須執行下列步驟： 
> <OL>
> <LI>
> <P>使用容錯回復 Cmdlet，將原來駐留在 P1 上的所有使用者，從 P2 切換回 P1。 在此情況下， <EM>PoolFQDN</EM>是 P1's FQDN。</P>
> <LI>
> <P>使用容錯移轉 Cmdlet，將原來駐留在 P2 上的所有使用者容錯移轉到 P1。 在此情況下， <EM>PoolFQDN</EM>是 P2's FQDN。</P>
> <LI>
> <P>如果系統管理員稍後想要將這些 P2 使用者傳回切回 P2， <EM>PoolFQDN</EM>是 P2's FQDN。</P></LI></OL>請注意，上述步驟1必須在步驟2之前執行，才能保留池完整性。 如果您先嘗試步驟2，再執行步驟1，則步驟 2 Cmdlet 將會失敗。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中設定和監控備份服務](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [在 Lync Server 2013 中容錯移轉集區](lync-server-2013-failing-over-a-pool.md)

  - [在 Lync Server 2013 中容錯回復集區](lync-server-2013-failing-back-a-pool.md)

  - [在 Lync Server 2013 中容錯移轉鏡像資料庫](lync-server-2013-failing-over-a-mirrored-database.md)

  - [在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [在 Lync Server 2013 中容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [在 Lync Server 2013 中變更與前端集區相關聯的 Edge 集區](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [在 Lync Server 2013 中使用備份服務還原會議內容](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

