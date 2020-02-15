---
title: 移除 BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f613f6e96261d256c4c1f15fd2161648eed4fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>移除 BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

停用所有集區並解除安裝所有 Edge Server 之後，請執行 [拓撲產生器合併精靈] 以移除 BackCompatSite****。

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>從拓撲產生器移除 BackCompat 網站

1.  從拓撲產生器開啟現有的部署。

2.  在 [執行]**** 功能表中，按一下 [合併 2007 R2 拓撲]****。

3.  按 [下一步]**** 繼續。

4.  在 [**指定舊版 Edge** ] 頁面上，確定 Edge server 的清單是空的。 若不是空的，請使用 [移除]**** 按鈕移除所有舊版的 Edge Server，然後按 [下一步]****。
    
    ![合併拓撲精靈] 的 [指定 Edge 安裝] 頁面](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "合併拓撲精靈] 的 [指定 Edge 安裝] 頁面")  

5.  在 [指定內部 SIP 連接埠]**** 設定頁面中按 [下一步]****。

6.  在 [**摘要**] 頁面上，按 [**下一步**以開始合併拓撲，進而移除舊版站台。

7.  在 [狀態]**** 欄中，檢查其值是否為 [成功]****，然後按一下 [完成]****，以關閉精靈。

8.  在拓撲產生器的左窗格中，展開 BackCompatSite 並確定沒有列出任何伺服器。

9.  以滑鼠右鍵按一下 [BackCompatSite]****，然後按一下 [刪除]****。

10. 在 [拓撲產生器]**** 中選取最頂端的節點 [Lync Server]****。

11. 在 **[執行]** 功能表中，選取 **[發行拓撲]**，然後按 **[下一步]**。

12. 當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。

</div>

</div>

<span> </span>

</div>

</div>

</div>

