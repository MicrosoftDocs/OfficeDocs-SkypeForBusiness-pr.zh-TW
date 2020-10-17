---
title: Lync Server 2013：檔案共用高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f58cd52da92e767357e7a0bee7f3584552c9868
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531980"
---
# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Lync Server 2013 中的檔共用高可用性

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-03-30_

為了確保單一資料中心內的 Lync Server 檔案共用的高可用性，您可以使用分散式檔案系統 (DFS) 。 DFS 支援在相同的資料中心內，從一個檔案伺服器到另一個檔案伺服器的容錯移轉。 在大規模部署中，建議您使用使用 DFS 成對的專用檔案伺服器。

根據您的網路規模和您想要的復原數量，您可以使用一組伺服器來裝載網站中的所有檔案共用，或在前端集區中使用一對。

DFS 是一種最佳的檔複寫方式，沒有發佈的復原時間目標 (RTO) 或復原點目標 (RPO) 承諾。 DFS 伺服器之間的容錯移轉應該會很快完成，但是資料複寫延遲可能會讓使用者無法繼續進行容錯移轉時進行中的工作。

如果您在檔共用上使用 DFS 和資料儲存區是很重要的，您應該經常備份檔案共用，例如每4到8個小時。 當一個檔案共用停機且複寫不是最新時，您可以使用備份將失敗伺服器上的內容還原至與目前無法使用之伺服器配對的另一部伺服器。

</div>

<span> </span>

</div>

</div>

</div>

