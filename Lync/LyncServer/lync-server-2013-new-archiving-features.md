---
title: Lync Server 2013： 新的封存功能
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
ms.openlocfilehash: 89a8969924acdf8268f059ae3b3660b70ca1dca7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Lync Server 2013 中的新封存功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

封存的 Lync Server 2013 可以封存下列類型的內容：

  - 對等立即訊息

  - 多方立即訊息的會議 （會議）

  - 會議內容，包括上傳的內容 (例如，講義) 和事件相關內容 (例如，加入、離開、上傳共用，以及可見度變更)

此外，封存 Lync Server 2013 中的提供改善部署和作業效率的新功能。 這些新功能所組成：

  - **組合的封存在前端伺服器上。**   Lync Server 2013 沒有個別封存伺服器角色。 封存是選擇性功能可在所有前端伺服器在 Enterprise Edition 部署中，以及在 Standard Edition 伺服器，可實作針對集區或網站上使用。

  - **Microsoft Exchange 整合。**   當您部署封存，您可以在整合針對與您現有的 Exchange 2013 儲存區位於 Exchange 2013 的所有使用者的封存資料存放區，他們的信箱放在原有範圍暫止時，因此您不需要部署個別的 SQL Server 資料庫，要封存 Lync 資料。 如果您沒有 Exchange 2013 部署中，如果您不想整合，或如果您有任何 Lync 2013 的使用者不位於 Exchange 2013 與他們放入原有範圍暫止的信箱，您可以使用 SQL Server 來儲存部署個別封存資料庫e 封存資料從 Lync 通訊。 如果您想要使用 Microsoft Exchange 整合的部署中的部分，但並非所有使用者，您可以使用 Microsoft Exchange 整合和 Lync Server 2013 封存資料庫。 如需原有範圍暫止的詳細資訊，請參閱 「 就地保留 」，在[https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500)。

  - **SQL 存放區鏡像。**   當您部署封存時，您可以啟用為封存資料庫的 SQL Server 資料庫鏡像。

  - **白板與投票的封存。**   封存會議內容現在包括白板與投票，在會議期間共用。

不會封存下列類型的內容：

  - 對等檔案傳輸

  - 對等立即訊息和會議的音訊/視訊

  - 應用程式共用的端對端即時訊息與會議

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中的封存](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

