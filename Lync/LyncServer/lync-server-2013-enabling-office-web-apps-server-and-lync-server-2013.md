---
title: Lync Server 2013：啟用 Office Web Apps Server 與 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a88a9a1649d8842c9c2c4a1f55aefcfc7853e05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>設定 Office Web Apps Server 與 Lync Server 2013 的整合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-08-19_

Lync Server 2013 使用 Office Web Apps 伺服器來處理 PowerPoint 簡報。 如需此方法的優點資訊，請參閱[Lync Server 2013 中的 web 會議概覽](lync-server-2013-web-conferencing-overview.md)。

若要使用這些新功能，系統管理員必須安裝 Office Web Apps 伺服器，而且必須設定 Lync Server 2013 與 Office Web Apps 伺服器進行通訊。 本檔提供如何設定 Lync Server 2013 以搭配 Office Web Apps 伺服器使用的相關資訊。 本檔不提供的內容是如何安裝 Office Web Apps Server 本身的資訊;如需相關資訊，請參閱 Microsoft Office Web Apps 部署網站<http://go.microsoft.com/fwlink/p/?linkid=257525>。 該指南包括完整的 Office Web Apps 伺服器必備資訊;請注意，Office Web Apps 伺服器應該安裝在未執行 Lync Server、Microsoft SQL Server 或任何其他伺服器應用程式的獨立電腦上。 （您不能在該電腦上安裝任何版本的 Microsoft Office）。任何用來執行 Office Web Apps Server 的電腦也必須安裝一組特定的軟體（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）;Microsoft Office Web Apps 部署網站中提供了這些需求，以及有關設定證書和網際網路資訊服務（IIS）的相關資訊<http://go.microsoft.com/fwlink/p/?linkid=257525>。

<div>


> [!NOTE]  
> Office Web Apps Server 的最新小版本命名為「Office Online Server」，而 Lync Server 2013 支援此伺服器。 如需詳細資訊，請參閱<A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server 檔</A>。



</div>

本檔涵蓋下列主題區域：

  - [將 Lync Server 2013 設定為使用 Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps 伺服器](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [驗證 Lync Server 2013 中的 Office Web Apps Server 設定](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [針對 Office Web Apps Server 所用的 Lync Server 2013 設定用戶端](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

