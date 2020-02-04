---
title: 將 Lync Server 2013 Survivable Branch Appliance 分支網站新增至您的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>將 Lync Server 2013 Survivable Branch Appliance 分支網站新增至您的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

Microsoft Lync Server 2013 Survivable 分支裝置（SBA）無法與 Microsoft Lync Server 2010 前端池（做為備份註冊機構）相關聯。 SBA 必須與 Microsoft Lync Server 2013 前端池相關聯。 這些步驟假設 Microsoft Lync Server 2013 SBA。 在中央網站執行此程式。

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>若要將分支網站與 Microsoft Lync Server 2013 SBA 新增至您的拓撲

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在主控台樹中，展開中央網站，展開 [**分支網站**]，然後按一下 [**新增分支網站**]。

3.  在 [**定義新分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入新分支網站的名稱。

4.  可選按一下 [**描述**]，然後為分支網站輸入有意義的描述。

5.  按一下 **[下一步]**。

6.  可選在 [下一步**定義分支網站**] 對話方塊中，執行下列任何一項操作：
    
      - 按一下 [**城市**]，然後輸入分支網站所在城市的名稱。
    
      - 按一下 [**狀態/地區**]，然後輸入分支網站所在的狀態或地區名稱。
    
      - 按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數電話號碼。

7.  按一下 **[下一步]**，然後執行下列其中一項操作：
    
      - 如果您是在此網站使用 Survivable 分支裝置或 Survivable 分支伺服器，請確定已選取 [**當此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊。
    
      - 如果您不是在此網站使用 Survivable 分支裝置或 Survivable 分支伺服器，請清除 [**當此嚮導關閉時，開啟新的 Survivable 嚮導]** 核取方塊。
    
      - 按一下 **[完成**]，然後依照嚮導中開啟的指示進行。 如需有關嚮導專案的資訊，請參閱[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。

8.  針對您要新增到拓撲結構中的每個分支網站，重複上述步驟。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中定義 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[在 Lync Server 2013 中定義分支網站的 PSTN 閘道](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中設定沒有媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

