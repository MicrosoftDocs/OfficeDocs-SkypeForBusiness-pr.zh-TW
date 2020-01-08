---
title: Lync Server 2013：刪除網路區域連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a097626f6e5eb5de8e3503baab0f1ab9ce462549
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a>刪除 Lync Server 2013 中的 [網路區域] 連結

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以設定兩個網路區域之間的連結，作為通話許可控制（CAC）的一部分。 網路中的區域是透過物理廣域網路（WAN）連線來連結。 您可以使用 Lync Server [控制台] 來刪除兩個網路區域之間的現有連結。 如需建立或修改網路區域連結的詳細資料，請參閱[在 Lync Server 2013 中設定網路區域連結](lync-server-2013-configuring-network-region-links.md)。

<div>

## <a name="to-delete-a-network-region-link"></a>刪除網路區域連結

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。

4.  在 [**地區連結**] 頁面上，按一下您要刪除的區域連結。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的區域連結。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域連結。 或者，若要選取所有區域連結，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  從 [**編輯**] 功能表中，選取 [**刪除**]。

6.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定網路區域連結](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

