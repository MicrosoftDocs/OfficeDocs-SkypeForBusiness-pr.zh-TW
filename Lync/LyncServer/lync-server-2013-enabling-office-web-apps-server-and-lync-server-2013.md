---
title: Lync Server 2013：啟用 Office Web Apps Server 和 Lync Server 2013
description: Lync Server 2013：啟用 Office Web Apps Server 和 Lync Server 2013。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1bf4e09dc29bf344b78df50595258f0663cd731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546519"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>設定 Office Web Apps Server 與 Lync Server 2013 的整合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-08-19_

Lync Server 2013 採用 Office Web Apps Server 來處理 PowerPoint 簡報。 如需此方法之優點的詳細資訊，請參閱 [Lync Server 2013 中的 web 會議概述](lync-server-2013-web-conferencing-overview.md)。

若要使用這些新功能，管理員必須安裝 Office Web Apps Server，而且必須設定 Lync Server 2013，以與 Office Web Apps Server 通訊。 本檔提供如何設定 Lync Server 2013 以搭配 Office Web Apps Server 使用的資訊。 本檔不提供的資訊，是有關如何安裝 Office Web Apps Server 本身的資訊，請參閱。如需相關資訊，請參閱 Microsoft Office Web Apps 部署網站 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。 該指南包含 Office Web Apps Server 的完整必要資訊。請注意，Office Web Apps Server 應該安裝在未執行 Lync Server、Microsoft SQL Server 或任何其他伺服器應用程式的獨立電腦上。  (您不能在該電腦上安裝任何版本的 Microsoft Office。 ) 任何用來執行 Office Web Apps Server 的電腦也必須安裝一組特定的軟體， (包括 .NET Framework 4.5 和 Windows PowerShell 3.0) ;Microsoft Office Web Apps 部署網站會詳細討論這些需求，以及設定憑證和網際網路資訊服務 (IIS) 的相關資訊 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。

<div>


> [!NOTE]  
> Office Web Apps Server 的最新小小小，稱為「Office Online Server」，這是 Lync Server 2013 的支援。 如需詳細資訊，請參閱 <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server 檔</A>。



</div>

本檔涵蓋下列主題區域：

  - [設定 Lync Server 2013 以使用 Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [驗證 Lync Server 2013 中的 Office Web Apps Server 設定](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [設定 Lync Server 2013 的用戶端以搭配 Office Web Apps Server 使用](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

