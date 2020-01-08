---
title: Lync Server 2013：建立或修改查尋群組工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c927b10107626c1d40c33290b30f331f660e45e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="7ab49-102">在 Lync Server 2013 中建立或修改查尋群組工作流程</span><span class="sxs-lookup"><span data-stu-id="7ab49-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ab49-103">_**主題上次修改日期：** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="7ab49-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="7ab49-104">使用下列其中一個程式來建立或修改查尋群組工作流程。</span><span class="sxs-lookup"><span data-stu-id="7ab49-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ab49-105">您可以使用 Lync Server 管理命令介面或 [回應群組設定] 工具來建立及修改查尋群組工作流程。</span><span class="sxs-lookup"><span data-stu-id="7ab49-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="7ab49-106">您可以從 Lync Server [控制台] 存取 [回應群組設定] 工具，或是透過在網頁瀏覽器中輸入下列 URL 來直接開啟網頁： <STRONG>HTTPs://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="7ab49-107">使用 [回應群組設定] 工具來建立或修改查尋群組工作流程</span><span class="sxs-lookup"><span data-stu-id="7ab49-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="7ab49-108">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="7ab49-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="7ab49-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7ab49-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7ab49-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7ab49-111">在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="7ab49-112">在 [**工作流程**] 頁面上，按一下 [**建立或編輯工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="7ab49-113">在 [**選取服務**搜尋] 欄位中，輸入您要建立或變更之工作流程之**ApplicationServer**服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="7ab49-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="7ab49-114">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7ab49-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-115">[回應群組設定] 工具隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="7ab49-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="7ab49-116">您也可以輸入下列 URL，直接從網頁瀏覽器開啟 [回應群組設定] 工具： <STRONG>HTTPs://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="7ab49-117">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="7ab49-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="7ab49-118">在 [**建立新工作流程**] 底下，**按一下 [查尋群組**] 旁的 [建立]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="7ab49-119">在 [**管理現有的工作流程**] 底下，找出您要變更的工作流程，然後在 [**動作**] 底下，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="7ab49-120">如果您已準備好讓使用者開始呼叫工作流程，請選取 [**啟用工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-121">如果您要建立受管理的工作流程，您必須選取 [<STRONG>啟用工作流程</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-121">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>.</span></span> <span data-ttu-id="7ab49-122">儲存作用中受管理的工作流程之後，您就可以進行修改及停用。</span><span class="sxs-lookup"><span data-stu-id="7ab49-122">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="7ab49-123">若要允許聯盟使用者呼叫群組，請選取 [**啟用聯盟**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7ab49-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="7ab49-124">您也必須有可套用至針對同盟設定之回應群組應用程式的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="7ab49-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-125">全域外部存取原則會套用至回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="7ab49-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="7ab49-126">您可以使用 Lync Server [控制台]，或使用<STRONG>CsExternalAccessPolicy</STRONG> Cmdlet 將 EnableOutsideAccess 參數設定為 True，來設定回應群組同盟的全域原則。</span><span class="sxs-lookup"><span data-stu-id="7ab49-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="7ab49-127">請記住，除非指派網站或使用者原則，否則全域原則設定將會套用至所有使用者。</span><span class="sxs-lookup"><span data-stu-id="7ab49-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="7ab49-128">因此，在變更回應群組的此設定之前，請確定同盟設定符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="7ab49-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="7ab49-129">如需如何將原則套用至使用者的詳細資料，請參閱<A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部存取原則</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="7ab49-130">如需同盟設定的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">設定 CsExternalAccessPolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-131">在 Lync Online 中託管的使用者無法將呼叫權放在內部部署中託管的回應群組。</span><span class="sxs-lookup"><span data-stu-id="7ab49-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="7ab49-132">這在混合式部署中，以及內部部署與 Lync Online 部署聯盟的情況下，都是如此。</span><span class="sxs-lookup"><span data-stu-id="7ab49-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="7ab49-133">若要在呼叫期間隱藏代理程式的身分識別，請選取 [**啟用代理程式匿名**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7ab49-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-134">匿名通話不能以立即訊息（IM）或影片啟動，不過代理或來電者可以在通話建立之後，新增 IM 和影片。</span><span class="sxs-lookup"><span data-stu-id="7ab49-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="7ab49-135">匿名代理程式也可以保留通話、轉接呼叫（盲人與顧問式轉移），以及寄存與取回通話。</span><span class="sxs-lookup"><span data-stu-id="7ab49-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="7ab49-136">匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、whiteboarding 與資料共同作業，以及通話錄製。</span><span class="sxs-lookup"><span data-stu-id="7ab49-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="7ab49-137">使用 Lync VDI 外掛程式的代理程式可以匿名接收來電，但不能匿名撥出來電。</span><span class="sxs-lookup"><span data-stu-id="7ab49-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="7ab49-138">在 [**輸入將會接收來電的群組的位址**] 底下，輸入群組的主要 SIP 統一資源識別項（URI）位址，將會應答工作流程的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7ab49-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-139">工作流程的主要 URI 是識別及參照工作流程的方式。</span><span class="sxs-lookup"><span data-stu-id="7ab49-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="7ab49-140">您輸入的 SIP URI 是在 Active Directory 網域服務中建立為連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="7ab49-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="7ab49-141">若要建立 URI，物件在 Active Directory 中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7ab49-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="7ab49-142">在 [**顯示名稱**] 中，輸入您要顯示的工作流程名稱（例如 [銷售回應] 群組）。</span><span class="sxs-lookup"><span data-stu-id="7ab49-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-143">不要在顯示名稱中&lt;包含 ""&gt;或 "" 字元。</span><span class="sxs-lookup"><span data-stu-id="7ab49-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="7ab49-144">請勿使用下列顯示名稱，因為它們是保留的： <STRONG>RGS 目前狀態觀察</STRONG>程式或<STRONG>宣告服務</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="7ab49-145">在 [**電話號碼**] 下，輸入回應群組的行 URI （例如 + 14255550165）。</span><span class="sxs-lookup"><span data-stu-id="7ab49-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="7ab49-146">在 [**顯示號碼**] 中，輸入您想要顯示給回應群組的數位（例如 + 1 （425）555-0165）。</span><span class="sxs-lookup"><span data-stu-id="7ab49-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="7ab49-147">可選在 [**描述**] 中，輸入您想要在 Lync 用戶端的連絡人卡片上顯示之工作流程的描述。</span><span class="sxs-lookup"><span data-stu-id="7ab49-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="7ab49-148">在 [**工作流程類型**] 中，如果此工作流程將由回應群組管理員管理，請選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="7ab49-149">請執行下列動作，將回應群組管理員指派給工作流程：</span><span class="sxs-lookup"><span data-stu-id="7ab49-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="7ab49-150">輸入此工作流程的管理員 SIP URI，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="7ab49-151">輸入要新增至工作流程的其他管理員 SIP URI，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7ab49-152">指派為回應群組管理員的每位使用者，都必須獲指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="7ab49-152">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="7ab49-153">如果沒有為使用者指派這個角色，就不能管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="7ab49-153">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="7ab49-154">在 [**步驟2選取語言**] 底下，按一下您要用於語音辨識和文字轉換語音的語言。</span><span class="sxs-lookup"><span data-stu-id="7ab49-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="7ab49-155">如果您想要設定歡迎訊息，請在 [**步驟3設定歡迎訊息**] 底下，選取 [**播放歡迎訊息**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="7ab49-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="7ab49-156">若要將歡迎郵件輸入為已轉換為呼叫者語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="7ab49-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-157">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="7ab49-157">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="7ab49-158">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7ab49-158">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="7ab49-159">若要使用波形（.wav）或 Windows Media 音訊（.wma）檔案錄製 [歡迎] 訊息，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-159">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**.</span></span> <span data-ttu-id="7ab49-160">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="7ab49-160">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="7ab49-161">在新的瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的音訊檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-161">In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="7ab49-162">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="7ab49-162">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-163">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="7ab49-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="7ab49-164">如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="7ab49-165">在 [**步驟 4**] 底下的 [**您的時區**] 中，按一下該工作流程的時區。</span><span class="sxs-lookup"><span data-stu-id="7ab49-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-166">[時區] 是工作流程的呼叫者和代理程式所在的時區。</span><span class="sxs-lookup"><span data-stu-id="7ab49-166">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="7ab49-167">它是用來計算開啟和關閉時間。</span><span class="sxs-lookup"><span data-stu-id="7ab49-167">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="7ab49-168">例如，如果工作流程設定為使用北美東部時區，且工作流程排程在 7:00 A.M. 開啟。</span><span class="sxs-lookup"><span data-stu-id="7ab49-168">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="7ab49-169">接著，請在 11:00 P.M.，將開啟和關閉時間分別視為7:00 東部時間和23:00 東部時間。</span><span class="sxs-lookup"><span data-stu-id="7ab49-169">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively.</span></span> <span data-ttu-id="7ab49-170">（您必須以24小時制時間格式輸入時間。）</span><span class="sxs-lookup"><span data-stu-id="7ab49-170">(You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="7ab49-171">請執行下列其中一項動作，選取您要使用的商務時間排程類型：</span><span class="sxs-lookup"><span data-stu-id="7ab49-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="7ab49-172">若要使用預先定義的上班時間排程，請按一下 [**使用預設排程**]，然後從下拉式清單中選取您要使用的排程。</span><span class="sxs-lookup"><span data-stu-id="7ab49-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-173">您之前必須已定義至少一個預設排程，才能選取此選項。</span><span class="sxs-lookup"><span data-stu-id="7ab49-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="7ab49-174">您可以使用<STRONG>CSRgsHoursOfBusiness</STRONG> Cmdlet 來定義預設排程。</span><span class="sxs-lookup"><span data-stu-id="7ab49-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="7ab49-175">如需詳細資訊，請參閱<A href="lync-server-2013-optional-define-response-group-business-hours.md">（選用）在 Lync Server 2013 中定義回應群組的上班時間</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-176">當您選取 [預置] 排程、[<STRONG>天</STRONG>]、[<STRONG>開啟</STRONG>] 和 [<STRONG>關閉</STRONG>] 時，系統會自動填入回應群組可用的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="7ab49-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="7ab49-177">若要使用只適用于此工作流程的自訂排程，請按一下 [**使用自訂排程**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="7ab49-178">如果您要建立此工作流程的自訂排程，請按一下回應群組可用之周的日期核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7ab49-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="7ab49-179">如果您要建立自訂排程，請輸入回應群組可用之周每一天的**開啟**和**關閉**時間。</span><span class="sxs-lookup"><span data-stu-id="7ab49-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-180">[<STRONG>開啟</STRONG>] 和 [<STRONG>關閉</STRONG>] 時間必須是24小時制時間格式。</span><span class="sxs-lookup"><span data-stu-id="7ab49-180">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation.</span></span> <span data-ttu-id="7ab49-181">例如，如果您的 office 的工作時間為9到5個工作日，而午餐時間為中午，則會將上班時間指定為<STRONG>開啟</STRONG>9:00、<STRONG>關閉</STRONG>12:00、<STRONG>開啟</STRONG>13:00，然後<STRONG>關閉</STRONG>17:00。</span><span class="sxs-lookup"><span data-stu-id="7ab49-181">For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="7ab49-182">如果您想要在 office 未開啟時播放郵件，請選取 [**當回應群組在上班時間以外時播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="7ab49-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="7ab49-183">若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="7ab49-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-184">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="7ab49-184">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="7ab49-185">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7ab49-185">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="7ab49-186">若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-186">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="7ab49-187">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="7ab49-187">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="7ab49-188">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-188">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="7ab49-189">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="7ab49-189">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-190">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="7ab49-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="7ab49-191">如需支援的音訊檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="7ab49-192">指定在播放郵件後如何處理呼叫（如果已設定郵件）：</span><span class="sxs-lookup"><span data-stu-id="7ab49-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="7ab49-193">若要中斷通話，請按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="7ab49-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="7ab49-194">若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="7ab49-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="7ab49-195">語音信箱位址的\<格式是 [使用者名\>@\<功能變數名稱\> ] （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="7ab49-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="7ab49-196">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。</span><span class="sxs-lookup"><span data-stu-id="7ab49-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="7ab49-197">使用者位址的\<格式是 [使用者名\>@\<功能變數名稱\>]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="7ab49-198">若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="7ab49-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="7ab49-199">電話\<號碼的格式是數位\>@\<domainName\> （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="7ab49-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="7ab49-200">功能變數名稱是用來將呼叫者路由至正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="7ab49-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="7ab49-201">在 [**步驟5指定您的假日**] 底下，按一下一或多組假期的核取方塊，以定義回應群組結束的日期。</span><span class="sxs-lookup"><span data-stu-id="7ab49-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-202">您必須先定義假日和假日集，然後才能設定工作流程。</span><span class="sxs-lookup"><span data-stu-id="7ab49-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="7ab49-203">使用<STRONG>新的-CsRgsHoliday</STRONG>和<STRONG>CsRgsHolidaySet</STRONG> Cmdlet 來定義假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="7ab49-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="7ab49-204">如需詳細資訊，請參閱<A href="lync-server-2013-optional-define-response-group-holiday-sets.md">（選用）在 Lync Server 2013 中定義回應群組假日集</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="7ab49-205">如果您想要在假日上播放郵件，請選取 [在**假日期間播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="7ab49-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="7ab49-206">若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="7ab49-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-207">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="7ab49-207">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="7ab49-208">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7ab49-208">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="7ab49-209">若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-209">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="7ab49-210">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="7ab49-210">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="7ab49-211">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-211">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="7ab49-212">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="7ab49-212">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-213">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="7ab49-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="7ab49-214">如需支援的音訊檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="7ab49-215">指定在播放郵件後如何處理呼叫（如果已設定郵件）：</span><span class="sxs-lookup"><span data-stu-id="7ab49-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="7ab49-216">若要中斷通話，請按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="7ab49-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="7ab49-217">若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="7ab49-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="7ab49-218">語音信箱位址的\<格式是 [使用者名\>@\<功能變數名稱\> ] （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="7ab49-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="7ab49-219">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。</span><span class="sxs-lookup"><span data-stu-id="7ab49-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="7ab49-220">使用者位址的\<格式是 [使用者名\>@\<功能變數名稱\>]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="7ab49-221">若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="7ab49-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="7ab49-222">電話\<號碼的格式是數位\>@\<domainName\> （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="7ab49-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="7ab49-223">功能變數名稱是用來將呼叫者路由至正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="7ab49-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="7ab49-224">在 [**步驟6設定佇列**] 底下的 **[選取將接收通話的佇列**] 中，選取您要保留呼叫者的佇列，直到有可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="7ab49-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="7ab49-225">在 [**步驟7設定暫停的音樂**] 底下，請執行下列其中一項動作，選擇您想要呼叫者在等候代理程式時聆聽的音樂：</span><span class="sxs-lookup"><span data-stu-id="7ab49-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="7ab49-226">若要使用預設的 [暫候] 錄製，請按一下 [**使用預設值**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="7ab49-227">若要在等候音樂時使用音訊檔案錄製，請按一下 [**選取音樂**檔案]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-227">To use an audio file recording for the music on hold, click **Select a music file**.</span></span> <span data-ttu-id="7ab49-228">如果您想要上傳新的音訊檔案，請按一下 [**音樂**檔案] 連結。</span><span class="sxs-lookup"><span data-stu-id="7ab49-228">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="7ab49-229">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-229">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="7ab49-230">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="7ab49-230">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7ab49-231">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="7ab49-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="7ab49-232">如需支援的音訊檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="7ab49-233">按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="7ab49-234">使用 Windows PowerShell 建立或修改查尋群組工作流程</span><span class="sxs-lookup"><span data-stu-id="7ab49-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="7ab49-235">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="7ab49-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="7ab49-236">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7ab49-237">建立要在歡迎訊息中播放的提示，然後將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="7ab49-237">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="7ab49-238">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="7ab49-238">At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="7ab49-239">例如：</span><span class="sxs-lookup"><span data-stu-id="7ab49-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-240">若要在提示時使用音訊檔案，請使用<STRONG>CsRgsAudioFile</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7ab49-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="7ab49-241">如需詳細資訊，請參閱匯<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">入-CsRgsAudioFile</A>。</span><span class="sxs-lookup"><span data-stu-id="7ab49-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="7ab49-242">取得要導向通話的佇列或問題的身分識別。</span><span class="sxs-lookup"><span data-stu-id="7ab49-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="7ab49-243">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="7ab49-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="7ab49-244">如需建立佇列的詳細資料，請參閱[新 CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)。</span><span class="sxs-lookup"><span data-stu-id="7ab49-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="7ab49-245">定義工作流程開啟時要採取的預設動作，然後將其儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="7ab49-245">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="7ab49-246">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="7ab49-246">At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-247">在查尋群組工作流程中，預設動作必須將呼叫定向至佇列。</span><span class="sxs-lookup"><span data-stu-id="7ab49-247">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="7ab49-248">此為活動工作流程所需的參數。</span><span class="sxs-lookup"><span data-stu-id="7ab49-248">This is parameter is required for active workflows.</span></span> <span data-ttu-id="7ab49-249">非作用中工作流程不需要。</span><span class="sxs-lookup"><span data-stu-id="7ab49-249">It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="7ab49-250">例如：</span><span class="sxs-lookup"><span data-stu-id="7ab49-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="7ab49-251">如果您想要定義上班時間和假日，您必須先建立，才能建立或修改工作流程。</span><span class="sxs-lookup"><span data-stu-id="7ab49-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="7ab49-252">如需詳細資訊，請參閱[（選用）在 Lync server 2013 中定義回應群組的上班時間](lync-server-2013-optional-define-response-group-business-hours.md)， [（選擇性）在 lync Server 2013 中定義回應群組的假日集合](lync-server-2013-optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="7ab49-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="7ab49-253">如果您想要針對在上班時間以外或假期收到的通話發出提示，請使用**CsRgsPrompt** Cmdlet 來定義提示，然後使用**新的-CsRgsCallAction**來定義提示之後要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7ab49-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="7ab49-254">如需詳細資訊，請參閱[新 CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)和[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)。</span><span class="sxs-lookup"><span data-stu-id="7ab49-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="7ab49-255">檢索 Lync Server 回應群組服務的服務名稱，並將它指派給一個變數。</span><span class="sxs-lookup"><span data-stu-id="7ab49-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="7ab49-256">在命令上執行：</span><span class="sxs-lookup"><span data-stu-id="7ab49-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="7ab49-257">建立或修改工作流程。</span><span class="sxs-lookup"><span data-stu-id="7ab49-257">Create or modify the workflow.</span></span> <span data-ttu-id="7ab49-258">若要建立工作流程，請使用 [**新-CsRgsWorkflow**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="7ab49-259">若要修改工作流程，請使用 [**設定-CsRgsWorkflow**]。</span><span class="sxs-lookup"><span data-stu-id="7ab49-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="7ab49-260">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="7ab49-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="7ab49-261">例如：</span><span class="sxs-lookup"><span data-stu-id="7ab49-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7ab49-262">指派工作流程管理員的所有使用者，都必須獲指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="7ab49-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab49-263">如需其他選擇性參數的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">新 CsRgsWorkflow</A>或<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">設定 CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="7ab49-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ab49-264">請參閱</span><span class="sxs-lookup"><span data-stu-id="7ab49-264">See Also</span></span>


[<span data-ttu-id="7ab49-265">可選在 Lync Server 2013 中定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="7ab49-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="7ab49-266">可選在 Lync Server 2013 中定義回應群組的上班時間</span><span class="sxs-lookup"><span data-stu-id="7ab49-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="7ab49-267">新-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="7ab49-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="7ab49-268">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="7ab49-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="7ab49-269">新-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="7ab49-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="7ab49-270">新-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="7ab49-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

