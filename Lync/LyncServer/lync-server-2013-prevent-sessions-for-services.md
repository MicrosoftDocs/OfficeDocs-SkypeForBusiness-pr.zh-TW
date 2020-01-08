---
title: Lync Server 2013：防止服務的會話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8d22b74168c784d6a5e19c3ffc32b9e275040b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a>在 Lync Server 2013 中避免服務的會話

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以使用 Lync Server [控制台] 來避免在特定電腦上執行的所有 Lync Server 2013 服務的新會話，或防止特定 Lync Server 2013 服務的新會話。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>避免電腦上所有 Lync Server 服務的新會話

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。

4.  在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您想要防止新會話之服務的電腦，然後按一下該電腦。

5.  按一下 [**動作**]。

6.  按一下 [**防止所有服務的新會話**]。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>若要防止特定服務的新會話

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。

4.  在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。

5.  按一下 [**屬性**]。

6.  如有需要，請排序服務清單，然後按一下您要防止新會話的服務。

7.  按一下 [**動作**]。

8.  按一下 [**避免新的服務會話**]。

9.  按一下 [**關閉**]。

</div>

<div>

## <a name="see-also"></a>請參閱


[管理 Lync Server 2013 拓撲](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

