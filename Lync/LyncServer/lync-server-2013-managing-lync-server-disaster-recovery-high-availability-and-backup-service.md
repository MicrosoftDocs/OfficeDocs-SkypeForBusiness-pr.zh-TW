---
title: 管理 Lync Server 災害復原、 高可用性及備份服務
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
ms.openlocfilehash: 89c18076a2bbc34386872a7fbee92c26b8084598
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>管理 Lync Server 2013 災害復原、 高可用性及備份服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-12_

本節包含災難復原作業，以及維護備份服務 」 的同步處理配對前端集區中的資料的程序。

災害復原程序，容錯移轉和容錯回復，都是手動。 如果沒有損毀，系統管理員必須以手動方式叫用容錯移轉程序。 適用於容錯回復之後修復之集區。

本節的其餘部分中的災害復原程序假設下列情況：

  - 您必須具有配對前端集區，位於不同的站台，作為 > 中所述[的高可用性和災害復原 Lync Server 2013 中的規劃](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)部署。 備份服務已經對它們進行同步化這些配對集區上執行。

  - 如果其中一個集區上裝載的中央管理存放區，它是安裝及執行在這兩個配對集區]，以其中一個這些集區代管作用中的主圖形和其他集區代管待命資料庫。

<div>


> [!IMPORTANT]
> 下列程序， <EM>PoolFQDN</EM>參數是指會受到嚴重損壞的集區的 FQDN，不會影響使用者的集區從重新導向。 如需受影響的使用者同一組，它參照相同的集區容錯移轉和容錯回復 cmdlet （亦即，集區的第一次位於 [容錯移轉之前的使用者） 中。<BR>例如，假設所有使用者都隸屬於 P1 已容錯移轉至備份集區 P2 的集區中的案例。 如果管理員想要移動目前由 P2 到由 P1 服務的所有使用者，系統管理員必須執行下列步驟： 
> <OL>
> <LI>
> <P>Fail 備份所有原先隸屬於 P1 從 P2 到 P1 的使用者使用容錯回復指令程式。 在此情況下，則<EM>PoolFQDN</EM>是 P1 的 FQDN。</P>
> <LI>
> <P>容錯移轉所有原先隸屬於 P2 到 P1 的使用者使用容錯移轉指令程式。 在此情況下，則<EM>PoolFQDN</EM>是 P2 的 FQDN。</P>
> <LI>
> <P>如果系統管理員稍後想要容錯回復那些 P2 使用者容錯回復至 P2，則<EM>PoolFQDN</EM>是 P2 的 FQDN。</P></LI></OL>請注意，上述步驟 1 必須執行步驟 2 來保留集區完整性之前。 如果您嘗試步驟 2 前面步驟 1，步驟 2 指令程式將會失敗。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [設定和監控 Lync Server 2013 中備份服務](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [容錯移轉集區中 Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [容錯回復的 Lync Server 2013 中的集區](lync-server-2013-failing-back-a-pool.md)

  - [容錯移轉鏡像資料庫在 Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [容錯移轉用於 Lync Server 2013 中的 Lync Server 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [容錯移轉用於 Lync Server 2013 中的 XMPP 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [容錯回復用於 Lync Server 同盟或 Lync Server 2013 中的 XMPP 同盟的 Edge 集區](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集區](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [使用 Lync Server 2013 中備份服務還原會議內容](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中的高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

