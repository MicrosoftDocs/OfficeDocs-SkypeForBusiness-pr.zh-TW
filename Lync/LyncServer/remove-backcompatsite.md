---
title: 移除 BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>移除 BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

在停用所有的池且已卸載所有邊緣伺服器之後，請執行拓撲產生器合併嚮導來移除**BackCompatSite**。

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>從拓撲建立器移除 BackCompat 網站

1.  從 [拓撲建立器] 開啟現有的部署。

2.  在 [**動作**] 功能表中，按一下 [**合併 2007 R2 拓撲結構**]。

3.  請按 [下一步]**** 繼續。

4.  在 [**指定舊版 Edge** ] 頁面上，確定 Edge 伺服器清單是空的。 如果清單不是空白，請使用 [**移除**] 按鈕來移除所有舊版邊緣伺服器，然後按 **[下一步]**。
    
    [![合併拓撲嚮導]，指定 [邊緣設定] 頁面](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "合併拓撲嚮導，指定 [edge 設定] 頁面")  

5.  在 [**指定內部 SIP 埠設定**] 頁面上，按一下 **[下一步]**。

6.  在 [**摘要**] 頁面上，按一下 **[下一步]** 以開始合併拓撲，以移除舊版網站。

7.  在 [**狀態**] 欄中，確認此值為 [**成功**]，然後按一下 **[完成**] 以關閉嚮導。

8.  在 [拓撲建立器] 的左窗格中，展開 [BackCompatSite]，並確認沒有列出任何伺服器。

9.  以滑鼠右鍵按一下**BackCompatSite**，然後按一下 [**刪除**]。

10. 在 [**拓撲**建立器] 中，選取最上方的 [ **Lync Server**]。

11. 從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。

12. **發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。

</div>

</div>

<span> </span>

</div>

</div>

</div>

