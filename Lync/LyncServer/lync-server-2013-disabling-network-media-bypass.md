---
title: Lync Server 2013：停用網路媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9bfab9fbf8174a1124a45681098196c84ac5444
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中停用網路媒體旁路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

在 Microsoft Lync Server 2013 部署中，媒體旁路設定會全域運用。 [旁路媒體] 允許呼叫繞過中繼伺服器。 如需有關何時使用媒體旁路的詳細資料，請參閱規劃區段中的[Lync Server 2013 中的媒體旁路規劃](lync-server-2013-planning-for-media-bypass.md)。您可以從 Lync Server [控制台] 停用 [媒體旁路]。 如需啟用和設定 [使用詞中旁路] 的詳細資料，請參閱[啟用 Lync Server 2013 的網路媒體旁路](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>停用媒體旁路

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**全域**]。

4.  在 [**全域**] 頁面上，按一下 [**全域**配置]。 永遠只有一個設定，且永遠會將它命名為 Global。

5.  按一下 [**編輯**] 功能表上的 [**查看詳細資料**]。

6.  在 [**編輯全域設定**] 頁面上，清除 [**啟用媒體旁路**] 核取方塊。

7.  按一下 [**認可**]，儲存您的變更。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中啟用網路媒體旁路](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

