---
title: Lync Server 2013：查看受信任的應用程式清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23866bfbc437d87911a84d065ae7f501c7d80466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>在 Lync Server 2013 中查看信任的應用程式清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

您可以使用 Lync Server 2013 [控制台] 來查看您已在 Lync Server 2013 環境中部署之受信任的應用程式清單。 受信任的應用程式是以 Microsoft 整合通訊 Managed API （UCMA）3.0 核心 SDK （受 Lync Server 2013 信任）為基礎的應用程式。 下列清單將摘要列出這項信任關係：

  - 受信任的應用程式不會因 Lync Server 的驗證而面臨挑戰。

  - Lync Server 不會針對 SIP 交易、連線或透過網際網路通訊協定（VoIP）通話的傳出語音限制受信任的應用程式。

  - 受信任的應用程式可以模仿任何使用者，而且無需出現在 rosters 中，即可加入會議。

  - 受信任的應用程式高度可用且具有彈性。

在 Lync Server [控制台] 中，您可以看見應用程式名稱、其執行所在的池中，以及它們所使用的埠。

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>若要查看受信任的應用程式清單

1.  從指派給 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 如需有關 Lync Server 2013 中預先定義的管理角色的詳細資訊，請參閱[在 Lync server 2013 中規劃角色式存取控制](lync-server-2013-planning-for-role-based-access-control.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**拓撲**]，然後按一下 [按一下**信任的應用程式**]。

4.  如有需要，請在 [**受信任的應用程式**] 頁面上，按一下欄標題來排序應用程式。

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

