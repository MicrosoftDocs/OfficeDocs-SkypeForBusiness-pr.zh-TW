---
title: Lync Server 2013：將分支網站新增至您的拓撲
description: Lync Server 2013：將分支網站新增至您的拓撲。
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
ms.openlocfilehash: 3c7a12373c6a60a2902ee451d39c99f756e2b2f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544569"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>將分支網站新增至您在 Lync Server 2013 中的拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

分支網站代表透過 WAN 連結連線至您的主要辦公室的實體分支辦公室。 若要將分支網站新增至您的 Lync 拓撲，請在中央網站執行此程式。

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>若要將分支網站新增至拓撲

1.  依序按一下 [ **開始**]、[ **所有程式**] 及 [ **Microsoft lync server**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在主控台樹中，展開中央網站，以滑鼠右鍵按一下 [ **分支網站**]，然後按一下 [ **新增分支網站**]。

3.  在 [ **定義新的分支網站** ] 對話方塊中，按一下 [ **名稱**]，然後輸入分支網站的名稱。

4.   (選用) 按一下 [ **描述**]，然後為分支網站輸入有意義的描述。

5.  按 **[下一步]**。

6.   (選用) 在下一個 [ **定義新的分支網站** ] 對話方塊中，執行下列其中一項：
    
      - 按一下 [ **城市**]，然後輸入分支網站所在位置的城市名稱。
    
      - 按一下 [ **省/地區**]，然後輸入分支網站所在位置的省或地區名稱。
    
      - 按一下 [ **國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數呼叫碼。

7.  按 **[下一步]**，然後執行下列其中一項動作：
    
      - 如果您是在此網站使用 Survivable 分支裝置或伺服器，請確定已選取 [ **當此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊，按一下 **[完成**]，然後依照所開啟之嚮導中的指示進行。 如需有關 [嚮導專案] 的詳細資訊，請參閱 [在 Lync Server 2013 中定義 Survivable Branch 裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
      - 如果您未使用此網站的 Survivable 分支裝置或伺服器，請清除 [在 **此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成]**。

8.  針對您要新增至拓撲的每一個分支網站重複上述步驟。

**下一步：**

針對 Survivable 分支裝置或伺服器： [定義 Lync Server 2013 中的 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

若為無復原的 PSTN 連線： [在 lync server 2013 中定義分支網站的 PSTN 閘道](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)，在 [lync server 2013 中使用媒體旁路設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)，或在 [lync server 2013 中設定無媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

