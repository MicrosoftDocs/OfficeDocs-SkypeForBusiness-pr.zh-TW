---
title: 移除封存伺服器關聯
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c53ef1e70b174681149593237db3f9d0268209
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a>移除封存伺服器關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

若要移除封存伺服器，您需要變更或清除 [關聯前端集區，前端伺服器、 Survivable Branch Appliance 和 Survivable Branch 伺服器上的相依性。 您編輯的內容的前端集區前端伺服器、 Survivable Branch Appliance 和 Survivable Branch 伺服器移除相依性。 清除 [相依性，並刪除拓撲產生器中的伺服器之後，您會收到通知也會刪除在拓撲產生器的相關聯的資料庫存放區物件。

<div>

## <a name="to-remove-the-archiving-server-association"></a>移除封存伺服器關聯

1.  開啟 Lync Server 2013 前端伺服器]，再開啟拓撲產生器]。

2.  瀏覽至 [Lync Server 2010] 節點。

3.  在拓撲產生器中，展開 [ **Enterprise Edition 前端集區**、 **Standard Edition 前端伺服器**或**分支站台**，根據定義封存伺服器的位置。

4.  如果您有相關聯的 Survivable Branch 伺服器，依序展開 [**分支站台**，依序展開 [分支網站名稱，然後展開 [ **Survivable Branch Appliance**。
    
    <div>
    

    > [!NOTE]  
    > 在使用者介面中的<STRONG>Survivable Branch Appliances</STRONG>會套用至 Survivable Branch 伺服器和 Survivable Branch Appliance。

    
    </div>

5.  以滑鼠右鍵按一下集區、 伺服器或封存伺服器，與相關聯的裝置，然後按一下 [**編輯內容]**。

6.  在 [編輯屬性]**** 的 [一般]**** 底下，清除 [關聯]**** 底下的 [建立封存伺服器的關聯]**** 核取方塊，然後按一下 [確定]****。

7.  任何其他集區、 伺服器或您想要移除封存伺服器相關聯的裝置，重複上述步驟。

8.  封存伺服器，以滑鼠右鍵按一下，然後按一下 [**刪除**。

9.  在 [刪除相依存放區]**** 上，按一下 [確定]****。

10. 發行拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署精靈。

</div>

</div>

<span> </span>

</div>

</div>

</div>

