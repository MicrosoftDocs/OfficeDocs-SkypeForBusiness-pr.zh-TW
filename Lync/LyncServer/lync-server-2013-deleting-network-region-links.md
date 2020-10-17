---
title: Lync Server 2013：刪除網路地區連結
description: Lync Server 2013：刪除網路地區連結。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a17c1ec64460e0f7cb447597f94aadd7fd2a9ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545329"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a>在 Lync Server 2013 中刪除網路地區連結

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。 網路中的地區是透過實體廣域網路 (WAN) 連線相連結。 您可以使用 Lync Server 控制台刪除兩個網路地區之間的現有連結。 如需建立或修改網路地區連結的詳細資訊，請參閱 [在 Lync Server 中設定網路地區連結 2013](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>刪除網路地區連結

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  按一下左導覽列中的 [網路設定]****，然後按一下 [地區連結]****。

4.  在 [地區連結]**** 頁面中，按一下要刪除的地區連結。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的地區連結。若要一次刪除一個以上的地區連結，請按住 CTRL 鍵並同時選取多個地區連結。若要選取多個地區，您也可以按一下 [編輯]<STRONG></STRONG> 功能表中的 [全選]<STRONG></STRONG>。

    
    </div>

5.  選取 [編輯]**** 功能表中的 [刪除]****。

6.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定網路地區連結](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

