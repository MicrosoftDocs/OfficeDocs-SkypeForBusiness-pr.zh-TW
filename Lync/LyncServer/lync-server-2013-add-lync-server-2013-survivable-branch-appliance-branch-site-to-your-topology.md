---
title: 將 Lync Server 2013 Survivable 分支裝置分支網站新增至您的拓撲
description: 將 Lync Server 2013 Survivable 分支裝置分支網站新增至您的拓撲。
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
ms.openlocfilehash: 1b50c03dd53c7637fcf0914db290b3e452b64b83
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572029"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>將 Lync Server 2013 Survivable 分支裝置分支網站新增至您的拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

Microsoft Lync Server 2013 Survivable 分支裝置 (SBA) 無法與 Microsoft Lync Server 2010 前端集區相關聯，成為備份註冊機構。 SBA 必須與 Microsoft Lync Server 2013 前端集區相關聯。 這些步驟假設使用 Microsoft Lync Server 2013 SBA。 請在中央網站執行這項程序。

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>將分支網站新增至您的拓撲的 Microsoft Lync Server 2013 SBA

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在主控台樹中，展開中央網站，展開 [ **分支**網站]，然後按一下 [ **新增分支網站**]。

3.  在 [ **定義新的分支網站** ] 對話方塊中，按一下 [ **名稱**]，然後輸入新分支網站的名稱。

4.   (選用) 按一下 [ **描述**]，然後為分支網站輸入有意義的描述。

5.  按 **[下一步]**。

6.   (選用) 在下一個 [ **定義新的分支網站** ] 對話方塊中，執行下列其中一項：
    
      - 按一下 [ **城市**]，然後輸入分支網站所在位置的城市名稱。
    
      - 按一下 [ **省/地區**]，然後輸入分支網站所在位置的省或地區名稱。
    
      - 按一下 [ **國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數呼叫碼。

7.  按 **[下一步]**，然後執行下列其中一項動作：
    
      - 如果您使用的是 Survivable Branch 裝置或 Survivable Branch Server 在此網站上，請確定已選取 [ **當此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊。
    
      - 如果您未在此網站上使用 Survivable Branch 裝置或 Survivable 分支伺服器，請清除 [ **當此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊。
    
      - 按一下 **[完成**]，然後依照嚮導中開啟的指示進行。 如需有關 [嚮導專案] 的詳細資訊，請參閱 [在 Lync Server 2013 中定義 Survivable Branch 裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。

8.  針對您要新增至拓撲的每一個分支網站重複上述步驟。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[在 Lync Server 2013 中定義分支網站的 PSTN 閘道](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[在 Lync Server 2013 中設定含媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中設定無媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

