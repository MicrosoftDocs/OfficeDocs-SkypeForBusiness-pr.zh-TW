---
title: Lync Server 2013：規劃會議
description: Lync Server 2013：規劃會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28e71d185b7be8971c451351aac60dcaaf7eaeda
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567329"
---
# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="c6256-103">在 Lync Server 2013 中規劃會議</span><span class="sxs-lookup"><span data-stu-id="c6256-103">Planning for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6256-104">_**主題上次修改日期：** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="c6256-104">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="c6256-105">Lync Server 2013 提供一組豐富的會議功能：</span><span class="sxs-lookup"><span data-stu-id="c6256-105">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="c6256-106">Web 會議，包含檔共同作業、應用程式共用和桌面共用。</span><span class="sxs-lookup"><span data-stu-id="c6256-106">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="c6256-107">Lync Server 2013 使用 Office Web Apps 與 Office Web apps Server 來處理 PowerPoint 簡報的共用及呈現。</span><span class="sxs-lookup"><span data-stu-id="c6256-107">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="c6256-108">如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱設定 [Office Web Apps server 與 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="c6256-108">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="c6256-109">音訊/視頻 (A/V) 會議，可讓使用者進行即時音訊或視訊會議，而不需要使用 Microsoft Live Meeting 服務或協力廠商音訊橋的外部服務。</span><span class="sxs-lookup"><span data-stu-id="c6256-109">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="c6256-110">電話撥入式會議，可讓使用者使用公用交換電話網路 (PSTN) 電話加入 Lync Server 2013 會議的音訊部分，而不需要協力廠商音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="c6256-110">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="c6256-111">立即訊息 (IM) 會議，其中有兩部以上的參與方在單一 IM 會話中進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c6256-111">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="c6256-112">如需 IM 會議的詳細資訊，請參閱 [在 Lync Server 2013 中規劃前端伺服器、立即訊息及顯示狀態](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="c6256-112">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="c6256-113">Lync Server 2013 支援排程會議和即時會議。</span><span class="sxs-lookup"><span data-stu-id="c6256-113">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="c6256-114">當您部署 Lync Server 2013 （前端伺服器）時，您可以選擇是否也部署 web 會議、A/V 會議和電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="c6256-114">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="c6256-115">IM 會議功能一定會在 Lync Server 2013 前端伺服器上自動與 IM 交談功能一起部署。</span><span class="sxs-lookup"><span data-stu-id="c6256-115">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6256-116">如果您的部署包含使用 Office Communicator 2007 R2 用戶端組織的會議 (包括 Live Meeting 主控台或 Microsoft Office Outlook 的會議增益集) ，當會議遷移至 Lync Server 2013 後，就會有下列限制：</span><span class="sxs-lookup"><span data-stu-id="c6256-116">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c6256-117">會議中的使用者將無法使用資料共同作業功能，包括檔共同作業、應用程式共用和桌面共用。</span><span class="sxs-lookup"><span data-stu-id="c6256-117">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="c6256-118">由於 Lync Server 2013 不支援 Office Communicator 2007 R2 用戶端，因此可能會發生穩定性問題。</span><span class="sxs-lookup"><span data-stu-id="c6256-118">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="c6256-119">若要避免這些問題，請使用 Lync 2013 的「Lync 2010」或「線上會議增益集」的線上會議增益集，以 Outlook 2010 或 Outlook 2013，重排任何組織使用 Office Communicator 2007 R2 用戶端組織的會議。</span><span class="sxs-lookup"><span data-stu-id="c6256-119">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="c6256-120">下列各節說明部署各種類型的會議功能（包括規劃程式、元件、硬體和軟體需求，以及部署程式）所需的專案。</span><span class="sxs-lookup"><span data-stu-id="c6256-120">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6256-121">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c6256-121">In This Section</span></span>

  - [<span data-ttu-id="c6256-122">Lync Server 2013 中的會議綜述</span><span class="sxs-lookup"><span data-stu-id="c6256-122">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="c6256-123">在 Lync Server 2013 中定義會議需求</span><span class="sxs-lookup"><span data-stu-id="c6256-123">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="c6256-124">Lync Server 2013 中的會議元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="c6256-124">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="c6256-125">Lync Server 2013 中的會議技術需求</span><span class="sxs-lookup"><span data-stu-id="c6256-125">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="c6256-126">Lync Server 2013 中會議的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="c6256-126">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="c6256-127">Lync Server 2013 中的大型會議支援</span><span class="sxs-lookup"><span data-stu-id="c6256-127">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

