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
ms.openlocfilehash: 25c015397b1c29bec50f05feeab4f21d54d3f1e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="0188e-102">Lync Server 2013 中的會議</span><span class="sxs-lookup"><span data-stu-id="0188e-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0188e-103">_**主題上次修改日期：** 2012年-09-11_</span><span class="sxs-lookup"><span data-stu-id="0188e-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="0188e-104">與整合 Lync Server 2013 中的會議，使用者可以進行共同作業、 共用的詳細資訊，及協調他們即時的努力。</span><span class="sxs-lookup"><span data-stu-id="0188e-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="0188e-105">所有使用者都可以完整使用自發性共同作業、排程會議及會議工具。</span><span class="sxs-lookup"><span data-stu-id="0188e-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="0188e-106">從任何具有網際網路連線的位置都可以使用語音及視訊會議功能，而離開電腦的使用者使用公用電話交換網路 (PSTN) 電話撥入，就可以參與音訊會議。</span><span class="sxs-lookup"><span data-stu-id="0188e-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="0188e-107">會議工具整合到 Outlook 啟用召集人可以排程會議或啟動即席會議，只要按一下，並也讓一樣簡單的出席者加入。</span><span class="sxs-lookup"><span data-stu-id="0188e-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="0188e-108">網頁用戶端會延伸至未執行 Lync 的桌上型版本的參與者的豐富的會議功能。</span><span class="sxs-lookup"><span data-stu-id="0188e-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="0188e-109">音訊與視訊會議</span><span class="sxs-lookup"><span data-stu-id="0188e-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="0188e-110">Lync Server 提供的傳統音訊橋接器服務包括 PSTN 電話撥入式服務使用按鍵式通話控制命令的使用者熟悉的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="0188e-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="0188e-111">同時，包含只有整合式整合通訊平台才提供的強大排程、加入及管理功能。</span><span class="sxs-lookup"><span data-stu-id="0188e-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="0188e-112">只要按一下，使用者可以排程從 Outlook 會議。</span><span class="sxs-lookup"><span data-stu-id="0188e-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="0188e-113">詳細資料，例如會議時間、 位置和出席者，請遵循熟悉 Outlook 範本。</span><span class="sxs-lookup"><span data-stu-id="0188e-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="0188e-114">此外，會自動填入特定電話會議的資訊 (如撥入號碼、會議 ID 及個人識別碼 (PIN) 提醒)。</span><span class="sxs-lookup"><span data-stu-id="0188e-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="0188e-115">為了協助確保只有授權的使用者參與的通話，Lync Server 提供多個層級的驗證的參與者。</span><span class="sxs-lookup"><span data-stu-id="0188e-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="0188e-116">使用 Lync 加入的使用者已經通過驗證的 Active Directory 網域服務，且不需要輸入 pin 碼，通過程式碼，或會議 id。</span><span class="sxs-lookup"><span data-stu-id="0188e-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="0188e-117">Lync 藉由將影片納入整合用戶端，使排程含有視訊的會議或自發性地擴大為視訊主動順暢及簡單簡化視訊會議使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="0188e-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="0188e-118">Lync Server 可以輕鬆中只要按一下標準電話呼叫期間新增視訊。</span><span class="sxs-lookup"><span data-stu-id="0188e-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="0188e-119">視訊通話或會議有多位參與者時，每位使用者最多可以同時看到其他五位使用者的視訊，或者簡報者可以選擇讓所有人只能看到同一個視訊。</span><span class="sxs-lookup"><span data-stu-id="0188e-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="0188e-120">在高階電腦執行 Lync 使用者之間的對等通話支援高畫質視訊 （解析度 1270 x 720，長寬比 16:9） 及 VGA 視訊 （解析度為 640 x 480，長寬比為 4:3）。</span><span class="sxs-lookup"><span data-stu-id="0188e-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="0188e-121">單一交談中每位參與者所看到的解析度可能會不同，這取決於每位使用者各自硬體的視訊功能。</span><span class="sxs-lookup"><span data-stu-id="0188e-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="0188e-p108">IT 系統管理員可以設定原則來限制或停用用戶端上的高畫質或 VGA 視訊，而這取決於電腦功能、網路頻寬，以及是否有可提供必要解析度的相機。這些原則會透過頻內佈建執行。</span><span class="sxs-lookup"><span data-stu-id="0188e-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="0188e-124">Web 會議</span><span class="sxs-lookup"><span data-stu-id="0188e-124">Web conferencing</span></span>

<span data-ttu-id="0188e-125">Lync Server 整合到簡化的 Lync 會議的共用功能，例如桌面、 應用程式、 附件、 白板、 投票與 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="0188e-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="0188e-126">與音訊或視訊會議結合後，會產生十分逼真及容易使用的共同作業工作階段。</span><span class="sxs-lookup"><span data-stu-id="0188e-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="0188e-127">若要改善整體呈現或檢視 PowerPoint 簡報的使用者經驗，Lync Server 2013 會採用 Office Web Apps 才能處理的 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="0188e-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="0188e-128">使用者可以共用的圖片或複製並貼上文字 Lync 會議中使用白板。</span><span class="sxs-lookup"><span data-stu-id="0188e-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="0188e-129">簡報者可以進行投票 Lync 會議請求出席者的意見反應。</span><span class="sxs-lookup"><span data-stu-id="0188e-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="0188e-130">桌面共用，可讓簡報者將可直接從 Lync 即時，遠端參與者廣播任何視覺效果、 應用程式、 網頁、 文件、 軟體或其桌面的一部分。</span><span class="sxs-lookup"><span data-stu-id="0188e-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="0188e-131">會議成員可以看到滑鼠的移動及鍵盤輸入情形。</span><span class="sxs-lookup"><span data-stu-id="0188e-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="0188e-132">簡報者可以選擇共用整個螢幕或只共用部分螢幕。</span><span class="sxs-lookup"><span data-stu-id="0188e-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="0188e-133">透過共用桌面，簡報者可以讓會議成員從任何位置參與互動式產品或軟體示範。</span><span class="sxs-lookup"><span data-stu-id="0188e-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="0188e-p112">應用程式共用可讓簡報者共用其桌面上的軟體控制，而不會漏失參與者的反應或文字問題。簡報者也可以將應用程式的控制委派給會議參與者。</span><span class="sxs-lookup"><span data-stu-id="0188e-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="0188e-136">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="0188e-136">Dial-in Conferencing</span></span>

<span data-ttu-id="0188e-137">不使用個人電腦的使用者，有幾種方法可用於加入 Lync Server 電話會議。</span><span class="sxs-lookup"><span data-stu-id="0188e-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="0188e-138">PSTN 使用者可以撥打存取號碼，並存取會議橋接器，然後輸入會議 ID。</span><span class="sxs-lookup"><span data-stu-id="0188e-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="0188e-139">若要進行更安全的會議，使用者也可能需要輸入 PIN，以根據 Active Directory 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="0188e-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="0188e-140">Lync Server 也支援 Lync Phone Edition 裝置，也就是由 Microsoft 協力廠商所提供的獨立 IP 電話裝置。</span><span class="sxs-lookup"><span data-stu-id="0188e-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

