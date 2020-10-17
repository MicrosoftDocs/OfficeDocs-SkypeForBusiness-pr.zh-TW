---
title: Lync Server 2013 A/V 會議概述
description: Lync Server 2013 A/V 會議概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76ef4f76a4df0187a7c36394b2c95e99876df9be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568959"
---
# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="a9444-103">Lync Server 2013 中的 A/V 會議綜述</span><span class="sxs-lookup"><span data-stu-id="a9444-103">Overview of A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9444-104">_**主題上次修改日期：** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="a9444-104">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="a9444-105">A/V 會議可讓您的使用者之間進行即時音訊和視頻通訊。</span><span class="sxs-lookup"><span data-stu-id="a9444-105">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="a9444-106">部署會議時，您可以選擇同時啟用及使用 Web 會議和 A/V 會議，或僅啟用及使用 Web 會議。</span><span class="sxs-lookup"><span data-stu-id="a9444-106">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="a9444-107">若要規劃 A/V 會議，您需要了解組織需要的會議媒體類型及其所需的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="a9444-107">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="a9444-108">這可能包括音訊、影片及全景影片。</span><span class="sxs-lookup"><span data-stu-id="a9444-108">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="a9444-109">在您為使用者啟用 A/V 會議之前，請先確定您的網路可以處理所產生的負載。</span><span class="sxs-lookup"><span data-stu-id="a9444-109">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="a9444-110">若沒有足夠的網路頻寬，使用者體驗可能會嚴重降低。</span><span class="sxs-lookup"><span data-stu-id="a9444-110">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="a9444-111">您可以使用 [通話許可控制] (CAC) 管理 A/V 會議所使用的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="a9444-111">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="a9444-112">這對限制網路很重要，例如中央和分支網站之間有限的頻寬連結。</span><span class="sxs-lookup"><span data-stu-id="a9444-112">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="a9444-113">如需詳細資訊，請參閱 [Lync Server 2013 中的 [通話許可控制](lync-server-2013-overview-of-call-admission-control.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9444-113">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="a9444-114">如需媒體頻寬需求的詳細資訊，請參閱 [Lync Server 2013 中媒體流量的網路頻寬需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。</span><span class="sxs-lookup"><span data-stu-id="a9444-114">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="a9444-115">如果您在網路中部署音訊會議，您的使用者將需要諸如耳機等音訊裝置參加音訊會議。</span><span class="sxs-lookup"><span data-stu-id="a9444-115">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="a9444-116">如果您部署了影片會議，您必須部署影片裝置，例如使用者的網路攝像機。</span><span class="sxs-lookup"><span data-stu-id="a9444-116">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="a9444-117">我們建議您針對所有的裝置類型，針對由 Microsoft 認證的 UC) 裝置，使用整合通訊 (，以確保最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="a9444-117">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="a9444-118">如需 UC 驗證裝置的詳細資訊，請參閱的「電話和裝置（Lync）」 [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861) 。</span><span class="sxs-lookup"><span data-stu-id="a9444-118">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="a9444-119">針對音訊或視頻裝置、裝置部署和使用者訓練，都是您考慮和規劃的重要步驟。</span><span class="sxs-lookup"><span data-stu-id="a9444-119">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="a9444-120">下列各節說明音訊和視訊會議的功能，包括有關管理頻寬及選擇適當用戶端的資訊。</span><span class="sxs-lookup"><span data-stu-id="a9444-120">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="a9444-121">音訊會議功能</span><span class="sxs-lookup"><span data-stu-id="a9444-121">Audio Conferencing Features</span></span>

<span data-ttu-id="a9444-122">Lync Server 2013 提供數種功能，可讓您用來為使用者設定語音會議體驗，包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="a9444-122">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="a9444-123">**物件靜音**    簡報者可以使用此設定來靜音會議中所有的音訊參與者，並將會議置於非簡報者無法自行取消靜音的狀態。</span><span class="sxs-lookup"><span data-stu-id="a9444-123">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="a9444-124">**會議進入/出口宣告**    如果您已啟用電話撥入式會議，簡報者可以使用此設定開啟或關閉進入和關閉宣告，以在會議進行中時，將干擾減至最小。</span><span class="sxs-lookup"><span data-stu-id="a9444-124">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="a9444-125">**以撥出**     方式新增使用者簡報者和授與出席者的許可權，可將 PSTN 號碼新增至會議，並讓會議撥出至這些號碼。</span><span class="sxs-lookup"><span data-stu-id="a9444-125">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="a9444-126">影片會議功能</span><span class="sxs-lookup"><span data-stu-id="a9444-126">Video Conferencing Features</span></span>

<span data-ttu-id="a9444-127">Lync Server 2013 提供數種功能，可讓您用來為使用者設定影片會議體驗，包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="a9444-127">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="a9444-128">**圖庫視圖**    在包含超過兩個人的影片會議中，使用者會自動查看會議中的所有人。</span><span class="sxs-lookup"><span data-stu-id="a9444-128">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="a9444-129">如果會議的參與者超過五位，則最活躍的參與者影片會出現在頂端列，而只有照片顯示給其他參與者。</span><span class="sxs-lookup"><span data-stu-id="a9444-129">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="a9444-130">預設會開啟多方影片。</span><span class="sxs-lookup"><span data-stu-id="a9444-130">Multiparty video is turned on by default.</span></span> <span data-ttu-id="a9444-131">如需設定或關閉多方影片的詳細資訊，請參閱 [在 Lync Server 2013 中設定影片頻寬](lync-server-2013-configuring-video-bandwidth.md)。</span><span class="sxs-lookup"><span data-stu-id="a9444-131">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="a9444-132">**全景影片**    如果在會議室中安裝 RoundTable 的視訊會議裝置，這項功能會提供會議室的完整360度視圖。</span><span class="sxs-lookup"><span data-stu-id="a9444-132">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="a9444-133">只有 RoundTable 裝置可以使用全景影片帶。</span><span class="sxs-lookup"><span data-stu-id="a9444-133">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="a9444-134">**僅限簡報者影片模式**    簡報者可以設定會議，只顯示簡報者的影片。</span><span class="sxs-lookup"><span data-stu-id="a9444-134">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="a9444-135">這會在多個視頻資料流程可供使用，並且鎖定于不同來源時，防止大型會議中的干擾。</span><span class="sxs-lookup"><span data-stu-id="a9444-135">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="a9444-136">這種模式也適用于 RoundTable 裝置所捕捉及提供的影片。</span><span class="sxs-lookup"><span data-stu-id="a9444-136">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="a9444-137">**HD 影片**    使用者可在雙方通話和多方會議中體驗高達 HD 1080P 的解析度。</span><span class="sxs-lookup"><span data-stu-id="a9444-137">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="a9444-138">**影片聚光燈**    簡報者可以設定會議，使會議中的其他參與者只會看到來自選取之參加影片來源之參與者的影片。</span><span class="sxs-lookup"><span data-stu-id="a9444-138">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="a9444-139">這種模式也適用于透過顯示全景影片 RoundTable 裝置所捕獲並提供的影片。</span><span class="sxs-lookup"><span data-stu-id="a9444-139">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

