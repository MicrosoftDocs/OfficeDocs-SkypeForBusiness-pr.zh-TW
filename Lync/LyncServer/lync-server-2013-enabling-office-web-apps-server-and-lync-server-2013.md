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
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="d4b89-103">設定 Office Web Apps Server 與 Lync Server 2013 的整合</span><span class="sxs-lookup"><span data-stu-id="d4b89-103">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b89-104">_**主題上次修改日期：** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="d4b89-104">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="d4b89-105">Lync Server 2013 採用 Office Web Apps Server 來處理 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="d4b89-105">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="d4b89-106">如需此方法之優點的詳細資訊，請參閱 [Lync Server 2013 中的 web 會議概述](lync-server-2013-web-conferencing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b89-106">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="d4b89-107">若要使用這些新功能，管理員必須安裝 Office Web Apps Server，而且必須設定 Lync Server 2013，以與 Office Web Apps Server 通訊。</span><span class="sxs-lookup"><span data-stu-id="d4b89-107">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="d4b89-108">本檔提供如何設定 Lync Server 2013 以搭配 Office Web Apps Server 使用的資訊。</span><span class="sxs-lookup"><span data-stu-id="d4b89-108">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="d4b89-109">本檔不提供的資訊，是有關如何安裝 Office Web Apps Server 本身的資訊，請參閱。如需相關資訊，請參閱 Microsoft Office Web Apps 部署網站 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。</span><span class="sxs-lookup"><span data-stu-id="d4b89-109">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="d4b89-110">該指南包含 Office Web Apps Server 的完整必要資訊。請注意，Office Web Apps Server 應該安裝在未執行 Lync Server、Microsoft SQL Server 或任何其他伺服器應用程式的獨立電腦上。</span><span class="sxs-lookup"><span data-stu-id="d4b89-110">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="d4b89-111"> (您不能在該電腦上安裝任何版本的 Microsoft Office。 ) 任何用來執行 Office Web Apps Server 的電腦也必須安裝一組特定的軟體， (包括 .NET Framework 4.5 和 Windows PowerShell 3.0) ;Microsoft Office Web Apps 部署網站會詳細討論這些需求，以及設定憑證和網際網路資訊服務 (IIS) 的相關資訊 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。</span><span class="sxs-lookup"><span data-stu-id="d4b89-111">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4b89-112">Office Web Apps Server 的最新小小小，稱為「Office Online Server」，這是 Lync Server 2013 的支援。</span><span class="sxs-lookup"><span data-stu-id="d4b89-112">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="d4b89-113">如需詳細資訊，請參閱 <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server 檔</A>。</span><span class="sxs-lookup"><span data-stu-id="d4b89-113">For more detail, refer to the <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="d4b89-114">本檔涵蓋下列主題區域：</span><span class="sxs-lookup"><span data-stu-id="d4b89-114">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="d4b89-115">設定 Lync Server 2013 以使用 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="d4b89-115">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="d4b89-116">使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="d4b89-116">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="d4b89-117">驗證 Lync Server 2013 中的 Office Web Apps Server 設定</span><span class="sxs-lookup"><span data-stu-id="d4b89-117">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="d4b89-118">設定 Lync Server 2013 的用戶端以搭配 Office Web Apps Server 使用</span><span class="sxs-lookup"><span data-stu-id="d4b89-118">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

