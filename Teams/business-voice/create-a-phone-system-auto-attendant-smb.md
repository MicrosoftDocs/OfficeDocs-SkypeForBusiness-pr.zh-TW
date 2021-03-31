---
title: 設定 Microsoft Teams 的自動總機 - 小型企業教學課程
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
- Phone System
description: 瞭解如何設定和測試 Microsoft 365 商務語音的自動語音機。
ms.openlocfilehash: fef89971ad99dff15332905d6f9b98a343af6ffd
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439718"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="f29bf-103">設定自動助理 - 小型企業教學課程</span><span class="sxs-lookup"><span data-stu-id="f29bf-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="f29bf-104">自動電話機可讓人打電話給您的組織，並流覽功能表系統，與正確的部門、通話佇列、人員或接線生通話。</span><span class="sxs-lookup"><span data-stu-id="f29bf-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="f29bf-105">您可以使用 Microsoft Teams 系統管理中心為貴組織建立自動助理。</span><span class="sxs-lookup"><span data-stu-id="f29bf-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="f29bf-106">開始之前</span><span class="sxs-lookup"><span data-stu-id="f29bf-106">Before you begin</span></span>

<span data-ttu-id="f29bf-107">從組織外部直接撥號，取得自動總機所需的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="f29bf-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="f29bf-108">這可能包括 [從另一個提供者移轉號碼](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [要求新的服務號碼](../getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="f29bf-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="f29bf-109">取得 [電話系統 - 針對](../teams-add-on-licensing/virtual-user.md) 您計畫建立的每個自動話務員取得虛擬使用者授權。</span><span class="sxs-lookup"><span data-stu-id="f29bf-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="f29bf-110">這些授權是免費的，因此我們建議您額外取得一些授權，以防您決定日後變更您的設定。</span><span class="sxs-lookup"><span data-stu-id="f29bf-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="f29bf-111">如果您想要在假日以不同方式讓自動電話機路由通話，請建立您想要[](../set-up-holidays-in-teams.md)使用的假日，然後再建立自動總機。</span><span class="sxs-lookup"><span data-stu-id="f29bf-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="f29bf-112">請遵循下列步驟來設定自動話務員</span><span class="sxs-lookup"><span data-stu-id="f29bf-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="f29bf-113">步驟 1 <br> 電話號碼</span><span class="sxs-lookup"><span data-stu-id="f29bf-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="f29bf-114">您建立的每個自動助理都需要資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="f29bf-115">這類似于使用者帳戶，除了該帳戶與自動通話或通話佇列相關聯，而不是與人員相關聯。</span><span class="sxs-lookup"><span data-stu-id="f29bf-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="f29bf-116">在此步驟中，我們將建立帳戶、指派 *Microsoft 365 電話系統 - 虛擬使用者* 授權，然後指派服務號碼。</span><span class="sxs-lookup"><span data-stu-id="f29bf-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="f29bf-117">建立資源帳戶</span><span class="sxs-lookup"><span data-stu-id="f29bf-117">Create a resource account</span></span>

<span data-ttu-id="f29bf-118">您可以在 Teams 系統管理中心建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="f29bf-119">在 Teams 系統管理中心，展開 **整個組織設定**，然後按一下 [ **資源帳戶**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="f29bf-120">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-120">Click **Add**.</span></span>

3. <span data-ttu-id="f29bf-121">在新增 **資源帳戶窗格中**，填寫 **顯示名稱**、**使用者名稱**，然後選擇資源帳戶類型的 **自動助理**</span><span class="sxs-lookup"><span data-stu-id="f29bf-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![新增資源帳戶使用者介面的螢幕擷取畫面](../media/resource-account-add.png)

4. <span data-ttu-id="f29bf-123">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="f29bf-123">Click **Save**.</span></span>

<span data-ttu-id="f29bf-124">新帳戶會顯示在帳戶清單中。</span><span class="sxs-lookup"><span data-stu-id="f29bf-124">The new account will appear in the list of accounts.</span></span>

![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="f29bf-126">指派授權</span><span class="sxs-lookup"><span data-stu-id="f29bf-126">Assign a license</span></span>

<span data-ttu-id="f29bf-127">您必須將 *Microsoft 365 Phone System - 虛擬使用者* 授權指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="f29bf-128">在 Microsoft 365 系統管理中心，按一下要指派授權的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="f29bf-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span><span class="sxs-lookup"><span data-stu-id="f29bf-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="f29bf-130">按一下 **[儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-130">Click **Save changes**.</span></span>

    ![Microsoft 365 系統管理中心指派授權使用者介面的螢幕擷取畫面](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="f29bf-132">指派服務號碼</span><span class="sxs-lookup"><span data-stu-id="f29bf-132">Assign a service number</span></span>

<span data-ttu-id="f29bf-133">如果您需要讓電話號碼可以聯繫到這個自動助理，請指派該號碼給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="f29bf-134">在 Teams 系統管理中心中的 [資源 **帳戶** > 頁面上，選取要指派服務號碼的資源帳戶，然後按一下 [ **指派/取消指派**> 。</span><span class="sxs-lookup"><span data-stu-id="f29bf-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="f29bf-135">在 **電話號碼類型** 下拉式下拉清單中，選擇您想要使用的號碼類型。</span><span class="sxs-lookup"><span data-stu-id="f29bf-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="f29bf-136">在 **[已指派的電話號碼** > 方塊中，搜尋您想要使用的號碼，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![指派服務編號使用者介面的螢幕擷取畫面](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="f29bf-138">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="f29bf-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f29bf-139">步驟 2 - 自動總></span><span class="sxs-lookup"><span data-stu-id="f29bf-139">Step 2 - Auto attendant general info ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="f29bf-140">步驟 2 <br> Attendant 一般資訊</span><span class="sxs-lookup"><span data-stu-id="f29bf-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="f29bf-141">設定自動話務員</span><span class="sxs-lookup"><span data-stu-id="f29bf-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="f29bf-142">在 Teams 系統管理中心，展開 **[語音，** 按一下 **[自動語音留言**，然後按一下 **[新增**> 。</span><span class="sxs-lookup"><span data-stu-id="f29bf-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="f29bf-143">在頂端方塊中輸入自動助理的名稱。</span><span class="sxs-lookup"><span data-stu-id="f29bf-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="f29bf-144">如果您想要指定運算子，請指定撥打給接線員的目的地。</span><span class="sxs-lookup"><span data-stu-id="f29bf-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="f29bf-145">這是選擇性選項 (，但建議使用) 。</span><span class="sxs-lookup"><span data-stu-id="f29bf-145">This is optional (but recommended).</span></span> <span data-ttu-id="f29bf-146">您可以將 **運算子選項設定** 為允許來電者中斷功能表，並和指定的人員通話。</span><span class="sxs-lookup"><span data-stu-id="f29bf-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="f29bf-147">指定此自動助理的時區。</span><span class="sxs-lookup"><span data-stu-id="f29bf-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="f29bf-148">如果您為小時後建立個別的通話流程，則時區會用來計算上班時間。</span><span class="sxs-lookup"><span data-stu-id="f29bf-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="f29bf-149">指定此自動翻譯的語言。</span><span class="sxs-lookup"><span data-stu-id="f29bf-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="f29bf-150">這是用於系統產生的語音提示的語言。</span><span class="sxs-lookup"><span data-stu-id="f29bf-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="f29bf-151">選擇是否要啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="f29bf-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="f29bf-152">啟用時，每個功能表選項的名稱會變成語音辨識關鍵字。</span><span class="sxs-lookup"><span data-stu-id="f29bf-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="f29bf-153">例如，來電者可以說「One」，以選取對應到按鍵 1 的功能表選項，或說「銷售」以選取名為「銷售」的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="f29bf-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![名稱、運算子、時區、語言和語音輸入的自動語音留言設定螢幕擷取畫面](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="f29bf-155">按一下 **[下一步**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f29bf-156">步驟 3 - 通話流程></span><span class="sxs-lookup"><span data-stu-id="f29bf-156">Step 3 - Call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="f29bf-157">步驟 3 <br> 通話流程</span><span class="sxs-lookup"><span data-stu-id="f29bf-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="f29bf-158">選擇您的通話流程選項</span><span class="sxs-lookup"><span data-stu-id="f29bf-158">Choose your call flow options</span></span>

1. <span data-ttu-id="f29bf-159">選擇當自動回應接聽來電時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="f29bf-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="f29bf-160">如果您選取 **播放音訊檔案，** 您可以使用上傳檔案按鈕來上傳儲存為音訊的錄製問候語訊息。Wav。MP3 或 。WMA 格式。</span><span class="sxs-lookup"><span data-stu-id="f29bf-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="f29bf-161">錄製內容不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="f29bf-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="f29bf-162">如果您選取輸入問候語 **訊息** ，當自動回應接聽來電時，系統會朗讀您輸入 (最多 1000 個字元) 文字。</span><span class="sxs-lookup"><span data-stu-id="f29bf-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![問候語訊息設定螢幕擷取畫面](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="f29bf-164">選擇通話的路由方式。</span><span class="sxs-lookup"><span data-stu-id="f29bf-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="f29bf-165">如果您選取中斷 **連接**，自動電話機會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="f29bf-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="f29bf-166">如果您選取 **重新導向通話**，您可以選擇其中一個呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="f29bf-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="f29bf-167">如果您選取 **了播放功能表選項**，您可以選擇播放音訊檔案或輸入問候語訊息，然後選擇功能表選項和目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f29bf-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![通話路由設定螢幕擷取畫面](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="f29bf-169">如果您希望來電者使用撥號鍵流覽，然後在設定功能表選項下，選擇當來電者按撥號鍵時要發生的專案。</span><span class="sxs-lookup"><span data-stu-id="f29bf-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="f29bf-170"> (如果您要將這個自動助理建立為公司目錄，請保留撥號鍵選項空白。) </span><span class="sxs-lookup"><span data-stu-id="f29bf-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="f29bf-171">您可以將任何撥號鍵設定為下列目的地：</span><span class="sxs-lookup"><span data-stu-id="f29bf-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="f29bf-172">**組織中能夠接聽** 語音通話的人。</span><span class="sxs-lookup"><span data-stu-id="f29bf-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="f29bf-173">**語音應用程式** - 另一個自動語音留言機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="f29bf-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="f29bf-174">**外部電話號碼** - 任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f29bf-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="f29bf-175">使用此格式：+[國碼][區碼][電話號碼]</span><span class="sxs-lookup"><span data-stu-id="f29bf-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="f29bf-176">**語音** 信箱 - 與您指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="f29bf-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="f29bf-177">**運算子** - 為自動話務員定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="f29bf-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="f29bf-178">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="f29bf-178">Defining an operator is optional.</span></span> <span data-ttu-id="f29bf-179">運算子可定義為此清單的其他目的地。</span><span class="sxs-lookup"><span data-stu-id="f29bf-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="f29bf-180">我們建議您將 0 鍵設定為運算子。</span><span class="sxs-lookup"><span data-stu-id="f29bf-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="f29bf-181">針對每個功能表選項，指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="f29bf-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="f29bf-182">**撥號鍵** - 電話鍵臺上的按鍵，以存取此選項。</span><span class="sxs-lookup"><span data-stu-id="f29bf-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="f29bf-183">**Voice 命令** - 定義來電者可給予存取此選項的語音命令 ，如果已啟用語音輸入。</span><span class="sxs-lookup"><span data-stu-id="f29bf-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="f29bf-184">它可以包含多個字詞，例如「客戶服務」或「營運與理由」。</span><span class="sxs-lookup"><span data-stu-id="f29bf-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="f29bf-185">**重新導向** 至 -當來電者選擇此選項時，您希望通話前往的地方。</span><span class="sxs-lookup"><span data-stu-id="f29bf-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="f29bf-186">如果您要重新導向到自動電話機或通話佇列，請選擇與其相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![撥號鍵選項的螢幕擷取畫面](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="f29bf-188">如果您想要使用此自動總機做為公司目錄，請在目錄搜尋 **下，選取\*\*\*\*按名稱撥號**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="f29bf-189">當您啟用此選項時，來電者可以說出使用者的名稱，或在電話鍵臺上輸入。</span><span class="sxs-lookup"><span data-stu-id="f29bf-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="f29bf-190">任何擁有電話系統授權的線上使用者都是合格的使用者，而且可以使用名稱撥號。</span><span class="sxs-lookup"><span data-stu-id="f29bf-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="f29bf-191"> (**您可以選擇分機撥號**，不過擴充功能必須在 Azure Active Directory.) </span><span class="sxs-lookup"><span data-stu-id="f29bf-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="f29bf-192">選取目錄搜尋 **選項之後，** 請按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f29bf-193">步驟 4 - 數小時後通話流程></span><span class="sxs-lookup"><span data-stu-id="f29bf-193">Step 4 - After hours call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="f29bf-194">步驟 4 <br> 小時之後</span><span class="sxs-lookup"><span data-stu-id="f29bf-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="f29bf-195">您可以針對每個自動話務員設定上班時間。</span><span class="sxs-lookup"><span data-stu-id="f29bf-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="f29bf-196">如果未設定上班時間，則一天中所有的天數和所有時數會視為上班時間，因為預設會設定 24/7 排程。</span><span class="sxs-lookup"><span data-stu-id="f29bf-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="f29bf-197">工作時間可以設定為一天中的休息時間，所有未設定為上班時間的時數會視為工作時間之後。</span><span class="sxs-lookup"><span data-stu-id="f29bf-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="f29bf-198">您可以為工作時間設定不同的來電處理選項和問候語。</span><span class="sxs-lookup"><span data-stu-id="f29bf-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="f29bf-199">根據您如何配置自動電話機和通話佇列，您可能只需要為具有直接電話號碼的自動電話機指定後通話路由。</span><span class="sxs-lookup"><span data-stu-id="f29bf-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="f29bf-200">如果您想要為非工作時間的來電者個別進行通話路由，請為每天指定您的上班時間。</span><span class="sxs-lookup"><span data-stu-id="f29bf-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="f29bf-201">例如 **，按一下 [新增時間** 以指定指定一天的陣列時數，以指定午餐休息時間。</span><span class="sxs-lookup"><span data-stu-id="f29bf-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![日與時數設定後小時數的螢幕擷取畫面](../media/auto-attendant-business-hours.png)

<span data-ttu-id="f29bf-203">指定上班時間之後，請選擇您的通話路由選項，以在數小時後進行。</span><span class="sxs-lookup"><span data-stu-id="f29bf-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="f29bf-204">在步驟 **3**- 通話流程中指定的上班時間通話路由，也提供相同的選項。</span><span class="sxs-lookup"><span data-stu-id="f29bf-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="f29bf-205">完成後 **，** 請按一下 [下一步。</span><span class="sxs-lookup"><span data-stu-id="f29bf-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f29bf-206">步驟 5 - 假日通話流程></span><span class="sxs-lookup"><span data-stu-id="f29bf-206">Step 5 - Holiday call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="f29bf-207">步驟 5 <br> 假日</span><span class="sxs-lookup"><span data-stu-id="f29bf-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="f29bf-208">您可以讓撥打到自動電話機的通話在假日路由方式與其他日期不同。</span><span class="sxs-lookup"><span data-stu-id="f29bf-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="f29bf-209"> (如果您不想為假日使用不同的通話流程，您可以略過此步驟。) </span><span class="sxs-lookup"><span data-stu-id="f29bf-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="f29bf-210">您的自動電話機可以針對您設定的每個假日設定通話流程。</span><span class="sxs-lookup"><span data-stu-id="f29bf-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="f29bf-211">您最多可以將 20 個排定的假日加到每個自動乘務員。</span><span class="sxs-lookup"><span data-stu-id="f29bf-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="f29bf-212">在 [假日通話設定」 頁面上，按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="f29bf-213">輸入此假日設定的名稱。</span><span class="sxs-lookup"><span data-stu-id="f29bf-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="f29bf-214">從假日 **下** 拉下拉，選擇您想要使用的假日。</span><span class="sxs-lookup"><span data-stu-id="f29bf-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="f29bf-215">選擇您想要使用的問候語類型。</span><span class="sxs-lookup"><span data-stu-id="f29bf-215">Choose the type of greeting that you want to use.</span></span>

    ![假日和假日問候語設定螢幕擷取畫面](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="f29bf-217">選擇是否要中斷 **連接或\*\*\*\*重新導向** 通話。</span><span class="sxs-lookup"><span data-stu-id="f29bf-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="f29bf-218">如果您選擇重新導向，請選擇通話的呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="f29bf-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![假日通話動作設定螢幕擷取畫面](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="f29bf-220">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="f29bf-220">Click **Save**.</span></span>

<span data-ttu-id="f29bf-221">針對每一個額外的假日，根據需要重複此程式。</span><span class="sxs-lookup"><span data-stu-id="f29bf-221">Repeat the procedure as needed for each additional holiday.</span></span>

![列出假日的假日設定螢幕擷取畫面](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="f29bf-223">當您新增所有假日後，請按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f29bf-224">步驟 6 - 選擇目錄中的></span><span class="sxs-lookup"><span data-stu-id="f29bf-224">Step 6 - Choose who's in the directory ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="f29bf-225">步驟 6 <br> 目錄成員</span><span class="sxs-lookup"><span data-stu-id="f29bf-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="f29bf-226">撥號 *範圍* 會定義當來電者使用撥號名稱或撥號分機時，哪些使用者可在目錄中使用。</span><span class="sxs-lookup"><span data-stu-id="f29bf-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="f29bf-227">所有線上 **使用者的預設值** 包含貴組織中具有電話系統授權之線上使用者的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="f29bf-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="f29bf-228">您可以選取包含或排除下的自訂使用者群組，並選擇一或多個Microsoft 365 群組、通訊群組清單或安全性群組，以包含或排除特定使用者。 </span><span class="sxs-lookup"><span data-stu-id="f29bf-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="f29bf-229">例如，您可能會想要將貴組織的主管排除在撥號目錄中。</span><span class="sxs-lookup"><span data-stu-id="f29bf-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="f29bf-230"> (如果使用者同時位於這兩個清單中，就會被排除在目錄中。) </span><span class="sxs-lookup"><span data-stu-id="f29bf-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![撥號範圍包含及排除選項的螢幕擷取畫面](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="f29bf-232">新使用者最多可能需要 36 小時，才能將名稱列在目錄中。</span><span class="sxs-lookup"><span data-stu-id="f29bf-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="f29bf-233">設定好撥號範圍後，請按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f29bf-234">步驟 7 - 指派資源帳戶></span><span class="sxs-lookup"><span data-stu-id="f29bf-234">Step 7 - Assign a resource account ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="f29bf-235">步驟 7 <br> 資源帳戶</span><span class="sxs-lookup"><span data-stu-id="f29bf-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="f29bf-236">所有自動話務員都必須有相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="f29bf-237">第一層自動總機至少需要一個具有關聯服務號碼的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="f29bf-238">您可以根據需要，將多個資源帳戶指派給自動助理，每個帳戶都有個別的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="f29bf-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="f29bf-239">新增資源帳戶</span><span class="sxs-lookup"><span data-stu-id="f29bf-239">To add a resource account</span></span>

1. <span data-ttu-id="f29bf-240">按一下 **[新增帳戶** 並搜尋您想要新增的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f29bf-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="f29bf-241">按一下 **[新增**，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-241">Click **Add**, and then click **Add**.</span></span>

    ![資源帳戶新增帳戶面板的螢幕擷取畫面](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="f29bf-243">當您完成新增服務帳戶後，請按一下 [ **提交>**。</span><span class="sxs-lookup"><span data-stu-id="f29bf-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![顯示資源帳戶與已指派服務編號的資源帳戶清單螢幕擷取畫面](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="f29bf-245">這會完成自動總機配置。</span><span class="sxs-lookup"><span data-stu-id="f29bf-245">This completes the auto attendant configuration.</span></span>

---


