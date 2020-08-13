---
title: Lync Server 2013：刪除現有的網路地區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad0f1c88e7c0a1ec855a69ad75f834f0a8982221
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有的網路地區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

網路地區會與跨多個地理區域的網路不同部分交互連線。 每個網路地區都必須與中央網站產生關聯。 中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。 您可以使用 Lync Server 控制台設定網路地區。 網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。 在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路地區。 使用此主題可刪除現有的網路地區。 如需建立或修改現有網路地區的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改網路地區](lync-server-2013-creating-or-modifying-network-regions.md)。

<div>

## <a name="to-delete-a-network-region"></a>若要刪除網路地區

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[地區]**。

4.  在 [**地區**] 頁面上，按一下您要刪除的地區。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的區域。 若要執行此動作，請按住 CTRL 鍵並選取多個區域，並按住 CTRL 鍵。 或者，若要選取所有區域，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]****。
    
    <div>
    

    > [!WARNING]  
    > 如果網路地區與網路網站相關聯，則無法加以移除。 如果您嘗試移除與網站相關聯的區域，您會收到錯誤訊息。 若要查看是否有任何網站相關聯的區域，請選取該區域，然後按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改網路地區](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

