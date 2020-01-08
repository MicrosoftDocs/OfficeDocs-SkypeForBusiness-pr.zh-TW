---
title: Lync Server 2013：會議規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aff3eef21ca150f4ad6fc9bb2358c2ac81680fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="304ca-102">Lync Server 2013 中的會議規劃</span><span class="sxs-lookup"><span data-stu-id="304ca-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="304ca-103">_**主題上次修改日期：** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="304ca-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="304ca-104">Lync Server 2013 提供了一組豐富的會議功能：</span><span class="sxs-lookup"><span data-stu-id="304ca-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="304ca-105">網路會議，包括檔共同作業、應用程式共用和桌面共用。</span><span class="sxs-lookup"><span data-stu-id="304ca-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="304ca-106">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 伺服器來處理 PowerPoint 簡報的共用和轉譯。</span><span class="sxs-lookup"><span data-stu-id="304ca-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="304ca-107">如需安裝及設定 Office Web Apps 伺服器的詳細資料，請參閱設定[與 Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="304ca-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="304ca-108">音訊/視頻（A/V）會議，可讓使用者在不需要外部服務（例如 Microsoft Live Meeting 服務或協力廠商音訊橋接器）的情況下進行即時音訊或視訊會議。</span><span class="sxs-lookup"><span data-stu-id="304ca-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="304ca-109">[電話撥入式會議] 可讓使用者使用公開的交換電話網絡（PSTN）電話（不需要協力廠商音訊會議提供者）加入 Lync Server 2013 會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="304ca-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="304ca-110">[立即訊息（IM）會議]，其中，有兩個以上雙方在單一 IM 會話中進行通訊。</span><span class="sxs-lookup"><span data-stu-id="304ca-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="304ca-111">如需 IM 會議的詳細資訊，請參閱[在 Lync Server 2013 中規劃前端伺服器、立即訊息和目前狀態](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="304ca-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="304ca-112">Lync Server 2013 支援排程的會議與臨時會議。</span><span class="sxs-lookup"><span data-stu-id="304ca-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="304ca-113">當您部署 Lync Server 2013 （前端伺服器）時，您可以選擇是否還要部署網路會議、A/V 會議和電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="304ca-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="304ca-114">IM 會議功能在 Lync Server 2013 前端伺服器上會自動部署，以及 IM 交談功能。</span><span class="sxs-lookup"><span data-stu-id="304ca-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="304ca-115">如果您的部署包含使用 Office Communicator 2007 R2 用戶端（包括 Live Meeting 主控台或 Microsoft Office Outlook 的會議增益集）組織的會議，則在將會議遷移至 Lync 之後，就會有下列限制：Server 2013：</span><span class="sxs-lookup"><span data-stu-id="304ca-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="304ca-116">會議中的使用者將無法使用資料共同作業功能，包括檔共同作業、應用程式共用和桌面共用。</span><span class="sxs-lookup"><span data-stu-id="304ca-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="304ca-117">在 Lync Server 2013 不支援 Office Communicator 2007 R2 用戶端後，可能會發生穩定性問題。</span><span class="sxs-lookup"><span data-stu-id="304ca-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="304ca-118">若要避免這些問題，請使用適用于 lync 2013 的線上會議增益集（Lync 2010 或線上會議增益集），重新安排使用 Office Communicator 2007 R2 用戶端與 Outlook 2010 或 Outlook 2013 組織的任何會議。</span><span class="sxs-lookup"><span data-stu-id="304ca-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="304ca-119">下列各節說明部署各種類型的會議功能所需的專案，包括規劃程式、元件、硬體和軟體需求，以及部署程式。</span><span class="sxs-lookup"><span data-stu-id="304ca-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="304ca-120">本節內容</span><span class="sxs-lookup"><span data-stu-id="304ca-120">In This Section</span></span>

  - [<span data-ttu-id="304ca-121">Lync Server 2013 中的會議概觀</span><span class="sxs-lookup"><span data-stu-id="304ca-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="304ca-122">在 Lync Server 2013 中定義會議需求</span><span class="sxs-lookup"><span data-stu-id="304ca-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="304ca-123">Lync Server 2013 中的會議元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="304ca-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="304ca-124">Lync Server 2013 中會議的技術需求</span><span class="sxs-lookup"><span data-stu-id="304ca-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="304ca-125">Lync Server 2013 中的會議部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="304ca-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="304ca-126">Lync Server 2013 中的大型會議支援</span><span class="sxs-lookup"><span data-stu-id="304ca-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

