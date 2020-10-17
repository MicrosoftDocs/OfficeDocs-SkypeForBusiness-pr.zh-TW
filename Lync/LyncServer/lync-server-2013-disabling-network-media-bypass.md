---
title: Lync Server 2013：停用網路媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29508180b54ace29e1ac913dd52d06d374068bfc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528980"
---
# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>停用 Lync Server 2013 中的網路媒體旁路

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

媒體旁路設定會在 Microsoft Lync Server 2013 部署中全域套用。 媒體旁路允許來電略過轉送伺服器。 如需有關何時使用媒體旁路的詳細資訊，請參閱規劃區段中的在 [Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 。您可以從 Lync Server 控制台停用媒體旁路。 如需啟用和設定詞中略過的詳細資訊，請參閱 [啟用網路媒體旁路 In Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>停用媒體旁路

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[網路設定]**，然後按一下 **[全域]**。

4.  在 **[全域]** 頁面上，按一下 **[全域]** 設定。 永遠只有一個設定，而且永遠稱為 Global。

5.  在 [ **編輯** ] 功能表上，按一下 [ **查看詳細資料**]。

6.  在 [ **編輯通用設定** ] 頁面上，清除 [ **啟用媒體旁路** ] 核取方塊。

7.  按一下 [ **認可** ] 以儲存變更。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中啟用網路媒體旁路](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

