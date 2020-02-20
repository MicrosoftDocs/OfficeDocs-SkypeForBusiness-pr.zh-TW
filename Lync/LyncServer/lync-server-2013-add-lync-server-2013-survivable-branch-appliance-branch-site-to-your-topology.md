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
ms.openlocfilehash: bfc267d20b9df284e458ff5883cfebb4c1e5b0b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>將 Lync Server 2013 Survivable Branch Appliance 分支網站新增至您的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-07_

Microsoft Lync Server 2013 Survivable Branch Appliance (SBA) 不能作為備份登錄器與 Microsoft Lync Server 2010 前端集區相關聯。 SBA 必須與 Microsoft Lync Server 2013 前端集區建立關聯。 這些步驟假設 Microsoft Lync Server 2013 SBA。 請在中央網站執行這項程序。

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>與 Microsoft Lync Server 2013 SBA 的分支網站新增至您的拓撲

1.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在主控台樹狀目錄中，展開中央網站，請依序展開 [**分支站台**，和 [**新的分支網站**。

3.  在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入新的分支網站的名稱。

4.  （選用）按一下 [**描述**] 中，，，然後輸入分支網站的有意義描述。

5.  按 [下一步]****。

6.  （選用）在下的 [**定義新的分支網站**] 對話方塊中，執行下列其中一項：
    
      - 按一下 [**縣/市**、，然後輸入分支網站所在位置的城市名稱。
    
      - 按一下 [省/地區****，然後輸入位置的省或地區的分支網站所在的名稱。
    
      - 按一下 [**國碼/地區碼**，，，然後輸入分支網站所在國家/地區的兩位數呼叫程式碼。

7.  按一下 [**下一步**，，然後執行下列其中一項：
    
      - 如果您在此網站使用 Survivable Branch Appliance 或 Survivable Branch 伺服器，請務必選取 [**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊。
    
      - 如果您未在此網站使用 Survivable Branch Appliance 或 Survivable Branch 伺服器，請清除 [**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊。
    
      - 按一下 [**完成**]，然後依照 [開啟精靈] 中的指示操作。 精靈項目的相關資訊，請參閱[定義 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。

8.  針對每個您想要新增至拓撲的分支網站重複上述步驟。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中定義 Survivable Branch Appliance 或 Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[在 Lync Server 2013 中定義 PSTN 閘道的分支網站](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[設定與 Lync Server 2013 中的媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[沒有媒體旁路 Lync Server 2013 中設定主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

