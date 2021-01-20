---
title: 在 Microsoft 團隊中建立通話佇列-小型企業教學課程
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
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
description: 瞭解如何使用 Microsoft 365 商務版語音設定通話佇列。
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909614"
---
# <a name="create-a-call-queue---small-business-tutorial"></a><span data-ttu-id="98fd5-103">建立通話佇列-小型企業教學課程</span><span class="sxs-lookup"><span data-stu-id="98fd5-103">Create a call queue - small business tutorial</span></span>

<span data-ttu-id="98fd5-104">通話佇列提供將呼叫者路由給組織中的人員的方法，可協助您解決特定問題。</span><span class="sxs-lookup"><span data-stu-id="98fd5-104">Call queues provide a method of routing callers to people in your organization who can help with with a particular issue or question.</span></span> <span data-ttu-id="98fd5-105">呼叫會一次散佈給佇列中的人員， (稱為 [ *代理* 程式]) 。</span><span class="sxs-lookup"><span data-stu-id="98fd5-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="98fd5-106">通話佇列提供：</span><span class="sxs-lookup"><span data-stu-id="98fd5-106">Call queues provide:</span></span>

- <span data-ttu-id="98fd5-107">問候訊息。</span><span class="sxs-lookup"><span data-stu-id="98fd5-107">A greeting message.</span></span>

- <span data-ttu-id="98fd5-108">當人員在佇列中等待保留時，請使用音樂。</span><span class="sxs-lookup"><span data-stu-id="98fd5-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="98fd5-109">呼叫路由-先進先 *出* (FIFO) 訂單至代理程式。</span><span class="sxs-lookup"><span data-stu-id="98fd5-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="98fd5-110">[佇列溢出] 和 [超時] 的處理選項。</span><span class="sxs-lookup"><span data-stu-id="98fd5-110">Handling options for queue overflow and timeout.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="98fd5-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="98fd5-111">Before you begin</span></span>

<span data-ttu-id="98fd5-112">取得一些 [電話系統-虛擬使用者授權（](../teams-add-on-licensing/virtual-user.md) 如果您還沒有的話）。</span><span class="sxs-lookup"><span data-stu-id="98fd5-112">Get some [Phone System - Virtual User licenses](../teams-add-on-licensing/virtual-user.md) if you don't already have them.</span></span> <span data-ttu-id="98fd5-113">針對您規劃設定的每個通話佇列和自動語音應答，取得一個。</span><span class="sxs-lookup"><span data-stu-id="98fd5-113">Get one for each call queue and auto attendant that you plan to set up.</span></span> <span data-ttu-id="98fd5-114">這些授權是免費的，因此我們建議您先取得幾個額外的案例，以備日後決定變更您的設定。</span><span class="sxs-lookup"><span data-stu-id="98fd5-114">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="98fd5-115">由於通話佇列中的代理程式可能會撥出以傳回客戶電話，因此請考慮將來電代理程式的本機號碼設定為您的主要電話號碼或適當的自動語音應答號碼。</span><span class="sxs-lookup"><span data-stu-id="98fd5-115">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for your call agents to your main phone number or the number of an appropriate auto attendant.</span></span> <span data-ttu-id="98fd5-116">如需詳細資訊，請參閱 [在 Microsoft 團隊中管理本機號碼原則](../caller-id-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="98fd5-116">See [Manage caller ID policies in Microsoft Teams](../caller-id-policies.md) for more information.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a><span data-ttu-id="98fd5-117">請依照下列步驟來設定您的通話佇列</span><span class="sxs-lookup"><span data-stu-id="98fd5-117">Follow these steps to set up your call queue</span></span>

# <a name="step-1brcreate-a-team"></a>[<span data-ttu-id="98fd5-118">步驟 1 <br> 建立小組</span><span class="sxs-lookup"><span data-stu-id="98fd5-118">Step 1<br>Create a team</span></span>](#tab/create-team)

<span data-ttu-id="98fd5-119">建立通話佇列時，您可以將個別使用者新增至佇列，或者您可以使用現有的安全性群組、Microsoft 365 群組或 Microsoft 團隊小組。</span><span class="sxs-lookup"><span data-stu-id="98fd5-119">When creating a call queue, you can add individual users to the queue, or you can use an existing security group, Microsoft 365 group, or Microsoft Teams team.</span></span> <span data-ttu-id="98fd5-120">我們建議使用團隊。</span><span class="sxs-lookup"><span data-stu-id="98fd5-120">We recommend using a team.</span></span> <span data-ttu-id="98fd5-121">這可讓佇列中的成員彼此聊天、分享想法，以及建立檔或其他資源，協助客戶進行協助。</span><span class="sxs-lookup"><span data-stu-id="98fd5-121">This allows members of the queue to chat with each other, share ideas, and create documents or other resources to help them help your customers.</span></span> <span data-ttu-id="98fd5-122">小組也會提供語音信箱，讓來電者在數小時後離開訊息，或當佇列達到其最大容量時。</span><span class="sxs-lookup"><span data-stu-id="98fd5-122">A team also provides a voice mailbox for callers to leave a message after hours or if the queue reaches its maximum capacity.</span></span>

<span data-ttu-id="98fd5-123">建立小組</span><span class="sxs-lookup"><span data-stu-id="98fd5-123">To create a team</span></span>

1. <span data-ttu-id="98fd5-124">首先，按一下應用程式左側的 [ **小組** ]，然後按一下團隊清單底部的 [ **加入] 或 [建立小組** ]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-124">First, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of your teams list.</span></span>

2. <span data-ttu-id="98fd5-125">然後按一下 [ **建立團隊** (第一張卡片，左上角) ]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-125">Then click **Create team** (first card, top left corner).</span></span>

3. <span data-ttu-id="98fd5-126">選擇 [ **從頭開始建立小組**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-126">Choose **Build a team from scratch**.</span></span>

4. <span data-ttu-id="98fd5-127">接下來，選擇您要的是公用或私人團隊。</span><span class="sxs-lookup"><span data-stu-id="98fd5-127">Next, choose whether you want a public or private team.</span></span> <span data-ttu-id="98fd5-128">我們建議您在通話佇列中使用 **私人** ，以避免人員透過加入小組而無意中成為佇列的一部分。</span><span class="sxs-lookup"><span data-stu-id="98fd5-128">We recommend **Private** for your call queue to avoid people unintentionally becoming part of the queue by joining the team.</span></span>

5. <span data-ttu-id="98fd5-129">為您的小組命名，並新增選用的描述。</span><span class="sxs-lookup"><span data-stu-id="98fd5-129">Name your team and add an optional description.</span></span>

6. <span data-ttu-id="98fd5-130">完成後，請按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-130">When you're done, click **Create**.</span></span>

8. <span data-ttu-id="98fd5-131">輸入您想在通話佇列中擁有的人員名稱，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-131">Type the names of the people that you want to have in your call queue, and then click **Add**.</span></span>

9. <span data-ttu-id="98fd5-132">按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-132">Click **Close**.</span></span> <span data-ttu-id="98fd5-133">您新增至小組的人員會收到一封電子郵件，讓他們知道他們現在是您的小組成員，而且小組會顯示在他們的小組清單中。</span><span class="sxs-lookup"><span data-stu-id="98fd5-133">People you add to a team will receive an email letting them know they are now a member of your team and the team will show up in their teams list.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="98fd5-134">步驟 2-資源帳戶 ></span><span class="sxs-lookup"><span data-stu-id="98fd5-134">Step 2 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<span data-ttu-id="98fd5-135">步驟 2 <br> 資源帳戶</span><span class="sxs-lookup"><span data-stu-id="98fd5-135">Step 2<br>Resource accounts</span></span>](#tab/resource-account)

<span data-ttu-id="98fd5-136">您建立的每個通話佇列都需要有資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="98fd5-136">Each call queue that you create requires a resource account.</span></span> <span data-ttu-id="98fd5-137">這與使用者帳戶類似，只是帳戶與自動語音應答或通話佇列無關，而不是寄件者。</span><span class="sxs-lookup"><span data-stu-id="98fd5-137">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="98fd5-138">在此步驟中，我們會建立帳戶，將它指派為 *Microsoft 365 電話系統-虛擬使用者* 授權，然後使用它來開始建立通話佇列。</span><span class="sxs-lookup"><span data-stu-id="98fd5-138">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then use it to start creating the call queue.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="98fd5-139">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="98fd5-139">Create a resource account</span></span>

<span data-ttu-id="98fd5-140">您可以在 [團隊管理中心] 中建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="98fd5-140">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="98fd5-141">在 [團隊管理中心] 中，展開 [ **整個組織的設定**]，然後按一下 [ **資源帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-141">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="98fd5-142">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-142">Click **Add**.</span></span>

3. <span data-ttu-id="98fd5-143">在 [ **新增資源帳戶** ] 窗格中，填寫 [ **顯示名稱**]、[使用者名稱 **]，然後** 選擇 [ **通話佇列** ] 作為 **資源帳戶類型**。</span><span class="sxs-lookup"><span data-stu-id="98fd5-143">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Call queue** for the **Resource account type**.</span></span>

    ![[新增資源帳戶] 使用者介面的螢幕擷取畫面](../media/resource-account-add-cq.png)

4. <span data-ttu-id="98fd5-145">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="98fd5-145">Click **Save**.</span></span>

<span data-ttu-id="98fd5-146">新帳戶將會出現在帳戶清單中。</span><span class="sxs-lookup"><span data-stu-id="98fd5-146">The new account will appear in the list of accounts.</span></span>

![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="98fd5-148">指派授權</span><span class="sxs-lookup"><span data-stu-id="98fd5-148">Assign a license</span></span>

<span data-ttu-id="98fd5-149">您必須將 *Microsoft 365 電話系統-虛擬使用者* 授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="98fd5-149">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="98fd5-150">在 Microsoft 365 系統管理中心，按一下您要指派授權的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="98fd5-150">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="98fd5-151">在 [ **授權及應用程式** ] 索引標籤的 [ **授權**] 底下，選取 [ **Microsoft 365 電話系統-虛擬使用者**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-151">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="98fd5-152">按一下 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-152">Click **Save changes**.</span></span>

    ![在 Microsoft 365 系統管理中心指派授權使用者介面的螢幕擷取畫面](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a><span data-ttu-id="98fd5-154">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="98fd5-154">Create a call queue</span></span>

<span data-ttu-id="98fd5-155">接下來，我們將開始建立新的通話佇列並指派資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="98fd5-155">Next, we'll start creating a new call queue and assign the resource account.</span></span>

1. <span data-ttu-id="98fd5-156">在 [團隊管理中心] 中，展開 [ **語音**]，按一下 [ **通話佇列**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-156">In the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

1. <span data-ttu-id="98fd5-157">輸入通話佇列的名稱。</span><span class="sxs-lookup"><span data-stu-id="98fd5-157">Type a name for the call queue.</span></span> <span data-ttu-id="98fd5-158">當代理程式從佇列接收來電時，就會看到這個名稱。</span><span class="sxs-lookup"><span data-stu-id="98fd5-158">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="98fd5-159">按一下 [ **新增帳戶**]，搜尋您要與此通話佇列搭配使用的資源帳戶，按一下 [ **新增**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-159">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="98fd5-160">選擇語言。</span><span class="sxs-lookup"><span data-stu-id="98fd5-160">Choose a language.</span></span> <span data-ttu-id="98fd5-161">此語言將用於系統產生的語音提示，以及語音信箱操作 (如果您) 啟用這些語言。</span><span class="sxs-lookup"><span data-stu-id="98fd5-161">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

    ![資源帳戶和語言設定的螢幕擷取畫面](../media/call-queue-name-language.png)

4. <span data-ttu-id="98fd5-163">指定是否要在來電者到達佇列時，向呼叫者播放問候語。</span><span class="sxs-lookup"><span data-stu-id="98fd5-163">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="98fd5-164">您必須上傳包含您要播放之問候語的 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="98fd5-164">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

5. <span data-ttu-id="98fd5-165">當來電者在佇列中保留時，小組會將預設音樂提供給呼叫者。</span><span class="sxs-lookup"><span data-stu-id="98fd5-165">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="98fd5-166">如果您想要播放特定音訊檔案，請選擇 [ **播放音訊** 檔案]，然後上傳 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="98fd5-166">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="98fd5-167">上傳的錄製不能超過 5 MB。</span><span class="sxs-lookup"><span data-stu-id="98fd5-167">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="98fd5-168">小組通話佇列中提供的預設音樂，由貴組織所提供的任何版稅免費提供。</span><span class="sxs-lookup"><span data-stu-id="98fd5-168">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

> [!div class="nextstepaction"]
> [<span data-ttu-id="98fd5-169">步驟 3-通話代理程式 ></span><span class="sxs-lookup"><span data-stu-id="98fd5-169">Step 3 - Call agents ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[<span data-ttu-id="98fd5-170">步驟3： <br> 撥號代理程式</span><span class="sxs-lookup"><span data-stu-id="98fd5-170">Step 3<br>Call agents</span></span>](#tab/call-agents)

<span data-ttu-id="98fd5-171">若要將代理程式新增到通話佇列，我們將新增我們先前建立的小組。</span><span class="sxs-lookup"><span data-stu-id="98fd5-171">To add agents to the call queue, we'll add the team that we created earlier.</span></span>

1. <span data-ttu-id="98fd5-172">按一下 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-172">Click **Add groups**.</span></span>
2. <span data-ttu-id="98fd5-173">輸入您建立的小組名稱。</span><span class="sxs-lookup"><span data-stu-id="98fd5-173">Type the name of the team that you created.</span></span>
3. <span data-ttu-id="98fd5-174">按一下 [ **新增**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-174">Click **Add**, and then click **Add**.</span></span>

    ![通話佇列之使用者與群組設定的螢幕擷取畫面](../media/call-queue-users-groups-smb.png)

<span data-ttu-id="98fd5-176">您可以透過群組或團隊新增最多20個代理程式，以及最多200個代理程式。</span><span class="sxs-lookup"><span data-stu-id="98fd5-176">You can add up to 20 agents individually and up to 200 agents via groups or teams.</span></span>

> [!NOTE]
> <span data-ttu-id="98fd5-177">在小組中新增新的使用者時，最多可能需要八個小時的時間，才能讓初次通話到達。</span><span class="sxs-lookup"><span data-stu-id="98fd5-177">When new users are added to the team, it can take up to eight hours for their first call to arrive.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="98fd5-178">步驟 4-資源帳戶 ></span><span class="sxs-lookup"><span data-stu-id="98fd5-178">Step 4 - Resource accounts ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[<span data-ttu-id="98fd5-179">步驟 4 <br> 呼叫路由</span><span class="sxs-lookup"><span data-stu-id="98fd5-179">Step 4<br>Call routing</span></span>](#tab/call-routing)

<span data-ttu-id="98fd5-180">選擇您想要使用的通話路由方法。</span><span class="sxs-lookup"><span data-stu-id="98fd5-180">Choose the call routing method that you want to use.</span></span>

1. <span data-ttu-id="98fd5-181">將 [ **會議模式]** 設定為 [ **自動**]。</span><span class="sxs-lookup"><span data-stu-id="98fd5-181">Set **Conference mode** to **Auto**.</span></span>

2. <span data-ttu-id="98fd5-182">選擇您要使用的 **路由方法** 。</span><span class="sxs-lookup"><span data-stu-id="98fd5-182">Choose the **Routing method** you want to use.</span></span> <span data-ttu-id="98fd5-183">這會決定代理從佇列接收呼叫的順序。</span><span class="sxs-lookup"><span data-stu-id="98fd5-183">This determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="98fd5-184">我們建議 **串列路由** 或  **迴圈**。</span><span class="sxs-lookup"><span data-stu-id="98fd5-184">We recommend **Serial routing** or  **Round robin**.</span></span> <span data-ttu-id="98fd5-185">從這些選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="98fd5-185">Choose from these options:</span></span>

    - <span data-ttu-id="98fd5-186">[**助理路由**] 會同時響鈴佇列中的所有代理程式。</span><span class="sxs-lookup"><span data-stu-id="98fd5-186">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="98fd5-187">第一個呼叫代理程式接聽電話，即可取得通話。</span><span class="sxs-lookup"><span data-stu-id="98fd5-187">The first call agent to pick up the call gets the call.</span></span>

    - <span data-ttu-id="98fd5-188">**串列路由** 逐一響鈴所有呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="98fd5-188">**Serial routing** rings all call agents one by one.</span></span> <span data-ttu-id="98fd5-189">如果代理程式關閉或沒接聽來電，該通話會撥打下一個代理程式，並嘗試所有的代理程式，直到它被挑選或超時為止。</span><span class="sxs-lookup"><span data-stu-id="98fd5-189">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

    - <span data-ttu-id="98fd5-190">**迴圈法** 會平衡來電的路由，讓每個通話代理程式從佇列取得相同數量的呼叫。</span><span class="sxs-lookup"><span data-stu-id="98fd5-190">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="98fd5-191">這在入站銷售環境中可能是您想要的，以確保所有通話代理程式之間有同等的機會。</span><span class="sxs-lookup"><span data-stu-id="98fd5-191">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

    - <span data-ttu-id="98fd5-192">閒置時間最長的 **閒置** 路由，每個呼叫都是閒置時間最長的代理程式。</span><span class="sxs-lookup"><span data-stu-id="98fd5-192">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="98fd5-193">[目前狀態] 為「已離開超過10分鐘的代理程式] 不會包含在其中。 )  (</span><span class="sxs-lookup"><span data-stu-id="98fd5-193">(Agents whose presence state has been Away for more than 10 minutes are not included.)</span></span>

    ![[會議模式] 與 [路由方法] 設定的螢幕擷取畫面](../media/call-queue-conference-mode-routing-method.png)

3. <span data-ttu-id="98fd5-195">開啟 [目前 **狀態] 路由** 。</span><span class="sxs-lookup"><span data-stu-id="98fd5-195">Turn **Presence-based routing** on.</span></span> <span data-ttu-id="98fd5-196">此路由會呼叫目前狀態為 [ **可用**] 的代理程式。</span><span class="sxs-lookup"><span data-stu-id="98fd5-196">This routes calls to agents whose presence status is **Available**.</span></span>

4. <span data-ttu-id="98fd5-197">選擇您是否要允許代理退出通話。</span><span class="sxs-lookup"><span data-stu-id="98fd5-197">Choose if you want to allow agents to opt out of calls.</span></span>

5. <span data-ttu-id="98fd5-198">設定 **代理程式警示時間** ，以指定在佇列將呼叫重新導向至下一部代理程式之前，電話會響鈴的時間。</span><span class="sxs-lookup"><span data-stu-id="98fd5-198">Set an **Agent alert time** to specify how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

    ![[路由]、[選擇外移] 及 [提醒時間] 設定的螢幕擷取畫面](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="98fd5-200">步驟 5-呼叫溢出 ></span><span class="sxs-lookup"><span data-stu-id="98fd5-200">Step 5 - Call overflow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[<span data-ttu-id="98fd5-201">步驟 5 <br> 通話溢出</span><span class="sxs-lookup"><span data-stu-id="98fd5-201">Step 5<br>Call overflow</span></span>](#tab/call-overflow)

<span data-ttu-id="98fd5-202">選擇您想要如何處理超過佇列中最大值的通話。</span><span class="sxs-lookup"><span data-stu-id="98fd5-202">Choose how you want to handle calls that exceed the maximum in the queue.</span></span>

1. <span data-ttu-id="98fd5-203">設定 **佇列中的最大通話** 數。</span><span class="sxs-lookup"><span data-stu-id="98fd5-203">Set the **Maximum calls in the queue**.</span></span>

2. <span data-ttu-id="98fd5-204">選擇達到最大通話數時要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="98fd5-204">Choose what you want to do when the maximum number of calls is reached.</span></span> <span data-ttu-id="98fd5-205">您可以中斷通話或重新導向。</span><span class="sxs-lookup"><span data-stu-id="98fd5-205">You can disconnect the call or redirect it.</span></span> <span data-ttu-id="98fd5-206">我們建議您將來電重新導向至下列其中一個目的地：</span><span class="sxs-lookup"><span data-stu-id="98fd5-206">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="98fd5-207">**組織中的人員** -您組織中能夠接聽語音通話的人員</span><span class="sxs-lookup"><span data-stu-id="98fd5-207">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="98fd5-208">**語音 app** -自動語音應答或其他通話佇列。</span><span class="sxs-lookup"><span data-stu-id="98fd5-208">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="98fd5-209"> (選擇 [選擇此目的地時，與自動語音應答或通話佇列] 相關聯的資源帳戶。 ) </span><span class="sxs-lookup"><span data-stu-id="98fd5-209">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="98fd5-210">**外部電話號碼** -任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="98fd5-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="98fd5-211">使用此格式： + [國家/地區碼] [區域碼] [電話號碼]</span><span class="sxs-lookup"><span data-stu-id="98fd5-211">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="98fd5-212">**語音信箱** -您可以使用您所建立之小組的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="98fd5-212">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通話溢出設定的螢幕擷取畫面](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [<span data-ttu-id="98fd5-214">步驟 6-通話超時 ></span><span class="sxs-lookup"><span data-stu-id="98fd5-214">Step 6 - Call timeout ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[<span data-ttu-id="98fd5-215">步驟 6 <br> 通話超時</span><span class="sxs-lookup"><span data-stu-id="98fd5-215">Step 6<br>Call timeout</span></span>](#tab/call-timeout)

<span data-ttu-id="98fd5-216">選擇當通話在佇列中等待的時間太長時要發生的情況。</span><span class="sxs-lookup"><span data-stu-id="98fd5-216">Choose what you want to happen when calls have been waiting in the queue for too long.</span></span>

1. <span data-ttu-id="98fd5-217">設定 **通話超時：最長等待時間**。</span><span class="sxs-lookup"><span data-stu-id="98fd5-217">Set the **Call Timeout: maximum wait time**.</span></span>

2. <span data-ttu-id="98fd5-218">選擇來電超時時要執行的動作。您可以中斷通話或重新導向。</span><span class="sxs-lookup"><span data-stu-id="98fd5-218">Choose what you want to do when a call times out. You can disconnect the call or redirect it.</span></span> <span data-ttu-id="98fd5-219">我們建議您將來電重新導向至下列其中一個目的地：</span><span class="sxs-lookup"><span data-stu-id="98fd5-219">We recommend that you redirect the call to one of the following destinations:</span></span>
    - <span data-ttu-id="98fd5-220">**組織中的人員** -您組織中能夠接聽語音通話的人員</span><span class="sxs-lookup"><span data-stu-id="98fd5-220">**Person in the organization** - a person in your organization who is able to receive voice calls</span></span>
    - <span data-ttu-id="98fd5-221">**語音 app** -自動語音應答或其他通話佇列。</span><span class="sxs-lookup"><span data-stu-id="98fd5-221">**Voice app** - an auto attendant or another call queue.</span></span> <span data-ttu-id="98fd5-222"> (選擇 [選擇此目的地時，與自動語音應答或通話佇列] 相關聯的資源帳戶。 ) </span><span class="sxs-lookup"><span data-stu-id="98fd5-222">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
    - <span data-ttu-id="98fd5-223">**外部電話號碼** -任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="98fd5-223">**External phone number** - any phone number.</span></span> <span data-ttu-id="98fd5-224">使用此格式： + [國家/地區碼] [區域碼] [電話號碼]</span><span class="sxs-lookup"><span data-stu-id="98fd5-224">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="98fd5-225">**語音信箱** -您可以使用您所建立之小組的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="98fd5-225">**Voicemail** - you can use the voice mailbox of the team that you created.</span></span>

    ![通話超時設定的螢幕擷取畫面](../media/call-queue-timeout-handling.png)

3. <span data-ttu-id="98fd5-227">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="98fd5-227">Click **Save**.</span></span>

<span data-ttu-id="98fd5-228">這樣就完成了您的通話佇列設定。</span><span class="sxs-lookup"><span data-stu-id="98fd5-228">This completes the setup of your call queue.</span></span> <span data-ttu-id="98fd5-229">接下來，您可能會想要 [設定自動](create-a-phone-system-auto-attendant-smb.md)語音應答。</span><span class="sxs-lookup"><span data-stu-id="98fd5-229">Next, you may want to [set up an auto attendant](create-a-phone-system-auto-attendant-smb.md).</span></span>

---

