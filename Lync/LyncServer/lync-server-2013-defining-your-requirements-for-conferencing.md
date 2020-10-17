---
title: Lync Server 2013：定義會議需求
description: Lync Server 2013：定義會議需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 009a80d2fd48341723743bb6a06ad2ee05289a6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545409"
---
# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="84f7a-103">在 Lync Server 2013 中定義會議需求</span><span class="sxs-lookup"><span data-stu-id="84f7a-103">Defining your requirements for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84f7a-104">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="84f7a-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="84f7a-p101">您在決定要部署哪些會議功能時，需要考量要提供給使用者的功能，以及網路頻寬功能。以下問題清單可在您的會議功能規劃期間，逐步引導您依據組織需求決定應該要部署的各項會議功能。</span><span class="sxs-lookup"><span data-stu-id="84f7a-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="84f7a-107">**您想要啟用 Web 會議功能，並納入文件共同作業及應用程式共用功能嗎？**</span><span class="sxs-lookup"><span data-stu-id="84f7a-107">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="84f7a-108">如果是的話，您必須在 Microsoft Lync Server 2013、規劃工具或拓撲產生器中啟用前端集區的會議。</span><span class="sxs-lookup"><span data-stu-id="84f7a-108">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="84f7a-109">啟用會議功能時，會同時啟用 Web 會議功能及 A/V 會議功能。</span><span class="sxs-lookup"><span data-stu-id="84f7a-109">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="84f7a-110">應用程式共用功能需要使用比文件共同作業更多的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="84f7a-110">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="84f7a-111">Lync Server 2013 提供節流機制來控制每個應用程式共用會話。</span><span class="sxs-lookup"><span data-stu-id="84f7a-111">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="84f7a-112">預設會將每一個工作階段的節流機制設為 1.5 KB/秒。</span><span class="sxs-lookup"><span data-stu-id="84f7a-112">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="84f7a-113">若您不想要啟用應用程式共用，但需要文件共同作業功能的話，可以啟用會議功能並使用會議原則來停用應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="84f7a-113">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="84f7a-114">如需設定會議原則的詳細資訊，請參閱 [Lync Server 2013 中的會議原則](lync-server-2013-conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="84f7a-114">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="84f7a-115">若要讓使用者能夠共用 PowerPoint 簡報，您必須設定 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="84f7a-115">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="84f7a-116">如需設定 Office Web Apps Server 的詳細資訊，請參閱設定 [Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="84f7a-116">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="84f7a-117">**您想要啟用 A/V 會議功能嗎？**</span><span class="sxs-lookup"><span data-stu-id="84f7a-117">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="84f7a-118">如果是的話，您必須在 Lync Server 2013、規劃工具或拓撲產生器中啟用前端集區的會議。</span><span class="sxs-lookup"><span data-stu-id="84f7a-118">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="84f7a-119">啟用會議功能時，會同時啟用 Web 會議功能及 A/V 會議功能。</span><span class="sxs-lookup"><span data-stu-id="84f7a-119">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="84f7a-p107">A/V 會議功能需要使用比 Web 會議 (包括文件共同作業和應用程式共用) 更多的網路頻寬。若您不想要啟用 A/V 會議功能，但要啟用 Web 會議功能的話，可以啟用會議功能並使用會議原則來停用 A/V 會議功能。</span><span class="sxs-lookup"><span data-stu-id="84f7a-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="84f7a-p108">若您想要啟用音訊會議功能，但不要視訊會議功能，可以啟用 A/V 會議功能並使用會議原則來停用視訊會議功能。或者，您可以啟用 A/V 會議功能並僅允許特定使用者啟動或參與 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="84f7a-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84f7a-124">您不需要使用企業語音，即可使用 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="84f7a-124">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="84f7a-125">若您啟用 A/V 會議功能，即使您的電話解決方案使用 PBX，使用者只要有音訊裝置，就可以在會議中新增音訊。</span><span class="sxs-lookup"><span data-stu-id="84f7a-125">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="84f7a-126">**您想要讓使用 PSTN 電話的使用者加入會議的音訊部分嗎？**</span><span class="sxs-lookup"><span data-stu-id="84f7a-126">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="84f7a-p110">如果是的話，請部署並啟用電話撥入式會議功能。這時，來自組織內外的受邀使用者就可以透過 PSTN 電話加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="84f7a-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="84f7a-129">**您想要讓具有 Lync Server 2013 用戶端的外部使用者加入您已啟用的會議類型嗎？**</span><span class="sxs-lookup"><span data-stu-id="84f7a-129">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="84f7a-130">如果是的話，請部署 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="84f7a-130">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="84f7a-131">透過允許外部參與會議，您可以在 Lync Server 2013 中達到最大的投資。</span><span class="sxs-lookup"><span data-stu-id="84f7a-131">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="84f7a-132">例如，擁有 Lync Server 2013 的可擕式電腦的使用者可以加入會議，不論他們身在家裡、機場或客戶網站。</span><span class="sxs-lookup"><span data-stu-id="84f7a-132">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="84f7a-133">此外，只要部署了 Edge Server，您就可以和其他組織 (例如您的客戶或廠商) 建立同盟關係，這些組織的使用者可以輕鬆和您的使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="84f7a-133">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="84f7a-134">如需部署 Edge server 的詳細資訊，請參閱在 lync server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md) 和 [部署 lync server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="84f7a-134">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="84f7a-135">如需啟用 Office Web Apps Server 的外部存取的詳細資訊，請參閱 [使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)。</span><span class="sxs-lookup"><span data-stu-id="84f7a-135">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="84f7a-136">**您想要控制可加入 Lync Server 2013 會議的用戶端嗎？**</span><span class="sxs-lookup"><span data-stu-id="84f7a-136">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="84f7a-137">如果是的話，請設定 [會議加入] 頁面，限制您想要支援的用戶端選項。</span><span class="sxs-lookup"><span data-stu-id="84f7a-137">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="84f7a-138">每當使用者按一下連結加入排程的會議時，Lync Server 2013 便會偵測是否已在電腦上安裝用戶端。</span><span class="sxs-lookup"><span data-stu-id="84f7a-138">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="84f7a-139">這時，它會啟動預設的用戶端並開啟 [會議加入] 頁面，其中包含其他用戶端的連結。</span><span class="sxs-lookup"><span data-stu-id="84f7a-139">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="84f7a-140">[會議加入] 頁面一定會包含使用 Microsoft Lync Web App 的選項。</span><span class="sxs-lookup"><span data-stu-id="84f7a-140">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="84f7a-141">除了此選項之外，您還可以決定是否要包含出席者和舊版 Communicator 的連結。</span><span class="sxs-lookup"><span data-stu-id="84f7a-141">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="84f7a-142">如需詳細資訊，請參閱 [在 Lync Server 2013 中設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md)。</span><span class="sxs-lookup"><span data-stu-id="84f7a-142">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84f7a-143">本章節內容</span><span class="sxs-lookup"><span data-stu-id="84f7a-143">In This Section</span></span>

  - [<span data-ttu-id="84f7a-144">Lync Server 2013 中的 Web 會議需求</span><span class="sxs-lookup"><span data-stu-id="84f7a-144">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="84f7a-145">Lync Server 2013 中的 A/V 會議需求</span><span class="sxs-lookup"><span data-stu-id="84f7a-145">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="84f7a-146">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="84f7a-146">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84f7a-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="84f7a-147">See Also</span></span>


[<span data-ttu-id="84f7a-148">在 Lync Server 2013 中規劃會議</span><span class="sxs-lookup"><span data-stu-id="84f7a-148">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="84f7a-149">Lync Server 2013 中會議的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="84f7a-149">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

