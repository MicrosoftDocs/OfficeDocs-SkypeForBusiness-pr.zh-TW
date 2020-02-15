---
title: 防止服務的工作階段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d936a063d5ce634a50b4ba4567f51473bf363612
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a>防止服務的工作階段

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

若要防止在特定電腦上執行的所有 Lync Server 2010 服務的新工作階段，或阻止特定的 Lync Server 2010 服務的新工作階段，您可以使用 Microsoft Lync Server 2010 Control Panel。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>阻止所有 Lync Server 服務的新工作階段於電腦上執行

1.  從使用者帳戶是 RTCUniversalServerAdmins 群組成員 （或具有相等使用者權限），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入是在您部署了 Lync Server 2013 網路中的任何電腦。

2.  開啟 Lync Server 控制台。

3.  在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。

4.  在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。

5.  按一下 **[動作]**。

6.  按一下 **[阻止對所有服務的新工作階段]**。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服務的新工作階段

1.  從使用者帳戶是 RTCUniversalServerAdmins 群組成員 （或具有相等使用者權限），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入是在您部署了 Lync Server 2013 網路中的任何電腦。

2.  開啟 Lync Server 控制台。

3.  在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。

4.  在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。

5.  按一下 **[內容]**。

6.  視需要排序服務清單，然後按一下要阻止新工作階段的服務。

7.  按一下 **[動作]**。

8.  按一下 **[阻止對服務的新工作階段]**。

9.  按一下 **[關閉]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

