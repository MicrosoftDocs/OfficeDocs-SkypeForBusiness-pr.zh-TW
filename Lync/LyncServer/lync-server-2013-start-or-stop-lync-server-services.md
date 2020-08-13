---
title: Lync Server 2013：啟動或停止 Lync Server 服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b95e9a49978499d16749f643cdd10d71637daf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>啟動或停止 Lync Server 2013 服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

您可以使用 Lync Server 控制台來啟動或停止在特定電腦上執行的所有 Lync Server 2013 服務，或是啟動或停止特定的服務。

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>啟動或停止電腦上的所有 Lync Server 服務

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。 您可以執行類似下列的命令，判斷是否已指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[拓撲]**，再按一下 **[狀態]**。

4.  在 **[狀態]** 頁面上，視需要排序或搜尋清單，找到正在執行您要啟動或停止之服務的電腦，然後按一下該電腦。

5.  按一下 **[動作]**。

6.  按一下 **[啟動所有服務]** 或 **[停止所有服務]**。

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>啟動或停止特定服務

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。

4.  在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。

5.  按一下 **[內容]**。

6.  視需要排序服務清單，然後按一下您要啟動或停止的服務。

7.  按一下 **[動作]**。

8.  按一下 **[啟動服務]** 或 **[停止服務]**。

9.  按一下 **[關閉]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中禁止服務的會話](lync-server-2013-prevent-sessions-for-services.md)  


[管理 Lync Server 2013 拓撲](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

