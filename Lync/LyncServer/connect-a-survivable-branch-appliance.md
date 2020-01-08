---
title: 連線 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>連線 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

每個 Survivable 分支裝置（SBA）都與一個前端池相關聯，可充當 SBA 的備份註冊機構。 當您將前端池遷移至 Lync Server 2013 時，在升級池時，必須從 Lync Server 2010 前端池解除 SBA，而將池遷移至 Lync Server 2013 之後，SBA 就可以與升級的前端池重新關聯。 這涉及從拓撲產生器中的舊版 Lync Server 2010 拓朴刪除 SBA，然後將 SBA 新增至 Lync Server 2013 拓撲。 必須先將駐留在舊版 Lync Server 2010 SBA 的使用者移到另一個前端池，才能從拓撲結構中移除 SBA。 將 SBA 新增至 Lync Server 2013 拓撲之後，這些使用者就可以移回 SBA。 下列步驟摘要如下所示：

1.  將駐留在舊版 SBA Lync Server 2010 的分支使用者移至另一個前端池。

2.  從舊版 Lync Server 2010 拓撲中移除 SBA，以將現有的前端池與備份註冊機構斷開連線。

3.  在 Lync Server 2013 拓撲中新增 SBA，並將這個新的 [前端] 池設定為備份註冊機構。

4.  將分支使用者移至新的 Lync Server 2013 SBA。

**將 Lync Server 2010 SBA 分支網站新增至您的拓撲**

1.  開啟**拓撲**建立器。

2.  在左窗格中，以滑鼠右鍵按一下 [**分支網站**]，然後按一下 [**新增分支網站**]。

3.  在 [**定義新分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入分支網站的名稱。

4.  可選按一下 [**描述**]，然後為分支網站輸入有意義的描述。

5.  按一下 **[下一步]**。

6.  可選在 [下一步**定義分支網站**] 對話方塊中，執行下列任何一項操作：
    
    1.  按一下 [**城市**]，然後輸入分支網站所在城市的名稱。
    
    2.  按一下 [**狀態/地區**]，然後輸入分支網站所在的狀態或地區名稱。
    
    3.  按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數電話號碼。

7.  按一下 **[下一步]**，然後執行下列其中一項操作：
    
    1.  如果您是在此網站使用 Lync 2010 Survivable 分支裝置或伺服器，請務必取消選取 [**當此嚮導關閉時，開啟新的 Survivable 嚮導]** 選項。 按一下 **[完成]**。

8.  若要將舊版 Lync Server 2010 SBA 與 Lync Server 2013 前端池建立關聯：
    
    1.  展開已建立的分支網站。
    
    2.  以滑鼠右鍵按一下 [ **Lync Server 2010** ]，然後按一下 [**新增**]。
    
    3.  按一下 [ **Survivable 分支裝置]。**

9.  依照嚮導中開啟的指示進行。 如需有關嚮導專案的資訊，請參閱[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2010 Survivable 分支裝置只能與 Lync Server 2010 監視存放區建立關聯。

    
    </div>

10. 如果您不是在此網站使用 Survivable 分支裝置或伺服器，請清除 [在**關閉此嚮導時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成**]。

11. 針對您要新增到拓撲結構中的每個分支網站，重複上述步驟。

</div>

<span> </span>

</div>

</div>

</div>

