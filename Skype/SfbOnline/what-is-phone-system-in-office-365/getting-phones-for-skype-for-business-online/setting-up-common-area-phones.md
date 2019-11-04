---
title: 設定常用的區域電話
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
f1keywords: None
ms.custom:
- Phone System
description: 瞭解如何取得正確的固件、根據需要進行更新、指派授權，以及設定常用區域手機的設定等部署步驟。
ms.openlocfilehash: a245db1a2033f08d50e9a3c1a32f27981a3eb702
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924894"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="7e95f-103">設定公共區域電話</span><span class="sxs-lookup"><span data-stu-id="7e95f-103">Set up common area phones</span></span>
<span data-ttu-id="7e95f-104">常見的區域電話（CAP）通常放在諸如大廳或其他許多人都可以使用的區域中。</span><span class="sxs-lookup"><span data-stu-id="7e95f-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="7e95f-105">例如，將 Cap 設定為裝置，而不是使用者並自動登入網路，即接收區域電話、[門 phone] 或 [會議室電話]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="7e95f-106">在下列步驟中，我們將協助您使用通話方案設定電話系統帳戶，以便為您的組織部署這些類型的電話。</span><span class="sxs-lookup"><span data-stu-id="7e95f-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="7e95f-107">常見區域手機的先決條件</span><span class="sxs-lookup"><span data-stu-id="7e95f-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="7e95f-108">您必須做的第一件事是確認您具備下列專案：</span><span class="sxs-lookup"><span data-stu-id="7e95f-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="7e95f-109">購買通用的區域電話授權和通話方案。</span><span class="sxs-lookup"><span data-stu-id="7e95f-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="7e95f-110">搜尋並購買核准的電話（在[此](deploying-skype-for-business-online-phones.md)查看清單）。</span><span class="sxs-lookup"><span data-stu-id="7e95f-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="7e95f-111">更新手機上的固件（請參閱[本主題中](getting-phones-for-skype-for-business-online.md)的支援的固件）。</span><span class="sxs-lookup"><span data-stu-id="7e95f-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="7e95f-112">您可以執行下列動作來檢查手機上的固件：</span><span class="sxs-lookup"><span data-stu-id="7e95f-112">You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="7e95f-113">**Polycom VVX 手機**：移至**設定** > **狀態** > **平臺** > **應用程式** > **主要**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="7e95f-114">**Yealink [電話**]：移至 [主要電話] 畫面上的 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="7e95f-115">**AudioCodes [電話**]：從 [開始] 畫面移至 [**功能表** > **裝置狀態** > **固件版本**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="7e95f-116">**Lync Phone Edition （lpw）手機**：移至 [開始] 畫面中的 [**功能表** > **系統資訊**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="7e95f-117">固件更新是由商務用 Skype 服務來管理。</span><span class="sxs-lookup"><span data-stu-id="7e95f-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="7e95f-118">每個商務用 Skype 認證手機的固件都會上傳到商務用 Skype 補救伺服器，且預設會在所有手機上啟用裝置更新。</span><span class="sxs-lookup"><span data-stu-id="7e95f-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="7e95f-119">電話會自動下載並安裝最新的認證組建，這取決於電話和巡迴檢測間隔中的非啟用時間。</span><span class="sxs-lookup"><span data-stu-id="7e95f-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="7e95f-120">您可以使用[CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) Cmdlet 來停用裝置更新設定，並將*EnableDeviceUpdate*參數設定為`false`。</span><span class="sxs-lookup"><span data-stu-id="7e95f-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="7e95f-121">設定一般的區域電話</span><span class="sxs-lookup"><span data-stu-id="7e95f-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="7e95f-122">您必須遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7e95f-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="7e95f-123">步驟 1-購買授權</span><span class="sxs-lookup"><span data-stu-id="7e95f-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="7e95f-124">在系統管理中心中，移至 [**帳單** > **購買服務**]，然後新增**其他方案**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-124">In the admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license .png](../../images/cap-license.png)
2. <span data-ttu-id="7e95f-126">按一下 [**常用區域電話** > **立即購買**] > 在 [**結帳**] 頁面上按一下 [**立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="7e95f-127">按一下 [開啟] 以展開 [**附加元件訂閱**]，然後按一下 [開啟] 以購買通話方案。</span><span class="sxs-lookup"><span data-stu-id="7e95f-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="7e95f-128">選擇 [**國內通話方案**] 或 [**國內與國際通話方案**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="7e95f-129">您不需要電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="7e95f-129">You don't need a Phone System license.</span></span> <span data-ttu-id="7e95f-130">它包含在**通用區域電話**授權中。</span><span class="sxs-lookup"><span data-stu-id="7e95f-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="7e95f-131">如需授權的詳細資訊，請參閱[商務用 Skype 和 Microsoft 團隊附加元件授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="7e95f-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="7e95f-132">步驟 2-為手機建立新的使用者帳戶並指派授權</span><span class="sxs-lookup"><span data-stu-id="7e95f-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="7e95f-133">在系統管理中心中，移至 [**使用者** > 作用中的**使用者** > ]**新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-133">In the admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="7e95f-134">將第一個名稱的**使用者名稱**（例如 "Main"）加上第二個名稱的 "接收"。</span><span class="sxs-lookup"><span data-stu-id="7e95f-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="7e95f-135">如果沒有自動產生類似 "主要接收" 的名稱，則放入**顯示名稱**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="7e95f-136">放在**使用者名稱**（例如 "MainReception" 或 "Mainlobby"）。</span><span class="sxs-lookup"><span data-stu-id="7e95f-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="7e95f-137">如果是常見的區域電話，您可能會想要手動設定密碼，或針對所有常見的區域手機設定密碼。</span><span class="sxs-lookup"><span data-stu-id="7e95f-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="7e95f-138">此外，您也可以考慮取消選中**讓此使用者在第一次登入時變更他們的密碼**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="7e95f-139">如果您仍在那裡，請指派授權給此使用者。</span><span class="sxs-lookup"><span data-stu-id="7e95f-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="7e95f-140">在同一個頁面上，按一下以展開 [**產品授權**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="7e95f-141">開啟下列各項：</span><span class="sxs-lookup"><span data-stu-id="7e95f-141">Turn on the following:</span></span>
   - <span data-ttu-id="7e95f-142">常見的區域電話</span><span class="sxs-lookup"><span data-stu-id="7e95f-142">Common Area Phone</span></span>
   - <span data-ttu-id="7e95f-143">接著，您必須挑選**國內通話方案**或國內與**國際通話方案**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="7e95f-144">指派授權的方式將如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e95f-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense .png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="7e95f-146">只要知道，商務用 Skype 方案2就包含在**通用區域電話**授權中。</span><span class="sxs-lookup"><span data-stu-id="7e95f-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="7e95f-147">如需詳細資訊，請參閱[新增使用者](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="7e95f-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="7e95f-148">步驟 3-將電話號碼指派給通用區域電話使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7e95f-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="7e95f-149">![顯示商務用 Skype 標誌](../../images/sfb-logo-30x30.png)的圖示，可使用商務用 Skype 系統**管理中心**將電話號碼指派給使用者</span><span class="sxs-lookup"><span data-stu-id="7e95f-149">![An icon showing the Skype for Business logo](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="7e95f-150">在系統管理中心中 > [系統**管理中心] 中心** > **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-150">In the admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="7e95f-151">在**商務用 Skype 系統管理中心** >  **語音** > **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="7e95f-152">從電話號碼清單中選取一個數位，然後按一下 [**指派**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="7e95f-153">在 [**指派**] 頁面上的 [**語音使用者**] 方塊中，輸入用於手機的使用者名稱，然後在 [**選取語音使用者**] 下拉式清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="7e95f-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="7e95f-154">當您在這裡時，您將需要新增緊急位址。</span><span class="sxs-lookup"><span data-stu-id="7e95f-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="7e95f-155">搜尋之後，請在 [**選取緊急位址**] 下查看，為您挑選一個合適的位址。</span><span class="sxs-lookup"><span data-stu-id="7e95f-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="7e95f-156">按一下 [**儲存**]，您的使用者看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="7e95f-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number .png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="7e95f-158">只有在已套用**電話系統**授權的情況中，使用者才會顯示。</span><span class="sxs-lookup"><span data-stu-id="7e95f-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="7e95f-159">如果您只這麼做，有時候使用者會在清單中顯示一個位。</span><span class="sxs-lookup"><span data-stu-id="7e95f-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="7e95f-160">如需更多相關資訊，請參閱為[您的使用者取得電話號碼](/microsoftteams/getting-phone-numbers-for-your-users)。</span><span class="sxs-lookup"><span data-stu-id="7e95f-160">For more stuff, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="7e95f-161">如果您想知道，您也可以將您的電話號碼與其他運輸公司和「*埠*」結合，或轉移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7e95f-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="7e95f-162">請參閱[將電話號碼轉移至團隊](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="7e95f-162">See, [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="7e95f-163">步驟 4-設定您的電話</span><span class="sxs-lookup"><span data-stu-id="7e95f-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="7e95f-164">**在手機上設定模式**</span><span class="sxs-lookup"><span data-stu-id="7e95f-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="7e95f-165">您所擁有的電話必須開啟 [**通用區域電話模式]** 。</span><span class="sxs-lookup"><span data-stu-id="7e95f-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="7e95f-166">您可能會想要檢查該選項，以確定它們的執行方式。</span><span class="sxs-lookup"><span data-stu-id="7e95f-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="7e95f-167">**以下是如何設定 Polycom VVX phone 的範例**</span><span class="sxs-lookup"><span data-stu-id="7e95f-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="7e95f-168">若要啟用 Polycom VVX 的通用區域電話模式，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7e95f-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="7e95f-169">在您的瀏覽器中，連線到網頁介面，讓您可以啟用 [CAP 模式]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="7e95f-170">接著，移至 [**設定**]，然後在 [**商務用 Skype] 設定**選項中，選取 [**通用區域電話**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="7e95f-171">按一下 **[是]** 儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="7e95f-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="7e95f-172">現在已啟用 [CAP] 模式，請使用手機的顯示器設定電話。</span><span class="sxs-lookup"><span data-stu-id="7e95f-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="7e95f-173">顯示器應該顯示**CaAP 已啟用**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="7e95f-174">然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7e95f-174">Then do the following:</span></span>

    1. <span data-ttu-id="7e95f-175">按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="7e95f-176">選取 [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="7e95f-177">輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="7e95f-177">Enter the password.</span></span>
    4. <span data-ttu-id="7e95f-178">在 [**管理設定**] 中，選取 [**常用區域電話設定**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="7e95f-179">啟用**CAP**和**Cap 系統管理模式**。</span><span class="sxs-lookup"><span data-stu-id="7e95f-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="7e95f-180">按一下 [**儲存配置**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-180">Click **Save Config**.</span></span>

- <span data-ttu-id="7e95f-181">現在，您的手機已準備就緒，您可以在主畫面上登入。</span><span class="sxs-lookup"><span data-stu-id="7e95f-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="7e95f-182">選取\*\*\*\* > [**設定** > ] 的 [**商務用 Skype** ]，登入。</span><span class="sxs-lookup"><span data-stu-id="7e95f-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="7e95f-183">選取 [**使用者認證**]，然後選取 **[web 登入（CAP）** ] 來產生程式碼。</span><span class="sxs-lookup"><span data-stu-id="7e95f-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="7e95f-184">移至 [[預配入口網站](https://aka.ms/skypecap)]，然後以系統**管理員**身分登入。</span><span class="sxs-lookup"><span data-stu-id="7e95f-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="7e95f-185">輸入顯示名稱（例如 [主要接收]）。</span><span class="sxs-lookup"><span data-stu-id="7e95f-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="7e95f-186">如果已核取 [**搜尋普通區域手機**]，請清除該核取方塊，然後再次搜尋。</span><span class="sxs-lookup"><span data-stu-id="7e95f-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="7e95f-187">在 [配對代碼] 視窗中，輸入顯示在手機上的程式碼，然後按一下 [**提供**]。</span><span class="sxs-lookup"><span data-stu-id="7e95f-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="7e95f-188">在這個最後一個步驟之後，手機應該會自動登入。</span><span class="sxs-lookup"><span data-stu-id="7e95f-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="7e95f-189">CAP 預配網站的狀態會將 CAP 帳戶的密碼重設為隨機密碼。</span><span class="sxs-lookup"><span data-stu-id="7e95f-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="7e95f-190">請注意，CAP 所參照的帳戶是 Azure Active Directory （AAD）帳戶。</span><span class="sxs-lookup"><span data-stu-id="7e95f-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="7e95f-191">如果您只在 AAD 中建立帳戶，程式就相當簡單。</span><span class="sxs-lookup"><span data-stu-id="7e95f-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="7e95f-192">如果您已將內部部署 Active Directory 同步處理到 AAD，且您使用的是協力廠商 IDP 或 ADFS，則 CAP 配置將會失敗。</span><span class="sxs-lookup"><span data-stu-id="7e95f-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="7e95f-193">在這種情況下，您只需要使用 Office 365/Azure Active Directory 帳戶（例如，擁有**onmicrosoft.com**網域的帳戶），才能執行 CAP 提供作業。</span><span class="sxs-lookup"><span data-stu-id="7e95f-193">In this case, you need to use an Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="7e95f-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="7e95f-194">Related topics</span></span>

- <span data-ttu-id="7e95f-195">深入瞭解[部署商務用 Skype Online 手機](deploying-skype-for-business-online-phones.md)時可用的手機。</span><span class="sxs-lookup"><span data-stu-id="7e95f-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="7e95f-196">在商務用 Skype Online 中取得電話</span><span class="sxs-lookup"><span data-stu-id="7e95f-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


