---
title: Lync Server 2013：刪除位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc554d24bc93b81969832c9d8d2b034d071760bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中刪除位置原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

在 Lync Server 2013 中，您可以使用位置原則，套用與增強型 9-1-1 (E9-1-1) 功能及使用者或連絡人的位置設定相關的設定。 位置原則會判斷使用者是否已啟用 E9-1-1，如果是，則會決定緊急電話的行為。 例如，您可以使用位置原則來定義組成緊急電話的數字 (例如，在美國為 911)、是否應自動告知公司的安全部門，以及應如何路由傳送來電。

您可以在 Lync Server 2013 [控制台] 中的 [**網路**設定] 群組設定位置原則。 從 Lync Server 控制台，您可以查看、建立、修改或刪除位置原則。 使用下列程式會刪除位置原則。 如需建立或修改位置原則的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改位置原則](lync-server-2013-creating-or-modifying-a-location-policy.md)。

<div>

## <a name="to-delete-a-location-policy"></a>刪除位置原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中按一下 **[網路設定]**，然後按一下 **[位置原則]**。

4.  在 [**位置原則**] 頁面上，選取您要刪除的位置原則。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的位置原則。 若要執行此動作，請按住 CTRL 鍵並選取多個原則，並按住 CTRL 鍵。 或者，若要選取所有原則，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 您無法刪除全域位置原則。 如果您嘗試刪除通用原則，您會收到警告訊息，而且該原則會重設為其預設值。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改位置原則](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[在 Lync Server 2013 中查看位置原則資訊](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

