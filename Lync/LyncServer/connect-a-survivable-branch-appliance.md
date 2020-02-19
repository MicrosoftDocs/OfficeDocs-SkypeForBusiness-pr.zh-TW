---
title: 連接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8840bb7c9beec8170b26783a180d9f8bf1347e22
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>連接 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

每個 Survivable Branch Appliance (SBA) 是做為備份登錄器 SBA 的前端集區相關聯。 當升級之集區時，一旦集區已移轉至 Lync Server 2013 時，必須分離前端集區移轉至 Lync Server 2013，SBA 從 Lync Server 2010 前端集區時，SBA 可以重新相關聯的已升級的前端集區。 這包括刪除 SBA 從拓撲產生器的舊版 Lync Server 2010 拓撲並再將 SBA 新增至 Lync Server 2013 拓撲。 隸屬於舊版 Lync Server 2010 SBA 必須先將移至另一個前端集區從拓撲移除 SBA 之前的使用者。 一旦 SBA 新增至 Lync Server 2013 拓撲後，這些使用者可以再移回 sba。 這些步驟的摘要如下：

1.  將分支使用者隸屬於舊版 SBA Lync Server 2010 至另一個前端集區。

2.  若要中斷作為備份登錄器的現有前端集區的舊版 Lync Server 2010 拓撲移除 SBA。

3.  將 SBA 新增至 Lync Server 2013 拓撲，並將此新前端集區設定為備份登錄器。

4.  將分支使用者移至新的 Lync Server 2013 SBA。

**將 Lync Server 2010 SBA 分支網站新增至您的拓撲**

1.  開啟**拓撲產生器]**。

2.  在左窗格中以滑鼠右鍵按一下 [**分支站台**，，，然後按一下 [**新的分支網站**。

3.  在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**] 中，，然後輸入分支網站的名稱。

4.  （選用）按一下 [**描述**] 中，，，然後輸入分支網站的有意義描述。

5.  按 [下一步]****。

6.  （選用）在下的 [**定義新的分支網站**] 對話方塊中，執行下列其中一項：
    
    1.  按一下 [**縣/市**、，然後輸入分支網站所在位置的城市名稱。
    
    2.  按一下 [省/地區****，然後輸入位置的省或地區的分支網站所在的名稱。
    
    3.  按一下 [**國碼/地區碼**，，，然後輸入分支網站所在國家/地區的兩位數呼叫程式碼。

7.  按一下 [**下一步**，，然後執行下列其中一項：
    
    1.  如果您在此網站使用的 Lync 2010 Survivable Branch Appliance 或 Server，請務必取消選取 [**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**的選項。 按一下 [完成]****。

8.  若要建立舊版 Lync Server 2010 SBA 與 Lync Server 2013 前端集區的關聯：
    
    1.  展開已建立的分支網站。
    
    2.  以滑鼠右鍵按一下 [ **Lync Server 2010** ]，然後按一下 [**新增]**。
    
    3.  按一下 [ **Survivable Branch Appliance...**

9.  依照精靈隨即開啟。 精靈項目的相關資訊，請參閱[定義 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2010 Survivable Branch Appliance 僅可與 Lync Server 2010 監控儲存區相關聯。

    
    </div>

10. 如果您未在此網站使用 Survivable Branch Appliance 或 Server，清除**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊，然後再按一下 [**完成]**。

11. 針對您想要新增至拓撲每一個分支網站重複上述步驟。

</div>

<span> </span>

</div>

</div>

</div>

