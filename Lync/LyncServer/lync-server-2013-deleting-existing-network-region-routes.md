---
title: Lync Server 2013：刪除現有的網路區域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e188ef3214088fe9c38c144fad1908d13fef162
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有的網路區域路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。 雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。 您可以使用 Lync Server [控制台] 來設定網路區域路由。 您可以從 Lync Server [控制台] 建立、修改或刪除網路區域路由。 使用本主題刪除現有的網路區域路由。 如需建立或修改網路區域路由的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路區域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。

<div>

## <a name="to-delete-a-network-region-route"></a>刪除網路區域路線

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路由**]。

4.  在 [**地區路線**] 頁面上，按一下您要刪除的地區路線。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次刪除一個以上的區域路由。 若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域路由。 或者，若要選取所有地區路線，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。

    
    </div>

5.  在 [**編輯**] 功能表上，按一下 [**刪除**]。

6.  按一下 [確定]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改網路區路由](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[設定網路地區路由](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))  


[新-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[移除-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

