---
title: Lync Server 2013：查看信任的應用程式清單
description: Lync Server 2013：查看信任的應用程式清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d45c682550640c3fc7284e0b60ca6844896b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574789"
---
# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>在 Lync Server 2013 中查看信任的應用程式清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

您可以使用 Lync Server 2013 控制台，以查看您已在 Lync Server 2013 環境中部署之信任的應用程式清單。 信任的應用程式是以 Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 為基礎的應用程式，該應用程式是由 Lync Server 2013 所信任。 此信任關係摘要如下清單所示：

  - 受信任的應用程式不會受到 Lync Server 的驗證的挑戰。

  - Lync Server 不會節流 SIP 交易的受信任應用程式、連接或呼出語音 over 網際網路通訊協定 (VoIP) 通話。

  - 信任的應用程式可以模仿任何使用者，並且可以加入會議，而不會出現在名冊中。

  - 信任的應用程式具有高可用性和彈性。

在 [Lync Server 控制台] 中，您可以看到應用程式的名稱、其執行所在的集區，以及其使用的埠。

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>若要查看信任的應用程式清單

1.  從指派給 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 如需 Lync Server 2013 中可用的預先定義管理角色的詳細資訊，請參閱 [在 Lync server 2013 中規劃以角色為基礎的存取控制](lync-server-2013-planning-for-role-based-access-control.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **拓撲** ]，然後按一下 [ **信任的應用程式**]。

4.  在 [ **信任的應用程式** ] 頁面上，按一下欄標題以排序應用程式（如有必要）。

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

