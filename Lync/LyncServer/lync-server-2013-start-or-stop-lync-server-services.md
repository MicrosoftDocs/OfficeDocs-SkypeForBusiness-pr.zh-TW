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
ms.openlocfilehash: a986f0bef8c41cf5113e99504369974562e294a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a>啟動或停止 Lync Server 2013 服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

您可以使用 Lync Server [控制台] 來啟動或停止在特定電腦上執行的所有 Lync Server 2013 服務，或是啟動或停止特定服務。

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a>在電腦上啟動或停止所有 Lync Server 服務

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。 您可以執行如下所示的命令來判斷您是否已獲指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。

4.  在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。

5.  按一下 [**動作**]。

6.  按一下 [**啟動所有服務**] 或 [**停止所有服務**]。

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a>啟動或停止特定服務

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。

4.  在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。

5.  按一下 [**屬性**]。

6.  如有需要，請排序服務清單，然後按一下您要開始或停止的服務。

7.  按一下 [**動作**]。

8.  按一下 [**開始服務**] 或 [**停止服務**]。

9.  按一下 [**關閉**]。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中避免服務的會話](lync-server-2013-prevent-sessions-for-services.md)  


[管理 Lync Server 2013 拓撲](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

