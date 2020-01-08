---
title: Lync Server 2013：查看網路區域路由資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4438a3af4a9bfbdaf88d4412b769cdaaba9d3d43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看網路區域路線資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。 雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。 使用下列程式來查看 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 中的現有網路區域路由。 如需建立或修改網路區域路由的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路區域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>在 Lync Server [控制台] 中查看網路區域路由資訊

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路由**]。

4.  在 [**地區路線**] 頁面上，按一下您要查看的地區路線。
    
    <div>
    

    > [!NOTE]  
    > 一次只能查看一個區域路線。

    
    </div>

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看網路區域路由資訊

您可以使用 Windows PowerShell 和 CsNetworkInterRegionRoute Cmdlet 來查看網路區域路由資訊。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-network-region-route-information"></a>若要查看網路區域路線資訊

  - 若要查看所有網路區域路由的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkInterRegionRoute
    
    這會傳回如下所示的資訊：
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

如需詳細資訊，請參閱[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改網路區路由](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[在 Lync Server 2013 中刪除現有的網路區域路由](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

