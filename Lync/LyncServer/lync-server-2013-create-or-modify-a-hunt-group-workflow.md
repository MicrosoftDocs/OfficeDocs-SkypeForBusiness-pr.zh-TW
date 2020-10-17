---
title: Lync Server 2013：建立或修改群組搜尋工作流程
description: Lync Server 2013：建立或修改群組搜尋工作流程。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f6374352c87d13b1e5c09bcef267059016eae0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570719"
---
# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="a91ac-103">在 Lync Server 2013 中建立或修改群組搜尋工作流程</span><span class="sxs-lookup"><span data-stu-id="a91ac-103">Create or modify a hunt group workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a91ac-104">_**主題上次修改日期：** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="a91ac-104">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="a91ac-105">使用下列其中一個程式來建立或修改群組搜尋工作流程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-105">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a91ac-106">您可以使用 Lync Server 管理命令介面或回應群組設定工具來建立及修改群組搜尋工作流程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-106">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="a91ac-107">您可以從 Lync Server 控制台存取回應群組設定工具，或是直接從網頁瀏覽器開啟網頁，只要輸入下列 URL: <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-107">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="a91ac-108">使用回應群組設定工具來建立或修改群組搜尋工作流程</span><span class="sxs-lookup"><span data-stu-id="a91ac-108">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="a91ac-109">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="a91ac-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a91ac-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a91ac-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a91ac-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a91ac-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a91ac-112">在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[工作流程]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-112">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="a91ac-113">在 **[工作流程]** 頁面上，按一下 **[建立或編輯工作流程]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-113">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="a91ac-114">在 [ **選取服務** ] 搜尋欄位中，輸入主控您要建立或變更之工作流程的 **ApplicationServer** 服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="a91ac-114">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="a91ac-115">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-115">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-116">回應群組設定工具隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="a91ac-116">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="a91ac-117">您也可以輸入下列 URL: <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>，直接從網頁瀏覽器開啟回應群組設定工具。</span><span class="sxs-lookup"><span data-stu-id="a91ac-117">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="a91ac-118">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a91ac-118">Do one of the following:</span></span>
    
      - <span data-ttu-id="a91ac-119">在 [ **建立新的工作流程**] 下， **按一下 [群組搜尋**] 旁的 [建立]。</span><span class="sxs-lookup"><span data-stu-id="a91ac-119">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="a91ac-120">在 **[管理現有工作流程]** 下，找到想要變更的工作流程，然後在 **[動作]** 下按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-120">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="a91ac-121">如果您準備好讓使用者開始呼叫工作流程，請選取 **[啟用工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="a91ac-121">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-122">若要建立受管理的工作流程，您必須選取 <STRONG>[啟用工作流程</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="a91ac-122">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>.</span></span> <span data-ttu-id="a91ac-123">在您儲存使用中的受管理工作流程之後，您可以修改並停用該工作流程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-123">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="a91ac-124">若要允許同盟使用者撥打群組，請選取 **[針對同盟啟用]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a91ac-124">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="a91ac-125">您也必須具有適用于同盟設定之回應群組應用程式的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="a91ac-125">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-126">全域外部存取原則會套用至回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="a91ac-126">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="a91ac-127">您可以使用 Lync Server 控制台或使用 <STRONG>get-csexternalaccesspolicy</STRONG> 指令程式將 EnableOutsideAccess 參數設定為 True，設定回應群組同盟的全域原則。</span><span class="sxs-lookup"><span data-stu-id="a91ac-127">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="a91ac-128">請記住，除非將站台原則或使用者原則指派給使用者，否則通用原則設定適用於所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a91ac-128">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="a91ac-129">因此在變更回應群組的此設定之前，請確認同盟設定符合您組織的需求。</span><span class="sxs-lookup"><span data-stu-id="a91ac-129">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="a91ac-130">如需有關如何將原則套用至使用者的詳細資訊，請參閱 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-130">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="a91ac-131">如需同盟設定的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-get-csexternalaccesspolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-131">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-132">在 Lync Online 中主控的使用者無法將呼叫放入內部部署中所主控的回應群組。</span><span class="sxs-lookup"><span data-stu-id="a91ac-132">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="a91ac-133">這在混合式部署中，以及內部部署與 Lync Online 部署同盟的情況皆為 true。</span><span class="sxs-lookup"><span data-stu-id="a91ac-133">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="a91ac-134">若要在通話期間隱藏代理人的身分識別，請選取 **[啟用代理人匿名]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a91ac-134">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-135">雖然代理人或來電者可以在建立通話之後新增 IM 及視訊，但是匿名通話不能以立即訊息 (IM) 或視訊開始。</span><span class="sxs-lookup"><span data-stu-id="a91ac-135">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="a91ac-136">匿名代理人也可以保留通話、轉接通話 (無條件轉接及諮詢轉接)，以及駐留及擷取通話。</span><span class="sxs-lookup"><span data-stu-id="a91ac-136">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="a91ac-137">匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、白板和資料共同作業，以及通話記錄。</span><span class="sxs-lookup"><span data-stu-id="a91ac-137">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="a91ac-138">使用 Lync VDI 外掛程式的代理程式可以以匿名方式接收來電，但無法以匿名方式撥打撥出電話。</span><span class="sxs-lookup"><span data-stu-id="a91ac-138">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="a91ac-139">在 [ **輸入要接聽電話的群組位址**] 下，輸入主要 SIP 統一資源識別項 (URI) 會接聽工作流程呼叫的群組的位址。</span><span class="sxs-lookup"><span data-stu-id="a91ac-139">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-140">工作流程的主要 URI 是如何識別及參考工作流程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-140">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="a91ac-141">您輸入的 SIP URI 會建立為 Active Directory 網域服務中的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="a91ac-141">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="a91ac-142">若要建立 URI，該物件在 Active Directory 中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a91ac-142">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="a91ac-143">在 [ **顯示名稱**] 中，輸入您要針對工作流程顯示的名稱 (例如，Sales Response Group) 。</span><span class="sxs-lookup"><span data-stu-id="a91ac-143">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-144">&lt;在顯示名稱中不要包含 "" 或 " &gt; " 字元。</span><span class="sxs-lookup"><span data-stu-id="a91ac-144">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="a91ac-145">請勿使用下列顯示名稱，因為它們是保留的： <STRONG>RGS 存在觀察</STRONG> 程式或 <STRONG>宣告服務</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-145">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="a91ac-146">在 **[電話號碼]** 下，輸入回應群組的線路 URI (例如，+14255550165)。</span><span class="sxs-lookup"><span data-stu-id="a91ac-146">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="a91ac-147">在 **[顯示號碼]** 中，輸入想要針對回應群組顯示的號碼 (例如，+1 (425) 555-0165)。</span><span class="sxs-lookup"><span data-stu-id="a91ac-147">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="a91ac-148"> (選用) 在 [ **描述**] 中，輸入您想要在 Lync 用戶端的連絡人卡片上顯示之工作流程的描述。</span><span class="sxs-lookup"><span data-stu-id="a91ac-148">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="a91ac-149">在 [ **工作流程類型**] 中，選取 [ **受** 回應群組管理員管理此工作流程]。</span><span class="sxs-lookup"><span data-stu-id="a91ac-149">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="a91ac-150">請執行下列動作，將回應群組管理員指派給工作流程：</span><span class="sxs-lookup"><span data-stu-id="a91ac-150">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="a91ac-151">為此工作流程輸入管理員的 SIP URI，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="a91ac-151">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="a91ac-152">輸入其他管理員的 SIP URI，以新增至工作流程，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="a91ac-152">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a91ac-153">指定為回應群組管理員的每一位使用者都必須指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="a91ac-153">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="a91ac-154">若未指派此角色的使用者，他們就無法管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="a91ac-154">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="a91ac-155">在 **[步驟 2 選取語言]** 下，按一下要用於語音辨識及文字轉語音的語言。</span><span class="sxs-lookup"><span data-stu-id="a91ac-155">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="a91ac-156">如果您想要設定歡迎訊息，請在 **[步驟 3 設定歡迎訊息]** 下選取 **[播放歡迎訊息]** 核取方塊，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a91ac-156">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="a91ac-157">若要以文字輸入為來電者轉換成語音的歡迎訊息，按一下 **[使用文字轉語音]**，然後在文字方塊中輸入歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="a91ac-157">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-p114">請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p114">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a91ac-p115">若要使用聲波 (.wav) 或 Windows Media 音訊 (.wma) 檔案錄音做為歡迎訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的音訊檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-164">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="a91ac-164">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a91ac-165">如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-165">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="a91ac-166">在 **[步驟 4 指定您的上班時間]** 的 **[您的時區]** 中，按一下工作流程的時區。</span><span class="sxs-lookup"><span data-stu-id="a91ac-166">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-p117">此時區即為工作流程的來電者和專員所在之時區，可用來計算開啟和關閉的時間。例如，如果工作流程設定為使用「北美東部時區」，而工作流程排定為早上 7:00 開啟，晚上 11:00 關閉，則開啟和關閉的時間就會分別假設為東部時區 7:00 和東部時區 23:00。(您必須使用 24 小時時間標記法輸入時間)。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="a91ac-172">執行下列其中一項，以選取想要使用的上班時間排程類型：</span><span class="sxs-lookup"><span data-stu-id="a91ac-172">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="a91ac-173">若要使用預先定義的上班時間排程，請按一下 **[使用預設排程]**，然後從下拉式清單中選取想要使用的排程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-173">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-174">您至少先前必須已定義一個預設排程，才能選取此選項。</span><span class="sxs-lookup"><span data-stu-id="a91ac-174">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="a91ac-175">您可以使用 <STRONG>New-CSRgsHoursOfBusiness</STRONG> Cmdlet，來定義預設排程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-175">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="a91ac-176">如需詳細資訊，請參閱 <A href="lync-server-2013-optional-define-response-group-business-hours.md"> (選用) 在 Lync Server 2013 中定義回應群組上班時間</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-176">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-177">當您選取預設排程時，<STRONG>[日]</STRONG>、<STRONG>[開啟]</STRONG> 及 <STRONG>[關閉]</STRONG> 會自動填入回應群組可用的日及時數。</span><span class="sxs-lookup"><span data-stu-id="a91ac-177">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="a91ac-178">若要使用只套用至此工作流程的自訂排程，請按一下 **[使用自訂排程]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-178">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="a91ac-179">如果您是建立此工作流程的自訂排程，請按一下回應群組可用之一星期的哪幾天的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a91ac-179">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="a91ac-180">如果您是建立自訂排程，請輸入回應群組可用時每個星期幾的 **[開啟]** 及 **[關閉]** 時間。</span><span class="sxs-lookup"><span data-stu-id="a91ac-180">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-p119"><STRONG>[開啟]</STRONG> 及 <STRONG>[關閉]</STRONG> 時間必須使用 24 小時時間標記法。例如，如果您辦公室平日的辦公時間為 9 點到 5 點，而且會在中午用餐時間關閉，則會將上班時間指定為 <STRONG>[開啟]</STRONG> 9:00、<STRONG>[關閉]</STRONG> 12:00、<STRONG>[開啟]</STRONG> 13:00 以及 <STRONG>[關閉]</STRONG> 17:00。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="a91ac-183">如果您想要在辦公室關閉時播放訊息，請選取 **[在回應群組下班時播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="a91ac-183">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="a91ac-184">若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="a91ac-184">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-p120">請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a91ac-p121">若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-191">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="a91ac-191">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a91ac-192">如需支援的音訊檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中回應群組的技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-192">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="a91ac-193">指定在播放訊息之後如何處理通話 (如果有設定訊息)：</span><span class="sxs-lookup"><span data-stu-id="a91ac-193">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="a91ac-194">若要中斷來電，按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-194">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="a91ac-195">若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="a91ac-195">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a91ac-196">語音信箱位址的格式為 \<username\> @ \<domainName\> (例如，bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a91ac-196">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="a91ac-197">若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。</span><span class="sxs-lookup"><span data-stu-id="a91ac-197">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a91ac-198">使用者位址的格式為 \<username\> @ \<domainName\> 。</span><span class="sxs-lookup"><span data-stu-id="a91ac-198">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="a91ac-199">若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="a91ac-199">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a91ac-200">電話號碼的格式為 \<number\> @ \<domainName\> (例如，+ 14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a91ac-200">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a91ac-201">網域名稱會用來將來電者路由到正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="a91ac-201">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="a91ac-202">在 **[步驟 5 指定您的假日]** 下，按一下可定義回應群組沒上班之天數的一或多個假日集的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a91ac-202">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-203">您需要先定義假日及假日集，再設定工作流程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-203">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="a91ac-204">使用 <STRONG>New-CsRgsHoliday</STRONG> 及 <STRONG>New-CsRgsHolidaySet</STRONG> Cmdlet，可定義假日及假日集。</span><span class="sxs-lookup"><span data-stu-id="a91ac-204">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="a91ac-205">如需詳細資訊，請參閱 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md"> (選用) 在 Lync Server 2013 中定義回應群組假日集</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-205">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="a91ac-206">如果您想要在假日時播放訊息，請選取 **[在假日期間播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="a91ac-206">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="a91ac-207">若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="a91ac-207">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-p127">請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="a91ac-p128">若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-214">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="a91ac-214">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a91ac-215">如需支援的音訊檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中回應群組的技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-215">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="a91ac-216">指定在播放訊息之後如何處理通話 (如果有設定訊息)：</span><span class="sxs-lookup"><span data-stu-id="a91ac-216">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="a91ac-217">若要中斷來電，按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-217">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="a91ac-218">若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="a91ac-218">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="a91ac-219">語音信箱位址的格式為 \<username\> @ \<domainName\> (例如，bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a91ac-219">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="a91ac-220">若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。</span><span class="sxs-lookup"><span data-stu-id="a91ac-220">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="a91ac-221">使用者位址的格式為 \<username\> @ \<domainName\> 。</span><span class="sxs-lookup"><span data-stu-id="a91ac-221">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="a91ac-222">若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="a91ac-222">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="a91ac-223">電話號碼的格式為 \<number\> @ \<domainName\> (例如，+ 14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="a91ac-223">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="a91ac-224">網域名稱會用來將來電者路由到正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="a91ac-224">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="a91ac-225">在 **[步驟 6 設定佇列]** 的 **[選取要接聽電話的佇列]** 下，選取想要保留來電者直到專員有空的佇列。</span><span class="sxs-lookup"><span data-stu-id="a91ac-225">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="a91ac-226">在 **[步驟 7 設定等候音樂]** 下，選擇您要來電者在等候專員時所聆聽的音樂，方法如下：</span><span class="sxs-lookup"><span data-stu-id="a91ac-226">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="a91ac-227">若要使用預設的等候音樂錄音，按一下 **[使用預設]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-227">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="a91ac-p133">若要使用音訊檔案錄音做為等候音樂，請按一下 **[選取音樂檔案]**。如果您想要上傳新的音訊檔案，請按一下 **[音樂檔案]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="a91ac-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a91ac-232">所有使用者提供的音訊檔案都必須符合特定要求。</span><span class="sxs-lookup"><span data-stu-id="a91ac-232">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="a91ac-233">如需支援的音訊檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中回應群組的技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-233">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="a91ac-234">按一下 **[部署]**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-234">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="a91ac-235">使用 Windows PowerShell 建立或修改群組搜尋工作流程</span><span class="sxs-lookup"><span data-stu-id="a91ac-235">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="a91ac-236">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="a91ac-236">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="a91ac-237">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a91ac-237">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a91ac-238">建立要對歡迎使用的訊息播放的提示，並將其儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="a91ac-238">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="a91ac-239">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="a91ac-239">At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="a91ac-240">例如：</span><span class="sxs-lookup"><span data-stu-id="a91ac-240">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-241">若要使用音訊檔以進行提示，請使用 <STRONG>Import-CsRgsAudioFile</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a91ac-241">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="a91ac-242">如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>。</span><span class="sxs-lookup"><span data-stu-id="a91ac-242">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="a91ac-243">取得會定向來電之佇列或問題的身分識別。</span><span class="sxs-lookup"><span data-stu-id="a91ac-243">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="a91ac-244">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="a91ac-244">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="a91ac-245">如需建立佇列的詳細資訊，請參閱 [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)。</span><span class="sxs-lookup"><span data-stu-id="a91ac-245">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="a91ac-246">定義當工作流程在上班時間開啟時所採取的預設動作，並將其儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="a91ac-246">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="a91ac-247">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="a91ac-247">At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-248">若要群組搜尋工作流程，預設動作必須將來電導向至佇列。</span><span class="sxs-lookup"><span data-stu-id="a91ac-248">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="a91ac-249">這是 active 工作流程所需的參數。</span><span class="sxs-lookup"><span data-stu-id="a91ac-249">This is parameter is required for active workflows.</span></span> <span data-ttu-id="a91ac-250">不需要使用非使用中的工作流程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-250">It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="a91ac-251">例如：</span><span class="sxs-lookup"><span data-stu-id="a91ac-251">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="a91ac-252">若要定義上班時間和假日，您必須在建立或修改工作流程之前加以建立。</span><span class="sxs-lookup"><span data-stu-id="a91ac-252">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="a91ac-253">如需詳細資訊，請參閱 [ (選用) 在 lync server 2013 中定義回應群組上班時間](lync-server-2013-optional-define-response-group-business-hours.md) 和 [ (選用) 在 lync Server 2013 中定義回應群組假日集](lync-server-2013-optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="a91ac-253">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="a91ac-254">如果您想要在上班時間或假期內收到來電的提示，請使用 **New-CsRgsPrompt** Cmdlet 來定義提示，然後使用 **New-CsRgsCallAction** 來定義要在提示之後採取的動作。</span><span class="sxs-lookup"><span data-stu-id="a91ac-254">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="a91ac-255">如需詳細資訊，請參閱 [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) 和 [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)。</span><span class="sxs-lookup"><span data-stu-id="a91ac-255">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="a91ac-256">取得 Lync Server 回應群組服務的服務名稱，並將其指派給變數。</span><span class="sxs-lookup"><span data-stu-id="a91ac-256">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="a91ac-257">在命令中執行：</span><span class="sxs-lookup"><span data-stu-id="a91ac-257">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="a91ac-258">建立或修改工作流程。</span><span class="sxs-lookup"><span data-stu-id="a91ac-258">Create or modify the workflow.</span></span> <span data-ttu-id="a91ac-259">若要建立工作流程，請使用 **New-CsRgsWorkflow**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-259">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="a91ac-260">若要修改工作流程，請使用 **Set-CsRgsWorkflow**。</span><span class="sxs-lookup"><span data-stu-id="a91ac-260">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="a91ac-261">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="a91ac-261">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="a91ac-262">例如：</span><span class="sxs-lookup"><span data-stu-id="a91ac-262">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a91ac-263">指派給工作流程管理員的所有使用者，都必須指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="a91ac-263">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a91ac-264">如需其他選擇性參數的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> 或 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="a91ac-264">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a91ac-265">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a91ac-265">See Also</span></span>


[<span data-ttu-id="a91ac-266"> (選用) 在 Lync Server 2013 中定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="a91ac-266">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="a91ac-267"> (選用) 在 Lync Server 2013 中定義回應群組上班時間</span><span class="sxs-lookup"><span data-stu-id="a91ac-267">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="a91ac-268">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="a91ac-268">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="a91ac-269">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="a91ac-269">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="a91ac-270">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="a91ac-270">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="a91ac-271">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="a91ac-271">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

