---
title: Lync Server 2013 會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="828e3-102">Lync Server 2013 中的會議</span><span class="sxs-lookup"><span data-stu-id="828e3-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="828e3-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="828e3-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="828e3-104">透過 Lync Server 2013 中的整合式會議，使用者可以共同作業、共用資訊，以及即時協調他們的工作。</span><span class="sxs-lookup"><span data-stu-id="828e3-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="828e3-105">您所有的使用者都可以使用全面的自發共同作業、排程的會議及會議工具。</span><span class="sxs-lookup"><span data-stu-id="828e3-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="828e3-106">語音及視訊會議功能可從任何網際網路連線的位置使用，而離開電腦的使用者可以使用公用的交換電話網絡（PSTN）電話撥入來參與音訊會議。</span><span class="sxs-lookup"><span data-stu-id="828e3-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="828e3-107">[會議工具] 集成在 Outlook 中，您可以透過按一下滑鼠來排程會議或啟動臨時會議，也可讓出席者輕鬆加入會議。</span><span class="sxs-lookup"><span data-stu-id="828e3-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="828e3-108">Web 用戶端將豐富的會議功能延伸到不執行桌上出版 Lync 的參與者。</span><span class="sxs-lookup"><span data-stu-id="828e3-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="828e3-109">音訊與視訊會議</span><span class="sxs-lookup"><span data-stu-id="828e3-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="828e3-110">Lync Server 提供傳統音訊橋接服務使用者所熟悉的使用者經驗，包括 PSTN 撥入服務與按鍵式通話控制命令。</span><span class="sxs-lookup"><span data-stu-id="828e3-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="828e3-111">同時，它會整合功能強大的排程、加入與管理功能，只適用于整合式整合通訊平臺。</span><span class="sxs-lookup"><span data-stu-id="828e3-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="828e3-112">只要按一下滑鼠，使用者就可以從 Outlook 排程會議。</span><span class="sxs-lookup"><span data-stu-id="828e3-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="828e3-113">詳細資料（例如會議時間、地點和出席者），請遵循熟悉的 Outlook 範本。</span><span class="sxs-lookup"><span data-stu-id="828e3-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="828e3-114">此外，會議通話的特定資訊，例如撥入號碼、會議 Id，以及個人識別碼（PIN）提醒，都會自動填入。</span><span class="sxs-lookup"><span data-stu-id="828e3-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="828e3-115">為了協助確保只有獲授權的人參與通話，Lync Server 提供多位參與者驗證等級。</span><span class="sxs-lookup"><span data-stu-id="828e3-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="828e3-116">使用 Lync 加入的使用者已經由 Active Directory 網域服務驗證，且不需要輸入 PIN、傳遞代碼或會議 ID。</span><span class="sxs-lookup"><span data-stu-id="828e3-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="828e3-117">Lync 簡化了視訊會議的使用者體驗，只要將影片併入整合的用戶端，就能順暢且輕鬆地排程會議，或透過影片進行升級。</span><span class="sxs-lookup"><span data-stu-id="828e3-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="828e3-118">Lync Server 可讓您只需一次按一下，就能輕鬆地將影片新增到標準通話中。</span><span class="sxs-lookup"><span data-stu-id="828e3-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="828e3-119">當在視頻通話或會議中有多個參與者時，每個使用者都可以同時查看最多五個其他使用者的影片，或者簡報者可以選擇只透過每個人看到的一個影片來源。</span><span class="sxs-lookup"><span data-stu-id="828e3-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="828e3-120">在高端電腦上執行 Lync 之使用者之間的對等呼叫支援高清晰度影片（解析度 1270 x 720; 長寬比16:9）和 VGA 影片（解析度 640 x 480; 長寬比4:3）。</span><span class="sxs-lookup"><span data-stu-id="828e3-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="828e3-121">由單一交談中的每個參與者所查看的解析度可能會有所不同，視每個使用者各自硬體的影片功能而定。</span><span class="sxs-lookup"><span data-stu-id="828e3-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="828e3-122">IT 管理員可以設定原則，以限制或停用用戶端上的高清或 VGA 影片，這要視電腦的功能、網路頻寬，以及相機是否能夠提供所需的解析度而定。</span><span class="sxs-lookup"><span data-stu-id="828e3-122">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution.</span></span> <span data-ttu-id="828e3-123">這些原則是透過頻帶內配來強制執行。</span><span class="sxs-lookup"><span data-stu-id="828e3-123">These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="828e3-124">網路會議</span><span class="sxs-lookup"><span data-stu-id="828e3-124">Web conferencing</span></span>

<span data-ttu-id="828e3-125">Lync Server 將會議共用功能（例如桌面、應用程式、附件、白板、投票和 PowerPoint）整合到精簡的 Lync 中。</span><span class="sxs-lookup"><span data-stu-id="828e3-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="828e3-126">在音訊或視訊會議中結合，結果就是一種非常輕鬆且易於進行的共同作業會話。</span><span class="sxs-lookup"><span data-stu-id="828e3-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="828e3-127">為了改善演示或查看 PowerPoint 簡報的使用者的整體體驗，Lync Server 2013 使用 Office Web Apps 來處理 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="828e3-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="828e3-128">使用者可以在 Lync 會議中使用白板共用圖片或複製及貼上文字。</span><span class="sxs-lookup"><span data-stu-id="828e3-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="828e3-129">簡報者可以在 Lync 會議中進行投票，徵求出席者的意見反應。</span><span class="sxs-lookup"><span data-stu-id="828e3-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="828e3-130">桌面共用可讓簡報者即時將任何視覺效果、應用程式、網頁、檔、軟體或部分桌面廣播至遠端參與者，直接從 Lync。</span><span class="sxs-lookup"><span data-stu-id="828e3-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="828e3-131">觀眾可以跟隨滑鼠移動與鍵盤輸入。</span><span class="sxs-lookup"><span data-stu-id="828e3-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="828e3-132">簡報者可以選擇共用整個畫面或只共用部分。</span><span class="sxs-lookup"><span data-stu-id="828e3-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="828e3-133">透過共用桌上型電腦，簡報者就能從任何位置在互動式產品或軟體示範中與他們的觀眾進行互動。</span><span class="sxs-lookup"><span data-stu-id="828e3-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="828e3-134">[應用程式共用] 可讓簡報者共用電腦上的軟體控制，而不會看到參與者意見反應或文字問題。</span><span class="sxs-lookup"><span data-stu-id="828e3-134">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions.</span></span> <span data-ttu-id="828e3-135">簡報者也可以將應用程式的控制權委派給會議參與者。</span><span class="sxs-lookup"><span data-stu-id="828e3-135">Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="828e3-136">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="828e3-136">Dial-in Conferencing</span></span>

<span data-ttu-id="828e3-137">對於不是使用個人電腦的使用者，有數種方法可加入 Lync Server 電話會議。</span><span class="sxs-lookup"><span data-stu-id="828e3-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="828e3-138">PSTN 使用者可以撥號存取號碼、存取會議橋接器，然後輸入會議 ID。</span><span class="sxs-lookup"><span data-stu-id="828e3-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="828e3-139">若要進行更安全的會議，您也可以要求使用者輸入其 PIN 來針對 Active Directory 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="828e3-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="828e3-140">Lync Server 也支援 Lync Phone Edition 裝置，這些裝置是由 Microsoft 合作夥伴提供的獨立 IP 電話裝置。</span><span class="sxs-lookup"><span data-stu-id="828e3-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

