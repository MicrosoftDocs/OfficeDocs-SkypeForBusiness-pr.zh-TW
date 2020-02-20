---
title: Lync Server 2013： 將分支網站新增至您的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a43d926fcc2883a36a577fd297567da0295a0f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>將分支網站新增至您在 Lync Server 2013 中的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-05_

分支站台代表實體的分公司，透過 WAN 連結連線至您主要的辦公室。 若要將分支網站新增至您的 Lync 拓樸，執行此程序在中央網站。

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>若要將分支網站新增至您的拓撲

1.  按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在主控台樹狀目錄中，展開中央網站，以滑鼠右鍵按一下 [**分支網站**]，然後按一下**新的分支網站**。

3.  在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**] 中，，然後輸入分支網站的名稱。

4.  （選用）按一下 [**描述**] 中，，，然後輸入分支網站的有意義描述。

5.  按 [下一步]****。

6.  （選用）在下的 [**定義新的分支網站**] 對話方塊中，執行下列其中一項：
    
      - 按一下 [**縣/市**、，然後輸入分支網站所在位置的城市名稱。
    
      - 按一下 [省/地區****，然後輸入位置的省或地區的分支網站所在的名稱。
    
      - 按一下 [**國碼/地區碼**，，，然後輸入分支網站所在國家/地區的兩位數呼叫程式碼。

7.  按一下 [**下一步**，，然後執行下列其中一項：
    
      - 如果您在此網站使用 Survivable Branch Appliance 或 Server，請確定已選取 [**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊、 按一下 [**完成**]，然後遵循開啟精靈] 中的指示操作。 精靈項目的相關資訊，請參閱[定義 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
      - 如果您未在此網站使用 Survivable Branch Appliance 或 Server，清除**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊，然後再按一下 [**完成]**。

8.  針對每個您想要新增至拓撲的分支網站重複上述步驟。

**下一個步驟：**

Survivable Branch Appliance 或 Server：[定義 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

不具彈性的 PSTN 連線：[定義 Lync Server 2013 中的分支網站的 PSTN 閘道](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)，[設定主幹，且媒體旁路 Lync Server 2013 中](lync-server-2013-configure-a-trunk-with-media-bypass.md)，或[設定沒有媒體主幹略過在 Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

