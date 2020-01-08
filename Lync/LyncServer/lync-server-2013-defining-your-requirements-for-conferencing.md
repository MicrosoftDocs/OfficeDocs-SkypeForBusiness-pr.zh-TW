---
title: Lync Server 2013：定義會議需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60193673efff29ec877626a9c5c18be23507e6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="3f936-102">在 Lync Server 2013 中定義會議需求</span><span class="sxs-lookup"><span data-stu-id="3f936-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f936-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="3f936-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="3f936-104">決定要部署哪些會議功能時，您必須考慮您要提供給使用者的功能，以及您的網路頻寬功能。</span><span class="sxs-lookup"><span data-stu-id="3f936-104">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities.</span></span> <span data-ttu-id="3f936-105">下列問題清單可引導您完成會議規劃程式，以根據貴組織的需求來判斷您應該部署的會議功能。</span><span class="sxs-lookup"><span data-stu-id="3f936-105">The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="3f936-106">**您想要啟用網路會議，包括檔共同作業和應用程式共用？**</span><span class="sxs-lookup"><span data-stu-id="3f936-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="3f936-107">如果是這樣，您必須在 Microsoft Lync Server 2013、規劃工具或拓撲建立器中，為您的前端池啟用會議。</span><span class="sxs-lookup"><span data-stu-id="3f936-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="3f936-108">當您啟用會議時，您會同時啟用 [web 會議] 和 [A/V 會議]。</span><span class="sxs-lookup"><span data-stu-id="3f936-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="3f936-109">應用程式共用需要和使用更多的網路頻寬，而不是檔共同作業。</span><span class="sxs-lookup"><span data-stu-id="3f936-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="3f936-110">Lync Server 2013 提供控制每個應用程式共用會話的節流機制。</span><span class="sxs-lookup"><span data-stu-id="3f936-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="3f936-111">根據預設，這會設定為每個會話的 1.5 KB/秒。</span><span class="sxs-lookup"><span data-stu-id="3f936-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="3f936-112">如果您不想啟用應用程式共用，但想要檔共同作業，您可以啟用會議並使用會議原則來停用應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="3f936-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="3f936-113">如需有關設定會議原則的詳細資訊，請參閱[Lync Server 2013 中的會議原則](lync-server-2013-conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3f936-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="3f936-114">若要讓使用者能夠共用 PowerPoint 簡報，您需要設定 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f936-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="3f936-115">如需有關設定 Office Web Apps Server 的詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="3f936-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="3f936-116">**您想要啟用 A/V 會議嗎？**</span><span class="sxs-lookup"><span data-stu-id="3f936-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="3f936-117">如果是這樣，您必須在 Lync Server 2013、規劃工具或拓撲建立器中，為您的前端池啟用會議。</span><span class="sxs-lookup"><span data-stu-id="3f936-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="3f936-118">當您啟用會議時，您會同時啟用 [web 會議] 和 [A/V 會議]。</span><span class="sxs-lookup"><span data-stu-id="3f936-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="3f936-119">A/V 會議需要並使用比 web 會議更多的網路頻寬（包括檔共同作業和應用程式共用）。</span><span class="sxs-lookup"><span data-stu-id="3f936-119">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing).</span></span> <span data-ttu-id="3f936-120">如果您不想啟用 A/V 會議，但想要啟用網路會議，您可以啟用會議並使用會議原則來停用 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="3f936-120">If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="3f936-121">如果您想要啟用音訊會議，但不想要啟用視訊會議，您可以啟用 A/V 會議，並使用會議原則來避免視訊會議。</span><span class="sxs-lookup"><span data-stu-id="3f936-121">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences.</span></span> <span data-ttu-id="3f936-122">或者，您也可以啟用 A/V 會議，並僅允許特定使用者開始或參與 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="3f936-122">Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f936-123">您不需要使用企業語音，您就可以使用 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="3f936-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="3f936-124">如果您啟用 A/V 會議，即使您在電話方案中使用 PBX，您的使用者也可以在會議中加入音訊。</span><span class="sxs-lookup"><span data-stu-id="3f936-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="3f936-125">**您想要讓使用者在使用 PSTN 手機時加入會議的音訊部分嗎？**</span><span class="sxs-lookup"><span data-stu-id="3f936-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="3f936-126">如果是，請部署並啟用電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="3f936-126">If so, deploy and enable dial-in conferencing.</span></span> <span data-ttu-id="3f936-127">您的組織內部和外部受邀的使用者，都可以使用 PSTN 手機加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="3f936-127">Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="3f936-128">**您想要讓 Lync Server 2013 用戶端的外部使用者加入您已啟用的會議類型嗎？**</span><span class="sxs-lookup"><span data-stu-id="3f936-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="3f936-129">如果是這樣，您應該部署邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f936-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="3f936-130">透過允許外部參與會議，您可以將投資最大化在 Lync Server 2013 中。</span><span class="sxs-lookup"><span data-stu-id="3f936-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="3f936-131">例如，擁有 Lync Server 2013 的膝上型電腦可以從在家、機場或客戶網站上的任何位置加入會議。</span><span class="sxs-lookup"><span data-stu-id="3f936-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="3f936-132">此外，部署邊緣伺服器之後，您可以建立與其他組織的聯盟關聯，例如您的客戶或廠商，以及這些組織的使用者可以更輕鬆地與您的使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="3f936-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="3f936-133">如需有關部署邊緣伺服器的詳細資訊，請參閱在 lync server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)，以及[在 lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3f936-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="3f936-134">如需啟用 Office Web Apps Server 外部 access 的詳細資料，請參閱[使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps 伺服器](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)。</span><span class="sxs-lookup"><span data-stu-id="3f936-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="3f936-135">**您想要控制可加入 Lync Server 2013 會議的用戶端嗎？**</span><span class="sxs-lookup"><span data-stu-id="3f936-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="3f936-136">如果是這樣，您應該設定會議加入頁面，以便只提供您想要支援的用戶端選項。</span><span class="sxs-lookup"><span data-stu-id="3f936-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="3f936-137">每當使用者按一下連結加入排程的會議時，Lync Server 2013 就會偵測到電腦上是否已安裝用戶端。</span><span class="sxs-lookup"><span data-stu-id="3f936-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="3f936-138">接著，它會啟動預設用戶端，並開啟 [會議加入] 頁面，其中包含備用用戶端的連結。</span><span class="sxs-lookup"><span data-stu-id="3f936-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="3f936-139">[會議加入] 頁面總是包含使用 Microsoft Lync Web App 的選項。</span><span class="sxs-lookup"><span data-stu-id="3f936-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="3f936-140">除了此選項之外，您還可以決定是否要包含出席者的連結，以及舊版的 Communicator。</span><span class="sxs-lookup"><span data-stu-id="3f936-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="3f936-141">如需詳細資訊，請參閱[在 Lync Server 2013 中設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3f936-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3f936-142">本節內容</span><span class="sxs-lookup"><span data-stu-id="3f936-142">In This Section</span></span>

  - [<span data-ttu-id="3f936-143">Lync Server 2013 的網路會議需求</span><span class="sxs-lookup"><span data-stu-id="3f936-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="3f936-144">Lync Server 2013 中的 A/V 會議需求</span><span class="sxs-lookup"><span data-stu-id="3f936-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="3f936-145">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="3f936-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3f936-146">請參閱</span><span class="sxs-lookup"><span data-stu-id="3f936-146">See Also</span></span>


[<span data-ttu-id="3f936-147">Lync Server 2013 中的會議規劃</span><span class="sxs-lookup"><span data-stu-id="3f936-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="3f936-148">Lync Server 2013 中的會議部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="3f936-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

