---
title: Lync Server 2013：用戶端最新訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf37f68d0ea11e17a799956f285d8ca82eb2a27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="e87e3-102">Lync Server 2013 中的用戶端最新訊息</span><span class="sxs-lookup"><span data-stu-id="e87e3-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e87e3-103">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="e87e3-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="e87e3-104">Microsoft Lync 2013 具有重新設計的使用者介面和重要的新功能。</span><span class="sxs-lookup"><span data-stu-id="e87e3-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="e87e3-105">就管理員而言，用戶端現已隨附于 Office 安裝程式，提供更簡單的方法來部署 Office 及自訂貴組織中的用戶端。</span><span class="sxs-lookup"><span data-stu-id="e87e3-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e87e3-106">如需 Lync 2013 使用者介面更新的圖例視圖，請參閱「Lync 2013 的新增功能」 <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>。</span><span class="sxs-lookup"><span data-stu-id="e87e3-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="e87e3-107">與 Office 安裝程式整合</span><span class="sxs-lookup"><span data-stu-id="e87e3-107">Integration with Office Setup</span></span>

<span data-ttu-id="e87e3-108">Lync 2013 的 Lync 2013 用戶端和線上會議增益集（可支援 Outlook 訊息和共同作業用戶端內的會議管理）現在都包含在 Office 2013 設定程式中。</span><span class="sxs-lookup"><span data-stu-id="e87e3-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="e87e3-109">在舊版 Lync 和 Office Communicator 中，您可以使用 Windows 安裝程式屬性來自訂及控制 Office 安裝。</span><span class="sxs-lookup"><span data-stu-id="e87e3-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="e87e3-110">由於 Lync 2013 是與 Office 設定整合，因此您可以使用下列方法來自訂 Lync 2013 設定：</span><span class="sxs-lookup"><span data-stu-id="e87e3-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="e87e3-111">使用 Office 自訂工具 (OCT)</span><span class="sxs-lookup"><span data-stu-id="e87e3-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="e87e3-112">使用 Config.xml 執行安裝任務</span><span class="sxs-lookup"><span data-stu-id="e87e3-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="e87e3-113">使用設定命令列選項</span><span class="sxs-lookup"><span data-stu-id="e87e3-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e87e3-114">Lync 2013 安裝程式不會卸載舊版的 Lync 或 Office Communicator。</span><span class="sxs-lookup"><span data-stu-id="e87e3-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="e87e3-115">Lync 2013 用戶端與其他 Lync 或 Office Communicator 用戶端並排安裝</span><span class="sxs-lookup"><span data-stu-id="e87e3-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="e87e3-116">如需詳細資訊，請參閱[在 Lync Server 2013 中部署 lync 用戶端](lync-server-2013-deploying-lync-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="e87e3-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="e87e3-117">群組原則部署</span><span class="sxs-lookup"><span data-stu-id="e87e3-117">Group Policy Deployment</span></span>

<span data-ttu-id="e87e3-118">由於 Lync 2013 現已包含在 Office 設定中，因此部署 Lync 群組原則設定的方法已變更。</span><span class="sxs-lookup"><span data-stu-id="e87e3-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="e87e3-119">在舊版的 Lync 和 Office Communicator 中，您可以使用 Communicator 來定義群組原則設定，但在 Lync 2013 中，您現在可以使用 Lync ADMX 及 ADML 與 Office 群組原則一起提供的管理範本管理範本。</span><span class="sxs-lookup"><span data-stu-id="e87e3-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="e87e3-120">如需詳細資訊，請參閱[Lync 2013 的群組原則設定](lync-server-2013-group-policy-settings-for-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="e87e3-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="e87e3-121">Outlook 排程增益集更新</span><span class="sxs-lookup"><span data-stu-id="e87e3-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="e87e3-122">Lync 2013 的線上會議增益集包含會議邀請自訂及新的會議選項。</span><span class="sxs-lookup"><span data-stu-id="e87e3-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="e87e3-123">系統管理員可以新增自訂標誌、支援 URL、合法免責聲明 URL 或自訂的頁尾文字，來自訂群組織的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="e87e3-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="e87e3-124">如需詳細資訊，請參閱[在 Lync Server 2013 中自訂線上會議增益集](lync-server-2013-customizing-the-online-meeting-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="e87e3-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="e87e3-125">新的出席者靜音控制項可讓會議召集人依預設將出席者音訊和影片設為靜音的會議進行排程。</span><span class="sxs-lookup"><span data-stu-id="e87e3-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="e87e3-126">虛擬桌面基礎結構外掛程式</span><span class="sxs-lookup"><span data-stu-id="e87e3-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="e87e3-127">Lync 2013 用戶端現在支援虛擬桌面基礎結構（VDI）環境中的音訊和視頻。</span><span class="sxs-lookup"><span data-stu-id="e87e3-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="e87e3-128">使用者可以將音訊或視頻裝置（例如耳機或相機）連線至本機電腦（例如瘦用戶端或用途電腦）。</span><span class="sxs-lookup"><span data-stu-id="e87e3-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="e87e3-129">使用者可以連線到虛擬機器、登入在虛擬機器上執行的 Lync 2013 用戶端，並參與即時音訊與視頻通訊，如同用戶端在本機執行。</span><span class="sxs-lookup"><span data-stu-id="e87e3-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="e87e3-130">虛擬桌面環境支援下列功能：</span><span class="sxs-lookup"><span data-stu-id="e87e3-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="e87e3-131">音訊與影片的裝置整合，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="e87e3-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="e87e3-132">從裝置呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e87e3-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="e87e3-133">裝置上的目前狀態整合</span><span class="sxs-lookup"><span data-stu-id="e87e3-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="e87e3-134">多個 HID （人體學介面裝置）支援</span><span class="sxs-lookup"><span data-stu-id="e87e3-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="e87e3-135">位置與緊急服務支援。</span><span class="sxs-lookup"><span data-stu-id="e87e3-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="e87e3-136">支援所有 Lync 形式，包括 IM、音訊、影片、應用程式共用、桌面共用、PowerPoint 共用、白板和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="e87e3-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="e87e3-137">在人對通話和電話會議中進行音訊與視頻支援。</span><span class="sxs-lookup"><span data-stu-id="e87e3-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="e87e3-138">如需有關部署 VDI 外掛程式的資訊，請參閱[在 Lync Server 2013 中部署 LYNC VDI 外掛程式](lync-server-2013-deploying-the-lync-vdi-plug-in.md)。</span><span class="sxs-lookup"><span data-stu-id="e87e3-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="e87e3-139">影片增強功能</span><span class="sxs-lookup"><span data-stu-id="e87e3-139">Video Enhancements</span></span>

<span data-ttu-id="e87e3-140">有幾項新功能可大大增強會議參與者的影片體驗。</span><span class="sxs-lookup"><span data-stu-id="e87e3-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="e87e3-141">影片是透過臉部偵測和智慧型組幀來加強，因此參與者的影片會移動，以協助將其放在框架中。</span><span class="sxs-lookup"><span data-stu-id="e87e3-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="e87e3-142">在雙方通話和多方會議中現在支援高解析度的影片。</span><span class="sxs-lookup"><span data-stu-id="e87e3-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="e87e3-143">使用者可以體驗高達 HD 1080P 的解析度。</span><span class="sxs-lookup"><span data-stu-id="e87e3-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="e87e3-144">參與者可以從不同的會議版面配置中選取： [庫視圖] 會顯示所有參與者的圖片或影片;[演講者] 視圖會顯示會議內容，且只顯示目前演講者的影片或圖片;[簡報] 視圖只會顯示會議內容;精簡查看只顯示會議控制項。</span><span class="sxs-lookup"><span data-stu-id="e87e3-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="e87e3-145">使用新的圖庫功能，參與者可以同時查看多個視頻摘要。</span><span class="sxs-lookup"><span data-stu-id="e87e3-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="e87e3-146">如果會議的參與者超過五個，則只有最活躍參與者的影片摘要會出現在頂端列中，而其他參與者則會顯示圖片。</span><span class="sxs-lookup"><span data-stu-id="e87e3-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="e87e3-147">參與者可以使用 [視頻釘選]，選取一或多個可用的影片摘要，讓它們隨時可見。</span><span class="sxs-lookup"><span data-stu-id="e87e3-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="e87e3-148">簡報者可以使用 [影片焦點] 功能來選取一個人員的影片摘要，讓會議中的每位參與者都只會看到該參與者。</span><span class="sxs-lookup"><span data-stu-id="e87e3-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="e87e3-149">聊天室整合</span><span class="sxs-lookup"><span data-stu-id="e87e3-149">Chat Room Integration</span></span>

<span data-ttu-id="e87e3-150">Lync 2013 現在已整合 Lync 2010 群組聊天先前提供的功能。</span><span class="sxs-lookup"><span data-stu-id="e87e3-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="e87e3-151">不再需要個別的群組聊天用戶端。</span><span class="sxs-lookup"><span data-stu-id="e87e3-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="e87e3-152">在 Lync 2013 中，使用者可以搜尋聊天室、新增聊天室給他們的連絡人、監控聊天室活動，以及讀取及張貼訊息。</span><span class="sxs-lookup"><span data-stu-id="e87e3-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="e87e3-153">使用者可以建立主題摘要，以便在其中一個聊天室中的某人新增包含特定關鍵字的文章時收到通知。</span><span class="sxs-lookup"><span data-stu-id="e87e3-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="e87e3-154">使用者可以使用新的 [**持續聊天**] 選項頁面，設定當人員將訊息張貼到聊天室時，要套用的通知通知與音效。</span><span class="sxs-lookup"><span data-stu-id="e87e3-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="e87e3-155">Lync Web App 更新</span><span class="sxs-lookup"><span data-stu-id="e87e3-155">Lync Web App Updates</span></span>

<span data-ttu-id="e87e3-156">Lync Web App 是 Lync Server 2013 會議的網路式會議用戶端。</span><span class="sxs-lookup"><span data-stu-id="e87e3-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="e87e3-157">在這個版本中，將電腦音訊和影片新增至 Lync Web App，可為沒有在本機安裝 Lync 用戶端的任何人提供完整的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="e87e3-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="e87e3-158">會議參與者可存取所有共同作業及共用功能及簡報者會議控制項。</span><span class="sxs-lookup"><span data-stu-id="e87e3-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="e87e3-159">當使用者嘗試加入會議，但沒有本機安裝的用戶端時，會開啟 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="e87e3-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="e87e3-160">如果您想要允許其他選項加入會議，您可以設定會議加入頁面;請參閱在部署檔中的[Lync Server 2013 中的 [設定會議加入] 頁面](lync-server-2013-configuring-the-meeting-join-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e87e3-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e87e3-161">由於 Lync Web App 的增強功能，因此無法使用 Lync Server 2013 的更新版本的出席者。</span><span class="sxs-lookup"><span data-stu-id="e87e3-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="e87e3-162">Lync Web App 是您組織外部參與者所選擇的用戶端。</span><span class="sxs-lookup"><span data-stu-id="e87e3-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="e87e3-163">您不需要安裝本機用戶端，不過音訊、影片和共用功能需要在第一次使用時才安裝外掛程式。</span><span class="sxs-lookup"><span data-stu-id="e87e3-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="e87e3-164">適用于行動用戶端更新的 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e87e3-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="e87e3-165">除了增強的目前狀態、連絡人及 IM 功能之外，Lync 2013 行動用戶端現在提供透過網際網路和行動資料連線進行語音及視頻通話。</span><span class="sxs-lookup"><span data-stu-id="e87e3-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="e87e3-166">在行事曆中的 [行事曆] 專案中，行動使用者可以加入 Lync 語音及視訊會議。</span><span class="sxs-lookup"><span data-stu-id="e87e3-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="e87e3-167">如需 Lync 2013 行動用戶端的詳細資訊，請參閱[在 Lync Server 2013 中規劃行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="e87e3-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="e87e3-168">Lync 2013 使用者介面更新</span><span class="sxs-lookup"><span data-stu-id="e87e3-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="e87e3-169">協助工具更新</span><span class="sxs-lookup"><span data-stu-id="e87e3-169">Accessibility Updates</span></span>

<span data-ttu-id="e87e3-170">Lync 2013 包含幾個新的協助工具功能。</span><span class="sxs-lookup"><span data-stu-id="e87e3-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="e87e3-171">Lync 2013 支援高 DPI 解析度，讓使用者能夠針對125% 和150% 點每英寸調整文字與圖形。</span><span class="sxs-lookup"><span data-stu-id="e87e3-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="e87e3-172">Lync 提供高對比支援，讓使用者介面在 Windows 中與高對比主題搭配使用時，能保持完全正常運作。</span><span class="sxs-lookup"><span data-stu-id="e87e3-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="e87e3-173">Lync 提供的鍵盤快速鍵超過100個，因此使用者無需滑鼠就能存取重要的功能。</span><span class="sxs-lookup"><span data-stu-id="e87e3-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="e87e3-174">例如，使用者可以按 Alt + C 來接受來電，或按 Alt + I 來忽略它，而不需要使用 tab 鍵或設定焦點。</span><span class="sxs-lookup"><span data-stu-id="e87e3-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="e87e3-175">按下（Alt + Q）會結束通話，（Ctrl + N）會啟動 OneNote，而（Alt + T）會開啟 [工具] 功能表。</span><span class="sxs-lookup"><span data-stu-id="e87e3-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="e87e3-176">Lync 2013 中的大量螢幕閱讀程式支援可確保在啟用螢幕閱讀器時，大聲讀出所有通知、傳入要求和立即訊息。</span><span class="sxs-lookup"><span data-stu-id="e87e3-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="e87e3-177">共用時的目前狀態</span><span class="sxs-lookup"><span data-stu-id="e87e3-177">Presence While Sharing</span></span>

<span data-ttu-id="e87e3-178">當 Lync 偵測到某個使用者正在共用時，Lync 會自動為該使用者指派簡報狀態。</span><span class="sxs-lookup"><span data-stu-id="e87e3-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="e87e3-179">除非給寄件者指派了工作組隱私權關係，否則此狀態會封鎖所有傳入通訊。</span><span class="sxs-lookup"><span data-stu-id="e87e3-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="e87e3-180">如果使用者完全在輔助監視器上使用共用功能，Lync 不會指派簡報目前狀態。</span><span class="sxs-lookup"><span data-stu-id="e87e3-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="e87e3-181">交談視窗更新</span><span class="sxs-lookup"><span data-stu-id="e87e3-181">Conversation Window Updates</span></span>

<span data-ttu-id="e87e3-182">重新設計的交談視窗可讓您更快速地存取重要功能。</span><span class="sxs-lookup"><span data-stu-id="e87e3-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="e87e3-183">透過新的 [索引標籤式交談] 功能，使用者現在可以在單一交談視窗中保留所有的 Im 和聊天室。</span><span class="sxs-lookup"><span data-stu-id="e87e3-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="e87e3-184">[交談] 視窗左側的索引標籤可讓使用者輕鬆地在所有活動交談中進行流覽。</span><span class="sxs-lookup"><span data-stu-id="e87e3-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="e87e3-185">使用者可以將個別的交談醒目提示到另一個視窗，然後調整視窗大小。</span><span class="sxs-lookup"><span data-stu-id="e87e3-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="e87e3-186">他們也可以將視窗放回到主要交談視窗中。</span><span class="sxs-lookup"><span data-stu-id="e87e3-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="e87e3-187">當使用者登出並重新登入 Lync 時，Lync 2013 會重新開啟使用者的交談。</span><span class="sxs-lookup"><span data-stu-id="e87e3-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="e87e3-188">使用者可以將 IM、影片、程式共用、桌面共用或 web 會議工具（白板、會議記事、共用筆記本及附件）快速新增至任何交談。</span><span class="sxs-lookup"><span data-stu-id="e87e3-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="e87e3-189">在共用影片或內容的會議中，使用者可以彈出會議影片或共用內容，然後調整視窗大小。</span><span class="sxs-lookup"><span data-stu-id="e87e3-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="e87e3-190">Lync 主視窗更新</span><span class="sxs-lookup"><span data-stu-id="e87e3-190">Lync Main Window Updates</span></span>

<span data-ttu-id="e87e3-191">新的精簡外觀會保留熟悉的功能，例如**今天所發生的問題？** 記事欄位、狀態選取器，以及**設定您的位置**選擇器。</span><span class="sxs-lookup"><span data-stu-id="e87e3-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="e87e3-192">啟用聊天室之後，使用者會在主要 Lync 頁面上看到新的**聊天室**圖示。</span><span class="sxs-lookup"><span data-stu-id="e87e3-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="e87e3-193">使用聊天室**圖示，** 使用者可以快速存取其聊天室和篩選。</span><span class="sxs-lookup"><span data-stu-id="e87e3-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="e87e3-194">使用者可以按一下 [視圖] 圖示，切換到 [**連絡人**] 視圖、[**聊天室**] 視圖、[**交談**] 視圖或 [**電話**] 視圖。</span><span class="sxs-lookup"><span data-stu-id="e87e3-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="e87e3-195">如果使用者已遷移至 Exchange 2013，就可以上傳高解析度的圖片。</span><span class="sxs-lookup"><span data-stu-id="e87e3-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="e87e3-196">連絡人視圖和連絡人卡片更新</span><span class="sxs-lookup"><span data-stu-id="e87e3-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="e87e3-197">Lync 2013 提供使用者在**連絡人**視圖中查看連絡人與群組的不同方式。</span><span class="sxs-lookup"><span data-stu-id="e87e3-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="e87e3-198">在新的整合連絡人存放區中，使用者的 Lync 連絡人被遷移至 Exchange 2013 之後，使用者就可以從 Lync 2013、Outlook 或 Outlook Web App 存取及管理他們的連絡人，而且他們的最愛仍保持同步處理。</span><span class="sxs-lookup"><span data-stu-id="e87e3-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="e87e3-199">例如，如果使用者在 Outlook 中新增連絡人至 [我的最愛]，該連絡人會出現在 Lync 2013 的 [我的最愛] 群組中。</span><span class="sxs-lookup"><span data-stu-id="e87e3-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="e87e3-200">如果您已新增並設定 XMPP proxy 和 XMPP gateway，使用者可以新增來自 XMPP 合作夥伴的連絡人以進行立即訊息和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="e87e3-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="e87e3-201">新的新增**連絡人不在「我的組織」中**」功能可讓使用者輕鬆地新增組織外部的人員。</span><span class="sxs-lookup"><span data-stu-id="e87e3-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="e87e3-202">新的 [我的最愛 **]** 群組可讓使用者建立使用者最常聯絡的人員清單，以快速存取。</span><span class="sxs-lookup"><span data-stu-id="e87e3-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="e87e3-203">使用者可以使用新的 [**連絡人清單**選項] 頁面，選擇使用者要排序及顯示連絡人的方式。</span><span class="sxs-lookup"><span data-stu-id="e87e3-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="e87e3-204">使用者可以選取一個展開的雙行視圖來顯示連絡人的圖片，或是一個簡潔的單行視圖。</span><span class="sxs-lookup"><span data-stu-id="e87e3-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="e87e3-205">使用者也可以依字母順序或依可用性排序連絡人。</span><span class="sxs-lookup"><span data-stu-id="e87e3-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="e87e3-206">會議更新</span><span class="sxs-lookup"><span data-stu-id="e87e3-206">Conferencing Updates</span></span>

<span data-ttu-id="e87e3-207">Lync 2013 提供數個功能，可增強會議功能。</span><span class="sxs-lookup"><span data-stu-id="e87e3-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="e87e3-208">根據會議類型而定，使用者現在可以將物件設為靜音，並允許或封鎖在排程會議時的影片共用。</span><span class="sxs-lookup"><span data-stu-id="e87e3-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="e87e3-209">您可以在 [**會議選項**] 頁面上使用這些選項，建議您在超過20名參與者的大型會議中使用這些選項。</span><span class="sxs-lookup"><span data-stu-id="e87e3-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="e87e3-210">您可以在會議室輕鬆使用音訊控制項，讓使用者能夠控制音訊選項，例如靜音、取消靜音、變更裝置等。</span><span class="sxs-lookup"><span data-stu-id="e87e3-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="e87e3-211">當您共用程式時，如果需要使用多個程式，使用者可以選取多個要共用的程式。</span><span class="sxs-lookup"><span data-stu-id="e87e3-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="e87e3-212">使用者現在可以上傳 PowerPoint 檔案，並將滑鼠指標放在投影片上，以顯示影片控制項（例如播放、暫停和音訊控制項），來上傳包含影片剪輯的簡報。</span><span class="sxs-lookup"><span data-stu-id="e87e3-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="e87e3-213">在會議中，使用者可以使用 [**其他選項**（**...**）] 功能表中的 [**合併此通話**]，將其他開啟的交談合併至會議中。</span><span class="sxs-lookup"><span data-stu-id="e87e3-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="e87e3-214">若要查看參與者的名稱，使用者可以將滑鼠游標暫留在 [**查看參與者**] 按鈕上，或按一下 [**顯示參與者清單**] 以將面板固定在會議中。</span><span class="sxs-lookup"><span data-stu-id="e87e3-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="e87e3-215">根據會議類型，使用者可以從數個不同的內容和參與者視圖中進行選取。</span><span class="sxs-lookup"><span data-stu-id="e87e3-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="e87e3-216">會議錄製會自動儲存為在 Windows Media Player （會議格式）中播放的格式。</span><span class="sxs-lookup"><span data-stu-id="e87e3-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="e87e3-217">使用者可以輕鬆地與任何人共用檔案，或使用錄製管理員中的 [**發佈**] 功能，將錄製張貼到共用位置。</span><span class="sxs-lookup"><span data-stu-id="e87e3-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="e87e3-218">OneNote 可讓您在會議中共同作業。</span><span class="sxs-lookup"><span data-stu-id="e87e3-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="e87e3-219">在會議期間，使用者可以在會議之後使用 OneNote 來記錄筆記，或使用共用筆記本並即時與會議參與者共同編輯會議。</span><span class="sxs-lookup"><span data-stu-id="e87e3-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="e87e3-220">所有小組成員都可以存取共用筆記，以參與資訊、集體討論想法，或使用筆記本頁面做為虛擬白板。</span><span class="sxs-lookup"><span data-stu-id="e87e3-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="e87e3-221">在會議中共用的人員和內容會自動新增到筆記中。</span><span class="sxs-lookup"><span data-stu-id="e87e3-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="e87e3-222">使用者可以使用會議會議室底部的 [**共用內容] 和 [引導會議活動]，** 在內容類型之間切換。</span><span class="sxs-lookup"><span data-stu-id="e87e3-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="e87e3-223">使用者也可以使用 [**管理簡報內容**] 功能表來選擇要共用的內容。</span><span class="sxs-lookup"><span data-stu-id="e87e3-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e87e3-224">請參閱</span><span class="sxs-lookup"><span data-stu-id="e87e3-224">See Also</span></span>


[<span data-ttu-id="e87e3-225">規劃 Lync Server 2013 中的用戶端</span><span class="sxs-lookup"><span data-stu-id="e87e3-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

