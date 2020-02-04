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
ms.openlocfilehash: 2ea7f585e42164c8387853c7525cd0478eeb4db4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>刪除 Lync Server 2013 中的位置原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

在 Lync Server 2013 中，您可以使用位置原則來套用與增強版9-1-1 （E9-1）功能相關的設定，以及使用者或連絡人的位置設定。 位置原則會判斷使用者是否已啟用 E9-1-1，以及是否有緊急通話的行為。 例如，您可以使用位置原則來定義代表緊急通話的號碼（例如，911在美國）、企業安全性是否應該自動收到通知，以及如何路由通話。

您可以在 Lync Server 2013 [控制台] 的 [**網路**設定] 群組中設定位置原則。 在 Lync Server [控制台] 中，您可以查看、建立、修改或刪除位置原則。 使用下列程式刪除位置原則。 如需建立或修改位置原則的詳細資料，請參閱[在 Lync Server 2013 中建立或修改位置原則](lync-server-2013-creating-or-modifying-a-location-policy.md)。

<div>

## <a name="to-delete-a-location-policy"></a>刪除位置原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**位置原則**]。

4.  在 [**位置原則**] 頁面上，選取您要刪除的位置原則。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的位置原則。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個原則。 或者，若要選取所有原則，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。

6.  按一下 [確定]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 您無法刪除全域位置原則。 如果您嘗試刪除全域原則，您會收到警告訊息，而該原則將會重設為預設值。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改位置原則](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[在 Lync Server 2013 中查看位置原則資訊](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

