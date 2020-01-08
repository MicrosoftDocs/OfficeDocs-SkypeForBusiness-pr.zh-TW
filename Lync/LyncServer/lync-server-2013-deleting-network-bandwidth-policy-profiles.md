---
title: Lync Server 2013：刪除網路頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c33f781e8818dbefa3dc37b3f17c789099e6add
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>刪除 Lync Server 2013 的網路頻寬原則設定檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。 在 Microsoft Lync Server 2013 中，只有音訊和視頻形式可獲指派頻寬限制。 您可以設定整體頻寬限制及會話限制。 您可以使用 Lync Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。 使用下列程式刪除網路頻寬原則設定檔。 如需建立或修改網路頻寬原則設定檔的詳細資料，請參閱[在 Lync Server 2013 中建立或修改頻寬原則設定檔](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>刪除頻寬原則設定檔

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。

4.  在 [**頻寬原則**] 頁面上，按一下您要刪除的頻寬原則設定檔。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的設定檔。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個設定檔。 或者，若要選取所有設定檔，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。
    
    <div>
    

    > [!WARNING]  
    > 您無法刪除與網路網站相關聯的頻寬原則設定檔。 您必須先移除與網路網站的關聯，然後才能刪除設定檔。 如需如何修改網路網站的詳細資訊，請參閱<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中建立或修改網路網站</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改頻寬原則設定檔](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[在 Lync Server 2013 中查看網路頻寬原則設定檔資訊](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)  
[移除-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

