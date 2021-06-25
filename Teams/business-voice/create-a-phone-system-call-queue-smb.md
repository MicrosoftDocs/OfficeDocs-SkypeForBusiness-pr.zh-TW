---
title: 在小型企業教學課程Microsoft Teams通話佇列
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: 瞭解如何在 Microsoft 365 商務語音 中為小型企業設定Microsoft 365 商務語音。
ms.openlocfilehash: e7141d32015207469346e018bc12bc362254ba2f
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126919"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="fcaab-103">建立通話佇列 - 小型企業教學課程</span><span class="sxs-lookup"><span data-stu-id="fcaab-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="fcaab-104">通話佇列提供將來電者路由給組織中可協助處理特定問題或問題的人的方法。</span><span class="sxs-lookup"><span data-stu-id="fcaab-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="fcaab-105">通話會一次一次分散給佇列中 (稱為 *代理人) 。*</span><span class="sxs-lookup"><span data-stu-id="fcaab-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="fcaab-106">通話佇列提供：</span><span class="sxs-lookup"><span data-stu-id="fcaab-106">Call queues provide:</span></span>

- <span data-ttu-id="fcaab-107">問候訊息。</span><span class="sxs-lookup"><span data-stu-id="fcaab-107">A greeting message.</span></span>

- <span data-ttu-id="fcaab-108">當其他人在佇列中等候時播放音樂。</span><span class="sxs-lookup"><span data-stu-id="fcaab-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="fcaab-109">呼叫路由 - 在 *FIFO (* 中，) 呼叫路由 - 給代理人。</span><span class="sxs-lookup"><span data-stu-id="fcaab-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="fcaab-110">處理佇列溢出和超時的選項。</span><span class="sxs-lookup"><span data-stu-id="fcaab-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="video-demonstration"></a><span data-ttu-id="fcaab-111">影片示範</span><span class="sxs-lookup"><span data-stu-id="fcaab-111">Video demonstration</span></span>

<span data-ttu-id="fcaab-112">這段影片示範如何在 Teams 中建立Teams。</span><span class="sxs-lookup"><span data-stu-id="fcaab-112">This video demonstrates how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="fcaab-113">開始之前</span><span class="sxs-lookup"><span data-stu-id="fcaab-113">Before you begin</span></span>

<span data-ttu-id="fcaab-114">取得一[電話系統 - 如果您](../teams-add-on-licensing/virtual-user.md)還沒有虛擬使用者授權。</span><span class="sxs-lookup"><span data-stu-id="fcaab-114">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="fcaab-115">針對您打算設定的每個通話佇列和自動話務員取得一個。</span><span class="sxs-lookup"><span data-stu-id="fcaab-115">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="fcaab-116">這些授權是免費的，因此我們建議您額外取得一些授權，以防您決定日後變更您的設定。</span><span class="sxs-lookup"><span data-stu-id="fcaab-116">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="fcaab-117">由於通話佇列中的代理人可能會撥出以傳回客戶電話，請考慮將呼叫代理的本機號碼設定為主電話號碼或適當的自動語音機號碼。</span><span class="sxs-lookup"><span data-stu-id="fcaab-117">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="fcaab-118">請參閱[在 Microsoft Teams](../caller-id-policies.md)管理本機號碼政策以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="fcaab-118">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="fcaab-119">請遵循下列步驟來設定您的通話佇列</span><span class="sxs-lookup"><span data-stu-id="fcaab-119">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="fcaab-120">步驟 1 <br> 建立團隊</span><span class="sxs-lookup"><span data-stu-id="fcaab-120">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="fcaab-121">建立通話佇列時，您可以新增個別使用者至佇列，或使用現有的安全性群組、Microsoft 365群組，或Microsoft Teams小組。</span><span class="sxs-lookup"><span data-stu-id="fcaab-121">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="fcaab-122">我們建議您 [使用小組頻道](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)。</span><span class="sxs-lookup"><span data-stu-id="fcaab-122">We recommend [using a team channel](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e).</span></span> <span data-ttu-id="fcaab-123">這可讓佇列成員彼此聊天、分享想法，以及建立檔或其他資源，協助他們協助您的客戶。</span><span class="sxs-lookup"><span data-stu-id="fcaab-123">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="fcaab-124">團隊也會提供語音信箱，讓來電者在數小時後留言，或佇列達到最大容量。</span><span class="sxs-lookup"><span data-stu-id="fcaab-124">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="fcaab-125">建立團隊</span><span class="sxs-lookup"><span data-stu-id="fcaab-125">To create a team</span></span>

1. <span data-ttu-id="fcaab-126">首先 **，Teams應用程式** 左側的 [加入或建立團隊>，然後在團隊清單底部按一下 [加入或建立團隊>。</span><span class="sxs-lookup"><span data-stu-id="fcaab-126">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="fcaab-127">然後按一下 [ **建立團隊** (第一張卡片，左上角) 。</span><span class="sxs-lookup"><span data-stu-id="fcaab-127">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="fcaab-128">選擇 **從頭開始建立團隊**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-128">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="fcaab-129">接下來，選擇您想要公開或私人團隊。</span><span class="sxs-lookup"><span data-stu-id="fcaab-129">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="fcaab-130">我們建議您使用 **私人** 通話佇列，以避免人員加入團隊而不小心成為佇列的一部分。</span><span class="sxs-lookup"><span data-stu-id="fcaab-130">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="fcaab-131">為您的小組命名，並新增選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="fcaab-131">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="fcaab-132">完成後，請按一下 [**建立。**</span><span class="sxs-lookup"><span data-stu-id="fcaab-132">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="fcaab-133">輸入您想要在通話佇列中擁有之人員的名稱，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-133">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="fcaab-134">按一下 **[關閉**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-134">Click **Close**.</span></span> <span data-ttu-id="fcaab-135">您新加入團隊的人會收到一封電子郵件，讓他們知道他們現在是您團隊的成員，而團隊會顯示在團隊清單中。</span><span class="sxs-lookup"><span data-stu-id="fcaab-135">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

<span data-ttu-id="fcaab-136">接下來，我們會新增一個頻道，用於通話佇列。</span><span class="sxs-lookup"><span data-stu-id="fcaab-136">Next, we'll add a channel to use with the call queue.</span></span>

<span data-ttu-id="fcaab-137">新增頻道</span><span class="sxs-lookup"><span data-stu-id="fcaab-137">To add a channel</span></span>

1. <span data-ttu-id="fcaab-138">在 Teams中，尋找您剛剛建立的團隊，按一下[更多選項 (...) ，然後按一下 [**新增頻道**> 。</span><span class="sxs-lookup"><span data-stu-id="fcaab-138">In Teams, find the team you just created, click **More options** (...), and then click **Add channel**.</span></span>

2. <span data-ttu-id="fcaab-139">輸入頻道的名稱和描述，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-139">Type a name and description for the channel, and then click **Add**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcaab-140">步驟 2 - 資源帳戶></span><span class="sxs-lookup"><span data-stu-id="fcaab-140">Step 2 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="fcaab-141">步驟 2 <br> 資源帳戶</span><span class="sxs-lookup"><span data-stu-id="fcaab-141">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="fcaab-142">您建立的每個通話佇列都需要資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="fcaab-142">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="fcaab-143">這類似于使用者帳戶，除了該帳戶與自動通話或通話佇列相關聯，而不是與人員相關聯。</span><span class="sxs-lookup"><span data-stu-id="fcaab-143">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="fcaab-144">在此步驟中，我們將建立帳戶、指派帳戶Microsoft 365 電話系統 *虛擬* 使用者授權，然後使用它開始建立通話佇列。</span><span class="sxs-lookup"><span data-stu-id="fcaab-144">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="fcaab-145">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="fcaab-145">Create a resource account</span></span>

<span data-ttu-id="fcaab-146">您可以在系統管理中心建立Teams帳戶。</span><span class="sxs-lookup"><span data-stu-id="fcaab-146">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="fcaab-147">在 Teams系統管理中心中，展開 **整個組織設定**，然後按一下 [**資源帳戶**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-147">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="fcaab-148">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-148">Click **Add**.</span></span>

3. <span data-ttu-id="fcaab-149">在新增 **資源帳戶窗格中**，填寫 **顯示名稱**、**使用者名稱**，然後選擇資源帳戶 **類型的通話佇列**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-149">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span> <span data-ttu-id="fcaab-150">當代理人收到來自佇列的來電時，會顯示顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="fcaab-150">Agents will see the display name when they receive an incoming call from the queue.</span></span>

    ![新增資源帳戶使用者介面的螢幕擷取畫面](../media/resource-account-add-cq.png)

4. <span data-ttu-id="fcaab-152">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="fcaab-152">Click **Save**.</span></span>

   <span data-ttu-id="fcaab-153">新帳戶會顯示在帳戶清單中。</span><span class="sxs-lookup"><span data-stu-id="fcaab-153">The new account will appear in the list of accounts.</span></span>

   ![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="fcaab-155">指派授權</span><span class="sxs-lookup"><span data-stu-id="fcaab-155">Assign a license</span></span>

<span data-ttu-id="fcaab-156">您必須指派一個 *Microsoft 365 電話系統 - 虛擬使用者* 授權給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="fcaab-156">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="fcaab-157">在 Microsoft 365 系統管理中心中，按一下 [使用中使用者」 清單中的您想要指派授權的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="fcaab-157">In the Microsoft 365 admin center, in the **Active users** list, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="fcaab-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span><span class="sxs-lookup"><span data-stu-id="fcaab-158">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="fcaab-159">按一下 **[儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-159">Click **Save changes**.</span></span>

    ![指派授權使用者介面的螢幕擷取畫面Microsoft 365 系統管理中心](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="fcaab-161">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="fcaab-161">Create a call queue</span></span>

<span data-ttu-id="fcaab-162">接下來，我們將開始建立新的通話佇列並指派資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="fcaab-162">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="fcaab-163">在系統管理Teams，展開 **[語音** 和通話佇列，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-163">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="fcaab-164">輸入通話佇列的名稱。</span><span class="sxs-lookup"><span data-stu-id="fcaab-164">Type a name for the call queue.</span></span>

2. <span data-ttu-id="fcaab-165">按一下 **[新增帳戶**，搜尋要用於此通話佇列的資源帳戶;按一下 [ **新增**，然後按一下 [ **新增**> 。</span><span class="sxs-lookup"><span data-stu-id="fcaab-165">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="fcaab-166"> ([) 指定通話識別碼下，按一下 [新增」，搜尋您為自動話務員建立的資源帳戶，按一下 [新增，然後按一下 [**新增**> 。 </span><span class="sxs-lookup"><span data-stu-id="fcaab-166">(Optional) Under **Assign calling ID**, click **Add**, search for the resource accounts that you created for your auto attendant, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="fcaab-167">這樣一來，通話代理人就會在來電時，提供主線本機號碼。</span><span class="sxs-lookup"><span data-stu-id="fcaab-167">This will give your call agents the caller ID of your main line when they call out.</span></span>

    ![通話識別碼設定螢幕擷取畫面](../media/call-queue-assign-calling-id.png)

3. <span data-ttu-id="fcaab-169">選擇語言。</span><span class="sxs-lookup"><span data-stu-id="fcaab-169">Choose a language.</span></span> <span data-ttu-id="fcaab-170">如果您啟用語音提示，系統產生的語音提示和語音信箱 (語音信箱) 。</span><span class="sxs-lookup"><span data-stu-id="fcaab-170">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![資源帳戶設定螢幕擷取畫面](../media/call-queue-name-language.png)

4. <span data-ttu-id="fcaab-172">指定當來電者抵達佇列時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="fcaab-172">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="fcaab-173">您必須上傳包含您想要播放的問候語的 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="fcaab-173">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="fcaab-174">Teams在佇列中保留來電者時，提供預設音樂。</span><span class="sxs-lookup"><span data-stu-id="fcaab-174">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="fcaab-175">如果您想要播放特定的音訊檔案，請選擇播放音訊檔案並上傳 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="fcaab-175">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fcaab-176">上傳的錄製不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="fcaab-176">The uploaded recording can be no larger than 5 MB.</span></span>
   > <span data-ttu-id="fcaab-177">在通話佇列Teams中提供的預設音樂，不含貴組織支付的任何版稅。</span><span class="sxs-lookup"><span data-stu-id="fcaab-177">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcaab-178">步驟 3 - 呼叫代理人></span><span class="sxs-lookup"><span data-stu-id="fcaab-178">Step 3 - Call agents ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="fcaab-179">步驟 3 <br> 通話代理程式</span><span class="sxs-lookup"><span data-stu-id="fcaab-179">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="fcaab-180">若要將代理人新增到通話佇列，我們會將它們新加到我們先前建立的團隊和頻道中。</span><span class="sxs-lookup"><span data-stu-id="fcaab-180">To add agents to the call queue, we'll add them to the team and channel that we created earlier.</span></span> <span data-ttu-id="fcaab-181">您必須是團隊的成員，以執行此工作。</span><span class="sxs-lookup"><span data-stu-id="fcaab-181">You need to be a member of the team to do this.</span></span>

1. <span data-ttu-id="fcaab-182">選取 [ **選擇團隊選項** ，然後按一下 **[新增頻道**> 。</span><span class="sxs-lookup"><span data-stu-id="fcaab-182">Select the **Choose a team** option and click **Add a channel**.</span></span>
2. <span data-ttu-id="fcaab-183">輸入您建立的團隊名稱，選取它，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-183">Type the name of the team that you created, select it, and click **Add**.</span></span>
3. <span data-ttu-id="fcaab-184">選取您為佇列所建立頻道。</span><span class="sxs-lookup"><span data-stu-id="fcaab-184">Select the channel that you created for the queue.</span></span>
3. <span data-ttu-id="fcaab-185">按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="fcaab-185">Click **Apply**.</span></span>

    ![通話佇列的使用者和群組設定螢幕擷取畫面](../media/call-queue-users-groups.png)

> [!NOTE]
> <span data-ttu-id="fcaab-187">新使用者新加入團隊時，第一次通話最多可能需要八小時才能到達。</span><span class="sxs-lookup"><span data-stu-id="fcaab-187">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcaab-188">步驟 4 - 資源帳戶></span><span class="sxs-lookup"><span data-stu-id="fcaab-188">Step 4 - Resource accounts ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="fcaab-189">步驟 4 <br> 通話路由</span><span class="sxs-lookup"><span data-stu-id="fcaab-189">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="fcaab-190">選擇您想要使用的通話路由方法。</span><span class="sxs-lookup"><span data-stu-id="fcaab-190">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="fcaab-191">將 **會議模式設定** 為 **自動**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-191">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="fcaab-192">選擇 **您想要使用的** 路由方法。</span><span class="sxs-lookup"><span data-stu-id="fcaab-192">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="fcaab-193">這決定代理程式從佇列接收來電的順序。</span><span class="sxs-lookup"><span data-stu-id="fcaab-193">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="fcaab-194">我們建議您使用 **序列路由或** **Round robin。**</span><span class="sxs-lookup"><span data-stu-id="fcaab-194">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="fcaab-195">從這些選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="fcaab-195">Choose from these options:</span></span>

    - <span data-ttu-id="fcaab-196">**話務員路由** 會同時響鈴佇列中的所有代理程式。</span><span class="sxs-lookup"><span data-stu-id="fcaab-196">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="fcaab-197">第一個接電話的代理人會接到電話。</span><span class="sxs-lookup"><span data-stu-id="fcaab-197">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="fcaab-198">**連續路由** 會一個接一個地撥打所有呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="fcaab-198">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="fcaab-199">如果客服人員關閉或不接電話，來電會撥打給下一個代理人，並嘗試所有代理人，直到被接回或打出電話。</span><span class="sxs-lookup"><span data-stu-id="fcaab-199">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="fcaab-200">**輪循** 機制會平衡來電的路由，讓每個通話代理程式從佇列取得相同數量的通話。</span><span class="sxs-lookup"><span data-stu-id="fcaab-200">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="fcaab-201">在內入銷售環境中，這可能是理想的選擇，以確保所有通話代理人之間享有同等的機會。</span><span class="sxs-lookup"><span data-stu-id="fcaab-201">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="fcaab-202">**最長空閒** 時間會路由每個通話給閒置時間最長的代理人。</span><span class="sxs-lookup"><span data-stu-id="fcaab-202">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="fcaab-203"> (狀態已離開超過 10 分鐘的代理人。) </span><span class="sxs-lookup"><span data-stu-id="fcaab-203">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![會議模式和路由方法設定螢幕擷取畫面](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="fcaab-205">開啟 **目前狀態路由** 。</span><span class="sxs-lookup"><span data-stu-id="fcaab-205">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="fcaab-206">這會將通話路由至目前狀態為可用的 **代理人**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-206">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="fcaab-207">選擇您是否要允許代理人退出宣告通話。</span><span class="sxs-lookup"><span data-stu-id="fcaab-207">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="fcaab-208">設定 **代理人通知** 時間，指定在佇列將通話重新導向至下一個代理人之前，代理人的電話會響鈴多久。</span><span class="sxs-lookup"><span data-stu-id="fcaab-208">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![路由、退出宣告和通知時間設定螢幕擷取畫面](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcaab-210">步驟 5 - 通話溢出></span><span class="sxs-lookup"><span data-stu-id="fcaab-210">Step 5 - Call overflow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="fcaab-211">步驟 5 <br> 通話溢出</span><span class="sxs-lookup"><span data-stu-id="fcaab-211">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="fcaab-212">選擇您想要如何處理超過佇列中上限的通話。</span><span class="sxs-lookup"><span data-stu-id="fcaab-212">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="fcaab-213">設定 **佇列中的通話上限**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-213">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="fcaab-214">選擇通話次數上限時要執行什麼工作。</span><span class="sxs-lookup"><span data-stu-id="fcaab-214">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="fcaab-215">您可以中斷通話或重新導向。</span><span class="sxs-lookup"><span data-stu-id="fcaab-215">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="fcaab-216">我們建議您將通話重新導向下列其中一個目的地：</span><span class="sxs-lookup"><span data-stu-id="fcaab-216">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="fcaab-217">**組織中能夠** 接聽語音通話的人</span><span class="sxs-lookup"><span data-stu-id="fcaab-217">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="fcaab-218">**語音應用程式** - 自動語音留言或其他通話佇列。</span><span class="sxs-lookup"><span data-stu-id="fcaab-218">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="fcaab-219"> (選擇此目的地時，選擇與自動電話機或通話佇列相關聯的資源帳戶。) </span><span class="sxs-lookup"><span data-stu-id="fcaab-219">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="fcaab-220">**外部電話號碼** - 任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="fcaab-220">**External phone number** - any phone number.</span></span> <span data-ttu-id="fcaab-221">使用此格式：+[國碼][區碼][電話號碼]</span><span class="sxs-lookup"><span data-stu-id="fcaab-221">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="fcaab-222">**語音** 信箱 - 您可以使用您建立團隊的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="fcaab-222">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通話溢出設定螢幕擷取畫面](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcaab-224">步驟 6 - 通話></span><span class="sxs-lookup"><span data-stu-id="fcaab-224">Step 6 - Call timeout ></span></span>](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="fcaab-225">步驟 6 <br> 通話超時</span><span class="sxs-lookup"><span data-stu-id="fcaab-225">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="fcaab-226">選擇當通話在佇列中等候太久時要發生的專案。</span><span class="sxs-lookup"><span data-stu-id="fcaab-226">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="fcaab-227">設定 **最長等待時間**。</span><span class="sxs-lookup"><span data-stu-id="fcaab-227">Set the **Maximum wait time**.</span></span>

2. <span data-ttu-id="fcaab-228">選擇當通話時間過時您想要執行什麼工作。您可以中斷通話或重新導向。</span><span class="sxs-lookup"><span data-stu-id="fcaab-228">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="fcaab-229">我們建議您將通話重新導向下列其中一個目的地：</span><span class="sxs-lookup"><span data-stu-id="fcaab-229">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="fcaab-230">**組織中能夠** 接聽語音通話的人</span><span class="sxs-lookup"><span data-stu-id="fcaab-230">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="fcaab-231">**語音應用程式** - 自動語音留言或其他通話佇列。</span><span class="sxs-lookup"><span data-stu-id="fcaab-231">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="fcaab-232"> (選擇此目的地時，選擇與自動電話機或通話佇列相關聯的資源帳戶。) </span><span class="sxs-lookup"><span data-stu-id="fcaab-232">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="fcaab-233">**外部電話號碼** - 任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="fcaab-233">**External phone number** - any phone number.</span></span> <span data-ttu-id="fcaab-234">使用此格式：+[國碼][區碼][電話號碼]</span><span class="sxs-lookup"><span data-stu-id="fcaab-234">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="fcaab-235">**語音** 信箱 - 您可以使用您建立團隊的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="fcaab-235">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通話超時設定螢幕擷取畫面](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="fcaab-237">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="fcaab-237">Click **Save**.</span></span>

<span data-ttu-id="fcaab-238">這會完成通話佇列的設定。</span><span class="sxs-lookup"><span data-stu-id="fcaab-238">This completes the setup of your call queue.</span></span> <span data-ttu-id="fcaab-239">接下來，您可能會想要 [設定自動話務員](create-a-phone-system-auto-attendant-smb.md)。</span><span class="sxs-lookup"><span data-stu-id="fcaab-239">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

