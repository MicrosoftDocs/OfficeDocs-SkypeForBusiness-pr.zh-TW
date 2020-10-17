---
title: Lync Server 2013：刪除現有的網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d37e08eddac5b6166043a45d7e669c7e0ecd71a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525380"
---
# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有的網路網站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。 您可以使用 Lync Server 2013 控制台來設定網站，並將其與區域產生關聯。 例如，北美洲的網路區域可能會和 Chicago、Redmond 及 Vancouver 等網路網站相關聯。 您必須為組織內的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制。 您可以從 Lync Server 控制台建立、修改和刪除網路網站。 使用下列程序刪除現有網路網站。 如需建立或修改網站的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>刪除網路網站

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 [網路設定]**** 和 [網站]****。

4.  在 [網站]**** 頁面上，按一下您要刪除的網站。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除多個網站。若要這樣做，請按 CTRL 並在按住 CTRL 鍵的同時選取多個網站。或者，若要選取所有網站，請按一下 [編輯]<STRONG></STRONG> 功能表上的 [全選]<STRONG></STRONG>。

    
    </div>

5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]****。
    
    <div>
    

    > [!WARNING]  
    > 但是如果網站與某個網路子網路相關聯時，則無法移除該網路網站。如果您嘗試移除與子網路相關聯的網站，則會收到錯誤訊息。若要查看網站是否與子網路相關聯，請按一下網站並按一下 [編輯]<STRONG></STRONG> 功能表上的 [顯示詳細資料]<STRONG></STRONG>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

