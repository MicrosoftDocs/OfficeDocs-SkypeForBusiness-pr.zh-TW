---
title: Lync Server 2013：匯出語音路由設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55ecc35d2724fa8c635b9d4099764c25e76874c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>在 Lync Server 2013 中匯出語音路由設定檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您想要儲存語音路由設定，但不發佈它，請依照下列步驟使用 Lync Server [控制台] 的 [匯出及匯入] 命令來儲存及取得語音路由設定的快照。 當您匯入語音路由設定檔（vcfg），但同時又在伺服器上對語音路由設定進行變更時，Lync Server [控制台] 中的 [**語音路由**] 群組中的頁面將會顯示 [語音路由] 中有未提交的變更。 那些未提交的變更是兩個需要調解的設定之間的差異。

如果您已對群組內任何頁面上的設定進行任何未提交的變更，這些變更就會儲存在匯出的語音設定檔案（vcfg）中。 這可讓您在發佈變更前，在多個會話期間進行語音路由設定的變更。

<div>

## <a name="to-export-a-voice-routing-configuration"></a>匯出語音路由設定

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]。

4.  在 [**動作**] 功能表上，按一下 [**匯出配置**]。

5.  指定位置和檔案名，然後按一下 [**儲存**]。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中匯入語音路由組態檔](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

