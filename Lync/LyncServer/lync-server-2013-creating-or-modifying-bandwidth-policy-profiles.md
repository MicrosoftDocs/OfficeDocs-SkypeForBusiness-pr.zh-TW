---
title: Lync Server 2013：建立或修改頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改頻寬原則設定檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。 在 Microsoft Lync Server 2013 中，只有音訊和視頻形式可獲指派頻寬限制。 您可以設定整體頻寬限制及會話限制。 您可以使用 Lync Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。 每個頻寬原則設定檔都可以與一個或多個網路網站建立關聯。 使用下列程式來建立或修改頻寬原則設定檔。 若要刪除頻寬原則設定檔，請參閱[在 Lync Server 2013 中刪除網路頻寬原則設定檔](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>建立新的頻寬原則設定檔

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。

4.  在 [**頻寬原則**] 頁面上，按一下 [**新增**]。

5.  在**新的頻寬原則設定檔**中，在 [**名稱**] 欄位中輸入名稱。 這個名稱在所有頻寬原則設定檔中都必須是唯一的。

6.  在 [**音訊限制**] 欄位中，輸入一個數值。 此值為所有音訊連線所要配置的最大頻寬量，以 kbps 表示。

7.  在 [**音訊會話限制**] 欄位中輸入一個數值。 此值為個別音訊連線所要配置的最大頻寬量，以 kbps 表示。 此值必須是40或更高版本。

8.  在 [**影片限制**] 欄位中輸入一個數值。 此值為所有視頻連線所要配置的最大頻寬量，以 kbps 表示。

9.  在 [**視頻會話限制**] 欄位中輸入一個數值。 此值為個別視頻連線所要配置的最大頻寬量，以 kbps 表示。 此值必須是100或更高版本。

10. 可選在**描述**欄位中輸入一個值，以提供此頻寬原則設定檔無法單獨表示的詳細資訊。

11. 按一下 [認可]****。
    
    <div>
    

    > [!NOTE]  
    > 建立新的頻寬原則設定檔並不會自動強制執行頻寬限制。 您必須先將原則設定檔與網站建立關聯。 如需有關如何將原則設定檔與網站建立關聯的詳細資訊，請參閱<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中建立或修改網路網站</A>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>修改頻寬原則設定檔

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。

4.  在 [**頻寬原則**] 頁面上，按一下您要修改的頻寬原則設定檔。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯頻寬原則策略設定檔**] 頁面上，視需要修改欄位（如需詳細資訊，請參閱本主題前面的「建立頻寬原則設定檔」一節）。

7.  按一下 [認可]****。
    
    <div>
    

    > [!NOTE]  
    > 當您修改頻寬原則設定檔時，它會立即更新與此頻寬原則設定檔相關聯之所有網路網站的頻寬限制。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[刪除 Lync Server 2013 的網路頻寬原則設定檔](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)  
[新-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

