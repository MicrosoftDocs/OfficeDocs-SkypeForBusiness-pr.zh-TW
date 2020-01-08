---
title: Lync Server 2013：新封存功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Lync Server 2013 中的新封存功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Lync Server 2013 中的封存功能可以封存下列類型的內容：

  - 對等立即訊息

  - 多方立即訊息的會議（會議）

  - 會議內容，包括上傳的內容（例如講義）及事件相關內容（例如加入、離開、上傳共用，以及在可見度中變更）

此外，Lync Server 2013 中的封存功能提供可改善部署和操作效率的新功能。 這些新功能包括：

  - **在前端伺服器上封存的 Collocation。**   Lync Server 2013 沒有個別的存檔伺服器角色。 [封存] 是在企業版部署中的所有前端伺服器以及在標準版伺服器上提供的選擇性功能，可針對文件庫或網站進行設定。

  - **Microsoft Exchange 整合。**   當您部署封存時，您可以將資料儲存在您現有的 exchange 2013 儲存空間中，針對所有託管于 Exchange 2013 的使用者進行歸檔，並將其信箱放在就地保留中，因此您不需要部署個別的 SQL Server 資料庫來封存 Lync 資料。 如果您沒有 Exchange 2013 部署，或是您不想要整合 Exchange 部署，或者如果您有任何不是託管于 Exchange 2013 的 Lync 2013 使用者，且其信箱放在就地保留中，您可以使用 SQL Server 來部署個別的存檔資料庫來 store 已歸檔來自 Lync 通訊的資料。 如果您想要針對部署中的部分但不是所有使用者使用 Microsoft Exchange 整合，您可以使用 Microsoft Exchange 整合和 Lync Server 2013 存檔資料庫。 如需就地保留的詳細資訊，請參閱 [就地保留] [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)。

  - **[SQL Store 鏡像]。**   當您部署封存時，您可以針對封存資料庫啟用 SQL Server 資料庫鏡像。

  - **[白板] 和 [投票] 的存檔。**   已歸檔的會議內容現在包含在會議期間共用的白板和投票。

下列內容類型沒有封存：

  - 對等檔案傳輸

  - 對等立即訊息與會議的音訊/視頻

  - 對等立即訊息和會議的應用程式共用

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃封存](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

