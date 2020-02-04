---
title: Lync Server 2013：建立或修改網路區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbebccd02b74c4fbfb69225a6397c1dd7cef862d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路區域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

網路區域跨多個地理區域互連網路的各個部分。 每個網路區域都必須與一個中央網站建立關聯。 中央網站是在其上執行呼叫許可控制（CAC）頻寬原則服務的資料中心網站。 您可以使用 Lync Server [控制台] 來設定網路區域。 網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。 在 Lync Server [控制台] 中，您可以建立、修改或刪除網路區域。 使用本主題來建立及修改網路區域。 如需有關刪除現有網路區域的詳細資訊，請參閱[在 Lync Server 2013 中刪除現有的網路區域](lync-server-2013-deleting-existing-network-regions.md)。

<div>

## <a name="to-create-a-network-region"></a>建立網路區域

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。

4.  在 [**地區**] 頁面上，按一下 [**新增**]。

5.  在 [**新區域**] 頁面上的 [**名稱**] 欄位中輸入值。 這個值在您的 Microsoft Lync Server 2013 部署中必須是唯一的。

6.  從 [**中央網站**] 下拉式清單中，選取此網路區域的中心網站。

7.  預設會選取 [**啟用音訊備用路徑**] 核取方塊。 此欄位會判斷在主要路徑中不存在足夠頻寬的情況下，是否會透過替代路徑路由音訊通話。 如果您需要關閉卸載至網際網路，請先清除此核取方塊。 如果您的任何通話是網際網路通話，則必須核取此核取方塊（無論頻寬設定為何）。

8.  預設會選取 [**啟用影片替換路徑**] 核取方塊。 此欄位會判斷在主要路徑中不存在足夠頻寬時，是否會透過備用路徑路由視頻通話。 如果您需要關閉卸載至網際網路，請先清除此核取方塊。 如果您的任何通話是網際網路通話，則必須核取此核取方塊（無論頻寬設定為何）。

9.  可選在 [**描述**] 欄位中輸入一個值，以提供關於此區域的詳細資訊，而不能單獨以名稱表示。

10. 按一下 [認可]****。

[**關聯的網站**] 資料表不是用來建立網路區域。 您可以在建立或修改網站時，將網站與區域建立關聯。 如需詳細資訊，請參閱[在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-creating-or-modifying-network-sites.md)。

</div>

<div>

## <a name="to-modify-a-network-region"></a>修改網路區域

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。

4.  在 [**地區**] 頁面上，按一下您要修改的地區。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯區域**] 頁面上，您可以修改啟用及停用音訊及視頻替代路徑的設定，以及變更描述（如需詳細資訊，請參閱本主題前面的「建立網路區域」一節。

7.  按一下 [認可]****。

您無法在此頁面上修改**關聯的網站**。 已提供相關網站的清單供參考，因此您知道在修改區域設定時，哪些網站會受到影響。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中刪除現有的網路區域](lync-server-2013-deleting-existing-network-regions.md)  
[在 Lync Server 2013 中設定 CAC 的網路區域](lync-server-2013-configure-network-regions-for-cac.md)  


[新-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[移除-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

