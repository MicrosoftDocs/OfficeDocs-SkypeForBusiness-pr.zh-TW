---
title: 為 Microsoft 團隊設定自動語音應答-小型企業教學課程
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
- Phone System
description: 瞭解如何為 Microsoft 365 商務語音設定及測試自動語音應答。
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909617"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="35565-103">設定自動語音應答-小型企業教學課程</span><span class="sxs-lookup"><span data-stu-id="35565-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="35565-104">自動語音應答讓其他人打電話給您的組織，並流覽功能表系統，以與正確的部門通話、呼叫佇列、人員或接線員。</span><span class="sxs-lookup"><span data-stu-id="35565-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="35565-105">您可以使用 Microsoft 團隊系統管理中心為貴組織建立自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="35565-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="35565-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="35565-106">Before you begin</span></span>

<span data-ttu-id="35565-107">取得您想要的自動語音應答所需的服務號碼（透過從貴組織外撥號直接撥號即可）。</span><span class="sxs-lookup"><span data-stu-id="35565-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="35565-108">這可能包括 [從另一個提供者轉移號碼](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [要求新的服務號碼](../getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="35565-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="35565-109">取得您打算建立之每個自動語音應答的 [電話系統-虛擬使用者授權](../teams-add-on-licensing/virtual-user.md) 。</span><span class="sxs-lookup"><span data-stu-id="35565-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="35565-110">這些授權是免費的，因此我們建議您先取得幾個額外的案例，以備日後決定變更您的設定。</span><span class="sxs-lookup"><span data-stu-id="35565-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="35565-111">如果您想讓自動語音應答傳送在假日上以不同方式呼叫，請在建立自動語音應答前， [建立您要使用的假日](../set-up-holidays-in-teams.md) 。</span><span class="sxs-lookup"><span data-stu-id="35565-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="35565-112">請依照下列步驟來設定您的自動語音應答</span><span class="sxs-lookup"><span data-stu-id="35565-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="35565-113">步驟 1 <br> 電話號碼</span><span class="sxs-lookup"><span data-stu-id="35565-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="35565-114">您建立的每個自動助理都需要有資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="35565-115">這與使用者帳戶類似，只是帳戶與自動語音應答或通話佇列無關，而不是寄件者。</span><span class="sxs-lookup"><span data-stu-id="35565-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="35565-116">在此步驟中，我們會建立帳戶，將它指派為 *Microsoft 365 電話系統-虛擬使用者* 授權，然後指派服務號碼。</span><span class="sxs-lookup"><span data-stu-id="35565-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="35565-117">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="35565-117">Create a resource account</span></span>

<span data-ttu-id="35565-118">您可以在 [團隊管理中心] 中建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="35565-119">在 [團隊管理中心] 中，展開 [ **整個組織的設定**]，然後按一下 [ **資源帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="35565-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="35565-120">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="35565-120">Click **Add**.</span></span>

3. <span data-ttu-id="35565-121">在 [**新增資源帳戶**] 窗格中，填寫 [**顯示名稱**]、[使用者名稱 **]，然後** 針對 **資源帳戶類型** 選擇 [**自動助理**]</span><span class="sxs-lookup"><span data-stu-id="35565-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![[新增資源帳戶] 使用者介面的螢幕擷取畫面](../media/resource-account-add.png)

4. <span data-ttu-id="35565-123">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="35565-123">Click **Save**.</span></span>

<span data-ttu-id="35565-124">新帳戶將會出現在帳戶清單中。</span><span class="sxs-lookup"><span data-stu-id="35565-124">The new account will appear in the list of accounts.</span></span>

![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="35565-126">指派授權</span><span class="sxs-lookup"><span data-stu-id="35565-126">Assign a license</span></span>

<span data-ttu-id="35565-127">您必須將 *Microsoft 365 電話系統-虛擬使用者* 授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="35565-128">在 Microsoft 365 系統管理中心，按一下您要指派授權的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="35565-129">在 [ **授權及應用程式** ] 索引標籤的 [ **授權**] 底下，選取 [ **Microsoft 365 電話系統-虛擬使用者**]。</span><span class="sxs-lookup"><span data-stu-id="35565-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="35565-130">按一下 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="35565-130">Click **Save changes**.</span></span>

    ![在 Microsoft 365 系統管理中心指派授權使用者介面的螢幕擷取畫面](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="35565-132">指派服務號碼</span><span class="sxs-lookup"><span data-stu-id="35565-132">Assign a service number</span></span>

<span data-ttu-id="35565-133">如果您需要電話號碼可達到這個自動助手，請將該號碼指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="35565-134">在團隊系統管理中心的 [ **資源帳戶** ] 頁面上，選取您要指派服務號碼的資源帳戶，然後按一下 [ **指派/取消指派**]。</span><span class="sxs-lookup"><span data-stu-id="35565-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="35565-135">在 [ **電話號碼類型** ] 下拉式清單中，選擇您要使用的號碼類型。</span><span class="sxs-lookup"><span data-stu-id="35565-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="35565-136">在 [ **已指派的電話號碼** ] 方塊中，搜尋您要使用的號碼，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="35565-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![指派服務號碼使用者介面的螢幕擷取畫面](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="35565-138">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="35565-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35565-139">步驟 2-自動助理一般資訊 ></span><span class="sxs-lookup"><span data-stu-id="35565-139">Step 2 - Auto attendant general info ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="35565-140">步驟 2 <br> 助理一般資訊</span><span class="sxs-lookup"><span data-stu-id="35565-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="35565-141">設定自動語音應答</span><span class="sxs-lookup"><span data-stu-id="35565-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="35565-142">在 [團隊管理中心] 中，展開 [語音]，按一下 [**自動\*\*\*\*語音**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="35565-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="35565-143">在頂端方塊中輸入自動語音應答的名稱。</span><span class="sxs-lookup"><span data-stu-id="35565-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="35565-144">如果您想要指派運算子，請指定呼叫操作員的目的地。</span><span class="sxs-lookup"><span data-stu-id="35565-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="35565-145">這是選擇性 (但建議) 。</span><span class="sxs-lookup"><span data-stu-id="35565-145">This is optional (but recommended).</span></span> <span data-ttu-id="35565-146">您可以設定 [ **運算子** ] 選項，讓呼叫者中斷功能表並向指定的人朗讀。</span><span class="sxs-lookup"><span data-stu-id="35565-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="35565-147">指定此自動語音應答的時區。</span><span class="sxs-lookup"><span data-stu-id="35565-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="35565-148">如果您在下班後建立單獨的通話流程，則會使用時區來計算上班時間。</span><span class="sxs-lookup"><span data-stu-id="35565-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="35565-149">指定此自動語音應答的語言。</span><span class="sxs-lookup"><span data-stu-id="35565-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="35565-150">這是將用於系統產生的語音提示的語言。</span><span class="sxs-lookup"><span data-stu-id="35565-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="35565-151">選擇是否要啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="35565-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="35565-152">啟用時，每個功能表選項的名稱都會變成語音辨識關鍵字。</span><span class="sxs-lookup"><span data-stu-id="35565-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="35565-153">例如，來電者可以說「一」，選取對應至鍵1的功能表選項，或者說「銷售」來選取名為「銷售」的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="35565-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![[名稱]、[操作員]、[時區]、[語言] 和 [語音輸入] 的自動助理設定的螢幕擷取畫面](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="35565-155">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="35565-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35565-156">步驟 3-通話流程 ></span><span class="sxs-lookup"><span data-stu-id="35565-156">Step 3 - Call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="35565-157">步驟 3 <br> 通話流程</span><span class="sxs-lookup"><span data-stu-id="35565-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="35565-158">選擇您的通話流程選項</span><span class="sxs-lookup"><span data-stu-id="35565-158">Choose your call flow options</span></span>

1. <span data-ttu-id="35565-159">選擇當自動語音接聽來電時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="35565-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="35565-160">如果您選取 [ **播放音訊** 檔]，您可以使用 [ **上傳** 檔案] 按鈕，上傳儲存為音訊的錄製問候語訊息。WAV，。[MP3] 或。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="35565-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="35565-161">錄製不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="35565-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="35565-162">如果您選取 [ **輸入問候語** ]，系統將會朗讀您在其中輸入文字的文字， (最多1000個字元) 當自動語音接聽來電時。</span><span class="sxs-lookup"><span data-stu-id="35565-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![問候訊息設定的螢幕擷取畫面](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="35565-164">選擇您要路由通話的方式。</span><span class="sxs-lookup"><span data-stu-id="35565-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="35565-165">如果您選取 **[中斷連線]**，自動語音應答就會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="35565-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="35565-166">如果您選取 [重新 **導向通話**]，您可以選擇其中一個呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="35565-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="35565-167">如果您選取 [ **播放] 功能表選項**，您可以選擇 **播放音訊** 檔案或 **輸入問候語** ，然後選擇 [功能表選項] 和 [目錄搜尋]。</span><span class="sxs-lookup"><span data-stu-id="35565-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![呼叫路由設定的螢幕擷取畫面](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="35565-169">如果您希望呼叫者使用撥號鍵來流覽，請在 [ **設定功能表選項**] 底下，選擇要在來電者按下撥號鍵時所發生的情況。</span><span class="sxs-lookup"><span data-stu-id="35565-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="35565-170"> (如果您是將此自動語音應答建立為公司目錄，請將 [撥號鍵選項] 留白。 ) </span><span class="sxs-lookup"><span data-stu-id="35565-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="35565-171">您可以將任何撥號鍵設定為下列目的地：</span><span class="sxs-lookup"><span data-stu-id="35565-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="35565-172">**組織中的人員** -您組織中能夠接聽語音通話的人員。</span><span class="sxs-lookup"><span data-stu-id="35565-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="35565-173">**語音 app** -另一個自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="35565-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="35565-174">**外部電話號碼** -任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="35565-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="35565-175">使用此格式： + [國家/地區碼] [區域碼] [電話號碼]</span><span class="sxs-lookup"><span data-stu-id="35565-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="35565-176">**語音信箱** -與您指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="35565-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="35565-177">**Operator** -為自動語音應答定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="35565-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="35565-178">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="35565-178">Defining an operator is optional.</span></span> <span data-ttu-id="35565-179">操作員可以定義為此清單中的任何其他目的地。</span><span class="sxs-lookup"><span data-stu-id="35565-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="35565-180">我們建議您設定0鍵至運算子。</span><span class="sxs-lookup"><span data-stu-id="35565-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="35565-181">針對每個功能表選項，指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="35565-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="35565-182">**撥號鍵** -電話鍵臺上的按鍵可存取此選項。</span><span class="sxs-lookup"><span data-stu-id="35565-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="35565-183">**Voice 命令** -定義來電者可提供的語音命令來存取此選項（如果已啟用語音輸入）。</span><span class="sxs-lookup"><span data-stu-id="35565-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="35565-184">它可以包含多個字詞，例如「客戶服務」或「作業與不限」。</span><span class="sxs-lookup"><span data-stu-id="35565-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="35565-185">[**重定向至**]-來電者選擇此選項時，您想要撥打電話的位置。</span><span class="sxs-lookup"><span data-stu-id="35565-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="35565-186">如果您要重新導向自動語音應答或通話佇列，請選擇與其關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![[撥號鍵] 選項的螢幕擷取畫面](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="35565-188">如果您想要將這個自動語音應答做為公司目錄，請在 [ **目錄搜尋**] 底下，選取 [ **依名稱撥號**]。</span><span class="sxs-lookup"><span data-stu-id="35565-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="35565-189">當您啟用此選項時，呼叫者可以說出使用者的名稱，或在電話鍵臺上輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="35565-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="35565-190">任何具備電話系統授權的線上使用者都是符合資格的使用者，而且可以使用 [按名稱撥號] 找到。</span><span class="sxs-lookup"><span data-stu-id="35565-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="35565-191"> (您可以選擇 [透過 **延伸撥號**]，但是必須在 Azure Active Directory 中設定延伸。 ) </span><span class="sxs-lookup"><span data-stu-id="35565-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="35565-192">選取 **目錄搜尋** 選項之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="35565-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35565-193">步驟 4-下班後通話流程 ></span><span class="sxs-lookup"><span data-stu-id="35565-193">Step 4 - After hours call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="35565-194">後4個工作的步驟 4 <br></span><span class="sxs-lookup"><span data-stu-id="35565-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="35565-195">每個自動語音應答的上班時間都可以設定。</span><span class="sxs-lookup"><span data-stu-id="35565-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="35565-196">如果未設定上班時間，則當天的所有日期和所有的時間都被視為「上班時間」，因為預設會設定24/7 排程。</span><span class="sxs-lookup"><span data-stu-id="35565-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="35565-197">您可以在一天中使用時段來設定上班時間，而且所有未設為「上班時間」的小時都會被視為時間。</span><span class="sxs-lookup"><span data-stu-id="35565-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="35565-198">您可以設定不同的來電處理選項和問候語（在下班後）。</span><span class="sxs-lookup"><span data-stu-id="35565-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="35565-199">視您設定自動語音應答及呼叫佇列的方式而定，您可能只需要使用直接電話號碼，指定自動語音接聽的時間呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="35565-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="35565-200">如果您想要在下班後的呼叫者單獨撥打通話路線，請指定每天的上班時間。</span><span class="sxs-lookup"><span data-stu-id="35565-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="35565-201">按一下 [ **新增時間** ]，為指定日期指定多組小時數（例如指定午餐時間）。</span><span class="sxs-lookup"><span data-stu-id="35565-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![[時間] 和 [時間] 設定的螢幕擷取畫面](../media/auto-attendant-business-hours.png)

<span data-ttu-id="35565-203">指定上班時間之後，請選擇您的通話路線選項，以供下班時間使用。</span><span class="sxs-lookup"><span data-stu-id="35565-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="35565-204">對於您在 **步驟3通話流程** 中指定的商務時間呼叫路由，您可以使用相同的選項。</span><span class="sxs-lookup"><span data-stu-id="35565-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="35565-205">完成後，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="35565-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35565-206">步驟 5-假日通話流程 ></span><span class="sxs-lookup"><span data-stu-id="35565-206">Step 5 - Holiday call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="35565-207">步驟 5 <br> 假日</span><span class="sxs-lookup"><span data-stu-id="35565-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="35565-208">您可以在假日上以不同于其他天數的方式傳送自動語音應答的來電。</span><span class="sxs-lookup"><span data-stu-id="35565-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="35565-209"> (如果您不想要使用不同的假日通話流程，您可以略過此步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="35565-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="35565-210">您的自動語音應答可以針對您設定的每一個假日進行通話流程。</span><span class="sxs-lookup"><span data-stu-id="35565-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="35565-211">您最多可以將20個排定的假日新增至每個自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="35565-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="35565-212">在 [假日通話設定] 頁面上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="35565-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="35565-213">輸入此假日設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="35565-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="35565-214">從 [ **假日** ] 下拉式清單中，選擇您要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="35565-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="35565-215">選擇您要使用的問候類型。</span><span class="sxs-lookup"><span data-stu-id="35565-215">Choose the type of greeting that you want to use.</span></span>

    ![假日和假日問候語設定的螢幕擷取畫面](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="35565-217">選擇您是否要 **中斷** 連線，或重新 **導向** 通話。</span><span class="sxs-lookup"><span data-stu-id="35565-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="35565-218">如果您選擇 [重新導向]，請選擇通話的呼叫傳送目的地。</span><span class="sxs-lookup"><span data-stu-id="35565-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![假日通話動作設定的螢幕擷取畫面](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="35565-220">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="35565-220">Click **Save**.</span></span>

<span data-ttu-id="35565-221">視需要針對每個額外的假日重複程式。</span><span class="sxs-lookup"><span data-stu-id="35565-221">Repeat the procedure as needed for each additional holiday.</span></span>

![[假日] 設定的螢幕擷取畫面，其中列出假日](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="35565-223">當您新增完所有假日之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="35565-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35565-224">步驟 6-選擇目錄中的人員 ></span><span class="sxs-lookup"><span data-stu-id="35565-224">Step 6 - Choose who's in the directory ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="35565-225">步驟 6 <br> 目錄成員</span><span class="sxs-lookup"><span data-stu-id="35565-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="35565-226">*撥號作用* 中定義來電者使用按名稱撥號或撥號延伸時，在目錄中可使用的使用者。</span><span class="sxs-lookup"><span data-stu-id="35565-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="35565-227">**所有線上使用者** 的預設值都是貴組織中所有以電話系統授權為線上使用者的使用者。</span><span class="sxs-lookup"><span data-stu-id="35565-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="35565-228">您可以選取 [**包括**] 或 [**排除**] 底下的 [**自訂使用者組**]，然後選擇一或多個 Microsoft 365 群組、通訊群組清單或安全性群組，以包含或排除特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="35565-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="35565-229">例如，您可能想要將貴組織中的主管從撥號目錄中排除。</span><span class="sxs-lookup"><span data-stu-id="35565-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="35565-230"> (如果使用者同時位於兩個清單中，則會將其從目錄中排除。 ) </span><span class="sxs-lookup"><span data-stu-id="35565-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![[撥號作用中包括] 和 [排除] 選項的螢幕擷取畫面](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="35565-232">最多可能需要36小時，才能讓新使用者將其名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="35565-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="35565-233">完成設定撥號作用中的範圍之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="35565-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35565-234">步驟 7-指派資源帳戶 ></span><span class="sxs-lookup"><span data-stu-id="35565-234">Step 7 - Assign a resource account ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="35565-235">步驟 7 <br> 資源帳戶</span><span class="sxs-lookup"><span data-stu-id="35565-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="35565-236">所有自動語音應答都必須有關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="35565-237">第一層自動語音應答將至少需要一個有相關服務號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="35565-238">如果您想要的話，您可以將多個資源帳戶指派給自動語音應答，每個都有不同的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="35565-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="35565-239">新增資源帳戶</span><span class="sxs-lookup"><span data-stu-id="35565-239">To add a resource account</span></span>

1. <span data-ttu-id="35565-240">按一下 [ **新增帳戶** ]，然後搜尋您要新增的帳戶。</span><span class="sxs-lookup"><span data-stu-id="35565-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="35565-241">按一下 [ **新增**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="35565-241">Click **Add**, and then click **Add**.</span></span>

    ![資源帳戶 [新增帳戶] 面板的螢幕擷取畫面](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="35565-243">完成新增服務帳戶後，請按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="35565-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![[資源帳戶] 清單的螢幕擷取畫面，其中顯示已指派服務號碼的資源帳戶](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="35565-245">這會完成自動助理設定。</span><span class="sxs-lookup"><span data-stu-id="35565-245">This completes the auto attendant configuration.</span></span>

---


