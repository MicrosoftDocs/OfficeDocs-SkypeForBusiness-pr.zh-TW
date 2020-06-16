---
title: 連線 Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fcba962129353ddeb5e5f4c77520cf6d127733
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>連線 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

每個 Survivable Branch 裝置（SBA）都與一個前端集區相關聯，此集區充當 SBA 的備份註冊機。 當前端集區遷移至 Lync Server 2013 時，當集區遷移至 Lync Server 2013 時，SBA 必須解除與 Lync Server 2010 前端集區的關聯，且在將集區遷移至 Lync Server 後，便可與升級的前端集區重新建立關聯。 這包括在拓撲產生器中從舊版 Lync Server 2010 拓撲刪除 SBA，然後將 SBA 新增至 Lync Server 2013 拓撲。 位於舊版 Lync Server 2010 SBA 的使用者必須先移至另一個前端集區，然後才能從拓撲中移除 SBA。 將 SBA 新增至 Lync Server 2013 拓撲之後，就可以將這些使用者移回 SBA。 這些步驟的摘要如下：

1.  將駐留在舊版 SBA Lync Server 2010 的分支使用者移至另一個前端集區。

2.  從舊版 Lync Server 2010 拓撲移除 SBA，以中斷現有前端集區的備份註冊機的連線。

3.  將 SBA 新增至 Lync Server 2013 拓撲，並將這個新的前端集區設定為備份註冊機。

4.  將分支使用者移至新的 Lync Server 2013 SBA。

**將 Lync Server 2010 SBA 分支網站新增至您的拓撲**

1.  開啟**拓撲**產生器。

2.  在左窗格中，以滑鼠右鍵按一下 [**分支網站**]，然後按一下 [**新增分支網站**]。

3.  在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入分支網站的名稱。

4.  選按一下 [**描述**]，然後為分支網站輸入有意義的描述。

5.  按 [下一步]****。

6.  選在下一個 [**定義新的分支網站**] 對話方塊中，執行下列任一項：
    
    1.  按一下 [**城市**]，然後輸入分支網站所在位置的城市名稱。
    
    2.  按一下 [**省/地區**]，然後輸入分支網站所在位置的省或地區名稱。
    
    3.  按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數呼叫碼。

7.  按 **[下一步]**，然後執行下列其中一項動作：
    
    1.  如果您在此網站使用 Lync 2010 Survivable 分支裝置或伺服器，請務必取消選取 [**當此嚮導關閉時開啟新的 Survivable 嚮導]** 選項。 按一下 [完成]****。

8.  若要將舊版 Lync Server 2010 SBA 關聯至 Lync Server 2013 前端集區：
    
    1.  展開已經建立的分支網站。
    
    2.  以滑鼠右鍵按一下 [ **Lync Server 2010** ]，然後按一下 [**新增**]。
    
    3.  按一下 [ **Survivable 分支裝置 ...]。**

9.  依照嚮導中開啟的指示進行。 如需有關 [嚮導專案] 的詳細資訊，請參閱[在 Lync Server 2013 中定義 Survivable Branch 裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2010 Survivable Branch 裝置只能與 Lync Server 2010 Monitoring Store 相關聯。

    
    </div>

10. 如果您未使用此網站的 Survivable 分支裝置或伺服器，請清除 [在**此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成]**。

11. 針對您要新增至拓撲的每一個分支網站重複上述步驟。

</div>

<span> </span>

</div>

</div>

</div>

