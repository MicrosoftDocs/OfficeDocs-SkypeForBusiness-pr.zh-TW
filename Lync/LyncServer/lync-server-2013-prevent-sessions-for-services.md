---
title: Lync Server 2013：阻止服務的會話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bfb2316de9ea09db49ac22e0cf0addd0a699739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513240"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a>在 Lync Server 2013 中禁止服務的會話

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以使用 Lync Server 控制台，避免在特定電腦上執行的所有 Lync Server 2013 服務的新會話，或阻止特定 Lync Server 2013 服務的新會話。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>阻止所有 Lync Server 服務的新工作階段於電腦上執行

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。

4.  在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。

5.  按一下 **[動作]**。

6.  按一下 **[阻止對所有服務的新工作階段]**。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服務的新工作階段

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。

4.  在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。

5.  按一下 **[內容]**。

6.  視需要排序服務清單，然後按一下要阻止新工作階段的服務。

7.  按一下 **[動作]**。

8.  按一下 **[阻止對服務的新工作階段]**。

9.  按一下 **[關閉]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[管理 Lync Server 2013 拓撲](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

