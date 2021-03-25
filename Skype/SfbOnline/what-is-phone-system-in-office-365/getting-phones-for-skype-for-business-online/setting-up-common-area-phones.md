---
title: 設定公用區域電話
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 瞭解部署步驟以取得正確的固件、如果需要更新、指派授權，以及設定一般地區電話的設定。
ms.openlocfilehash: 16490c10418928f875d4513c509f17e09ac4359d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106429"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="08de0-103">設定公共區域電話</span><span class="sxs-lookup"><span data-stu-id="08de0-103">Set up common area phones</span></span>
<span data-ttu-id="08de0-104">在 CAP (中) 一般會放置在大廳等區域，或是可供許多人使用的另一個區域中。</span><span class="sxs-lookup"><span data-stu-id="08de0-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="08de0-105">例如，接收區電話、門電話或會議室電話、CAP 會設定為裝置，而不是使用者，並自動登入網路。</span><span class="sxs-lookup"><span data-stu-id="08de0-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="08de0-106">在下列步驟中，我們會協助您設定具有通話方案的電話系統帳戶，以便為貴組織部署這類電話。</span><span class="sxs-lookup"><span data-stu-id="08de0-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="08de0-107">一般地區電話的先決條件</span><span class="sxs-lookup"><span data-stu-id="08de0-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="08de0-108">您要做的第一件事是確認您擁有下列專案：</span><span class="sxs-lookup"><span data-stu-id="08de0-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="08de0-109">購買公用地區電話授權和通話方案。</span><span class="sxs-lookup"><span data-stu-id="08de0-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="08de0-110">搜尋及購買核准的電話 (在這裡[查看清單) 。](deploying-skype-for-business-online-phones.md)</span><span class="sxs-lookup"><span data-stu-id="08de0-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="08de0-111">更新您手機上的 (請參閱本主題[中的支援) 。](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="08de0-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="08de0-112">您可以執行以下方法檢查手機上的固件：</span><span class="sxs-lookup"><span data-stu-id="08de0-112">You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="08de0-113">**Polycom VVX 電話**：**前往設定**  >  **狀態**  >  **平臺**  >  **應用程式**  >  **主**。</span><span class="sxs-lookup"><span data-stu-id="08de0-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="08de0-114">**Yealink 手機\*\*\*\*：前往主要** 電話畫面上的狀態。</span><span class="sxs-lookup"><span data-stu-id="08de0-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="08de0-115">**音訊代碼手機\*\*\*\*：從開始** 畫面前往功能表  >  **裝置**  >  狀態固件版本。</span><span class="sxs-lookup"><span data-stu-id="08de0-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="08de0-116">**Lync Phone Edition (LPE)** 手機：從開始畫面前往  >  功能表系統資訊。</span><span class="sxs-lookup"><span data-stu-id="08de0-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="08de0-117">商務用 Skype 服務會管理固件更新。</span><span class="sxs-lookup"><span data-stu-id="08de0-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="08de0-118">每一部經商務用 Skype 認證的手機的固件都會上傳到商務用 Skype Update 伺服器，且裝置更新預設會啟用所有電話。</span><span class="sxs-lookup"><span data-stu-id="08de0-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="08de0-119">根據電話和投票間隔上的非啟用時間，電話會自動下載並安裝最新的認證版本。</span><span class="sxs-lookup"><span data-stu-id="08de0-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="08de0-120">您可以使用  [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) Cmdlet，將 *EnableDeviceUpdate* 參數設定為 來停用裝置更新設定 `false` 。</span><span class="sxs-lookup"><span data-stu-id="08de0-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="08de0-121">設定公用區域電話</span><span class="sxs-lookup"><span data-stu-id="08de0-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="08de0-122">您需要遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="08de0-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="08de0-123">步驟 1 - 購買授權</span><span class="sxs-lookup"><span data-stu-id="08de0-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="08de0-124">在系統管理中心，**前往帳單**  >  **購買服務**，然後新增 **其他方案**。</span><span class="sxs-lookup"><span data-stu-id="08de0-124">In the admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![一般地區電話授權螢幕擷取畫面](../../images/cap-license.png)
2. <span data-ttu-id="08de0-126">按一下 [**立即購買常用區域電話**  >  \*\*\*\*> [結帳>按一下 [**立即購買**> 。</span><span class="sxs-lookup"><span data-stu-id="08de0-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="08de0-127">按一下以展開 **附加元件訂閱** ，然後按一下以購買通話方案。</span><span class="sxs-lookup"><span data-stu-id="08de0-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="08de0-128">選擇國內 **通話方案或\*\*\*\*國內及國際通話方案**。</span><span class="sxs-lookup"><span data-stu-id="08de0-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="08de0-129">您不需要電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="08de0-129">You don't need a Phone System license.</span></span> <span data-ttu-id="08de0-130">它包含在共同區域 **電話授權** 中。</span><span class="sxs-lookup"><span data-stu-id="08de0-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="08de0-131">有關授權詳細資訊，請參閱商務用 Skype 和 [Microsoft Teams 附加元件授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="08de0-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="08de0-132">步驟 2 - 為手機建立新使用者帳戶並指派授權</span><span class="sxs-lookup"><span data-stu-id="08de0-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="08de0-133">在系統管理中心，前往 **使用者**  >  **活動使用者**  >  **新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="08de0-133">In the admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="08de0-134">輸入使用者名稱 **，** 例如名字的「主」，第二個名稱為「接收」。</span><span class="sxs-lookup"><span data-stu-id="08de0-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="08de0-135">如果顯示 **名稱無法** 像「主要接收」一樣自動生成，請輸入顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="08de0-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="08de0-136">輸入使用者 **名稱，** 例如「MainReception」或「Mainlobby」。</span><span class="sxs-lookup"><span data-stu-id="08de0-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="08de0-137">對於一般地區電話，您可能會想要手動設定密碼，或針對所有常見的地區電話設定相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="08de0-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="08de0-138">此外，您可能會考慮取消選擇讓此使用者在首次登出 **時變更其密碼**。</span><span class="sxs-lookup"><span data-stu-id="08de0-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="08de0-139">如果您仍然在那裡，請指派授權給此使用者。</span><span class="sxs-lookup"><span data-stu-id="08de0-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="08de0-140">在同一頁上，按一下 以展開 **[產品授權**> 。</span><span class="sxs-lookup"><span data-stu-id="08de0-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="08de0-141">開啟下列功能：</span><span class="sxs-lookup"><span data-stu-id="08de0-141">Turn on the following:</span></span>
   - <span data-ttu-id="08de0-142">公用區域電話</span><span class="sxs-lookup"><span data-stu-id="08de0-142">Common Area Phone</span></span>
   - <span data-ttu-id="08de0-143">然後，您需要選擇國內通話方案或國內及 **國際通話方案**。</span><span class="sxs-lookup"><span data-stu-id="08de0-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="08de0-144">指派授權看起來像：</span><span class="sxs-lookup"><span data-stu-id="08de0-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="08de0-146">就如您所知，商務用 Skype 方案 2 已包含在 **一般地區電話授權** 中。</span><span class="sxs-lookup"><span data-stu-id="08de0-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="08de0-147">有關詳細資料，請參閱 [新增使用者](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="08de0-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="08de0-148">步驟 3 - 將電話號碼指派給公用區域電話使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="08de0-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="08de0-149">![顯示商務用 Skype 標誌的圖示使用商務用 Skype 系統管理中心指派電話號碼 ](../../images/sfb-logo-30x30.png) **給使用者**</span><span class="sxs-lookup"><span data-stu-id="08de0-149">![An icon showing the Skype for Business logo](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="08de0-150">在系統管理中心>**系統管理中心**  >  **商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="08de0-150">In the admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="08de0-151">在 **商務用 Skype 系統管理中心**  >   **語音**  >  **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="08de0-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="08de0-152">從電話號碼清單中選取一個數位，然後按一下 [ **指派**。</span><span class="sxs-lookup"><span data-stu-id="08de0-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="08de0-153">在 **指派頁面上**，**在語音使用者** 方塊中輸入用於電話的使用者名稱，然後在選取語音使用者下拉式清單 **選取使用者。**</span><span class="sxs-lookup"><span data-stu-id="08de0-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="08de0-154">當您在那裡時，您需要新增緊急位址。</span><span class="sxs-lookup"><span data-stu-id="08de0-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="08de0-155">搜尋後，請在選取緊急位址下尋找，以挑選適合您的位址。</span><span class="sxs-lookup"><span data-stu-id="08de0-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="08de0-156">按一下 **[儲存** ，您的使用者看起來應該像這樣：</span><span class="sxs-lookup"><span data-stu-id="08de0-156">Click **Save** and your user should look like this:</span></span>

    ![使用者電話號碼的螢幕擷取畫面](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="08de0-158">使用者只有在已申請電話系統授權 **時** ，才能顯示。</span><span class="sxs-lookup"><span data-stu-id="08de0-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="08de0-159">如果您只是這麼做，有時候使用者需要一點時間，才顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="08de0-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="08de0-160">有關更多內容，請參閱 [取得使用者的電話號碼](/microsoftteams/getting-phone-numbers-for-your-users)。</span><span class="sxs-lookup"><span data-stu-id="08de0-160">For more stuff, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="08de0-161">如果您想知道，您也可以將您擁有的電話號碼帶至另一個電信公司，然後「移轉」，或移轉至 Microsoft 365 或 Office 365。\*\*</span><span class="sxs-lookup"><span data-stu-id="08de0-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="08de0-162">請參閱將 [電話號碼轉接至 Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="08de0-162">See, [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="08de0-163">步驟 4 - 設定您的手機</span><span class="sxs-lookup"><span data-stu-id="08de0-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="08de0-164">**在手機上設定模式**</span><span class="sxs-lookup"><span data-stu-id="08de0-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="08de0-165">您擁有的電話或電話必須開啟 **共同區域電話** 模式。</span><span class="sxs-lookup"><span data-stu-id="08de0-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="08de0-166">您可能會想要檢查該核取方塊，以確保它們確實可以。</span><span class="sxs-lookup"><span data-stu-id="08de0-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="08de0-167">**以下是如何設定 Polycom VVX 手機的範例**</span><span class="sxs-lookup"><span data-stu-id="08de0-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="08de0-168">遵循下列步驟，為 Polycom VVX 啟用公用區域電話模式：</span><span class="sxs-lookup"><span data-stu-id="08de0-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="08de0-169">在瀏覽器中，連接到 Web 介面，以便啟用 CAP 模式。</span><span class="sxs-lookup"><span data-stu-id="08de0-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="08de0-170">接著，請前往 **設定，**  然後在 **商務** 用 Skype 設定選項中，選取 **共同區域電話**。</span><span class="sxs-lookup"><span data-stu-id="08de0-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="08de0-171">按一下 **[是** 」 以儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="08de0-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="08de0-172">現在已啟用 CAP 模式，使用手機的顯示器來設定手機。</span><span class="sxs-lookup"><span data-stu-id="08de0-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="08de0-173">顯示器應該會顯示 **已啟用 CaAP。**</span><span class="sxs-lookup"><span data-stu-id="08de0-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="08de0-174">然後執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="08de0-174">Then do the following:</span></span>

    1. <span data-ttu-id="08de0-175">按一下 **[設定>**。</span><span class="sxs-lookup"><span data-stu-id="08de0-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="08de0-176">選取 **進位**。</span><span class="sxs-lookup"><span data-stu-id="08de0-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="08de0-177">輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="08de0-177">Enter the password.</span></span>
    4. <span data-ttu-id="08de0-178">在 **系統管理設定中**，選取 **共同區域電話設定**。</span><span class="sxs-lookup"><span data-stu-id="08de0-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="08de0-179">啟用 **CAP** 和 **CAP 系統管理模式**。</span><span class="sxs-lookup"><span data-stu-id="08de0-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="08de0-180">按一下 **[儲存 Config>**。</span><span class="sxs-lookup"><span data-stu-id="08de0-180">Click **Save Config**.</span></span>

- <span data-ttu-id="08de0-181">現在您的手機已準備就緒，因此您可以在主畫面上登錄。</span><span class="sxs-lookup"><span data-stu-id="08de0-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="08de0-182">選取商務用Skype 的設定功能  >    >  **來登錄。**</span><span class="sxs-lookup"><span data-stu-id="08de0-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="08de0-183">選取 **使用者認證**，然後選取 **CAP** (網頁) 以產生程式碼。</span><span class="sxs-lookup"><span data-stu-id="08de0-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="08de0-184">請前往 [資源調配入口網站](https://aka.ms/skypecap)，然後以系統管理員的登錄 **。**</span><span class="sxs-lookup"><span data-stu-id="08de0-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="08de0-185">輸入顯示名稱 (例如，主要接收) 。</span><span class="sxs-lookup"><span data-stu-id="08de0-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="08de0-186">如果 **只勾選了搜尋一般地區** 電話，請清除核取方塊，然後再次搜尋。</span><span class="sxs-lookup"><span data-stu-id="08de0-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="08de0-187">在配對程式碼視窗中，輸入手機上顯示的代碼，然後按一下 [ **備入**。</span><span class="sxs-lookup"><span data-stu-id="08de0-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="08de0-188">遵循最後一個步驟，電話應該會自動登入。</span><span class="sxs-lookup"><span data-stu-id="08de0-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="08de0-189">CAP 設定網站指出，它會將 CAP 帳戶的密碼重設為隨機密碼。</span><span class="sxs-lookup"><span data-stu-id="08de0-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="08de0-190">請注意，CAP 所參照的帳戶是 AAD (Azure Active Directory) 帳戶。</span><span class="sxs-lookup"><span data-stu-id="08de0-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="08de0-191">如果您只在 AAD 中建立帳戶，則程式很簡單。</span><span class="sxs-lookup"><span data-stu-id="08de0-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="08de0-192">如果您將內部部署 Active Directory 同步到 AAD，而且使用協力廠商 IDP 或 ADFS，則 CAP 置備將會失敗。</span><span class="sxs-lookup"><span data-stu-id="08de0-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="08de0-193">在這種情況下，您只需要使用 Microsoft 365 或 Office 365/Azure Active Directory 帳戶 (，例如具有 **onmicrosoft.com** 網域) 的帳戶，才能使用 CAP 資源配置。</span><span class="sxs-lookup"><span data-stu-id="08de0-193">In this case, you need to use a Microsoft 365 or Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="08de0-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="08de0-194">Related topics</span></span>

- <span data-ttu-id="08de0-195">在部署商務用 Skype Online 電話時深入瞭解 [可用的電話](deploying-skype-for-business-online-phones.md)。</span><span class="sxs-lookup"><span data-stu-id="08de0-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="08de0-196">取得商務用 Skype Online 的電話</span><span class="sxs-lookup"><span data-stu-id="08de0-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)
