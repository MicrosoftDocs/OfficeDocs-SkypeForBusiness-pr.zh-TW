---
title: 設定 Microsoft 團隊的通用區域電話授權
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '瞭解如何為大廳、接待區域及會議室設定通用區域電話 '
ms.openlocfilehash: d00d91d4461a8b197f8629d3dfe9cee6653b2473
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925304"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="88f7f-103">設定 Microsoft 團隊的通用區域電話授權</span><span class="sxs-lookup"><span data-stu-id="88f7f-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="88f7f-104">常見的區域電話不支援語音信箱。</span><span class="sxs-lookup"><span data-stu-id="88f7f-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="88f7f-105">常見的區域手機通常位於大廳或另一個區域（例如可供許多人撥打通話的區域）。例如，接收區域、會議廳或會議電話。</span><span class="sxs-lookup"><span data-stu-id="88f7f-105">A common area phone is typically placed in an area like a lobby or another area which is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="88f7f-106">常見的區域手機是設定為裝置，而不是使用者，而且可以自動登入網路。</span><span class="sxs-lookup"><span data-stu-id="88f7f-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="88f7f-107">在下列步驟中，我們將協助您設定電話系統帳戶，以便為您的組織部署常見的區域電話。</span><span class="sxs-lookup"><span data-stu-id="88f7f-107">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="88f7f-108">如需更完整的會議室體驗（包括音訊會議），請考慮使用會議室裝置購買專用的會議室授權。</span><span class="sxs-lookup"><span data-stu-id="88f7f-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="88f7f-109">您需要做的第一件事是購買常見的區域電話（CAP）授權，並確認您有已認證的電話。</span><span class="sxs-lookup"><span data-stu-id="88f7f-109">The first things you need to do are purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="88f7f-110">若要搜尋並深入瞭解認證的手機，請移至[Microsoft 團隊裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="88f7f-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="88f7f-111">步驟 1-購買授權</span><span class="sxs-lookup"><span data-stu-id="88f7f-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="88f7f-112">在 Microsoft 365 系統管理中心中，移至 [**帳單** > **購買服務**]，然後展開**其他方案**。</span><span class="sxs-lookup"><span data-stu-id="88f7f-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![顯示常見區域電話磚的螢幕擷取畫面](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="88f7f-114">選取 [**通用區域電話** > **立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="88f7f-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="88f7f-115">在 [**結帳**] 頁面上，按一下 [**立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="88f7f-115">On the **Checkout** page click **Buy now**.</span></span>

4. <span data-ttu-id="88f7f-116">展開 [**附加元件訂閱**]，然後按一下以購買通話方案。</span><span class="sxs-lookup"><span data-stu-id="88f7f-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="88f7f-117">選擇 [**國內通話方案**] 或 [**國內與國際通話方案**]。</span><span class="sxs-lookup"><span data-stu-id="88f7f-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="88f7f-118">您不需要電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="88f7f-118">You don't need a Phone System license.</span></span> <span data-ttu-id="88f7f-119">它包含在通用區域電話授權中。</span><span class="sxs-lookup"><span data-stu-id="88f7f-119">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="88f7f-120">如需授權的詳細資訊，請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="88f7f-120">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="88f7f-121">常見的區域電話授權支援：</span><span class="sxs-lookup"><span data-stu-id="88f7f-121">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="88f7f-122">常見的區域電話</span><span class="sxs-lookup"><span data-stu-id="88f7f-122">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="88f7f-123">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="88f7f-123">Skype for Business</span></span> |   <span data-ttu-id="88f7f-124">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="88f7f-124">&#x2714;</span></span> |
|<span data-ttu-id="88f7f-125">Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="88f7f-125">Microsoft Teams</span></span> |   <span data-ttu-id="88f7f-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="88f7f-126">&#x2714;</span></span> |
|<span data-ttu-id="88f7f-127">電話系統</span><span class="sxs-lookup"><span data-stu-id="88f7f-127">Phone Systems</span></span> |    <span data-ttu-id="88f7f-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="88f7f-128">&#x2714;</span></span> |
|<span data-ttu-id="88f7f-129">音訊會議</span><span class="sxs-lookup"><span data-stu-id="88f7f-129">Audio Conferencing</span></span> |       <span data-ttu-id="88f7f-130">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="88f7f-130">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="88f7f-131">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="88f7f-131">Microsoft Intune</span></span> |        <span data-ttu-id="88f7f-132">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="88f7f-132">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="88f7f-133">全球可用性</span><span class="sxs-lookup"><span data-stu-id="88f7f-133">Worldwide Availability</span></span> |    <span data-ttu-id="88f7f-134">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="88f7f-134">&#x2714;</span></span> |
|<span data-ttu-id="88f7f-135">頻道可用性</span><span class="sxs-lookup"><span data-stu-id="88f7f-135">Channel Availability</span></span> |    <span data-ttu-id="88f7f-136">EA、EAS、CSP、GCC、EES、Web Direct</span><span class="sxs-lookup"><span data-stu-id="88f7f-136">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="88f7f-137">&sup1;常見的區域手機可透過會議召集人提供的撥入號碼加入音訊會議</span><span class="sxs-lookup"><span data-stu-id="88f7f-137">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="88f7f-138">&sup2;在主權雲彩中無法使用</span><span class="sxs-lookup"><span data-stu-id="88f7f-138">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="88f7f-139">步驟 2-為手機建立新的使用者帳戶並指派授權</span><span class="sxs-lookup"><span data-stu-id="88f7f-139">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="88f7f-140">在 Microsoft 365 系統管理中心，移至 [**使用者** > 作用中的**使用者** > ]**新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="88f7f-140">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="88f7f-141">針對第一個名稱輸入名為 "Main" 的使用者名稱，輸入 "接收" （第二個名稱）。</span><span class="sxs-lookup"><span data-stu-id="88f7f-141">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="88f7f-142">如果沒有自動產生 [主要接收] 等命令，請輸入顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="88f7f-142">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="88f7f-143">輸入使用者名稱，例如 "MainReception" 或 "Mainlobby"。</span><span class="sxs-lookup"><span data-stu-id="88f7f-143">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="88f7f-144">如果是常見的區域電話，您可能會想要手動設定密碼，或在所有常用的區域手機上使用相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="88f7f-144">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="88f7f-145">此外，您也可以考慮清除 [**讓此使用者在第一次登入時變更密碼**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="88f7f-145">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="88f7f-146">指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="88f7f-146">Assign the licenses to the user.</span></span> <span data-ttu-id="88f7f-147">在同一個頁面上，按一下以展開 [**產品授權**]。</span><span class="sxs-lookup"><span data-stu-id="88f7f-147">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="88f7f-148">開啟 [通用區域手機]，然後挑選**國內通話方案**或**國內和國際通話方案**。</span><span class="sxs-lookup"><span data-stu-id="88f7f-148">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![顯示授權指派的螢幕擷取畫面](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="88f7f-150">如需詳細資訊，請參閱[新增使用者](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="88f7f-150">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="88f7f-151">步驟 3-將電話號碼指派給通用區域電話使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="88f7f-151">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="88f7f-152">使用商務用 Skype 系統管理中心將號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="88f7f-152">Use the Skype for Business admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="88f7f-153">在 Microsoft 365 系統管理中心，選取 [系統**管理中心** > ]**團隊 & Skype** > **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="88f7f-153">In the Microsoft 365 admin center, select **Admin centers** > **Teams & Skype** > **Legacy portal**.</span></span>

2. <span data-ttu-id="88f7f-154">在商務用 Skype 系統管理中心中，選取 [**語音** > **電話號碼**]。</span><span class="sxs-lookup"><span data-stu-id="88f7f-154">In the Skype for Business admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="88f7f-155">從電話號碼清單中選取一個數位，然後按一下 [**指派**]。</span><span class="sxs-lookup"><span data-stu-id="88f7f-155">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="88f7f-156">在 [**指派**] 頁面上，于 [語音使用者] 方塊中，輸入將使用電話的使用者名稱，然後在 [**選取語音使用者**] 下拉式清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="88f7f-156">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="88f7f-157">當您在這裡時，您將需要新增緊急位址。</span><span class="sxs-lookup"><span data-stu-id="88f7f-157">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="88f7f-158">選擇 [**依城市搜尋**]、[**依描述搜尋**] 或 [**依位置**從下拉式清單中搜尋]，然後在文字方塊中輸入 [城市]、[描述] 或 [位置]。</span><span class="sxs-lookup"><span data-stu-id="88f7f-158">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="88f7f-159">搜尋之後，請在 [**選取緊急位址**] 下查看，為您挑選合適的位址。</span><span class="sxs-lookup"><span data-stu-id="88f7f-159">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="88f7f-160">按一下 [**儲存**]，您的使用者看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="88f7f-160">Click **Save** and your user should look like this:</span></span>

   ![顯示授權指派的螢幕擷取畫面](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="88f7f-162">使用者只有在已套用電話系統授權時，才會顯示。</span><span class="sxs-lookup"><span data-stu-id="88f7f-162">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="88f7f-163">如果您只這麼做，有時候使用者會在清單中顯示一個位。</span><span class="sxs-lookup"><span data-stu-id="88f7f-163">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="88f7f-164">如需詳細資訊，請參閱為[您的使用者取得電話號碼](/microsoftteams/getting-phone-numbers-for-your-users)。</span><span class="sxs-lookup"><span data-stu-id="88f7f-164">For more information, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="88f7f-165">您也可以將您的電話號碼與其他運輸公司和「埠」取得聯繫，或將它傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="88f7f-165">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="88f7f-166">請參閱[將電話號碼傳送給團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="88f7f-166">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


