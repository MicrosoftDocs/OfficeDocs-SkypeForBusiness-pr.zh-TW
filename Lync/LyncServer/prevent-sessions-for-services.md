---
title: 防止服務的工作階段
description: 防止服務的會話。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563689"
---
# <a name="prevent-sessions-for-services"></a>防止服務的工作階段

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

您可以使用 Microsoft Lync Server 2010 控制台，以防止在特定電腦上執行的所有 Lync Server 2010 服務的新會話，或阻止特定 Lync Server 2010 服務的新會話。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>阻止所有 Lync Server 服務的新工作階段於電腦上執行

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟 [Lync Server 控制台]。

3.  在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。

4.  在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。

5.  按一下 **[動作]**。

6.  按一下 **[阻止對所有服務的新工作階段]**。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服務的新工作階段

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟 [Lync Server 控制台]。

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

