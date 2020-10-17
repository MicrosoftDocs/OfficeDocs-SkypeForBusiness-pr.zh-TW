---
title: Lync Server 2013：刪除網路頻寬原則設定檔
description: Lync Server 2013：刪除網路頻寬原則設定檔。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f460d9620158d1857dae41e0033f6d36078868
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552659"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>在 Lync Server 2013 中刪除網路頻寬原則設定檔

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。 在 Microsoft Lync Server 2013 中，只有音訊和影片形式可以獲指派頻寬限制。 您可以設定整體頻寬限制和工作階段限制。 您可以使用 Lync Server 控制台建立、修改或刪除這些原則的容器設定檔。 請使用下列程序來刪除網路頻寬原則設定檔。 如需建立或修改網路頻寬原則設定檔的詳細資訊，請參閱 [建立或修改 Lync Server 2013 中的頻寬原則設定檔](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>刪除頻寬原則設定檔

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[網路設定]**，再按一下 **[頻寬原則]**。

4.  在 **[頻寬原則]** 頁面上，按一下您要刪除的頻寬原則設定檔。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的設定檔。若要這麼做，請按住 CTRL 鍵並同時選取多個設定檔。或者，若要選取所有設定檔，請按一下 <STRONG>[編輯]</STRONG> 功能表上的 <STRONG>[全選]</STRONG>。

    
    </div>

5.  在 **[編輯]** 功能表上，按一下 **[刪除]**。
    
    <div>
    

    > [!WARNING]  
    > 您無法刪除與網站關聯的頻寬原則設定檔。 您必須先移除與網站的關聯，才可以刪除設定檔。 如需如何修改網路網站的詳細資訊，請參閱 <A href="lync-server-2013-creating-or-modifying-network-sites.md">建立或修改 Lync Server 2013 中的網路網站</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改頻寬原則設定檔](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[在 Lync Server 2013 中查看網路頻寬原則設定檔資訊](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

