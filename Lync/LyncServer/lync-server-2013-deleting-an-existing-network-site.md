---
title: Lync Server 2013：刪除現有的網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772d653e0bde803f47a5742a4f3824bdef01c3f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有的網路網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

[網路網站] 是在通話許可控制（CAC）或增強型9-1-1 部署的每個區域中設定的辦公室或位置。 您可以使用 Lync Server 2013 的 [控制台] 來設定網站，並將它們與區域建立關聯。 例如，北美的網路區域可能會與「芝加哥」、「雷德蒙」和「范與范」等網路網站相關聯。 您必須針對組織中的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制也一樣。 您可以從 Lync Server [控制台] 建立、修改及刪除網路網站。 使用下列程式刪除現有的網路網站。 如需建立或修改網路網站的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>刪除網路網站

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。

4.  在 [**網站**] 頁面上，按一下您要刪除的網站。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的網站。 若要這樣做，請按住 CTRL 並在按住 CTRL 鍵的同時選取多個網站。 或者，若要選取 [所有網站]，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。

6.  按一下 [確定]****。
    
    <div>
    

    > [!WARNING]  
    > 如果網路網站與網路子網相關聯，您就無法移除它。 如果您嘗試移除與子網相關聯的網站，您會收到錯誤訊息。 若要查看網站是否與任何子網產生關聯，請按一下該網站，然後按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

