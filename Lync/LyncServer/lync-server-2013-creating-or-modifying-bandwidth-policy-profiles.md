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
ms.openlocfilehash: ee744459f284355b0bd4aa13f7ac6a1cfba908e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516770"
---
# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改頻寬原則設定檔

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。 在 Microsoft Lync Server 2013 中，只有音訊和影片形式可以獲指派頻寬限制。 您可以設定整體頻寬限制和工作階段限制。 您可以使用 Lync Server 控制台建立、修改或刪除這些原則的容器設定檔。 每個頻寬原則設定檔可以與一或多個網路網站產生關聯。 請使用下列程序來建立或修改頻寬原則設定檔。 若要刪除頻寬原則設定檔，請參閱 [刪除 Lync Server 2013 中的網路頻寬原則設定檔](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>若要建立新的頻寬原則設定檔

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [網路設定]****，然後按一下 [頻寬原則]****。

4.  在「頻寬原則」**** 頁面上，按一下 [新增]****。

5.  在 **[新增頻寬原則設定檔]** 的 **[名稱]** 欄位中輸入名稱。在所有頻寬原則設定檔中，此名稱必須是唯一的。

6.  在 **[音訊限制]** 欄位中輸入數值。此值是要配置給所有音訊連線的最大頻寬數量 (以 kbps 表示)。

7.  在 **[音訊工作階段限制]** 欄位中輸入數值。此值是要配置給個別音訊連線的最大頻寬數量 (以 kbps 表示)。此值必須為 40 或更大。

8.  在 **[視訊限制]** 欄位中輸入數值。此值是要配置給所有視訊連線的最大頻寬數量 (以 kbps 表示)。

9.  在 **[視訊工作階段限制]** 欄位中輸入數值。此值是要配置給個別視訊連線的最大頻寬數量 (以 kbps 表示)。此值必須為 100 或更大。

10. (選用) 在 **[描述]** 欄位中輸入值，以提供更多有關此頻寬原則設定檔 (無法單獨以名稱表示) 的資訊。

11. 按一下 **[認可]**。
    
    <div>
    

    > [!NOTE]  
    > 建立新的頻寬原則設定檔並不會自動強制頻寬限制。 您必須先讓原則設定檔與網站產生關聯。 如需如何關聯原則設定檔與網站的詳細資訊，請參閱 <A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中建立或修改網路網站</A>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>若要修改頻寬原則設定檔

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [網路設定]****，然後按一下 [頻寬原則]****。

4.  在「頻寬原則」**** 頁面上，按一下您要修改的頻寬原則設定檔。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 **[編輯頻寬原則設定檔]** 頁面上，視需要修改欄位 (如需詳細資訊，請參閱本主題中前面的＜若要建立頻寬原則設定檔＞一節)。

7.  按一下 **[認可]**。
    
    <div>
    

    > [!NOTE]  
    > 當您修改頻寬原則設定檔時，將會立即更新與此頻寬原則設定檔關聯的所有網路網站的頻寬限制。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除網路頻寬原則設定檔](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

