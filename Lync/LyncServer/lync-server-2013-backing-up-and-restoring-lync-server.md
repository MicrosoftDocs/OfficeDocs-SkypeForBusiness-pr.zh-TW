---
title: Lync Server 2013：備份及還原 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f2f907c8efb663816ca50152643cea70fcc2ff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>備份及還原 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在本節中，您將會發現備份 Lync Server 2013 資料的最佳作法，以及在發生失敗時進行還原。 這些最佳作法適用于下列情況：

  - 完整的 Lync 伺服器集區，任何類型 (前端伺服器、Edge Server、轉送伺服器、Persistent Chat Server 或 Director) ，或是其中一個集區中的個別伺服器。

  - 中央管理伺服器

  - Standard Edition server

  - Enterprise Edition 後端伺服器

  - 檔存放區

  - 封存資料庫、監控資料庫或 Persistent 聊天資料庫

本節不包含還原整個網站或開發待機網站的相關資訊。 如需開發搭配前端集區的嚴重損壞修復解決方案的詳細資訊，請參閱[在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。 這是規劃嚴重損壞修復的建議方法。

如果您已部署成對的前端集區，當其中一個集區失敗且無法復原時，您可以使用其配對的集區中的新完整功能變數名稱 (FQDN) 還原此集區。 如需執行此復原之步驟的詳細資訊，請參閱[在 Lync Server 2013 中容錯移轉集](lync-server-2013-failing-over-a-pool.md)區。 此外，如果您稍後想要重新建立屬於前端對的失敗和不可復原的集區，您可以使用在[Lync Server 2013 中執行 ABC 前端集區容錯移轉](lync-server-2013-performing-an-abc-front-end-pool-failover.md)的步驟。

本文件中所說明的方法涉及規劃階段的特殊考量。 如需詳細資訊，請參閱[建立 Lync Server 2013 的備份與還原方案](lync-server-2013-establishing-a-backup-and-restoration-plan.md)。

<div>

## <a name="in-this-section"></a>本章節內容

  - [準備 Lync Server 2013 備份及還原](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [在 Lync Server 2013 中備份資料和設定](lync-server-2013-backing-up-data-and-settings.md)

  - [在 Lync Server 2013 中還原資料和設定](lync-server-2013-restoring-data-and-settings.md)

  - [Lync Server 2013 的備份及還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

