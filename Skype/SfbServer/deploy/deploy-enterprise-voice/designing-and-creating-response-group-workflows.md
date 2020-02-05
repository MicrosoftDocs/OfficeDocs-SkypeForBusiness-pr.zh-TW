---
title: 在商務用 Skype 中設計及建立回應群組工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 在商務用 Skype Server Enterprise Voice 中設計及建立回應群組工作流程。 已覆蓋查尋群組工作流程和互動式工作流程。
ms.openlocfilehash: a8e53ea6e36a175a33648e4e1783bf2040556c8f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767356"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a><span data-ttu-id="09d5e-104">在商務用 Skype 中設計及建立回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="09d5e-104">Designing and creating response group workflows in Skype for Business</span></span>

<span data-ttu-id="09d5e-105">在商務用 Skype Server Enterprise Voice 中設計及建立回應群組工作流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-105">Design and create Response Group workflows, in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="09d5e-106">已覆蓋查尋群組工作流程和互動式工作流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-106">Both hunt group workflows and interactive workflows are covered.</span></span>

<span data-ttu-id="09d5e-107">工作流程會定義撥打電話到某人接聽來電之時間的通話行為。</span><span class="sxs-lookup"><span data-stu-id="09d5e-107">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="09d5e-108">工作流程會指定要用來進行通話的佇列，並指定用於查尋群組工作流程的傳送方法，或是用於互動式回應群組工作流程的問題與解答。</span><span class="sxs-lookup"><span data-stu-id="09d5e-108">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt group workflows or the questions and answers to use for interactive response group workflows.</span></span>

<span data-ttu-id="09d5e-109">工作流程也會定義設定，例如 [歡迎] 訊息、[等候音樂]、[上班時間] 和 [假日]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-109">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

> [!NOTE]
> <span data-ttu-id="09d5e-110">您必須先建立代理群組和佇列，才能建立使用它們的工作流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-110">You must create agent groups and queues before you create a workflow that uses them.</span></span>

## <a name="creating-or-modifying-a-hunt-group-workflow"></a><span data-ttu-id="09d5e-111">建立或修改查尋群組工作流程</span><span class="sxs-lookup"><span data-stu-id="09d5e-111">Creating or modifying a hunt group workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="09d5e-112">使用 [回應群組設定] 工具來建立或修改查尋群組工作流程</span><span class="sxs-lookup"><span data-stu-id="09d5e-112">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="09d5e-113">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="09d5e-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="09d5e-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="09d5e-115">在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-115">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="09d5e-116">在 [**工作流程**] 頁面上，按一下 [**建立或編輯工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-116">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="09d5e-117">在 [**選取服務**搜尋] 欄位中，輸入您要建立或變更之工作流程之**ApplicationServer**服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="09d5e-117">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="09d5e-118">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="09d5e-118">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-119">[回應群組設定] 工具隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="09d5e-119">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="09d5e-120">您也可以輸入下列 URL，在網頁瀏覽器中直接開啟 [回應群組設定] 工具：\<Https://\>webPoolFqdn/RgsConfig。</span><span class="sxs-lookup"><span data-stu-id="09d5e-120">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="09d5e-121">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="09d5e-121">Do one of the following:</span></span>

   - <span data-ttu-id="09d5e-122">在 [**建立新工作流程**] 底下，按一下 [**查尋群組**] 旁的 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-122">Under **Create a New Workflow**, next to **Hunt Group**, click **Create**.</span></span>

   - <span data-ttu-id="09d5e-123">在 [**管理現有的工作流程**] 底下，找出您要變更的工作流程，然後在 [**動作**] 底下，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-123">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="09d5e-124">如果您已準備好讓使用者開始呼叫工作流程，請選取 [**啟用工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-124">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="09d5e-125">如果您要建立受管理的工作流程，您必須選取 [**啟用工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-125">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="09d5e-126">儲存作用中受管理的工作流程之後，您就可以進行修改及停用。</span><span class="sxs-lookup"><span data-stu-id="09d5e-126">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="09d5e-127">若要允許聯盟使用者呼叫群組，請選取 [**啟用聯盟**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-127">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="09d5e-128">您也必須有可套用至針對同盟設定之回應群組應用程式的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="09d5e-128">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-129">全域外部存取原則會套用至回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-129">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="09d5e-130">您可以使用商務用 Skype Server 的 [控制台]，或使用**CsExternalAccessPolicy** Cmdlet 將 EnableOutsideAccess 參數設定為 True，來設定回應群組同盟的全域原則。</span><span class="sxs-lookup"><span data-stu-id="09d5e-130">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="09d5e-131">請記住，除非指派網站或使用者原則，否則全域原則設定將會套用至所有使用者。</span><span class="sxs-lookup"><span data-stu-id="09d5e-131">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="09d5e-132">因此，在變更回應群組的此設定之前，請確定同盟設定符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-132">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="09d5e-133">如需有關如何將原則套用至使用者的詳細資訊，請參閱[管理貴組織的外部存取原則](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-133">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="09d5e-134">如需同盟設定的詳細資訊，請參閱[設定 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-134">For details about the federation setting, see [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-135">在商務用 Skype Online 中託管的使用者無法將呼叫權放在內部部署中託管的回應群組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-135">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="09d5e-136">這在混合式部署中，以及內部部署與商務用 Skype Online 部署聯盟的情況下，都是如此。</span><span class="sxs-lookup"><span data-stu-id="09d5e-136">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="09d5e-137">若要在呼叫期間隱藏代理程式的身分識別，請選取 [**啟用代理程式匿名**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-137">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-138">匿名通話不能以立即訊息（IM）或影片啟動，不過代理或來電者可以在通話建立之後，新增 IM 和影片。</span><span class="sxs-lookup"><span data-stu-id="09d5e-138">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="09d5e-139">匿名代理程式也可以保留通話、轉接呼叫（盲人與顧問式轉移），以及寄存與取回通話。</span><span class="sxs-lookup"><span data-stu-id="09d5e-139">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="09d5e-140">匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、whiteboarding 與資料共同作業，以及通話錄製。</span><span class="sxs-lookup"><span data-stu-id="09d5e-140">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="09d5e-141">使用 Lync VDI 外掛程式的代理程式可以匿名接收來電，但不能匿名撥出來電。</span><span class="sxs-lookup"><span data-stu-id="09d5e-141">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="09d5e-142">在 [**輸入將會接收來電的群組的位址**] 底下，輸入群組的主要 SIP 統一資源識別項（URI）位址，將會應答工作流程的呼叫。</span><span class="sxs-lookup"><span data-stu-id="09d5e-142">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-143">工作流程的主要 URI 是識別及參照工作流程的方式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-143">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="09d5e-144">您輸入的 SIP URI 是在 Active Directory 網域服務中建立為連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="09d5e-144">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="09d5e-145">若要建立 URI，物件在 Active Directory 中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="09d5e-145">To create the URI, the object must be unique in Active Directory.</span></span>

11. <span data-ttu-id="09d5e-146">在 [**顯示名稱**] 中，輸入您要顯示的工作流程名稱（例如 [銷售回應] 群組）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-146">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-147">請勿在顯示名稱中包含「<」或「>」字元。</span><span class="sxs-lookup"><span data-stu-id="09d5e-147">Do not include the "<" or ">" characters in the display name.</span></span> <span data-ttu-id="09d5e-148">請勿使用下列顯示名稱，因為它們是保留的： **RGS 目前狀態觀察**程式或**宣告服務**。</span><span class="sxs-lookup"><span data-stu-id="09d5e-148">Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="09d5e-149">在 [**電話號碼**] 下，輸入回應群組的行 URI （例如 + 14255550165）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-149">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="09d5e-150">在 [**顯示號碼**] 中，輸入您想要顯示給回應群組的數位（例如 + 1 （425）555-0165）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-150">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="09d5e-151">可選在 [**描述**] 中，輸入您想要在商務用 Skype 的連絡人卡片上顯示之工作流程的描述。</span><span class="sxs-lookup"><span data-stu-id="09d5e-151">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="09d5e-152">在 [**工作流程類型**] 中，如果此工作流程將由回應群組管理員管理，請選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-152">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="09d5e-153">請執行下列動作，將回應群組管理員指派給工作流程：</span><span class="sxs-lookup"><span data-stu-id="09d5e-153">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="09d5e-154">是.</span><span class="sxs-lookup"><span data-stu-id="09d5e-154">a.</span></span> <span data-ttu-id="09d5e-155">輸入此工作流程的管理員 SIP URI，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-155">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="09d5e-156">乙.</span><span class="sxs-lookup"><span data-stu-id="09d5e-156">b.</span></span> <span data-ttu-id="09d5e-157">輸入要新增至工作流程的其他管理員 SIP URI，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-157">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="09d5e-158">指派為回應群組管理員的每位使用者，都必須獲指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="09d5e-158">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="09d5e-159">如果沒有為使用者指派這個角色，就不能管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-159">If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="09d5e-160">在 [**步驟2選取語言**] 底下，按一下您要用於語音辨識和文字轉換語音的語言。</span><span class="sxs-lookup"><span data-stu-id="09d5e-160">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="09d5e-161">如果您想要設定歡迎訊息，請在 [**步驟3設定歡迎訊息**] 底下，選取 [**播放歡迎訊息**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="09d5e-161">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="09d5e-162">若要將歡迎郵件輸入為已轉換為呼叫者語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-162">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-163">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="09d5e-163">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="09d5e-164">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-164">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="09d5e-165">若要使用波形（.wav）或 Windows Media 音訊（.wma）檔案錄製 [歡迎] 訊息，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-165">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**.</span></span> <span data-ttu-id="09d5e-166">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="09d5e-166">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="09d5e-167">在新的瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的音訊檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-167">In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="09d5e-168">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-168">Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-169">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-169">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-170">如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-170">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="09d5e-171">在 [**步驟 4**] 底下的 [**您的時區**] 中，按一下該工作流程的時區。</span><span class="sxs-lookup"><span data-stu-id="09d5e-171">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-172">[時區] 是工作流程的呼叫者和代理程式所在的時區。</span><span class="sxs-lookup"><span data-stu-id="09d5e-172">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="09d5e-173">它是用來計算開啟和關閉時間。</span><span class="sxs-lookup"><span data-stu-id="09d5e-173">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="09d5e-174">例如，如果工作流程設定為使用北美東部時區，且工作流程排程在 7:00 A.M. 開啟。</span><span class="sxs-lookup"><span data-stu-id="09d5e-174">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="09d5e-175">接著，請在 11:00 P.M.，將開啟和關閉時間分別視為7:00 東部時間和23:00 東部時間。</span><span class="sxs-lookup"><span data-stu-id="09d5e-175">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively.</span></span> <span data-ttu-id="09d5e-176">（您必須以24小時制時間格式輸入時間。）</span><span class="sxs-lookup"><span data-stu-id="09d5e-176">(You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="09d5e-177">請執行下列其中一項動作，選取您要使用的商務時間排程類型：</span><span class="sxs-lookup"><span data-stu-id="09d5e-177">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="09d5e-178">若要使用預先定義的上班時間排程，請按一下 [**使用預設排程**]，然後從下拉式清單中選取您要使用的排程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-178">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-179">您之前必須已定義至少一個預設排程，才能選取此選項。</span><span class="sxs-lookup"><span data-stu-id="09d5e-179">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="09d5e-180">您可以使用**CSRgsHoursOfBusiness** Cmdlet 來定義預設排程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-180">You define preset schedules by using the **New-CSRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="09d5e-181">如需詳細資訊，請參閱[（選用）在商務用 Skype 中定義回應群組的上班時間](optional-define-response-group-business-hours.md)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-181">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-182">當您選取 [預置] 排程、[**天**]、[**開啟**] 和 [**關閉**] 時，系統會自動填入回應群組可用的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="09d5e-182">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="09d5e-183">若要使用只適用于此工作流程的自訂排程，請按一下 [**使用自訂排程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-183">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="09d5e-184">如果您要建立此工作流程的自訂排程，請按一下回應群組可用之周的日期核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-184">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="09d5e-185">如果您要建立自訂排程，請輸入回應群組可用之周的每一天的 [**開啟**] 和 [**結束**] 時間。</span><span class="sxs-lookup"><span data-stu-id="09d5e-185">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group is available.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-186">[**開啟**] 和 [**關閉**] 時間必須是24小時制時間格式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-186">The **Open** and **Close** hours must be in 24-hour time notation.</span></span> <span data-ttu-id="09d5e-187">例如，如果您的 office 的工作時間為9到5個工作日，而午餐時間為中午，則會將上班時間指定為**開啟**9:00、**關閉**12:00、**開啟**13:00，然後**關閉**17:00。</span><span class="sxs-lookup"><span data-stu-id="09d5e-187">For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="09d5e-188">如果您想要在 office 未開啟時播放郵件，請選取 [**當回應群組在上班時間以外時播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="09d5e-188">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="09d5e-189">若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-189">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-190">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="09d5e-190">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="09d5e-191">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-191">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="09d5e-192">若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-192">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="09d5e-193">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="09d5e-193">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="09d5e-194">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-194">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="09d5e-195">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-195">Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-196">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-196">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-197">如需支援的音訊檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-197">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="09d5e-198">指定在播放郵件後如何處理呼叫（如果已設定郵件）：</span><span class="sxs-lookup"><span data-stu-id="09d5e-198">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="09d5e-199">若要中斷通話，請按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="09d5e-199">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="09d5e-200">若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="09d5e-200">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="09d5e-201">語音信箱位址的格式是@ \* \<[使用者名\>\*\*\<功能變數名稱\> \* ] （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-201">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="09d5e-202">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。</span><span class="sxs-lookup"><span data-stu-id="09d5e-202">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="09d5e-203">使用者位址的格式是@ _ \<[使用者名\>__\<功能變數名稱\>_]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-203">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="09d5e-204">若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="09d5e-204">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="09d5e-205">電話號碼的格式是\* \<數位\>*@*\<domainName\> \* （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-205">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="09d5e-206">功能變數名稱是用來將呼叫者路由至正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="09d5e-206">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="09d5e-207">在 [**步驟5指定您的假日**] 底下，按一下一或多組假期的核取方塊，以定義回應群組結束的日期。</span><span class="sxs-lookup"><span data-stu-id="09d5e-207">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-208">您必須先定義假日和假日集，然後才能設定工作流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-208">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="09d5e-209">使用**新的-CsRgsHoliday**和**CsRgsHolidaySet** Cmdlet 來定義假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="09d5e-209">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="09d5e-210">如需詳細資訊，請參閱[（選用）在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-210">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="09d5e-211">如果您想要在假日上播放郵件，請選取 [在**假日期間播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="09d5e-211">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="09d5e-212">若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-212">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-213">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="09d5e-213">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="09d5e-214">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-214">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="09d5e-215">若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-215">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="09d5e-216">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="09d5e-216">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="09d5e-217">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-217">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="09d5e-218">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-218">Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-219">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-219">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-220">如需支援的音訊檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-220">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="09d5e-221">指定在播放郵件後如何處理呼叫（如果已設定郵件）：</span><span class="sxs-lookup"><span data-stu-id="09d5e-221">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="09d5e-222">若要中斷通話，請按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="09d5e-222">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="09d5e-223">若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="09d5e-223">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="09d5e-224">語音信箱位址的格式是@ \* \<[使用者名\>\*\*\<功能變數名稱\> \* ] （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-224">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="09d5e-225">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。</span><span class="sxs-lookup"><span data-stu-id="09d5e-225">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="09d5e-226">使用者位址的格式是@ _ \<[使用者名\>__\<功能變數名稱\>_]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-226">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="09d5e-227">若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="09d5e-227">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="09d5e-228">電話號碼的格式是\* \<數位\>*@*\<domainName\> \* （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-228">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="09d5e-229">功能變數名稱是用來將呼叫者路由至正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="09d5e-229">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="09d5e-230">在 [**步驟6設定佇列**] 底下的 **[選取將接收通話的佇列**] 中，選取您要保留呼叫者的佇列，直到有可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-230">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="09d5e-231">在 [**步驟7設定暫停的音樂**] 底下，請執行下列其中一項動作，選擇您想要呼叫者在等候代理程式時聆聽的音樂：</span><span class="sxs-lookup"><span data-stu-id="09d5e-231">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="09d5e-232">若要使用預設的 [暫候] 錄製，請按一下 [**使用預設值**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-232">To use the default music-on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="09d5e-233">若要在等候音樂時使用音訊檔案錄製，請按一下 [**選取音樂**檔案]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-233">To use an audio file recording for the music on hold, click **Select a music file**.</span></span> <span data-ttu-id="09d5e-234">如果您想要上傳新的音訊檔案，請按一下 [**音樂**檔案] 連結。</span><span class="sxs-lookup"><span data-stu-id="09d5e-234">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="09d5e-235">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-235">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="09d5e-236">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-236">Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-237">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-237">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-238">如需支援的音訊檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-238">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="09d5e-239">按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-239">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="09d5e-240">若要使用商務用 Skype Server Management Shell 來建立或修改查尋群組工作流程</span><span class="sxs-lookup"><span data-stu-id="09d5e-240">To use Skype for Business Server Management Shell to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="09d5e-241">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="09d5e-241">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="09d5e-242">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-242">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="09d5e-243">建立要在歡迎訊息中播放的提示，然後將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="09d5e-243">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="09d5e-244">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="09d5e-244">At the command line, run:</span></span>

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    <span data-ttu-id="09d5e-245">例如：</span><span class="sxs-lookup"><span data-stu-id="09d5e-245">For example:</span></span>

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > <span data-ttu-id="09d5e-246">若要在提示時使用音訊檔案，請使用**CsRgsAudioFile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="09d5e-246">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="09d5e-247">如需詳細資訊，請參閱匯[入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-247">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span>

4. <span data-ttu-id="09d5e-248">取得要導向通話的佇列或問題的身分識別。</span><span class="sxs-lookup"><span data-stu-id="09d5e-248">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="09d5e-249">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="09d5e-249">At the command line, run:</span></span>

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    <span data-ttu-id="09d5e-250">如需建立佇列的詳細資料，請參閱[新 CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-250">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).</span></span>

5. <span data-ttu-id="09d5e-251">定義工作流程開啟時要採取的預設動作，然後將其儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="09d5e-251">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="09d5e-252">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="09d5e-252">At the command line, run:</span></span>

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > <span data-ttu-id="09d5e-253">在查尋群組工作流程中，預設動作必須將呼叫定向至佇列。</span><span class="sxs-lookup"><span data-stu-id="09d5e-253">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="09d5e-254">此參數對於使用中的工作流程是必要的。</span><span class="sxs-lookup"><span data-stu-id="09d5e-254">This parameter is required for active workflows.</span></span> <span data-ttu-id="09d5e-255">非作用中工作流程不需要。</span><span class="sxs-lookup"><span data-stu-id="09d5e-255">It is not required for inactive workflows.</span></span>

    <span data-ttu-id="09d5e-256">例如：</span><span class="sxs-lookup"><span data-stu-id="09d5e-256">For example:</span></span>

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. <span data-ttu-id="09d5e-257">如果您想要定義上班時間和假日，您必須先建立，才能建立或修改工作流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-257">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="09d5e-258">如需詳細資訊，請參閱[（選用）在商務用 skype 中定義回應群組的商務時間](optional-define-response-group-business-hours.md) [（選用）在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-258">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

7. <span data-ttu-id="09d5e-259">如果您想要針對在上班時間以外或假期收到的通話發出提示，請使用**CsRgsPrompt** Cmdlet 來定義提示，然後使用**新的-CsRgsCallAction**來定義提示之後要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="09d5e-259">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="09d5e-260">如需詳細資訊，請參閱[新 CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)和[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-260">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span>

8. <span data-ttu-id="09d5e-261">檢索 Lync Server 回應群組服務的服務名稱，並將它指派給一個變數。</span><span class="sxs-lookup"><span data-stu-id="09d5e-261">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="09d5e-262">在命令上執行：</span><span class="sxs-lookup"><span data-stu-id="09d5e-262">At the command, run:</span></span>

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. <span data-ttu-id="09d5e-263">建立或修改工作流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-263">Create or modify the workflow.</span></span> <span data-ttu-id="09d5e-264">若要建立工作流程，請使用 [**新-CsRgsWorkflow**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-264">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="09d5e-265">若要修改工作流程，請使用 [**設定-CsRgsWorkflow**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-265">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="09d5e-266">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="09d5e-266">At the command line, type:</span></span>

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    <span data-ttu-id="09d5e-267">例如：</span><span class="sxs-lookup"><span data-stu-id="09d5e-267">For example:</span></span>

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > <span data-ttu-id="09d5e-268">指派工作流程管理員的所有使用者，都必須獲指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="09d5e-268">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09d5e-269">如需其他選擇性參數的詳細資訊，請參閱[新 CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)或[設定 CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="09d5e-269">For details about additional optional parameters, see [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) or [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span></span>

## <a name="designing-an-interactive-workflow"></a><span data-ttu-id="09d5e-270">設計互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="09d5e-270">Designing an interactive workflow</span></span>

<span data-ttu-id="09d5e-271">您可以使用互動式語音回應（IVR），從來電者取得資訊，並將呼叫定向至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="09d5e-271">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="09d5e-272">問題與答案配對決定要使用哪個佇列。</span><span class="sxs-lookup"><span data-stu-id="09d5e-272">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="09d5e-273">視來電者的回應而定，來電者可能會聽到後續問題，或是路由至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="09d5e-273">Depending on the caller's response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="09d5e-274">IVR 問題與來電者的回應會提供給接受通話的回應代理程式，提供有價值的資訊給代理程式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-274">The IVR questions and the caller's responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

### <a name="overview-of-ivr-features"></a><span data-ttu-id="09d5e-275">IVR 功能概覽</span><span class="sxs-lookup"><span data-stu-id="09d5e-275">Overview of IVR Features</span></span>

<span data-ttu-id="09d5e-276">回應群組應用程式提供的語音辨識和文字轉換語音功能都有26種語言。</span><span class="sxs-lookup"><span data-stu-id="09d5e-276">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="09d5e-277">您可以使用文字轉換語音或波形（.wav）或 Windows Media 音訊（.wma）檔案輸入 IVR 問題。</span><span class="sxs-lookup"><span data-stu-id="09d5e-277">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="09d5e-278">呼叫者可以使用語音或雙音調 multifrequency （DTMF）回應來回應。</span><span class="sxs-lookup"><span data-stu-id="09d5e-278">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="09d5e-279">互動式工作流程最多可支援兩個層級的問題，每個問題都有四個可能的答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-279">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="09d5e-280">IVR 會向呼叫者提出問題，視來電者的回應而定，將呼叫者路由至佇列或提出第二個問題。</span><span class="sxs-lookup"><span data-stu-id="09d5e-280">The IVR asks the caller a question, and depending on the caller's response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="09d5e-281">第二個問題也可能有四個可能的答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-281">The second question can also have four possible answers.</span></span> <span data-ttu-id="09d5e-282">根據第二層問題的答案而定，來電者會路由至適當的佇列。</span><span class="sxs-lookup"><span data-stu-id="09d5e-282">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

> [!NOTE]
> <span data-ttu-id="09d5e-283">當您使用商務用 Skype Server Management Shell 設計通話流程時，您可以定義任何數目的 IVR 問題以及任何數目的答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-283">When you design call flows by using Skype for Business Server Management Shell, you can define any number of levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="09d5e-284">不過，對於呼叫者的可用性，我們建議您不要使用超過三層的問題，每一個都不超過五個答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-284">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="09d5e-285">此外，如果您設計的通話流程中有兩個以上的問題，每個層次都有四個以上的答案，您就無法使用商務用 Skype Server [控制台] 來編輯通話流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-285">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="09d5e-286">IVR 問題及來電者的回應會提供給接受通話的回應代理程式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-286">The IVR questions and the caller's responses are provided to the responding agent who accepts the call.</span></span>

### <a name="working-with-speech-technologies"></a><span data-ttu-id="09d5e-287">使用語音技術</span><span class="sxs-lookup"><span data-stu-id="09d5e-287">Working with Speech Technologies</span></span>

<span data-ttu-id="09d5e-288">語音技術（例如語音辨識和文字轉換語音）可加強客戶體驗，讓使用者更容易地存取訊號。</span><span class="sxs-lookup"><span data-stu-id="09d5e-288">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="09d5e-289">不過，您可能會有語音引擎無法正確辨識指定文字或使用者語音回應的情況。</span><span class="sxs-lookup"><span data-stu-id="09d5e-289">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="09d5e-290">例如，「#」符號是由文字到語音引擎轉譯為「數位」字樣。</span><span class="sxs-lookup"><span data-stu-id="09d5e-290">For example, the "#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="09d5e-291">您可以透過下列方式緩解此問題：</span><span class="sxs-lookup"><span data-stu-id="09d5e-291">This issue can be mitigated by the following:</span></span>

- <span data-ttu-id="09d5e-292">語音引擎提供給呼叫者五次，回答問題。</span><span class="sxs-lookup"><span data-stu-id="09d5e-292">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="09d5e-293">如果來電者回答的問題不正確（也就是說，答案不是指定的回應），或是根本無法提供答案，則呼叫者會收到另一個回答問題的機會。</span><span class="sxs-lookup"><span data-stu-id="09d5e-293">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="09d5e-294">呼叫者有五個嘗試在中斷連線之前回答問題。</span><span class="sxs-lookup"><span data-stu-id="09d5e-294">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="09d5e-295">您可以將 IVR 設定為在每個本機號碼之後，播放自訂的訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-295">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="09d5e-296">每次都會重複出現這個問題。</span><span class="sxs-lookup"><span data-stu-id="09d5e-296">The question is repeated each time.</span></span>

- <span data-ttu-id="09d5e-297">若要將由語音引擎轉譯為回應的環境干擾可能性降至最低，請使用較長的回應。</span><span class="sxs-lookup"><span data-stu-id="09d5e-297">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="09d5e-298">例如，回應應該有一個以上的音節，而且應該會有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="09d5e-298">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

- <span data-ttu-id="09d5e-299">如果您的問題同時具有語音和 DTMF 回應，請使用代表概念的文字（而不是 DTMF 回應）來設定語音回應。</span><span class="sxs-lookup"><span data-stu-id="09d5e-299">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="09d5e-300">例如，請不要使用「按下或說一次」，而是按1或說帳單。」</span><span class="sxs-lookup"><span data-stu-id="09d5e-300">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

- <span data-ttu-id="09d5e-301">在您設計 IVR 之後，請呼叫工作流程、聆聽提示、使用語音回應每個提示，並確認 IVR 的音效和行為如期運作。</span><span class="sxs-lookup"><span data-stu-id="09d5e-301">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="09d5e-302">然後，您可以修改 IVR 以修正任何轉譯問題。</span><span class="sxs-lookup"><span data-stu-id="09d5e-302">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="09d5e-303">在前面的範例中，如果您需要參照 # 鍵，可以重新寫入 IVR 提示，以使用索引鍵名稱，而不是 # 符號。</span><span class="sxs-lookup"><span data-stu-id="09d5e-303">Following the previous example, if you need to refer to the # key, you can rewrite your IVR prompt to use the key name, rather than the # symbol.</span></span> <span data-ttu-id="09d5e-304">例如，若要與銷售額交談，請按井號鍵。</span><span class="sxs-lookup"><span data-stu-id="09d5e-304">For example, "To talk to sales, press the pound key."</span></span>

### <a name="ivr-design-examples"></a><span data-ttu-id="09d5e-305">IVR 設計範例</span><span class="sxs-lookup"><span data-stu-id="09d5e-305">IVR Design Examples</span></span>

<span data-ttu-id="09d5e-306">下列各節包含不同 IVR 案例與問題與答案組的範例。</span><span class="sxs-lookup"><span data-stu-id="09d5e-306">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

#### <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="09d5e-307">包含一層問題的 IVR</span><span class="sxs-lookup"><span data-stu-id="09d5e-307">IVR with One Level of Questions</span></span>

<span data-ttu-id="09d5e-308">下列範例顯示使用一層問題的 IVR。</span><span class="sxs-lookup"><span data-stu-id="09d5e-308">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="09d5e-309">它會使用語音辨識來偵測來電者的回應。</span><span class="sxs-lookup"><span data-stu-id="09d5e-309">It uses speech recognition to detect the caller's response.</span></span>

 <span data-ttu-id="09d5e-310">**問題：**「感謝您打電話給人力資源。</span><span class="sxs-lookup"><span data-stu-id="09d5e-310">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="09d5e-311">如果您想要與工資單通話，請說出工資。</span><span class="sxs-lookup"><span data-stu-id="09d5e-311">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="09d5e-312">否則請說人力資源。」</span><span class="sxs-lookup"><span data-stu-id="09d5e-312">Otherwise, say HR."</span></span>

- <span data-ttu-id="09d5e-313">**已選取選項1：** 來電者會傳送給工資小組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-313">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

- <span data-ttu-id="09d5e-314">**已選取選項2：** 來電者會傳送給人力資源小組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-314">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="09d5e-315">下圖顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-315">The following figure shows the call flow.</span></span>

 <span data-ttu-id="09d5e-316">**一對一互動式呼叫流程**</span><span class="sxs-lookup"><span data-stu-id="09d5e-316">**One-level interactive call flow**</span></span>

![使用互動語音回應設計通話流程](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="09d5e-318">IVR 有兩個等級的問題</span><span class="sxs-lookup"><span data-stu-id="09d5e-318">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="09d5e-319">下列範例顯示的是使用兩層問題的 IVR。</span><span class="sxs-lookup"><span data-stu-id="09d5e-319">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="09d5e-320">它可讓呼叫者使用語音或 DTMF 小鍵盤輸入來回應。</span><span class="sxs-lookup"><span data-stu-id="09d5e-320">It allows callers to respond using either speech or DTMF keypad input.</span></span>

 <span data-ttu-id="09d5e-321">**問題：**「感謝您致電 IT 技術支援人員。</span><span class="sxs-lookup"><span data-stu-id="09d5e-321">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="09d5e-322">如果有網路存取問題，請按1或說 [網路]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-322">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="09d5e-323">如果您有軟體問題，請按2或說軟體。</span><span class="sxs-lookup"><span data-stu-id="09d5e-323">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="09d5e-324">如果有硬體問題，請按3或說硬體。」</span><span class="sxs-lookup"><span data-stu-id="09d5e-324">If you have a hardware problem, press 3 or say hardware."</span></span>

- <span data-ttu-id="09d5e-325">**已選取選項1：** 來電者會路由至網路支援小組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-325">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

- <span data-ttu-id="09d5e-326">**已選取選項2：** 來電者會問到待處理問題：</span><span class="sxs-lookup"><span data-stu-id="09d5e-326">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="09d5e-327">**問題：**「如果這是作業系統問題，請按1或說作業系統。</span><span class="sxs-lookup"><span data-stu-id="09d5e-327">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="09d5e-328">如果這是內部應用程式的問題，請按2或說出內部應用程式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-328">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="09d5e-329">否則，請按3或說 [其他]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-329">Otherwise, press 3 or say other."</span></span>

  - <span data-ttu-id="09d5e-330">**已選取選項1：** 來電者會路由至作業系統支援小組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-330">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>

  - <span data-ttu-id="09d5e-331">**已選取選項2：** 來電者會路由到內部應用程式支援小組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-331">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>

  - <span data-ttu-id="09d5e-332">**已選取選項3：** 來電者會傳送給軟體支援小組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-332">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

- <span data-ttu-id="09d5e-333">**已選取選項3：** 來電者會問到待處理問題：</span><span class="sxs-lookup"><span data-stu-id="09d5e-333">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="09d5e-334">**問題：**「如果這是印表機問題，請按1。</span><span class="sxs-lookup"><span data-stu-id="09d5e-334">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="09d5e-335">否則，請按2。</span><span class="sxs-lookup"><span data-stu-id="09d5e-335">Otherwise, press 2."</span></span>

  - <span data-ttu-id="09d5e-336">**已選取選項1：** 來電者會傳送給印表機支援小組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-336">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>

  - <span data-ttu-id="09d5e-337">**已選取選項2：** 來電者會路由到硬體支援小組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-337">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="09d5e-338">下圖顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-338">The following figure shows the call flow.</span></span>

 <span data-ttu-id="09d5e-339">**兩層互動式通話流程**</span><span class="sxs-lookup"><span data-stu-id="09d5e-339">**Two-level interactive call flow**</span></span>

![使用互動語音回應設計通話流程](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a><span data-ttu-id="09d5e-341">最佳做法</span><span class="sxs-lookup"><span data-stu-id="09d5e-341">Best Practices</span></span>

<span data-ttu-id="09d5e-342">下列清單說明設計 IVR 的一些最佳做法：</span><span class="sxs-lookup"><span data-stu-id="09d5e-342">The following list describes some best practices for designing your IVR:</span></span>

- <span data-ttu-id="09d5e-343">讓呼叫者快速取得工作。</span><span class="sxs-lookup"><span data-stu-id="09d5e-343">Let the caller get to the task quickly.</span></span> <span data-ttu-id="09d5e-344">避免在您的 IVR 中提供太多的資訊或冗長的行銷訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-344">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

- <span data-ttu-id="09d5e-345">如果您想要包含較長的訊息，請考慮將它附加到第一個問題，而不是加入 [歡迎使用] 訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-345">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="09d5e-346">如果您回答的問題是第一個問題的一部分，來電者可以略過這封郵件，但他們無法略過歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-346">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

- <span data-ttu-id="09d5e-347">在來電者語言中說話。</span><span class="sxs-lookup"><span data-stu-id="09d5e-347">Speak in the caller's language.</span></span> <span data-ttu-id="09d5e-348">避免 stilted 語言。</span><span class="sxs-lookup"><span data-stu-id="09d5e-348">Avoid stilted language.</span></span> <span data-ttu-id="09d5e-349">自然說話。</span><span class="sxs-lookup"><span data-stu-id="09d5e-349">Speak naturally.</span></span>

- <span data-ttu-id="09d5e-350">撰寫高效且有效的提示。</span><span class="sxs-lookup"><span data-stu-id="09d5e-350">Write efficient and effective prompts.</span></span> <span data-ttu-id="09d5e-351">移除任何不必要的選項。</span><span class="sxs-lookup"><span data-stu-id="09d5e-351">Remove any unnecessary options.</span></span> <span data-ttu-id="09d5e-352">構造資訊，讓來電者預期的回應在句子的結尾。</span><span class="sxs-lookup"><span data-stu-id="09d5e-352">Structure the information so that the caller's expected response is at the end of the sentence.</span></span> <span data-ttu-id="09d5e-353">例如，「若要與銷售團隊通話，請按1。」</span><span class="sxs-lookup"><span data-stu-id="09d5e-353">For example, "To speak to the sales team, press 1."</span></span>

- <span data-ttu-id="09d5e-354">讓語音回復使用者更容易。</span><span class="sxs-lookup"><span data-stu-id="09d5e-354">Make voice responses user friendly.</span></span> <span data-ttu-id="09d5e-355">例如，如果您指定 DTMF 和語音回應，請使用如下所示的內容：「若要與銷售團隊進行通話，請按1或說出銷售。」</span><span class="sxs-lookup"><span data-stu-id="09d5e-355">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

- <span data-ttu-id="09d5e-356">在您的組織中部署使用者群組之前，請先測試一組使用者的 IVR。</span><span class="sxs-lookup"><span data-stu-id="09d5e-356">Test the IVR on a group of users before you deploy it across your organization.</span></span>

## <a name="creating-or-modifying-an-interactive-workflow"></a><span data-ttu-id="09d5e-357">建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="09d5e-357">Creating or modifying an interactive workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="09d5e-358">使用 [回應群組設定] 工具來建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="09d5e-358">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1. <span data-ttu-id="09d5e-359">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="09d5e-359">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="09d5e-360">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-360">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="09d5e-361">在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-361">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="09d5e-362">在 [**工作流程**] 頁面上，按一下 [**建立或編輯工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-362">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="09d5e-363">在 [**選取服務**搜尋] 欄位中，輸入您要建立或修改之工作流程之**ApplicationServer**服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="09d5e-363">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="09d5e-364">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="09d5e-364">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-365">[回應群組設定] 工具隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="09d5e-365">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="09d5e-366">您也可以輸入下列 URL，在網頁瀏覽器中直接開啟 [回應群組設定] 工具：\<Https://\>webPoolFqdn/RgsConfig。</span><span class="sxs-lookup"><span data-stu-id="09d5e-366">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="09d5e-367">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="09d5e-367">Do one of the following:</span></span>

   - <span data-ttu-id="09d5e-368">在 [**建立新工作流程**] 底下，按一下 [**互動式**] 旁的 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-368">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>

   - <span data-ttu-id="09d5e-369">在 [**管理現有的工作流程**] 底下，找出您要變更的工作流程，然後在 [**動作**] 底下，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-369">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="09d5e-370">如果您未準備好讓使用者開始呼叫工作流程，請清除 [**啟用工作流程**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-370">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="09d5e-371">如果您要建立受管理的工作流程，您必須選取 [**啟用工作流程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-371">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="09d5e-372">儲存作用中受管理的工作流程之後，您就可以進行修改及停用。</span><span class="sxs-lookup"><span data-stu-id="09d5e-372">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="09d5e-373">若要允許聯盟使用者呼叫群組，請選取 [**啟用聯盟**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-373">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="09d5e-374">您也必須有可套用至針對同盟設定之回應群組應用程式的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="09d5e-374">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-375">全域外部存取原則會套用至回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-375">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="09d5e-376">您可以使用商務用 Skype Server 的 [控制台]，或使用**CsExternalAccessPolicy** Cmdlet 將 EnableOutsideAccess 參數設定為 True，來設定回應群組同盟的全域原則。</span><span class="sxs-lookup"><span data-stu-id="09d5e-376">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="09d5e-377">請記住，除非指派網站或使用者原則，否則全域原則設定將會套用至所有使用者。</span><span class="sxs-lookup"><span data-stu-id="09d5e-377">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="09d5e-378">因此，在變更回應群組的此設定之前，請確定同盟設定符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-378">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="09d5e-379">如需有關如何將原則套用至使用者的詳細資訊，請參閱[管理貴組織的外部存取原則](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-379">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="09d5e-380">如需同盟設定的詳細資訊，請參閱在檔中**設定 CsExternalAccessPolicy** 。</span><span class="sxs-lookup"><span data-stu-id="09d5e-380">For details about the federation setting, see **Set-CsExternalAccessPolicy** in documentation..</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-381">在商務用 Skype Online 中託管的使用者無法將呼叫權放在內部部署中託管的回應群組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-381">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="09d5e-382">這在混合式部署中，以及內部部署與商務用 Skype Online 部署聯盟的情況下，都是如此。</span><span class="sxs-lookup"><span data-stu-id="09d5e-382">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="09d5e-383">若要在呼叫期間隱藏代理程式的身分識別，請選取 [**啟用代理程式匿名**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-383">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-384">匿名通話不能以立即訊息（IM）或影片啟動，不過代理或來電者可以在通話建立之後，新增 IM 和影片。</span><span class="sxs-lookup"><span data-stu-id="09d5e-384">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="09d5e-385">匿名代理程式也可以保留通話、轉接呼叫（盲人與顧問式轉移），以及寄存與取回通話。</span><span class="sxs-lookup"><span data-stu-id="09d5e-385">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="09d5e-386">匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、whiteboarding 與資料共同作業，以及通話錄製。</span><span class="sxs-lookup"><span data-stu-id="09d5e-386">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="09d5e-387">使用 Lync VDI 外掛程式的代理程式可以匿名接收來電，但不能匿名撥出來電。</span><span class="sxs-lookup"><span data-stu-id="09d5e-387">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="09d5e-388">在 [**輸入將會接收來電的群組的位址**] 底下，輸入群組的主要 SIP 統一資源識別項（URI）位址，將會應答工作流程的呼叫。</span><span class="sxs-lookup"><span data-stu-id="09d5e-388">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="09d5e-389">在 [**顯示名稱**] 中，輸入您要顯示的工作流程名稱（例如 [銷售 IVR] 回應群組）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-389">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-390">不要在顯示名稱中\<包含 ""\>或 "" 字元。</span><span class="sxs-lookup"><span data-stu-id="09d5e-390">Do not include the "\<" or "\>" characters in the display name.</span></span> <span data-ttu-id="09d5e-391">請勿使用下列顯示名稱，因為它們是保留的： **RGS 目前狀態觀察**程式或**宣告服務**。</span><span class="sxs-lookup"><span data-stu-id="09d5e-391">Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="09d5e-392">在 [**電話號碼**] 中，輸入回應群組的行 URI （例如 + 14255550165）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-392">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="09d5e-393">在 [**顯示號碼**] 中，輸入您想要顯示給回應群組的數位（例如 + 1 （425）555-0165）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-393">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="09d5e-394">可選在 [**描述**] 中，輸入您想要在商務用 Skype 的連絡人卡片上顯示之工作流程的描述。</span><span class="sxs-lookup"><span data-stu-id="09d5e-394">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="09d5e-395">在 [**工作流程類型**] 中，如果此工作流程將由回應群組管理員管理，請選取 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-395">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="09d5e-396">請執行下列動作，將回應群組管理員指派給工作流程：</span><span class="sxs-lookup"><span data-stu-id="09d5e-396">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="09d5e-397">是.</span><span class="sxs-lookup"><span data-stu-id="09d5e-397">a.</span></span> <span data-ttu-id="09d5e-398">輸入此工作流程的管理員 SIP URI，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-398">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="09d5e-399">乙.</span><span class="sxs-lookup"><span data-stu-id="09d5e-399">b.</span></span> <span data-ttu-id="09d5e-400">輸入要新增至工作流程的其他管理員 SIP URI，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-400">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="09d5e-401">指派為回應群組管理員的每位使用者，都必須獲指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="09d5e-401">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="09d5e-402">如果沒有為使用者指派這個角色，就不能管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-402">If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="09d5e-403">在 [**步驟2選取語言**] 底下，按一下要用於語音辨識和文字轉換語音的語言。</span><span class="sxs-lookup"><span data-stu-id="09d5e-403">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="09d5e-404">如果您想要設定歡迎訊息，請在 [**步驟3設定歡迎訊息**] 底下，選取 [**播放歡迎訊息**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="09d5e-404">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="09d5e-405">若要將歡迎郵件輸入為已轉換為呼叫者語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入歡迎訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-405">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-406">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="09d5e-406">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="09d5e-407">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-407">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="09d5e-408">若要使用波形或 Windows Media 音訊檔案錄製以取得歡迎訊息，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-408">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**.</span></span> <span data-ttu-id="09d5e-409">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="09d5e-409">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="09d5e-410">在新的瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的音訊檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-410">In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="09d5e-411">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-411">Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-412">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-412">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-413">如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-413">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="09d5e-414">在 [**步驟4指定您的工作**時間] 底下的 [**您的時區**] 方塊中，按一下工作流程的時區。</span><span class="sxs-lookup"><span data-stu-id="09d5e-414">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-415">[時區] 是工作流程的呼叫者和代理程式所在的時區。</span><span class="sxs-lookup"><span data-stu-id="09d5e-415">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="09d5e-416">它是用來計算開啟和關閉時間。</span><span class="sxs-lookup"><span data-stu-id="09d5e-416">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="09d5e-417">例如，如果工作流程設定為使用北美東部時區，且工作流程排程在 7:00 A.M. 開啟。</span><span class="sxs-lookup"><span data-stu-id="09d5e-417">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="09d5e-418">接著，請在 11:00 P.M.，將開啟和關閉時間分別視為7:00 東部時間和11:00 東部時間。</span><span class="sxs-lookup"><span data-stu-id="09d5e-418">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively.</span></span> <span data-ttu-id="09d5e-419">（您必須以24小時制時間格式輸入時間。）</span><span class="sxs-lookup"><span data-stu-id="09d5e-419">(You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="09d5e-420">請執行下列其中一項動作，選取您要使用的商務時間排程類型：</span><span class="sxs-lookup"><span data-stu-id="09d5e-420">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="09d5e-421">若要使用預先定義的上班時間排程，請按一下 [**使用預設排程**]，然後從下拉式清單中選取您要使用的排程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-421">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-422">您之前必須已定義至少一個預設排程，才能選取此選項。</span><span class="sxs-lookup"><span data-stu-id="09d5e-422">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="09d5e-423">您可以使用**CsRgsHoursOfBusiness** Cmdlet 來定義預設排程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-423">You define preset schedules by using the **New-CsRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="09d5e-424">如需詳細資訊，請參閱[（選用）在商務用 Skype 中定義回應群組的上班時間](optional-define-response-group-business-hours.md)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-424">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span> <span data-ttu-id="09d5e-425">當您選取 [預置] 排程、[**天**]、[**開啟**] 和 [**關閉**] 時，系統會自動填入回應群組可用的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="09d5e-425">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="09d5e-426">若要使用只適用于此工作流程的自訂排程，請按一下 [**使用自訂排程**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-426">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="09d5e-427">如果您要建立此工作流程的自訂排程，請按一下回應群組可用之周的日期核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-427">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="09d5e-428">如果您要建立自訂排程，請在回應群組可供使用時，輸入**開啟**和**關閉**的時間。</span><span class="sxs-lookup"><span data-stu-id="09d5e-428">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group will be available.</span></span>

     > [!NOTE]
     > <span data-ttu-id="09d5e-429">[**開啟**] 和 [**關閉**] 時間必須是24小時制時間格式。</span><span class="sxs-lookup"><span data-stu-id="09d5e-429">The **Open** and **Close** hours must be in 24-hour time notation.</span></span> <span data-ttu-id="09d5e-430">例如，如果您的 office 的工作時間為9到5個工作日，而午餐時間為中午，則會將上班時間指定為**開啟**9:00、**關閉**12:00、**開啟**13:00，然後**關閉**17:00。</span><span class="sxs-lookup"><span data-stu-id="09d5e-430">For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="09d5e-431">如果您想要在 office 未開啟時播放郵件，請選取 [**當回應群組在上班時間以外時播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="09d5e-431">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="09d5e-432">若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-432">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-433">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="09d5e-433">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="09d5e-434">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-434">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="09d5e-435">若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-435">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="09d5e-436">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="09d5e-436">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="09d5e-437">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-437">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="09d5e-438">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-438">Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-439">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-439">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-440">如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-440">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="09d5e-441">指定在播放郵件後如何處理呼叫（如果已設定郵件）：</span><span class="sxs-lookup"><span data-stu-id="09d5e-441">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="09d5e-442">若要中斷通話，請按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="09d5e-442">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="09d5e-443">若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="09d5e-443">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="09d5e-444">語音信箱位址的格式是@ \* \<[使用者名\>\*\*\<功能變數名稱\> \* ] （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-444">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="09d5e-445">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。</span><span class="sxs-lookup"><span data-stu-id="09d5e-445">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="09d5e-446">使用者位址的格式是@ _ \<[使用者名\>__\<功能變數名稱\>_]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-446">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="09d5e-447">若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="09d5e-447">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="09d5e-448">電話號碼的格式是\* \<數位\>*@*\<domainname\> \* （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-448">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="09d5e-449">功能變數名稱是用來將呼叫者路由至正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="09d5e-449">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="09d5e-450">在 [**步驟5指定您的假日**] 底下，按一下一或多組假期的核取方塊，以定義回應群組結束的日期。</span><span class="sxs-lookup"><span data-stu-id="09d5e-450">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-451">您必須先定義假日和假日集，然後才能設定工作流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-451">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="09d5e-452">使用**新的-CsRgsHoliday**和**CsRgsHolidaySet** Cmdlet 來定義假日和假日集。</span><span class="sxs-lookup"><span data-stu-id="09d5e-452">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="09d5e-453">如需詳細資訊，請參閱[（選用）在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-453">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="09d5e-454">如果您想要在假日上播放郵件，請選取 [在**假日期間播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：</span><span class="sxs-lookup"><span data-stu-id="09d5e-454">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="09d5e-455">若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-455">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-456">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="09d5e-456">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="09d5e-457">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-457">If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="09d5e-458">若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-458">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="09d5e-459">如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。</span><span class="sxs-lookup"><span data-stu-id="09d5e-459">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="09d5e-460">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-460">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="09d5e-461">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-461">Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-462">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-462">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-463">如需支援的音訊檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-463">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="09d5e-464">指定在播放郵件後如何處理呼叫（如果已設定郵件）：</span><span class="sxs-lookup"><span data-stu-id="09d5e-464">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="09d5e-465">若要中斷通話，請按一下 **[中斷通話]**。</span><span class="sxs-lookup"><span data-stu-id="09d5e-465">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="09d5e-466">若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。</span><span class="sxs-lookup"><span data-stu-id="09d5e-466">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="09d5e-467">語音信箱位址的格式是@ \* \<[使用者名\>\*\*\<功能變數名稱\> \* ] （例如，bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-467">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="09d5e-468">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。</span><span class="sxs-lookup"><span data-stu-id="09d5e-468">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="09d5e-469">使用者位址的格式是@ _ \<[使用者名\>__\<功能變數名稱\>_]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-469">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="09d5e-470">若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="09d5e-470">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="09d5e-471">電話號碼的格式是\* \<數位\>*@*\<domainname\> \* （例如，+ 14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-471">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="09d5e-472">功能變數名稱是用來將呼叫者路由至正確的目的地。</span><span class="sxs-lookup"><span data-stu-id="09d5e-472">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="09d5e-473">在 [**步驟6設定暫停的音樂**] 底下，請執行下列其中一項動作，選擇您想要讓呼叫者在等待代理程式時聆聽的內容：</span><span class="sxs-lookup"><span data-stu-id="09d5e-473">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="09d5e-474">若要使用預設的音樂保留錄製，請按一下 [**使用預設值**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-474">To use the default music on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="09d5e-475">若要將音訊檔案錄製用於等候音樂，請按一下 [**選取音樂**檔案]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-475">To use an audio file recording for the on-hold music, click **Select a music file**.</span></span> <span data-ttu-id="09d5e-476">如果您想要上傳新的音訊檔案，請按一下 [**音樂**檔案] 連結。</span><span class="sxs-lookup"><span data-stu-id="09d5e-476">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="09d5e-477">在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-477">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="09d5e-478">按一下 **[上傳**] 載入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-478">Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-479">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-479">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-480">如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-480">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

28. <span data-ttu-id="09d5e-481">在 [**步驟7設定互動式語音回應**] 底下的 **[使用者將會聽到下列文字] 或 [錄製的郵件**] 標題中，指定要求呼叫者的問題，如下所示：</span><span class="sxs-lookup"><span data-stu-id="09d5e-481">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>

    - <span data-ttu-id="09d5e-482">若要以文字格式輸入問題，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入問題。</span><span class="sxs-lookup"><span data-stu-id="09d5e-482">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-483">請勿在您輸入的文字中包含 HTML 標籤。</span><span class="sxs-lookup"><span data-stu-id="09d5e-483">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="09d5e-484">如果您包含 HTML 標籤，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="09d5e-484">If you include HTML tags, you will receive an error message.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-485">"#" 符號是由文字到語音引擎轉譯為「數位」一詞。</span><span class="sxs-lookup"><span data-stu-id="09d5e-485">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="09d5e-486">如果您需要參照 # 鍵，您應該在提示中使用索引鍵名稱，而不是符號。</span><span class="sxs-lookup"><span data-stu-id="09d5e-486">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="09d5e-487">例如，若要與銷售額交談，請按井號鍵。</span><span class="sxs-lookup"><span data-stu-id="09d5e-487">For example, "To talk to sales, press the pound key."</span></span>

    - <span data-ttu-id="09d5e-488">若要使用含有問題的預先錄製音訊檔案，請按一下 [**選取錄製**]，然後按一下 [**錄製**] 連結來上傳檔案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-488">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="09d5e-489">在新的瀏覽器視窗中，按一下 **[流覽]**，選取音訊檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-489">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="09d5e-490">按一下 **[上傳**] 載入檔案，然後選擇您可以在文字方塊中輸入問題（這可讓您將問題及來電者回應轉寄到回應的代理程式）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-490">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller's response, to be forwarded to the responding agent).</span></span>

      > [!NOTE]
      > <span data-ttu-id="09d5e-491">所有使用者提供的音訊檔都必須符合特定的需求。</span><span class="sxs-lookup"><span data-stu-id="09d5e-491">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="09d5e-492">如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09d5e-492">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="09d5e-493">在 [**回應 1**] 底下，請執行下列動作，以指定第一次可能的問題答案：</span><span class="sxs-lookup"><span data-stu-id="09d5e-493">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="09d5e-494">請勿在任何語音回復中使用引號（"）。</span><span class="sxs-lookup"><span data-stu-id="09d5e-494">Do not use quotation marks (") in any voice responses.</span></span> <span data-ttu-id="09d5e-495">引號會導致 IVR 失敗。</span><span class="sxs-lookup"><span data-stu-id="09d5e-495">Quotation marks cause the IVR to fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09d5e-496">您可以選擇允許呼叫者使用語音、數位數位鍵台輸入或兩者同時接聽。</span><span class="sxs-lookup"><span data-stu-id="09d5e-496">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    - <span data-ttu-id="09d5e-497">如果您想要讓來電者使用語音進行回應，請在 [**輸入語音回應**] 中輸入答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-497">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>

    - <span data-ttu-id="09d5e-498">如果您想要允許呼叫者以鍵盤上的按鍵進行回應，請按一下 [**數位**] 中的小數位。</span><span class="sxs-lookup"><span data-stu-id="09d5e-498">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="09d5e-499">指定是否要將呼叫者路由到佇列，或是依以下方式提出其他問題：</span><span class="sxs-lookup"><span data-stu-id="09d5e-499">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>

    - <span data-ttu-id="09d5e-500">若要將呼叫者路由到佇列，請按一下 [**傳送至佇列**]，然後在 [**選取佇列**] 中，按一下您要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="09d5e-500">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>

    - <span data-ttu-id="09d5e-501">若要提出其他問題，請按一下 [**提出其他問題**]，然後按一下 [**使用文字轉換語音**] 並輸入問題，或按一下 [**選取錄製**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-501">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**.</span></span> <span data-ttu-id="09d5e-502">使用本節中的 [回應群組]，指定最多四個可能回應其他問題的回應，以及每個回應所要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="09d5e-502">Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response.</span></span> <span data-ttu-id="09d5e-503">若要指定第三或第四種可能的回復，請按一下 [**回應 3** ] 核取方塊或 [**回應 4** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-503">To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="09d5e-504">重複步驟28和29，以指定可能的回應，以及針對每個回應所採取的動作，指定最多三個可能的原始問題答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-504">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response.</span></span> <span data-ttu-id="09d5e-505">若要指定第三個或第四個可能的答案，請按一下 [**回應 3** ] 核取方塊或 [**回應 4** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="09d5e-505">To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="09d5e-506">按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-506">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="09d5e-507">若要使用商務用 Skype Server Management Shell 來建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="09d5e-507">To use Skype for Business Server Management Shell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="09d5e-508">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="09d5e-508">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="09d5e-509">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="09d5e-509">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="09d5e-510">檢索回應群組服務的服務名稱，並將它指派給變數。</span><span class="sxs-lookup"><span data-stu-id="09d5e-510">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="09d5e-511">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="09d5e-511">At the command line, run:</span></span>

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. <span data-ttu-id="09d5e-512">互動式工作流程需要兩個或多個佇列，以及兩個以上的代理群組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-512">An interactive workflow requires two or more queues and two or more agent groups.</span></span> <span data-ttu-id="09d5e-513">首先，建立代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-513">First, create the agent groups.</span></span> <span data-ttu-id="09d5e-514">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-514">Run:</span></span>

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. <span data-ttu-id="09d5e-515">建立佇列。</span><span class="sxs-lookup"><span data-stu-id="09d5e-515">Create the queues.</span></span> <span data-ttu-id="09d5e-516">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-516">Run:</span></span>

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. <span data-ttu-id="09d5e-517">建立第一個回應群組提示。</span><span class="sxs-lookup"><span data-stu-id="09d5e-517">Create the first response group prompt.</span></span> <span data-ttu-id="09d5e-518">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-518">Run:</span></span>

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. <span data-ttu-id="09d5e-519">然後建立在提示之後要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="09d5e-519">Then create the action to be performed after the prompt.</span></span> <span data-ttu-id="09d5e-520">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-520">Run:</span></span>

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. <span data-ttu-id="09d5e-521">建立第一個回應群組答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-521">Create the first response group answer.</span></span> <span data-ttu-id="09d5e-522">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-522">Run:</span></span>

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. <span data-ttu-id="09d5e-523">現在，建立第二個提示、通話動作及答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-523">Now create the second prompt, call action, and answer.</span></span> <span data-ttu-id="09d5e-524">首先建立提示。</span><span class="sxs-lookup"><span data-stu-id="09d5e-524">First create the prompt.</span></span> <span data-ttu-id="09d5e-525">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-525">Run:</span></span>

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. <span data-ttu-id="09d5e-526">建立第二個通話動作。</span><span class="sxs-lookup"><span data-stu-id="09d5e-526">Create the second call action.</span></span> <span data-ttu-id="09d5e-527">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-527">Run:</span></span>

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. <span data-ttu-id="09d5e-528">建立第二個回應群組答案。</span><span class="sxs-lookup"><span data-stu-id="09d5e-528">Create the second response group answer.</span></span> <span data-ttu-id="09d5e-529">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-529">Run:</span></span>

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. <span data-ttu-id="09d5e-530">建立最上層的提示。</span><span class="sxs-lookup"><span data-stu-id="09d5e-530">Create the top-level prompt.</span></span> <span data-ttu-id="09d5e-531">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-531">Run:</span></span>

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. <span data-ttu-id="09d5e-532">建立最上層的問題。</span><span class="sxs-lookup"><span data-stu-id="09d5e-532">Create the top-level question.</span></span> <span data-ttu-id="09d5e-533">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-533">Run:</span></span>

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. <span data-ttu-id="09d5e-534">現在，建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="09d5e-534">Now create the workflow.</span></span> <span data-ttu-id="09d5e-535">用盡</span><span class="sxs-lookup"><span data-stu-id="09d5e-535">Run:</span></span>

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > <span data-ttu-id="09d5e-536">已指定為回應群組管理員的所有使用者，都必須獲指派 CsResponseGroupManager 角色。</span><span class="sxs-lookup"><span data-stu-id="09d5e-536">All users who have been designated as manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="09d5e-537">如果沒有為使用者指派這個角色，就不能管理回應群組。</span><span class="sxs-lookup"><span data-stu-id="09d5e-537">If users are not assigned this role, they cannot manage response groups.</span></span>

## <a name="see-also"></a><span data-ttu-id="09d5e-538">另請參閱</span><span class="sxs-lookup"><span data-stu-id="09d5e-538">See also</span></span>

[<span data-ttu-id="09d5e-539">可選在商務用 Skype 中定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="09d5e-539">(Optional) Define Response Group holiday sets in Skype for Business</span></span>](optional-define-response-group-holiday-sets.md)

[<span data-ttu-id="09d5e-540">可選在商務用 Skype 中定義回應群組上班時間</span><span class="sxs-lookup"><span data-stu-id="09d5e-540">(Optional) Define Response Group business hours in Skype for Business</span></span>](optional-define-response-group-business-hours.md)

[<span data-ttu-id="09d5e-541">新-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="09d5e-541">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="09d5e-542">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="09d5e-542">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="09d5e-543">新-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="09d5e-543">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[<span data-ttu-id="09d5e-544">新-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="09d5e-544">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

