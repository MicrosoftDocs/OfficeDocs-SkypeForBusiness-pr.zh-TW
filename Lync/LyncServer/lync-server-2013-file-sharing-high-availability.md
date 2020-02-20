---
title: Lync Server 2013： 檔案共用高可用性
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
ms.openlocfilehash: bf27a7316494d24127f65309bdef347b558fade5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>檔案共用 Lync Server 2013 中的高可用性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-03-30_

若要確保高可用性的 Lync Server 檔案共用單一資料中心內，您可以使用分散式檔案系統 (DFS)。 DFS 支援從一個檔案伺服器容錯移轉至另一個相同的資料中心內。 針對大型部署，建議您使用的成對使用 DFS 專用的檔案伺服器。

根據您的網路大小與想要的恢復量，您可以使用一對伺服器來裝載站台中的所有檔案共用，或使用一對每個前端集區。

DFS 是最佳投入比檔案複寫機制，任何已發佈的復原時間目標 (RTO) 或復原點目標 (RPO) 承諾。 快速，應該完成 DFS 伺服器之間容錯移轉，但資料複寫延遲可能阻止使用者能夠繼續進行中的工作時，若發生容錯移轉。

如果您使用 DFS 和檔案共用上的資料存放區非常重要，您應該先備份的檔案共用常見問題，例如，為每隔 4 到 8 小時。 當一個檔案共用下降並複寫不是最新狀態時，您可以使用備份來還原與伺服器現在無法使用的成對的另一部伺服器失敗的伺服器上的內容。

</div>

<span> </span>

</div>

</div>

</div>

