---
title: Lync Server 2013：刪除現有的網路區域
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
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有的網路區域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

網路區域跨多個地理區域互連網路的各個部分。 每個網路區域都必須與一個中央網站建立關聯。 中央網站是在其上執行呼叫許可控制（CAC）頻寬原則服務的資料中心網站。 您可以使用 Lync Server [控制台] 來設定網路區域。 網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。 在 Lync Server [控制台] 中，您可以建立、修改或刪除網路區域。 使用本主題刪除現有的網路區域。 如需建立或修改現有網路區域的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路區域](lync-server-2013-creating-or-modifying-network-regions.md)。

<div>

## <a name="to-delete-a-network-region"></a>刪除網路區域

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。

4.  在 [**地區**] 頁面上，按一下您要刪除的地區。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的區域。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域。 或者，若要選取所有區域，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。

6.  按一下 [確定]****。
    
    <div>
    

    > [!WARNING]  
    > 如果網路區域與網路網站相關聯，則無法移除。 如果您嘗試移除與網站相關聯的區域，您會收到錯誤訊息。 若要查看某個地區是否與任何網站相關聯，請選取該區域，然後按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改網路區域](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

