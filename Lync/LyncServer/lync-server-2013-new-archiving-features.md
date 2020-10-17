---
title: Lync Server 2013：新的封存功能
description: Lync Server 2013：新的封存功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b69c90e62914284f178ae328375c6e350f5b3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561349"
---
# <a name="new-archiving-features-in-lync-server-2013"></a>Lync Server 2013 中的新封存功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Lync Server 2013 中的封存可封存下列類型的內容：

  - 對等立即訊息

  - 會議 (參加多方立即訊息) 

  - 會議內容，包括上傳的內容 (例如，講義) 和事件相關內容 (例如，加入、離開、上傳共用，以及可見度變更)

此外，Lync Server 2013 中的封存功能提供了可提升部署和作業效率的新功能。 這些新功能包括：

  - **前端伺服器上封存的組合。**    Lync Server 2013 沒有個別的封存伺服器角色。 封存是可在企業版部署的所有前端伺服器上，以及 Standard Edition server 上的所有前端伺服器上可用的選用功能，可針對集區或網站執行設定。

  - **Microsoft Exchange 整合。**    當您部署封存時，您可以將資料儲存區與現有的 Exchange 2013 儲存區整合，以用於所有位於 Exchange 2013 的使用者，並將其信箱置於 In-Place 保留狀態，所以您不需要部署個別的 SQL Server 資料庫來封存 Lync 資料。 如果您沒有 Exchange 2013 部署，或您不想要將其與其整合，或者如果您有任何 Lync 2013 使用者未裝載在 Exchange 2013 上，且其信箱置於 In-Place 保留狀態，您可以使用 SQL Server 來儲存不同的封存資料庫，使其具有 Lync 通訊的封存資料。 如果您想要對部分但不是部署中的所有使用者使用 Microsoft Exchange 整合，您可以使用 Microsoft Exchange 整合和 Lync Server 2013 封存資料庫。 如需 In-Place 保留的詳細資訊，請參閱的「In-Place 保留」 [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) 。

  - **SQL 存放區鏡像。**    當您部署封存時，您可以啟用封存資料庫的 SQL Server 資料庫鏡像。

  - **白板和投票的封存。**    封存的會議內容現在包含在會議期間共用的白板和投票。

不會封存下列類型的內容：

  - 對等檔案傳輸

  - 對等立即訊息和會議的音訊/視訊

  - 對等立即訊息與會議的應用程式共用

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃封存](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

