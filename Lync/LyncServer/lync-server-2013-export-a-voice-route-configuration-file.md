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
ms.openlocfilehash: ca000e2ba0c1802d8ec97a2a9c2f361f2c0a1b68
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528380"
---
# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>在 Lync Server 2013 中匯出語音路由設定檔

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您想要儲存語音路由設定，但未發佈它，請遵循下列步驟，使用 Lync Server 控制台的 [匯出] 和 [匯入] 命令，儲存並取得您的語音路由設定快照。 當您匯入語音路由設定檔 (。 vcfg) ，但目前在伺服器上對語音路由設定進行變更時，Lync Server [控制台] 中的 [ **語音** 路由] 群組中的頁面會指出有未認可的變更可供語音路由使用。 這些未認可的變更會使兩個設定出現差異且需要重新調整。

如果您已對群組內任何頁面上的設定進行任何未認可的變更，則所做的變更會儲存在匯出的語音設定檔中 (。 vcfg) 。 這可讓您在發佈變更之前，在多個會話期間進行語音路由設定變更。

<div>

## <a name="to-export-a-voice-routing-configuration"></a>若要匯出語音路由設定

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[語音路由]**。

4.  在 **[執行]** 功能表上，按一下 **[匯出設定]**。

5.  指定位置和檔案名稱，然後按一下 **[儲存]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中匯入語音路由設定檔](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

