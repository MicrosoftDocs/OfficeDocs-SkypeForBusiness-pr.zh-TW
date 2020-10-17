---
title: Lync Server 2013：用戶端的新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6103c6cd8ae762402a94412a56eda107f43a58fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518200"
---
# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="b9b62-102">Lync Server 2013 中用戶端的新功能</span><span class="sxs-lookup"><span data-stu-id="b9b62-102">What's new for clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9b62-103">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="b9b62-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="b9b62-104">Microsoft Lync 2013 具有重新設計的使用者介面及重要的新功能。</span><span class="sxs-lookup"><span data-stu-id="b9b62-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="b9b62-105">針對系統管理員，用戶端現在已包含在 Office 安裝程式中，可提供更簡潔的方法來部署 Office 及自訂群組織中的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b9b62-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9b62-106">如需 Lync 2013 使用者介面更新的圖解視圖，請參閱的「Lync 2013 的新功能」 <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A> 。</span><span class="sxs-lookup"><span data-stu-id="b9b62-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="b9b62-107">與 Office 安裝程式整合</span><span class="sxs-lookup"><span data-stu-id="b9b62-107">Integration with Office Setup</span></span>

<span data-ttu-id="b9b62-108">Lync 2013 （支援來自 Outlook 郵件和共同作業用戶端的會議管理）的 Lync 2013 用戶端和線上會議增益集現在已包含在 Office 2013 安裝程式中。</span><span class="sxs-lookup"><span data-stu-id="b9b62-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="b9b62-109">在舊版的 Lync 和 Office Communicator 中，您可以使用 Windows Installer 內容自訂和控制 Office 安裝。</span><span class="sxs-lookup"><span data-stu-id="b9b62-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="b9b62-110">因為 Lync 2013 已與 Office 安裝程式整合，您可以使用下列方法來自訂 Lync 2013 安裝程式：</span><span class="sxs-lookup"><span data-stu-id="b9b62-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="b9b62-111">使用 Office 自訂工具 (OCT)</span><span class="sxs-lookup"><span data-stu-id="b9b62-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="b9b62-112">使用 Config.xml 執行安裝工作</span><span class="sxs-lookup"><span data-stu-id="b9b62-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="b9b62-113">使用安裝程式命令列選項</span><span class="sxs-lookup"><span data-stu-id="b9b62-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9b62-114">Lync 2013 安裝程式不會卸載舊版的 Lync 或 Office Communicator。</span><span class="sxs-lookup"><span data-stu-id="b9b62-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="b9b62-115">Lync 2013 用戶端會與其他 Lync 或 Office Communicator 用戶端同時安裝</span><span class="sxs-lookup"><span data-stu-id="b9b62-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="b9b62-116">如需詳細資訊，請參閱 [在 Lync Server 2013 中部署 Lync 用戶端](lync-server-2013-deploying-lync-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b62-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="b9b62-117">群組原則部署</span><span class="sxs-lookup"><span data-stu-id="b9b62-117">Group Policy Deployment</span></span>

<span data-ttu-id="b9b62-118">因為 Lync 2013 現在已包含在 Office 安裝程式中，所以部署 Lync 群組原則設定的方法已變更。</span><span class="sxs-lookup"><span data-stu-id="b9b62-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="b9b62-119">在舊版的 Lync 和 Office Communicator 中，您可以使用 Communicator 來定義群組原則設定，而在 Lync 2013 中，您現在可以使用 Lync ADMX 和 ADML 系統管理範本，以及 Office 群組原則系統管理範本提供。</span><span class="sxs-lookup"><span data-stu-id="b9b62-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="b9b62-120">如需詳細資訊，請參閱 [Lync 2013 的群組原則設定](lync-server-2013-group-policy-settings-for-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b62-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="b9b62-121">Outlook 排程增益集更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="b9b62-122">Lync 2013 的線上會議增益集包括會議邀請自訂及新的會議選項。</span><span class="sxs-lookup"><span data-stu-id="b9b62-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="b9b62-123">管理員可以藉由新增自訂標誌、支援 URL、法律免責聲明 URL 或自訂頁尾文字，自訂組織的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="b9b62-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="b9b62-124">如需詳細資訊，請參閱 [在 Lync Server 2013 中自訂線上會議增益集](lync-server-2013-customizing-the-online-meeting-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b62-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="b9b62-125">新的出席者靜音控制讓會議召集人可在排程會議時，將出席者音訊及視訊預設為靜音。</span><span class="sxs-lookup"><span data-stu-id="b9b62-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="b9b62-126">虛擬桌面基礎結構外掛程式</span><span class="sxs-lookup"><span data-stu-id="b9b62-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="b9b62-127">Lync 2013 用戶端現在支援虛擬桌面基礎結構 (VDI) 環境中的音訊和影片。</span><span class="sxs-lookup"><span data-stu-id="b9b62-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="b9b62-128">使用者可以將音訊和視訊裝置 (例如，耳機或相機) 連線至本機電腦 (例如，精簡型用戶端或重新設定功能的電腦)。</span><span class="sxs-lookup"><span data-stu-id="b9b62-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="b9b62-129">使用者可以連線至虛擬機器，登入虛擬機器上執行的 Lync 2013 用戶端，並參與即時音訊和視頻通訊，如同用戶端在本機執行。</span><span class="sxs-lookup"><span data-stu-id="b9b62-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="b9b62-130">在虛擬桌面環境中支援下列功能：</span><span class="sxs-lookup"><span data-stu-id="b9b62-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="b9b62-131">音訊及視訊的裝置整合，包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="b9b62-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="b9b62-132">裝置的通話控制</span><span class="sxs-lookup"><span data-stu-id="b9b62-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="b9b62-133">裝置上的狀態整合</span><span class="sxs-lookup"><span data-stu-id="b9b62-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="b9b62-134">多重 HID (人性化介面裝置) 支援</span><span class="sxs-lookup"><span data-stu-id="b9b62-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="b9b62-135">位置及緊急服務支援。</span><span class="sxs-lookup"><span data-stu-id="b9b62-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="b9b62-136">支援所有 Lync 形式，包括 IM、音訊、影片、應用程式共用、桌面共用、PowerPoint 共用、白板及檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="b9b62-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="b9b62-137">人對人通話及會議通話中的音訊及視訊支援。</span><span class="sxs-lookup"><span data-stu-id="b9b62-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="b9b62-138">如需部署 VDI 外掛程式的相關資訊，請參閱 [在 Lync Server 2013 中部署 LYNC VDI 外掛程式](lync-server-2013-deploying-the-lync-vdi-plug-in.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b62-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="b9b62-139">視訊增強功能</span><span class="sxs-lookup"><span data-stu-id="b9b62-139">Video Enhancements</span></span>

<span data-ttu-id="b9b62-140">許多新的功能大幅增強會議參與者的視訊體驗。</span><span class="sxs-lookup"><span data-stu-id="b9b62-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="b9b62-141">視訊中加入了臉部偵測及智慧框架增強功能，讓參與者的視訊會移動，將參與者保持在框架中心。</span><span class="sxs-lookup"><span data-stu-id="b9b62-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="b9b62-p107">雙方通話及多方會議現在支援高畫質視訊。使用者可以體驗到高達 HD 1080P 的解析度。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p107">High-definition video is now supported in two-party calls and multiparty conferences. Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="b9b62-144">參與者可以選取不同的會議配置：「圖庫檢視」會顯示所有參與者的圖片或視訊；「演講者檢視」會顯示會議內容以及僅目前演講者的視訊或圖片；「簡報檢視」僅會顯示會議內容；「精簡檢視」僅會顯示會議控制。</span><span class="sxs-lookup"><span data-stu-id="b9b62-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="b9b62-p108">透過新的圖庫功能，參與者可以同時見到多重視訊播放。如果會議有超過五位參與者，頂端列中會出現最積極參與者的視訊播放，對於其他參與者則顯示圖片。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p108">With the new Gallery feature, participants can see multiple video feeds at the same time. If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="b9b62-147">參與者可以使用視訊固定功能，選取讓一或多個可用的視訊播放隨時可見。</span><span class="sxs-lookup"><span data-stu-id="b9b62-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="b9b62-148">簡報者可以使用「視訊焦點」功能，選取某個人的視訊播放，讓會議中所有參與者僅看到該參與者。</span><span class="sxs-lookup"><span data-stu-id="b9b62-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="b9b62-149">聊天室整合</span><span class="sxs-lookup"><span data-stu-id="b9b62-149">Chat Room Integration</span></span>

<span data-ttu-id="b9b62-150">Lync 2013 現在會整合 Lync 2010 群組聊天先前提供的功能。</span><span class="sxs-lookup"><span data-stu-id="b9b62-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="b9b62-151">不再需要個別的群組聊天用戶端。</span><span class="sxs-lookup"><span data-stu-id="b9b62-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="b9b62-152">在 Lync 2013 中，使用者可以搜尋聊天室、將聊天室新增至其連絡人、監控聊天室活動，以及閱讀和張貼訊息。</span><span class="sxs-lookup"><span data-stu-id="b9b62-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="b9b62-153">使用者可以建立主題摘要，如果某人在他們其中一個聊天室中新增包含特定關鍵字的文章時，使用者就會收到通知。</span><span class="sxs-lookup"><span data-stu-id="b9b62-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="b9b62-154">透過新的 **[常設聊天室]** 選項頁面，使用者可以設定當有人在他們的聊天室張貼訊息時要套用的通知警示與音效。</span><span class="sxs-lookup"><span data-stu-id="b9b62-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="b9b62-155">Lync Web App 更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-155">Lync Web App Updates</span></span>

<span data-ttu-id="b9b62-156">Lync Web App 是 Lync Server 2013 會議的 Web 式會議用戶端。</span><span class="sxs-lookup"><span data-stu-id="b9b62-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="b9b62-157">在此版本中，對 Lync Web App 的電腦音訊和影片的加入，可為沒有在本機安裝 Lync 用戶端的任何人提供完整的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="b9b62-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="b9b62-158">會議參與者可存取所有共同作業與共用功能，以及簡報者會議控制。</span><span class="sxs-lookup"><span data-stu-id="b9b62-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="b9b62-159">當使用者嘗試加入會議，但沒有本機安裝的用戶端時，Lync Web App 隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="b9b62-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="b9b62-160">如果您想要允許其他選項加入會議，您可以設定會議加入頁面;請參閱部署檔中的 [Lync Server 2013 中的設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md) 。</span><span class="sxs-lookup"><span data-stu-id="b9b62-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b9b62-161">由於 Lync Web App 的增強功能，Lync Server 2013 不提供更新版本的出席者。</span><span class="sxs-lookup"><span data-stu-id="b9b62-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="b9b62-162">Lync Web App 是您組織外部參與者的選擇用戶端。</span><span class="sxs-lookup"><span data-stu-id="b9b62-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="b9b62-163">不需要安裝本機用戶端，但在第一次使用音訊、視訊及共用功能時，需要安裝外掛程式。</span><span class="sxs-lookup"><span data-stu-id="b9b62-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="b9b62-164">Lync 2013 用於行動用戶端更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="b9b62-165">除了增強的目前狀態、連絡人及 IM 功能之外，Lync 2013 行動用戶端現在也會透過網際網路和行動電話資料連線提供語音和影片呼叫。</span><span class="sxs-lookup"><span data-stu-id="b9b62-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="b9b62-166">使用 [行事曆] 專案中的會議連結的單一點擊，行動使用者便可加入 Lync 語音和影片會議。</span><span class="sxs-lookup"><span data-stu-id="b9b62-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="b9b62-167">如需 Lync 2013 行動用戶端的詳細資訊，請參閱 [在 Lync Server 2013 中規劃行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="b9b62-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="b9b62-168">Lync 2013 使用者介面更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="b9b62-169">協助工具更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-169">Accessibility Updates</span></span>

<span data-ttu-id="b9b62-170">Lync 2013 包含數個新的協助工具。</span><span class="sxs-lookup"><span data-stu-id="b9b62-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="b9b62-171">Lync 2013 支援高 DPI 解析度，讓使用者能夠調整125% 的文字和圖形，以及每英寸150% 點。</span><span class="sxs-lookup"><span data-stu-id="b9b62-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="b9b62-172">Lync 提供高對比支援，讓使用者介面在與 Windows 中的高對比主題搭配使用時仍然保持完整運作。</span><span class="sxs-lookup"><span data-stu-id="b9b62-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="b9b62-173">Lync 提供超過100個鍵盤快速鍵，讓使用者不必使用滑鼠即可存取重要的功能。</span><span class="sxs-lookup"><span data-stu-id="b9b62-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="b9b62-174">例如，使用者可以按 Alt+C 接受通話，或 Alt + I 忽略通話，而不需要索引標籤或設定焦點。</span><span class="sxs-lookup"><span data-stu-id="b9b62-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="b9b62-175">按 (Alt+Q) 結束通話、(Ctrl+N) 啟動 OneNote，以及 (Alt+T) 開啟 [工具] 功能表。</span><span class="sxs-lookup"><span data-stu-id="b9b62-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="b9b62-176">Lync 2013 中的廣泛螢幕讀取器支援，可確保在啟用螢幕閱讀器時，高聲閱讀所有通知、傳入要求和立即訊息。</span><span class="sxs-lookup"><span data-stu-id="b9b62-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="b9b62-177">共用時的狀態</span><span class="sxs-lookup"><span data-stu-id="b9b62-177">Presence While Sharing</span></span>

<span data-ttu-id="b9b62-178">當 Lync 偵測到使用者正在共用時，Lync 會自動為使用者指派展示目前狀態。</span><span class="sxs-lookup"><span data-stu-id="b9b62-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="b9b62-179">此狀態會封鎖所有的傳入通訊，除非已指派工作群組私人關係給傳送者。</span><span class="sxs-lookup"><span data-stu-id="b9b62-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="b9b62-180">如果使用者完全在第二個監視器上使用共用功能，Lync 便不會指派呈現狀態。</span><span class="sxs-lookup"><span data-stu-id="b9b62-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="b9b62-181">交談視窗更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-181">Conversation Window Updates</span></span>

<span data-ttu-id="b9b62-182">重新設計的交談視窗對重要功能提供了更快的存取方式。</span><span class="sxs-lookup"><span data-stu-id="b9b62-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="b9b62-p116">透過新的分頁交談功能，使用者現在可以將所有 IM 及聊天室保持在一個交談視窗中。交談視窗左側的分頁可讓使用者在所有使用中交談中輕鬆瀏覽。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p116">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window. The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="b9b62-p117">使用者可以將個別交談取消固定到個別視窗中，然後調整視窗大小。也可將視窗固定回主要的交談視窗中。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p117">Users can pop out an individual conversation into a separate window, and then resize the window. They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="b9b62-187">當使用者登出並重新登入 Lync 時，Lync 2013 會重新打開使用者的交談。</span><span class="sxs-lookup"><span data-stu-id="b9b62-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="b9b62-188">使用者可以在任何交談中快速新增 IM、視訊、程式共用、桌面共用或 Web 會議工具 (白板、會議記錄、共用筆記本及附件)。</span><span class="sxs-lookup"><span data-stu-id="b9b62-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="b9b62-189">在共用視訊或內容的會議中，使用者可以取消固定會議視訊或共用內容，然後調整視窗大小。</span><span class="sxs-lookup"><span data-stu-id="b9b62-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="b9b62-190">Lync 主視窗更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-190">Lync Main Window Updates</span></span>

<span data-ttu-id="b9b62-191">嶄新的簡化外觀保留了熟悉的功能，例如 **[今天有什麼新鮮事？]** 記錄欄位、狀態選取器以及 **[設定您的位置]** 選取器。</span><span class="sxs-lookup"><span data-stu-id="b9b62-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="b9b62-192">啟用聊天室時，使用者會在主要 Lync 頁面上 **看到新的聊天室圖示** 。</span><span class="sxs-lookup"><span data-stu-id="b9b62-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="b9b62-193">透過 **[聊天室]** 圖示，使用者可以快速存取聊天室及篩選條件。</span><span class="sxs-lookup"><span data-stu-id="b9b62-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="b9b62-194">使用者可以按一下檢視圖示切換至 **[連絡人]** 檢視、**[聊天室]** 檢視、**[交談]** 檢視或 **[電話]** 檢視。</span><span class="sxs-lookup"><span data-stu-id="b9b62-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="b9b62-195">如果使用者已遷移至 Exchange 2013，可上傳高解析度圖片。</span><span class="sxs-lookup"><span data-stu-id="b9b62-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="b9b62-196">連絡人檢視及連絡人卡片更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="b9b62-197">Lync 2013 為使用者提供不同的方式來查看其 **連絡人** 視圖中的連絡人和群組。</span><span class="sxs-lookup"><span data-stu-id="b9b62-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="b9b62-198">在新的整合連絡人存放區中，使用者的 Lync 連絡人會遷移至 Exchange 2013 之後，使用者就可以從 Lync 2013、Outlook 或 Outlook Web App 存取及管理其連絡人，其最愛保持同步。</span><span class="sxs-lookup"><span data-stu-id="b9b62-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="b9b62-199">例如，如果使用者將連絡人新增至 Outlook 中的 [我的最愛]，該連絡人會出現在 Lync 2013 的 [我的最愛] 群組中。</span><span class="sxs-lookup"><span data-stu-id="b9b62-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="b9b62-200">如果已新增並設定 XMPP Proxy 及 XMPP 閘道，使用者就可以新增以 XMPP 為基礎之協力廠商的連絡人，用於立即訊息與目前狀態。</span><span class="sxs-lookup"><span data-stu-id="b9b62-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="b9b62-201">新的 **[新增非組織內部的連絡人]** 功能讓使用者可輕鬆新增組織外人員。</span><span class="sxs-lookup"><span data-stu-id="b9b62-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="b9b62-202">新的 **[我的最愛]** 群組讓使用者可以建立使用者最常連絡的人員清單，以供快速存取。</span><span class="sxs-lookup"><span data-stu-id="b9b62-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="b9b62-p120">使用者可以使用新的 **[連絡人清單]** 選項頁面，選擇使用者如何排序及顯示連絡人的方式。使用者可以選擇展開的雙行檢視 (顯示連絡人圖片) 或緊縮的單行檢視。使用者也可以依字母順序或依顯示狀態來排序連絡人。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p120">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts. Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view. Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="b9b62-206">會議更新</span><span class="sxs-lookup"><span data-stu-id="b9b62-206">Conferencing Updates</span></span>

<span data-ttu-id="b9b62-207">Lync 2013 提供許多對會議功能的增強功能。</span><span class="sxs-lookup"><span data-stu-id="b9b62-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="b9b62-p121">視會議類型而定，使用者現在可以在排程會議時將觀眾設為靜音，以及允許或封鎖視訊共用。這些選項提供於 **[會議選項]** 頁面，建議使用於超過 20 位參與者的大型會議。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p121">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting. These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="b9b62-210">會議室中容易使用的音訊控制讓使用者可以控制音訊選項，例如靜音、取消靜音、變更裝置等。</span><span class="sxs-lookup"><span data-stu-id="b9b62-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="b9b62-211">共用程式時，如果使用者需要使用一個以上的程式，則可以選取共用多個程式。</span><span class="sxs-lookup"><span data-stu-id="b9b62-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="b9b62-212">使用者現在可以上傳包含視訊剪輯的簡報：上傳 PowerPoint 檔案，然後將滑鼠指向投影片以顯示視訊控制，例如播放、暫停及音訊控制。</span><span class="sxs-lookup"><span data-stu-id="b9b62-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="b9b62-213">在會議進行中，使用者可以使用 **[更多選項]** (**[...]**) 功能表上的 **[將這個通話合併為]**，將其他開啟交談合併至會議中。</span><span class="sxs-lookup"><span data-stu-id="b9b62-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="b9b62-214">如要檢視參與者的名稱，使用者可以將滑鼠暫留在 **[檢視參與者]** 按鈕上，或按一下 **[顯示參與者清單]**，將面板固定在會議中。</span><span class="sxs-lookup"><span data-stu-id="b9b62-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="b9b62-215">視會議類型而定，使用者可以選取許多不同的內容及參與者檢視。</span><span class="sxs-lookup"><span data-stu-id="b9b62-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="b9b62-p122">會議錄製會自動儲存為可在 Windows Media Player 中播放的格式 (MP4)。使用者可以輕鬆與任何人共用檔案，或使用錄製管理員中的 **[發佈]** 功能，將錄製張貼到共用的位置。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p122">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4). Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="b9b62-p123">OneNote 讓會議中共同作業有了新方法。在會議進行中，使用者可以使用 OneNote 作筆記，供會議後私人之用，或者使用共用筆記本，與會議參與者進行即時共同編輯。所有的小組成員都可以存取共用的記事來提供資訊、腦力激盪，或使用筆記本頁面作為虛擬白板。在會議中共用的人員及內容會自動新增到 Notes。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p123">OneNote enables new ways to collaborate in a meeting. During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time. All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard. People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="b9b62-p124">使用者可以使用會議室底端的 **[共用內容並引導會議活動]**，在內容類型之間切換。使用者還可以使用 **[管理簡報內容]** 功能表，選擇要共用的內容。</span><span class="sxs-lookup"><span data-stu-id="b9b62-p124">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room. Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9b62-224">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b9b62-224">See Also</span></span>


[<span data-ttu-id="b9b62-225">在 Lync Server 2013 中規劃用戶端</span><span class="sxs-lookup"><span data-stu-id="b9b62-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

