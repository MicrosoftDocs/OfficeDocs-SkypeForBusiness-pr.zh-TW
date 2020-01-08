---
title: Lync Server 2013：查看網路頻寬原則設定檔資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 513bd20e9a1ecd40f061c4873e7da8bff4738f36
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看網路頻寬原則設定檔資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。 在 Microsoft Lync Server 2013 中，只有音訊和視頻形式可獲指派頻寬限制。 您可以設定整體頻寬限制及會話限制。 您可以使用 Lync Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。 每個頻寬原則設定檔都可以與一個或多個網路網站建立關聯。 使用下列程式來查看頻寬原則設定檔。 若要建立或修改頻寬策略設定檔，請參閱[在 Lync Server 2013 中建立或修改頻寬原則設定檔](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>若要查看頻寬原則設定檔

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。

4.  在 [**頻寬原則**] 頁面上，按一下您要查看的頻寬原則設定檔。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看網路頻寬原則設定檔資訊

您可以使用 Windows PowerShell 和 CsNetworkBandwidthPolicyProfile Cmdlet 來查看網路頻寬設定檔。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>若要查看網路頻寬原則設定檔資訊

  - 若要查看所有網路頻寬策略設定檔的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkBandwidthPolicyProfile
    
    這會傳回如下所示的資訊：
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

如需詳細資訊，請參閱[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改頻寬原則設定檔](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[刪除 Lync Server 2013 的網路頻寬原則設定檔](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

