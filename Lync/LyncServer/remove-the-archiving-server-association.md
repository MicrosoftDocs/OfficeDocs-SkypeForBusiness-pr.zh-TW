---
title: 移除封存伺服器關聯
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87578bad234adfad254b45961b07180176f9b027
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a>移除封存伺服器關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

若要移除封存伺服器，您必須變更或清除關聯的前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器上的相依性。 您可以編輯前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器的屬性，以移除相依性。 清除相依性並在拓撲產生器中刪除伺服器後，系統會通知您也會刪除拓撲產生器中相關聯的資料庫存放區物件。

<div>

## <a name="to-remove-the-archiving-server-association"></a>移除封存伺服器關聯

1.  開啟 Lync Server 2013 前端伺服器，開啟拓撲產生器。

2.  流覽至 [Lync Server 2010] 節點。

3.  在 [拓撲產生器] 中，根據封存伺服器定義的位置，展開 [ **Enterprise Edition 前端**集區]、[ **Standard Edition 前端伺服器**] 或 [**分支網站**]。

4.  如果您有相關聯的 Survivable 分支伺服器，請展開 [**分支網站**]，展開分支網站名稱，然後展開 [ **Survivable 分支裝置**]。
    
    <div>
    

    > [!NOTE]  
    > 使用者介面中的<STRONG>Survivable 分支裝置</STRONG>會同時套用至 Survivable branch Server 和 Survivable branch 裝置。

    
    </div>

5.  以滑鼠右鍵按一下與封存伺服器關聯的集區、伺服器或裝置，然後按一下 [**編輯屬性**]。

6.  在 [編輯屬性]**** 的 [一般]**** 底下，清除 [關聯]**** 底下的 [建立封存伺服器的關聯]**** 核取方塊，然後按一下 [確定]****。

7.  針對與您要移除之封存伺服器相關聯的任何其他集區、伺服器或裝置，重複上述步驟。

8.  以滑鼠右鍵按一下封存伺服器，然後按一下 [**刪除**]。

9.  在 [刪除相依存放區]**** 上，按一下 [確定]****。

10. 發佈拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署嚮導。

</div>

</div>

<span> </span>

</div>

</div>

</div>

