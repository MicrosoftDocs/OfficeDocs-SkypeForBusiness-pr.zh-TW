---
title: Lync Server 2013：建立或修改互動式工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79af52b46c25796127fcb345360ed9f424ca3bf3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514760"
---
# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="6d06d-102">在 Lync Server 2013 中建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="6d06d-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d06d-103">_**主題上次修改日期：** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="6d06d-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="6d06d-104">使用下列其中一個程式來建立或修改互動式工作流程。</span><span class="sxs-lookup"><span data-stu-id="6d06d-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d06d-105">您可以使用 Lync Server 管理命令介面或回應群組設定工具來建立及修改互動式工作流程。</span><span class="sxs-lookup"><span data-stu-id="6d06d-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="6d06d-106">您可以從 Lync Server 控制台存取回應群組設定工具，或是直接從網頁瀏覽器開啟網頁，只要輸入下列 URL: <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="6d06d-107">使用回應群組設定工具來建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="6d06d-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="6d06d-108">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="6d06d-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="6d06d-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6d06d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6d06d-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="6d06d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6d06d-111">在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[工作流程]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="6d06d-112">在 **[工作流程]** 頁面上，按一下 **[建立或編輯工作流程]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="6d06d-113">在 [ **選取服務** ] 搜尋欄位中，輸入主控您要建立或修改之工作流程的 **ApplicationServer** 服務全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="6d06d-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="6d06d-114">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-115">回應群組設定工具隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="6d06d-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="6d06d-116">您也可以輸入下列 URL: <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>，直接從網頁瀏覽器開啟回應群組設定工具。</span><span class="sxs-lookup"><span data-stu-id="6d06d-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="6d06d-117">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6d06d-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="6d06d-118">在 **[建立新的工作流程]** 的 **[互動]** 旁邊，按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="6d06d-119">在 **[管理現有工作流程]** 下，找到想要變更的工作流程，然後在 **[動作]** 下按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="6d06d-120">如果尚未準備好讓使用者開始撥號至工作流程，請清除 **[啟用工作流程]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6d06d-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-121">若要建立受管理的工作流程，您必須選取 <STRONG>[啟用工作流程</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="6d06d-121">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>.</span></span> <span data-ttu-id="6d06d-122">在您儲存使用中的受管理工作流程之後，您可以修改並停用該工作流程。</span><span class="sxs-lookup"><span data-stu-id="6d06d-122">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="6d06d-123">若要允許同盟使用者撥打群組，請選取 **[針對同盟啟用]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6d06d-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="6d06d-124">您也必須具有適用于同盟設定之回應群組應用程式的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="6d06d-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-125">全域外部存取原則會套用至回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="6d06d-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="6d06d-126">您可以使用 Lync Server 控制台或使用 <STRONG>get-csexternalaccesspolicy</STRONG> 指令程式將 EnableOutsideAccess 參數設定為 True，設定回應群組同盟的全域原則。</span><span class="sxs-lookup"><span data-stu-id="6d06d-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="6d06d-127">請記住，除非將站台原則或使用者原則指派給使用者，否則通用原則設定適用於所有使用者。</span><span class="sxs-lookup"><span data-stu-id="6d06d-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="6d06d-128">因此在變更回應群組的此設定之前，請確認同盟設定符合您組織的需求。</span><span class="sxs-lookup"><span data-stu-id="6d06d-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="6d06d-129">如需有關如何將原則套用至使用者的詳細資訊，請參閱 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="6d06d-130">如需同盟設定的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 <STRONG>Set-get-csexternalaccesspolicy</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="6d06d-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-131">在 Lync Online 中主控的使用者無法將呼叫放入內部部署中所主控的回應群組。</span><span class="sxs-lookup"><span data-stu-id="6d06d-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="6d06d-132">這在混合式部署中，以及內部部署與 Lync Online 部署同盟的情況皆為 true。</span><span class="sxs-lookup"><span data-stu-id="6d06d-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="6d06d-133">若要在通話期間隱藏代理人的身分識別，請選取 **[啟用代理人匿名]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6d06d-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-134">雖然代理人或來電者可以在建立通話之後新增 IM 及視訊，但是匿名通話不能以立即訊息 (IM) 或視訊開始。</span><span class="sxs-lookup"><span data-stu-id="6d06d-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="6d06d-135">匿名代理人也可以保留通話、轉接通話 (無條件轉接及諮詢轉接)，以及駐留及擷取通話。</span><span class="sxs-lookup"><span data-stu-id="6d06d-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="6d06d-136">匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、白板和資料共同作業，以及通話記錄。</span><span class="sxs-lookup"><span data-stu-id="6d06d-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="6d06d-137">使用 Lync VDI 外掛程式的代理程式可以以匿名方式接收來電，但無法以匿名方式撥打撥出電話。</span><span class="sxs-lookup"><span data-stu-id="6d06d-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="6d06d-138">在 [ **輸入要接聽電話的群組位址**] 下，輸入主要 SIP 統一資源識別項 (URI) 會接聽工作流程呼叫的群組的位址。</span><span class="sxs-lookup"><span data-stu-id="6d06d-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="6d06d-139">在 [ **顯示名稱**] 中，輸入您要針對工作流程顯示的名稱 (例如，Sales IVR Response Group) 。</span><span class="sxs-lookup"><span data-stu-id="6d06d-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-140">&lt;在顯示名稱中不要包含 "" 或 " &gt; " 字元。</span><span class="sxs-lookup"><span data-stu-id="6d06d-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="6d06d-141">下列是保留的顯示名稱，因此請不要使用它們：RGS Presence Watcher 或宣告服務。</span><span class="sxs-lookup"><span data-stu-id="6d06d-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="6d06d-142">在 **[電話號碼]** 中，輸入回應群組的線路 URI (例如，+14255550165)。</span><span class="sxs-lookup"><span data-stu-id="6d06d-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="6d06d-143">在 **[顯示號碼]** 中，輸入想要針對回應群組顯示的號碼 (例如，+1 (425) 555-0165)。</span><span class="sxs-lookup"><span data-stu-id="6d06d-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="6d06d-144"> (選用) 在 [ **描述**] 中，輸入您要顯示在 Lync 用戶端連絡人卡片上之工作流程的描述。</span><span class="sxs-lookup"><span data-stu-id="6d06d-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="6d06d-145">在 [ **工作流程類型**] 中，選取 [ **受** 回應群組管理員管理此工作流程]。</span><span class="sxs-lookup"><span data-stu-id="6d06d-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="6d06d-146">請執行下列動作，將回應群組管理員指派給工作流程：</span><span class="sxs-lookup"><span data-stu-id="6d06d-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="6d06d-147">為此工作流程輸入管理員的 SIP URI，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6d06d-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="6d06d-148">輸入其他管理員的 SIP URI 以新增至工作流程，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="6d06d-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6d06d-149">指定為回應群組管理員的每一位使用者都必須指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="6d06d-149">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="6d06d-150">若未指派此角色的使用者，他們就無法管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="6d06d-150">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="6d06d-151">在 **[步驟 2 選取語言]** 下，按一下要用於語音辨識及文字轉換語音的語言。</span><span class="sxs-lookup"><span data-stu-id="6d06d-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="6d06d-152">如果您想要設定歡迎訊息，請在 **[步驟 3 設定歡迎訊息]** 下選取 **[播放歡迎訊息]** 核取方塊，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6d06d-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="6d06d-153">若要以文字輸入為來電者轉換成語音的歡迎訊息，按一下 **[使用文字轉語音]**，然後在文字方塊中輸入歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="6d06d-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-p113">請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="6d06d-p114">若要使用 Wave 或 Windows Media 音訊檔案錄音做為歡迎訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的音訊檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-160">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="6d06d-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="6d06d-161">如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="6d06d-162">在 **[步驟 4 指定您的上班時間]** 的 **[您的時區]** 方塊中，按一下工作流程的時區。</span><span class="sxs-lookup"><span data-stu-id="6d06d-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-p116">此時區即為工作流程的來電者和專員所在之時區，可用來計算開啟和關閉的時間。例如，如果工作流程設定為使用「北美東部時區」，而工作流程排定為早上 7:00 開啟，晚上 11:00 關閉，則開啟和關閉的時間就會分別假設為東部時區 7:00 和東部時區 11:00:00。(您必須使用 24 小時時間標記法輸入時間)。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="6d06d-168">執行下列其中一項，以選取想要使用的上班時間排程類型：</span><span class="sxs-lookup"><span data-stu-id="6d06d-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="6d06d-169">若要使用預先定義的上班時間排程，請按一下 **[使用預設排程]**，然後從下拉式清單中選取想要使用的排程。</span><span class="sxs-lookup"><span data-stu-id="6d06d-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-170">您至少先前必須已定義一個預設排程，才能選取此選項。</span><span class="sxs-lookup"><span data-stu-id="6d06d-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="6d06d-171">您可以使用 <STRONG>New-CSRgsHoursOfBusiness</STRONG> Cmdlet，來定義預設排程。</span><span class="sxs-lookup"><span data-stu-id="6d06d-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="6d06d-172">如需詳細資訊，請參閱 <A href="lync-server-2013-optional-define-response-group-business-hours.md"> (選用) 在 Lync Server 2013 中定義回應群組上班時間</A>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="6d06d-173">當您選取預設排程時，<STRONG>[日]</STRONG>、<STRONG>[開啟]</STRONG> 及 <STRONG>[關閉]</STRONG> 會自動填入回應群組可用的日及時數。</span><span class="sxs-lookup"><span data-stu-id="6d06d-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="6d06d-174">若要使用只套用至此工作流程的自訂排程，請按一下 **[使用自訂排程]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="6d06d-175">如果您是建立此工作流程的自訂排程，請按一下回應群組可用之一星期的哪幾天的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6d06d-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="6d06d-176">如果您是建立自訂排程，請輸入回應群組可用時的 **[開啟]** 及 **[關閉]** 時間。</span><span class="sxs-lookup"><span data-stu-id="6d06d-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-p118"><STRONG>[開啟]</STRONG> 及 <STRONG>[關閉]</STRONG> 時間必須使用 24 小時時間標記法。例如，如果您辦公室平日的辦公時間為 9 點到 5 點，而且會在中午用餐時間關閉，則會將上班時間指定為 <STRONG>[開啟]</STRONG> 9:00、<STRONG>[關閉]</STRONG> 12:00、<STRONG>[開啟]</STRONG> 13:00 以及 <STRONG>[關閉]</STRONG> 17:00。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="6d06d-179">如果您想要在辦公室關閉時播放訊息，請選取 **[在回應群組下班時播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="6d06d-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="6d06d-180">若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="6d06d-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-p119">請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="6d06d-p120">若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-187">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="6d06d-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="6d06d-188">如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="6d06d-189">指定在播放訊息之後如何處理通話 (如果有設定訊息)：</span><span class="sxs-lookup"><span data-stu-id="6d06d-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="6d06d-190">若要中斷來電，按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="6d06d-191">若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="6d06d-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="6d06d-192">語音信箱位址的格式為 \<username\> @ \<domainname\> (例如，bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="6d06d-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="6d06d-193">若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。</span><span class="sxs-lookup"><span data-stu-id="6d06d-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="6d06d-194">使用者位址的格式為 \<username\> @ \<domainname\> 。</span><span class="sxs-lookup"><span data-stu-id="6d06d-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="6d06d-195">若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6d06d-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="6d06d-196">電話號碼的格式為 \<number\> @ \<domainname\> (例如，+ 14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="6d06d-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="6d06d-197">網域名稱會用來將來電者路由到正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="6d06d-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="6d06d-198">在 **[步驟 5 指定您的假日]** 下，按一下可定義回應群組沒上班之天數的一或多個假日集的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6d06d-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-199">您需要先定義假日及假日集，再設定工作流程。</span><span class="sxs-lookup"><span data-stu-id="6d06d-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="6d06d-200">使用 <STRONG>New-CsRgsHoliday</STRONG> 及 <STRONG>New-CsRgsHolidaySet</STRONG> Cmdlet，可定義假日及假日集。</span><span class="sxs-lookup"><span data-stu-id="6d06d-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="6d06d-201">如需詳細資訊，請參閱 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md"> (選用) 在 Lync Server 2013 中定義回應群組假日集</A>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="6d06d-202">如果您想要在假日時播放訊息，請選取 **[在假日期間播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="6d06d-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="6d06d-203">若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="6d06d-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-p126">請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="6d06d-p127">若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-210">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="6d06d-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="6d06d-211">如需支援的音訊檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中回應群組的技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="6d06d-212">指定在播放訊息之後如何處理通話 (如果有設定訊息)：</span><span class="sxs-lookup"><span data-stu-id="6d06d-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="6d06d-213">若要中斷來電，按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="6d06d-214">若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="6d06d-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="6d06d-215">語音信箱位址的格式為 \<username\> @ \<domainname\> (例如，bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="6d06d-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="6d06d-216">若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。</span><span class="sxs-lookup"><span data-stu-id="6d06d-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="6d06d-217">使用者位址的格式為 \<username\> @ \<domainname\> 。</span><span class="sxs-lookup"><span data-stu-id="6d06d-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="6d06d-218">若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6d06d-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="6d06d-219">電話號碼的格式為 \<number\> @ \<domainname\> (例如，+ 14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="6d06d-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="6d06d-220">網域名稱會用來將來電者路由到正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="6d06d-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="6d06d-221">在 **[步驟 6 設定等候音樂]** 中，選擇您要來電者在等候專員時所聆聽的音樂，方法如下：</span><span class="sxs-lookup"><span data-stu-id="6d06d-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="6d06d-222">若要使用預設的等候音樂錄音，按一下 **[使用預設]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="6d06d-p132">若要使用音訊檔案錄音做為等候音樂，請按一下 **[選取音樂檔案]**。如果您想要上傳新的音訊檔案，請按一下 **[音樂檔案]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-227">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="6d06d-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="6d06d-228">如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="6d06d-229">在 **[步驟 7 設定互動語音回應**] 的 **[使用者將聽到下列文字或錄製的訊息]** 標題下，依下列方式指定要詢問來電者的問題：</span><span class="sxs-lookup"><span data-stu-id="6d06d-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="6d06d-230">若要以文字格式輸入問題，按一下 **[使用文字轉語音]**，然後在文字方塊中輸入問題。</span><span class="sxs-lookup"><span data-stu-id="6d06d-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-p134">請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-233">文字轉語音引擎會將 "#" 符號轉譯為「號碼」一詞。</span><span class="sxs-lookup"><span data-stu-id="6d06d-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="6d06d-234">如果需要在提示中提及 # 鍵，則應該使用按鍵名稱，而非使用該符號。</span><span class="sxs-lookup"><span data-stu-id="6d06d-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="6d06d-235">例如，「與銷售人員交談，按井字鍵。」</span><span class="sxs-lookup"><span data-stu-id="6d06d-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="6d06d-p136">若要使用包含問題的預錄音訊檔案，請按一下 **[選取錄音]**，然後按一下 **[一筆記錄]** 連結以上傳檔案。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取音訊檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入檔案，然後在文字方塊中選擇性地輸入問題 (如此可將問題和來電者的回應轉送給回應代理人)。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d06d-239">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="6d06d-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="6d06d-240">如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="6d06d-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="6d06d-241">在 **[回應 1]** 中，藉由下列動作指定問題的第一個可能答覆：</span><span class="sxs-lookup"><span data-stu-id="6d06d-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6d06d-p138">請不要在任何語音回應中使用引號 (")。引號會導致 IVR 失敗。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-244">您可以選擇讓來電者使用語音及 (或) 英數鍵台輸入來進行答覆。</span><span class="sxs-lookup"><span data-stu-id="6d06d-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="6d06d-245">如果您想要讓來電者使用語音來回應，請在 **[輸入語音回應]** 中輸入答覆。</span><span class="sxs-lookup"><span data-stu-id="6d06d-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="6d06d-246">如果您想要讓來電者按鍵台上的按鍵來回應，請在 **[數字]** 中按一下鍵台數字。</span><span class="sxs-lookup"><span data-stu-id="6d06d-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="6d06d-247">指定是否要將來電者路由傳送到佇列或詢問另一個問題，如下所述：</span><span class="sxs-lookup"><span data-stu-id="6d06d-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="6d06d-248">若要將來電者路由傳送到佇列，請按一下 **[傳送到佇列]**，並在 **[選取佇列]** 中按一下想要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="6d06d-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="6d06d-249">若要詢問另一個問題，請按一下 **[詢問另一個問題]**，然後按一下 **[使用文字轉語音]**，並輸入問題，或按一下 **[選取錄音]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-249">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**.</span></span> <span data-ttu-id="6d06d-250">使用本節中的回應分組，指定其他問題最多四個可能回應，以及用於每個回應的佇列。</span><span class="sxs-lookup"><span data-stu-id="6d06d-250">Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response.</span></span> <span data-ttu-id="6d06d-251">若要指定第三或第四種可能的回應，請按一下 [ **回應 3** ] 核取方塊或 [ **回應 4** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6d06d-251">To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="6d06d-p140">重複步驟 28 及 29 指定可能的回應，以及針對每個回應採取的動作，以指定原始問題最多三個可能的答案。若要指定第三個或第四個可能的答案，請按一下 **[回應 3]** 核取方塊或 **[回應 4]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6d06d-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="6d06d-254">按一下 **[部署]**。</span><span class="sxs-lookup"><span data-stu-id="6d06d-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="6d06d-255">使用 Windows PowerShell 建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="6d06d-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="6d06d-256">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="6d06d-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="6d06d-257">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6d06d-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d06d-258">取得回應群組服務的服務名稱，並將其指派給變數。</span><span class="sxs-lookup"><span data-stu-id="6d06d-258">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="6d06d-259">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-259">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="6d06d-260">互動式工作流程需要兩個以上的佇列以及兩個以上的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="6d06d-260">An interactive workflow requires two or more queues and two or more agent groups.</span></span> <span data-ttu-id="6d06d-261">首先，建立代理人群組。</span><span class="sxs-lookup"><span data-stu-id="6d06d-261">First, create the agent groups.</span></span> <span data-ttu-id="6d06d-262">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-262">Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="6d06d-263">建立佇列。</span><span class="sxs-lookup"><span data-stu-id="6d06d-263">Create the queues.</span></span> <span data-ttu-id="6d06d-264">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-264">Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="6d06d-265">建立第一個回應群組提示。</span><span class="sxs-lookup"><span data-stu-id="6d06d-265">Create the first response group prompt.</span></span> <span data-ttu-id="6d06d-266">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-266">Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="6d06d-267">然後建立在提示後要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="6d06d-267">Then create the action to be performed after the prompt.</span></span> <span data-ttu-id="6d06d-268">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-268">Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="6d06d-269">建立第一個回應群組答案。</span><span class="sxs-lookup"><span data-stu-id="6d06d-269">Create the first response group answer.</span></span> <span data-ttu-id="6d06d-270">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-270">Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="6d06d-271">現在，建立第二個提示、通話動作和答案。</span><span class="sxs-lookup"><span data-stu-id="6d06d-271">Now create the second prompt, call action, and answer.</span></span> <span data-ttu-id="6d06d-272">請先建立提示。</span><span class="sxs-lookup"><span data-stu-id="6d06d-272">First create the prompt.</span></span> <span data-ttu-id="6d06d-273">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-273">Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="6d06d-274">建立第二個通話動作。</span><span class="sxs-lookup"><span data-stu-id="6d06d-274">Create the second call action.</span></span> <span data-ttu-id="6d06d-275">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-275">Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="6d06d-276">建立第二個回應群組答案。</span><span class="sxs-lookup"><span data-stu-id="6d06d-276">Create the second response group answer.</span></span> <span data-ttu-id="6d06d-277">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-277">Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="6d06d-278">建立最高層級提示。</span><span class="sxs-lookup"><span data-stu-id="6d06d-278">Create the top-level prompt.</span></span> <span data-ttu-id="6d06d-279">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-279">Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="6d06d-280">建立最上層問題。</span><span class="sxs-lookup"><span data-stu-id="6d06d-280">Create the top-level question.</span></span> <span data-ttu-id="6d06d-281">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-281">Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="6d06d-282">現在建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="6d06d-282">Now create the workflow.</span></span> <span data-ttu-id="6d06d-283">運行：</span><span class="sxs-lookup"><span data-stu-id="6d06d-283">Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d06d-284">指定為回應群組管理員的所有使用者都必須指派第 CsResponseGroupManager role。</span><span class="sxs-lookup"><span data-stu-id="6d06d-284">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role.</span></span> <span data-ttu-id="6d06d-285">若未指派此角色的使用者，他們就無法管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="6d06d-285">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

