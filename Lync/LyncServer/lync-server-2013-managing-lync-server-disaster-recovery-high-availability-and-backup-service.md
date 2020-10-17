---
title: 管理 Lync Server 災難修復、高可用性及備份服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c935a27f737d8ec7fdb012f4e0c13930d20a1319
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498150"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>管理 Lync Server 2013 災難修復、高可用性及備份服務

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-12_

本節包含嚴重損壞復原作業的程式，以及維護備份服務，以同步處理成對前端集區中的資料。

容錯移轉和回切回的嚴重損壞修復程式都是手動。 如果發生災難，系統管理員必須手動呼叫容錯移轉程式。 修復集區之後，回復器也同樣適用。

本節其餘部分的嚴重損壞修復程式會假設下列各項：

  - 您的部署具有成對的前端集區，位於不同的網站，如在 [Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。 備份服務已在這些配對集區上執行，使其保持同步。

  - 如果中央管理存放區裝載于任何集區上，則會在兩個配對集區上安裝並執行，其中一個集區會裝載作用中的主集區，而另一個集區會主控備用的集區。

<div>


> [!IMPORTANT]
> 在下列程式中， <EM>PoolFQDN</EM> 參數會參照受災難影響的集區的 FQDN，而不會重新導向受影響使用者的集區。 針對相同組受影響的使用者，它會在容錯移轉和回切 (Cmdlet 中同時參考相同的集區，也就是在容錯移轉) 之前第一位使用者的集區。<BR>例如，假設某個案例位於集區 P1 的所有使用者都已容錯移轉至備份組區 P2。 如果系統管理員想要移動所有目前由 P2 服務服務的使用者，以 P1 為服務，系統管理員必須執行下列步驟： 
> <OL>
> <LI>
> <P>使用回復指令 Cmdlet，將原來在 P1 上的所有使用者都從 P2 重新容錯回復至 P1。 在此情況下， <EM>PoolFQDN</EM> 為 P1's FQDN。</P>
> <LI>
> <P>使用容錯移轉指令，將所有原先位於 P2 的使用者容錯移轉至 P1。 在此情況下， <EM>PoolFQDN</EM> 為 P2's FQDN。</P>
> <LI>
> <P>如果系統管理員稍後想要將這些 P2 使用者容錯回復回 P2，則 <EM>PoolFQDN</EM> 為 P2's FQDN。</P></LI></OL>請注意，必須先執行上述步驟1，再執行步驟2以保留集區完整性。 如果您在步驟1之前嘗試步驟2，則步驟 2 Cmdlet 會失敗。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中設定及監視備份服務](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [在 Lync Server 2013 中容錯移轉集區](lync-server-2013-failing-over-a-pool.md)

  - [在 Lync Server 2013 中回復集區失敗](lync-server-2013-failing-back-a-pool.md)

  - [在 Lync Server 2013 中容錯移轉鏡像資料庫](lync-server-2013-failing-over-a-mirrored-database.md)

  - [在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [在 Lync Server 2013 中回復用於 Lync Server 同盟或 XMPP 同盟的 Edge 集區](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [在 Lync Server 2013 中變更與前端集區相關聯的 Edge 集區](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [在 Lync Server 2013 中使用備份服務還原會議內容](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

