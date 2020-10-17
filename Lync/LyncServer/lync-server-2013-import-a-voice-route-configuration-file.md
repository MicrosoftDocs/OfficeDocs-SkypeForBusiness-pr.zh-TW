---
title: Lync Server 2013：匯入語音路由設定檔
description: Lync Server 2013：匯入語音路由設定檔。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 994095598b39548f00447edd4b0d322a7ec5545e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547839"
---
# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>在 Lync Server 2013 中匯入語音路由設定檔

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

## <a name="to-import-a-voice-routing-configuration"></a>若要匯入語音路由設定

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[語音路由]**。

4.  在 **[執行]** 功能表上，按一下 **[匯入設定]**。

5.  尋找您要匯入的組態檔，然後按一下 **[開啟]**。

6.  依序按一下 **[認可]** 和 **[全部認可]**。
    
    <div>
    

    > [!NOTE]  
    > 每當您匯入語音設定檔時，您必須執行 <STRONG>[全部認可]</STRONG> 命令來發佈設定變更。 如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中匯出語音路由設定檔](lync-server-2013-export-a-voice-route-configuration-file.md)  
[在 Lync Server 2013 中將擱置的變更發佈至語音路由設定](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

