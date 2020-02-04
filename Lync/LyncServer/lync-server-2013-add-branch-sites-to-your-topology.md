---
title: Lync Server 2013：新增分支網站至拓撲
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
ms.openlocfilehash: 2df1871956b33b3781128e2b62af13bdd875d10b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>在 Lync Server 2013 中新增分支網站至拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

分支網站代表通過 WAN 連結連線到主要辦公室的物理分支辦公室。 若要將分支網站新增至您的 Lync 拓撲，請在中央網站執行此程式。

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>在拓撲中新增分支網站

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在主控台樹中，展開中央網站，以滑鼠右鍵按一下 [**分支網站**]，然後按一下 [**新增分支網站**]。

3.  在 [**定義新分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入分支網站的名稱。

4.  可選按一下 [**描述**]，然後為分支網站輸入有意義的描述。

5.  按一下 **[下一步]**。

6.  可選在 [下一步**定義分支網站**] 對話方塊中，執行下列任何一項操作：
    
      - 按一下 [**城市**]，然後輸入分支網站所在城市的名稱。
    
      - 按一下 [**狀態/地區**]，然後輸入分支網站所在的狀態或地區名稱。
    
      - 按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數電話號碼。

7.  按一下 **[下一步]**，然後執行下列其中一項操作：
    
      - 如果您是在此網站使用 Survivable 分支裝置或伺服器，請確定已選取 [在**關閉此嚮導時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成**]，然後依照嚮導中開啟的指示進行。 如需有關嚮導專案的資訊，請參閱[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
      - 如果您不是在此網站使用 Survivable 分支裝置或伺服器，請清除 [在**關閉此嚮導時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成**]。

8.  針對您要新增到拓撲結構中的每個分支網站，重複上述步驟。

**後續步驟：**

針對 Survivable 分支裝置或伺服器：[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

針對非復原 PSTN 連線：針對[lync server 2013 中的分支網站定義 PSTN 閘道](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)，請[在 lync server 2013 中使用 [媒體旁路] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)，或在[lync server 2013 中設定不含媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

