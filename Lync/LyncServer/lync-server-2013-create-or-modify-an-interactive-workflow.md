---
title: Lync Server 2013：建立或修改互動式工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede826df74d63270afe2ea3f4e992cdcddbbe412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="dda56-102">在 Lync Server 2013 中建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="dda56-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dda56-103">_**主題上次修改日期：** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="dda56-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="dda56-104">使用下列其中一個程式來建立或修改互動式工作流程。</span><span class="sxs-lookup"><span data-stu-id="dda56-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dda56-105">您可以使用 Lync Server 管理命令介面或 [回應群組設定] 工具來建立及修改互動式工作流程。</span><span class="sxs-lookup"><span data-stu-id="dda56-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="dda56-106">您可以從 Lync Server [控制台] 存取 [回應群組設定] 工具，或是透過在網頁瀏覽器中輸入下列 URL 來直接開啟網頁： <STRONG>HTTPs://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="dda56-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="dda56-107">使用 [回應群組設定] 工具來建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="dda56-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="dda56-108">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="dda56-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="dda56-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dda56-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dda56-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dda56-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dda56-111">在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="dda56-112">在 [**工作流程**] 頁面上，按一下 [**建立或編輯工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="dda56-113">在 [**選取服務**搜尋] 欄位中，輸入您要建立或修改之工作流程之**ApplicationServer**服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="dda56-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="dda56-114">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dda56-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-115">[回應群組設定] 工具隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="dda56-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="dda56-116">您也可以輸入下列 URL，直接從網頁瀏覽器開啟 [回應群組設定] 工具： <STRONG>HTTPs://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="dda56-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="dda56-117">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="dda56-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="dda56-118">在 [**建立新工作流程**] 底下，按一下 [**互動式**] 旁的 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="dda56-119">在 [**管理現有的工作流程**] 底下，找出您要變更的工作流程，然後在 [**動作**] 底下，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="dda56-120">如果您未準備好讓使用者開始呼叫工作流程，請清除 [**啟用工作流程**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dda56-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-121">如果您要建立受管理的工作流程，您必須選取 [<STRONG>啟用工作流程</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="dda56-121">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>.</span></span> <span data-ttu-id="dda56-122">儲存作用中受管理的工作流程之後，您就可以進行修改及停用。</span><span class="sxs-lookup"><span data-stu-id="dda56-122">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="dda56-123">若要允許聯盟使用者呼叫群組，請選取 [**啟用聯盟**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dda56-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="dda56-124">您也必須有可套用至針對同盟設定之回應群組應用程式的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="dda56-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-125">全域外部存取原則會套用至回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="dda56-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="dda56-126">您可以使用 Lync Server [控制台]，或使用<STRONG>CsExternalAccessPolicy</STRONG> Cmdlet 將 EnableOutsideAccess 參數設定為 True，來設定回應群組同盟的全域原則。</span><span class="sxs-lookup"><span data-stu-id="dda56-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="dda56-127">請記住，除非指派網站或使用者原則，否則全域原則設定將會套用至所有使用者。</span><span class="sxs-lookup"><span data-stu-id="dda56-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="dda56-128">因此，在變更回應群組的此設定之前，請確定同盟設定符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="dda56-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="dda56-129">如需如何將原則套用至使用者的詳細資料，請參閱<A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部存取原則</A>。</span><span class="sxs-lookup"><span data-stu-id="dda56-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="dda56-130">如需同盟設定的詳細資訊，請參閱 Lync Server 管理命令介面檔中的<STRONG>設定 CsExternalAccessPolicy</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="dda56-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-131">在 Lync Online 中託管的使用者無法將呼叫權放在內部部署中託管的回應群組。</span><span class="sxs-lookup"><span data-stu-id="dda56-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="dda56-132">這在混合式部署中，以及內部部署與 Lync Online 部署聯盟的情況下，都是如此。</span><span class="sxs-lookup"><span data-stu-id="dda56-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="dda56-133">若要在呼叫期間隱藏代理程式的身分識別，請選取 [**啟用代理程式匿名**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dda56-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-134">匿名通話不能以立即訊息（IM）或影片啟動，不過代理或來電者可以在通話建立之後，新增 IM 和影片。</span><span class="sxs-lookup"><span data-stu-id="dda56-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="dda56-135">匿名代理程式也可以保留通話、轉接呼叫（盲人與顧問式轉移），以及寄存與取回通話。</span><span class="sxs-lookup"><span data-stu-id="dda56-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="dda56-136">匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、whiteboarding 與資料共同作業，以及通話錄製。</span><span class="sxs-lookup"><span data-stu-id="dda56-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="dda56-137">使用 Lync VDI 外掛程式的代理程式可以匿名接收來電，但不能匿名撥出來電。</span><span class="sxs-lookup"><span data-stu-id="dda56-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="dda56-138">在 [**輸入將會接收來電的群組的位址**] 底下，輸入群組的主要 SIP 統一資源識別項（URI）位址，將會應答工作流程的呼叫。</span><span class="sxs-lookup"><span data-stu-id="dda56-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="dda56-139">在 [**顯示名稱**] 中，輸入您要顯示的工作流程名稱（例如 [銷售 IVR] 回應群組）。</span><span class="sxs-lookup"><span data-stu-id="dda56-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-140">不要在顯示名稱中&lt;包含 ""&gt;或 "" 字元。</span><span class="sxs-lookup"><span data-stu-id="dda56-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="dda56-141">請勿使用下列顯示名稱，因為它們是保留的： RGS 目前狀態觀察程式或宣告服務。</span><span class="sxs-lookup"><span data-stu-id="dda56-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="dda56-142">在 [**電話號碼**] 中，輸入回應群組的行 URI （例如 + 14255550165）。</span><span class="sxs-lookup"><span data-stu-id="dda56-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="dda56-143">在 [**顯示號碼**] 中，輸入您想要顯示給回應群組的數位（例如 + 1 （425）555-0165）。</span><span class="sxs-lookup"><span data-stu-id="dda56-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="dda56-144">可選在 [**描述**] 中，輸入您想要在 Lync 用戶端的連絡人卡片上顯示之工作流程的描述。</span><span class="sxs-lookup"><span data-stu-id="dda56-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="dda56-145">在 [**工作流程類型**] 中，如果此工作流程將由回應群組管理員管理，請選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="dda56-146">請執行下列動作，將回應群組管理員指派給工作流程：</span><span class="sxs-lookup"><span data-stu-id="dda56-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="dda56-147">輸入此工作流程的管理員 SIP URI，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="dda56-148">輸入要新增至工作流程的其他管理員 SIP URI，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dda56-149">指派為回應群組管理員的每位使用者，都必須獲指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="dda56-149">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="dda56-150">如果沒有為使用者指派這個角色，就不能管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="dda56-150">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="dda56-151">在 [**步驟2選取語言**] 底下，按一下要用於語音辨識和文字轉換語音的語言。</span><span class="sxs-lookup"><span data-stu-id="dda56-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="dda56-152">如果您想要設定歡迎訊息，請在 [**步驟3設定歡迎訊息**] 底下，選取 [**播放歡迎訊息**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="dda56-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="dda56-153">若要將歡迎郵件輸入為已轉換為呼叫者語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="dda56-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-154">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="dda56-154">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="dda56-155">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="dda56-155">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="dda56-156">若要使用波形或 Windows Media 音訊檔案錄製以取得歡迎訊息，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-156">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**.</span></span> <span data-ttu-id="dda56-157">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="dda56-157">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="dda56-158">在新的瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的音訊檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-158">In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="dda56-159">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="dda56-159">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-160">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="dda56-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="dda56-161">如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="dda56-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="dda56-162">在 [**步驟4指定您的工作**時間] 底下的 [**您的時區**] 方塊中，按一下工作流程的時區。</span><span class="sxs-lookup"><span data-stu-id="dda56-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-163">[時區] 是工作流程的呼叫者和代理程式所在的時區。</span><span class="sxs-lookup"><span data-stu-id="dda56-163">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="dda56-164">它是用來計算開啟和關閉時間。</span><span class="sxs-lookup"><span data-stu-id="dda56-164">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="dda56-165">例如，如果工作流程設定為使用北美東部時區，且工作流程排程在 7:00 A.M. 開啟。</span><span class="sxs-lookup"><span data-stu-id="dda56-165">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="dda56-166">接著，請在 11:00 P.M.，將開啟和關閉時間分別視為7:00 東部時間和11:00 東部時間。</span><span class="sxs-lookup"><span data-stu-id="dda56-166">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively.</span></span> <span data-ttu-id="dda56-167">（您必須以24小時制時間格式輸入時間。）</span><span class="sxs-lookup"><span data-stu-id="dda56-167">(You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="dda56-168">請執行下列其中一項動作，選取您要使用的商務時間排程類型：</span><span class="sxs-lookup"><span data-stu-id="dda56-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="dda56-169">若要使用預先定義的上班時間排程，請按一下 [**使用預設排程**]，然後從下拉式清單中選取您要使用的排程。</span><span class="sxs-lookup"><span data-stu-id="dda56-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-170">您之前必須已定義至少一個預設排程，才能選取此選項。</span><span class="sxs-lookup"><span data-stu-id="dda56-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="dda56-171">您可以使用<STRONG>CSRgsHoursOfBusiness</STRONG> Cmdlet 來定義預設排程。</span><span class="sxs-lookup"><span data-stu-id="dda56-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="dda56-172">如需詳細資訊，請參閱<A href="lync-server-2013-optional-define-response-group-business-hours.md">（選用）在 Lync Server 2013 中定義回應群組的上班時間</A>。</span><span class="sxs-lookup"><span data-stu-id="dda56-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="dda56-173">當您選取 [預置] 排程、[<STRONG>天</STRONG>]、[<STRONG>開啟</STRONG>] 和 [<STRONG>關閉</STRONG>] 時，系統會自動填入回應群組可用的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="dda56-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="dda56-174">若要使用只適用于此工作流程的自訂排程，請按一下 [**使用自訂排程**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="dda56-175">如果您要建立此工作流程的自訂排程，請按一下回應群組可用之周的日期核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dda56-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="dda56-176">如果您要建立自訂排程，請在回應群組可用時，輸入 [**開啟**] 和 [**關閉**] 時間。</span><span class="sxs-lookup"><span data-stu-id="dda56-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-177">[<STRONG>開啟</STRONG>] 和 [<STRONG>關閉</STRONG>] 時間必須是24小時制時間格式。</span><span class="sxs-lookup"><span data-stu-id="dda56-177">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation.</span></span> <span data-ttu-id="dda56-178">例如，如果您的 office 的工作時間為9到5個工作日，而午餐時間為中午，則會將上班時間指定為<STRONG>開啟</STRONG>9:00、<STRONG>關閉</STRONG>12:00、<STRONG>開啟</STRONG>13:00，然後<STRONG>關閉</STRONG>17:00。</span><span class="sxs-lookup"><span data-stu-id="dda56-178">For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="dda56-179">如果您想要在 office 未開啟時播放郵件，請選取 [**當回應群組在上班時間以外時播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="dda56-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="dda56-180">若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="dda56-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-181">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="dda56-181">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="dda56-182">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="dda56-182">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="dda56-183">若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-183">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="dda56-184">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="dda56-184">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="dda56-185">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-185">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="dda56-186">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="dda56-186">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-187">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="dda56-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="dda56-188">如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="dda56-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="dda56-189">指定在播放郵件後如何處理呼叫（如果已設定郵件）：</span><span class="sxs-lookup"><span data-stu-id="dda56-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="dda56-190">若要中斷通話，請按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="dda56-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="dda56-191">若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="dda56-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="dda56-192">語音信箱位址的\<格式是 [使用者名\>@\<功能變數名稱\> ] （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="dda56-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="dda56-193">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。</span><span class="sxs-lookup"><span data-stu-id="dda56-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="dda56-194">使用者位址的\<格式是 [使用者名\>@\<功能變數名稱\>]。</span><span class="sxs-lookup"><span data-stu-id="dda56-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="dda56-195">若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dda56-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="dda56-196">電話\<號碼的格式是數位\>@\<domainname\> （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="dda56-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="dda56-197">功能變數名稱是用來將呼叫者路由至正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="dda56-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="dda56-198">在 [**步驟5指定您的假日**] 底下，按一下一或多組假期的核取方塊，以定義回應群組結束的日期。</span><span class="sxs-lookup"><span data-stu-id="dda56-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-199">您必須先定義假日和假日集，然後才能設定工作流程。</span><span class="sxs-lookup"><span data-stu-id="dda56-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="dda56-200">使用<STRONG>新的-CsRgsHoliday</STRONG>和<STRONG>CsRgsHolidaySet</STRONG> Cmdlet 來定義假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="dda56-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="dda56-201">如需詳細資訊，請參閱<A href="lync-server-2013-optional-define-response-group-holiday-sets.md">（選用）在 Lync Server 2013 中定義回應群組假日集</A>。</span><span class="sxs-lookup"><span data-stu-id="dda56-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="dda56-202">如果您想要在假日上播放郵件，請選取 [在**假日期間播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="dda56-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="dda56-203">若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="dda56-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-204">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="dda56-204">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="dda56-205">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="dda56-205">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="dda56-206">若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-206">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="dda56-207">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="dda56-207">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="dda56-208">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-208">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="dda56-209">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="dda56-209">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-210">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="dda56-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="dda56-211">如需支援的音訊檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="dda56-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="dda56-212">指定在播放郵件後如何處理呼叫（如果已設定郵件）：</span><span class="sxs-lookup"><span data-stu-id="dda56-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="dda56-213">若要中斷通話，請按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="dda56-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="dda56-214">若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="dda56-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="dda56-215">語音信箱位址的\<格式是 [使用者名\>@\<功能變數名稱\> ] （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="dda56-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="dda56-216">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。</span><span class="sxs-lookup"><span data-stu-id="dda56-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="dda56-217">使用者位址的\<格式是 [使用者名\>@\<功能變數名稱\>]。</span><span class="sxs-lookup"><span data-stu-id="dda56-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="dda56-218">若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="dda56-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="dda56-219">電話\<號碼的格式是數位\>@\<domainname\> （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="dda56-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="dda56-220">功能變數名稱是用來將呼叫者路由至正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="dda56-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="dda56-221">在 [**步驟6設定暫停的音樂**] 底下，請執行下列其中一項動作，選擇您想要讓呼叫者在等待代理程式時聆聽的內容：</span><span class="sxs-lookup"><span data-stu-id="dda56-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="dda56-222">若要使用預設的音樂保留錄製，請按一下 [**使用預設值**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="dda56-223">若要將音訊檔案錄製用於等候音樂，請按一下 [**選取音樂**檔案]。</span><span class="sxs-lookup"><span data-stu-id="dda56-223">To use an audio file recording for the on-hold music, click **Select a music file**.</span></span> <span data-ttu-id="dda56-224">如果您想要上傳新的音訊檔案，請按一下 [**音樂**檔案] 連結。</span><span class="sxs-lookup"><span data-stu-id="dda56-224">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="dda56-225">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-225">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="dda56-226">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="dda56-226">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-227">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="dda56-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="dda56-228">如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="dda56-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="dda56-229">在 [**步驟7設定互動式語音回應**] 底下的 **[使用者將會聽到下列文字] 或 [錄製的郵件**] 標題中，指定要求呼叫者的問題，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dda56-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="dda56-230">若要以文字格式輸入問題，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入問題。</span><span class="sxs-lookup"><span data-stu-id="dda56-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-231">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="dda56-231">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="dda56-232">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="dda56-232">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-233">"#" 符號是由文字到語音引擎轉譯為「數位」一詞。</span><span class="sxs-lookup"><span data-stu-id="dda56-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="dda56-234">如果您需要參照 # 鍵，您應該在提示中使用索引鍵名稱，而不是符號。</span><span class="sxs-lookup"><span data-stu-id="dda56-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="dda56-235">例如，若要與銷售額交談，請按井號鍵。</span><span class="sxs-lookup"><span data-stu-id="dda56-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="dda56-236">若要使用含有問題的預先錄製音訊檔案，請按一下 [**選取錄製**]，然後按一下 [**錄製**] 連結來上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="dda56-236">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="dda56-237">在新的瀏覽器視窗中，按一下 **[流覽]**，選取音訊檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-237">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="dda56-238">按一下 **[上傳**] 載入檔案，然後選擇您可以在文字方塊中輸入問題（這可讓您將問題及來電者回應轉寄到回應的代理程式）。</span><span class="sxs-lookup"><span data-stu-id="dda56-238">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dda56-239">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="dda56-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="dda56-240">如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="dda56-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="dda56-241">在 [**回應 1**] 底下，請執行下列動作，以指定第一次可能的問題答案：</span><span class="sxs-lookup"><span data-stu-id="dda56-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dda56-242">請勿在任何語音回復中使用引號（"）。</span><span class="sxs-lookup"><span data-stu-id="dda56-242">Do not use quotation marks (") in any voice responses.</span></span> <span data-ttu-id="dda56-243">引號會導致 IVR 失敗。</span><span class="sxs-lookup"><span data-stu-id="dda56-243">Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-244">您可以選擇允許呼叫者使用語音、數位數位鍵台輸入或兩者同時接聽。</span><span class="sxs-lookup"><span data-stu-id="dda56-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="dda56-245">如果您想要讓來電者使用語音進行回應，請在 [**輸入語音回應**] 中輸入答案。</span><span class="sxs-lookup"><span data-stu-id="dda56-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="dda56-246">如果您想要允許呼叫者以鍵盤上的按鍵進行回應，請按一下 [**數位**] 中的小數位。</span><span class="sxs-lookup"><span data-stu-id="dda56-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="dda56-247">指定是否要將呼叫者路由到佇列，或是依以下方式提出其他問題：</span><span class="sxs-lookup"><span data-stu-id="dda56-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="dda56-248">若要將呼叫者路由到佇列，請按一下 [**傳送至佇列**]，然後在 [**選取佇列**] 中，按一下您要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="dda56-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="dda56-249">若要提出其他問題，請按一下 [**提出其他問題**]，然後按一下 [**使用文字轉換語音**] 並輸入問題，或按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-249">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**.</span></span> <span data-ttu-id="dda56-250">使用本節中的 [回應群組]，指定最多四個可能回應其他問題的回應，以及每個回應所要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="dda56-250">Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response.</span></span> <span data-ttu-id="dda56-251">若要指定第三或第四種可能的回復，請按一下 [**回應 3** ] 核取方塊或 [**回應 4** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dda56-251">To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="dda56-252">重複步驟28和29，以指定可能的回應，以及針對每個回應所採取的動作，指定最多三個可能的原始問題答案。</span><span class="sxs-lookup"><span data-stu-id="dda56-252">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response.</span></span> <span data-ttu-id="dda56-253">若要指定第三個或第四個可能的答案，請按一下 [**回應 3** ] 核取方塊或 [**回應 4** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dda56-253">To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="dda56-254">按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="dda56-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="dda56-255">使用 Windows PowerShell 來建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="dda56-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="dda56-256">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="dda56-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="dda56-257">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="dda56-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dda56-258">檢索回應群組服務的服務名稱，並將它指派給變數。</span><span class="sxs-lookup"><span data-stu-id="dda56-258">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="dda56-259">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="dda56-259">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="dda56-260">互動式工作流程需要兩個或多個佇列，以及兩個以上的代理群組。</span><span class="sxs-lookup"><span data-stu-id="dda56-260">An interactive workflow requires two or more queues and two or more agent groups.</span></span> <span data-ttu-id="dda56-261">首先，建立代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="dda56-261">First, create the agent groups.</span></span> <span data-ttu-id="dda56-262">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-262">Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="dda56-263">建立佇列。</span><span class="sxs-lookup"><span data-stu-id="dda56-263">Create the queues.</span></span> <span data-ttu-id="dda56-264">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-264">Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="dda56-265">建立第一個回應群組提示。</span><span class="sxs-lookup"><span data-stu-id="dda56-265">Create the first response group prompt.</span></span> <span data-ttu-id="dda56-266">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-266">Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="dda56-267">然後建立在提示之後要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="dda56-267">Then create the action to be performed after the prompt.</span></span> <span data-ttu-id="dda56-268">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-268">Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="dda56-269">建立第一個回應群組答案。</span><span class="sxs-lookup"><span data-stu-id="dda56-269">Create the first response group answer.</span></span> <span data-ttu-id="dda56-270">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-270">Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="dda56-271">現在，建立第二個提示、通話動作及答案。</span><span class="sxs-lookup"><span data-stu-id="dda56-271">Now create the second prompt, call action, and answer.</span></span> <span data-ttu-id="dda56-272">首先建立提示。</span><span class="sxs-lookup"><span data-stu-id="dda56-272">First create the prompt.</span></span> <span data-ttu-id="dda56-273">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-273">Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="dda56-274">建立第二個通話動作。</span><span class="sxs-lookup"><span data-stu-id="dda56-274">Create the second call action.</span></span> <span data-ttu-id="dda56-275">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-275">Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="dda56-276">建立第二個回應群組答案。</span><span class="sxs-lookup"><span data-stu-id="dda56-276">Create the second response group answer.</span></span> <span data-ttu-id="dda56-277">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-277">Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="dda56-278">建立最上層的提示。</span><span class="sxs-lookup"><span data-stu-id="dda56-278">Create the top-level prompt.</span></span> <span data-ttu-id="dda56-279">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-279">Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="dda56-280">建立最上層的問題。</span><span class="sxs-lookup"><span data-stu-id="dda56-280">Create the top-level question.</span></span> <span data-ttu-id="dda56-281">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-281">Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="dda56-282">現在，建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="dda56-282">Now create the workflow.</span></span> <span data-ttu-id="dda56-283">用盡</span><span class="sxs-lookup"><span data-stu-id="dda56-283">Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dda56-284">已指定為回應群組管理員的所有使用者，都必須指派第 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="dda56-284">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role.</span></span> <span data-ttu-id="dda56-285">如果沒有為使用者指派這個角色，就不能管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="dda56-285">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

