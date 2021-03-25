---
title: 設定公用區域電話授權
ms.author: serdars
author: SerdarSoysal
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
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '瞭解如何設定大廳、接待區和會議室的公用區域電話 '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117111"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="79d58-103">設定 Microsoft Teams 的公用區域電話授權</span><span class="sxs-lookup"><span data-stu-id="79d58-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="79d58-104">一般地區電話不支援語音信箱。</span><span class="sxs-lookup"><span data-stu-id="79d58-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="79d58-105">一般地區電話會放在大廳等區域，或是許多人可以撥打的另一個區域;例如，接待區、大廳或會議電話。</span><span class="sxs-lookup"><span data-stu-id="79d58-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="79d58-106">一般地區電話會使用與共同區域電話授權相關的帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="79d58-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="79d58-107">也必須適當設定 TeamsIPPhone 政策，讓手機擁有共同的區域使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="79d58-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="79d58-108">在下列步驟中，我們會協助您設定電話系統帳戶，為貴組織部署常見的地區電話。</span><span class="sxs-lookup"><span data-stu-id="79d58-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="79d58-109">為獲得更完整的會議室體驗 ，包括音訊會議，請考慮使用會議室裝置購買專屬的會議室授權。</span><span class="sxs-lookup"><span data-stu-id="79d58-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="79d58-110">首先，您必須購買一般地區電話 (CAP) 授權，並確認您擁有經過認證的電話。</span><span class="sxs-lookup"><span data-stu-id="79d58-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="79d58-111">若要搜尋並深入瞭解認證電話，請前往 Microsoft [Teams 裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="79d58-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="79d58-112">步驟 1 - 購買授權</span><span class="sxs-lookup"><span data-stu-id="79d58-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="79d58-113">在 Microsoft 365 系統管理中心，前往帳單  >  **購買服務**，然後展開 **其他方案**。</span><span class="sxs-lookup"><span data-stu-id="79d58-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![顯示公用區域電話磚的螢幕擷取畫面](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="79d58-115">選取 **共同區域電話**  >  **立即購買**。</span><span class="sxs-lookup"><span data-stu-id="79d58-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="79d58-116">在 [結帳」 頁面上，按一下 [ **立即購買**> 。</span><span class="sxs-lookup"><span data-stu-id="79d58-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="79d58-117">展開 **附加元件訂閱，** 然後按一下以購買通話方案。</span><span class="sxs-lookup"><span data-stu-id="79d58-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="79d58-118">選擇國內 **通話方案或\*\*\*\*國內及國際通話方案**。</span><span class="sxs-lookup"><span data-stu-id="79d58-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="79d58-119">如果您使用的是 Microsoft Phone System Direct Routing，則不需要通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="79d58-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="79d58-120">您不需要新增電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="79d58-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="79d58-121">它包含在共同區域電話授權中。</span><span class="sxs-lookup"><span data-stu-id="79d58-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="79d58-122">有關授權詳細資訊，請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="79d58-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="79d58-123">通用地區電話授權支援：</span><span class="sxs-lookup"><span data-stu-id="79d58-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="79d58-124">公用區域電話</span><span class="sxs-lookup"><span data-stu-id="79d58-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="79d58-125">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="79d58-125">Skype for Business</span></span> |   <span data-ttu-id="79d58-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="79d58-126">&#x2714;</span></span> |
|<span data-ttu-id="79d58-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79d58-127">Microsoft Teams</span></span> |   <span data-ttu-id="79d58-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="79d58-128">&#x2714;</span></span> |
|<span data-ttu-id="79d58-129">電話系統</span><span class="sxs-lookup"><span data-stu-id="79d58-129">Phone System</span></span> |    <span data-ttu-id="79d58-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="79d58-130">&#x2714;</span></span> |
|<span data-ttu-id="79d58-131">音訊會議</span><span class="sxs-lookup"><span data-stu-id="79d58-131">Audio Conferencing</span></span> |       <span data-ttu-id="79d58-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="79d58-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="79d58-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="79d58-133">Microsoft Intune</span></span> |    <span data-ttu-id="79d58-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="79d58-134">&#x2718;</span></span> |
|<span data-ttu-id="79d58-135">全球可用性</span><span class="sxs-lookup"><span data-stu-id="79d58-135">Worldwide Availability</span></span> |       <span data-ttu-id="79d58-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="79d58-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="79d58-137">通道可用性</span><span class="sxs-lookup"><span data-stu-id="79d58-137">Channel Availability</span></span> |    <span data-ttu-id="79d58-138">EA、EAS、CSP、GCC、EES、Web Direct</span><span class="sxs-lookup"><span data-stu-id="79d58-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="79d58-139">&sup1;一般地區電話可以透過會議召集人提供的撥入號碼加入音訊會議</span><span class="sxs-lookup"><span data-stu-id="79d58-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="79d58-140">&sup2;在主權雲端中不可用</span><span class="sxs-lookup"><span data-stu-id="79d58-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="79d58-141">步驟 2 - 為手機建立新使用者帳戶並指派授權</span><span class="sxs-lookup"><span data-stu-id="79d58-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="79d58-142">在 Microsoft 365 系統管理中心，前往 **使用者**  >  **使用中使用者**  >  **新增使用者**。</span><span class="sxs-lookup"><span data-stu-id="79d58-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="79d58-143">輸入使用者名稱，例如名字的「主」，第二個名稱的「接收」。</span><span class="sxs-lookup"><span data-stu-id="79d58-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="79d58-144">如果顯示名稱無法像「主要接收」一樣自動生成，請輸入顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="79d58-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="79d58-145">輸入使用者名稱，例如「MainReception」或「Mainlobby」。</span><span class="sxs-lookup"><span data-stu-id="79d58-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="79d58-146">對於一般地區電話，您可能會想要手動設定密碼，或針對所有公用區域電話設定相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="79d58-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="79d58-147">此外，您可能會考慮清除讓此使用者第一次 **登錄時變更** 其密碼核取方塊。</span><span class="sxs-lookup"><span data-stu-id="79d58-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="79d58-148">指派授權給使用者。</span><span class="sxs-lookup"><span data-stu-id="79d58-148">Assign the licenses to the user.</span></span> <span data-ttu-id="79d58-149">在同一頁上，按一下 以展開 **[產品授權>**。</span><span class="sxs-lookup"><span data-stu-id="79d58-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="79d58-150">開啟公用區域電話，然後挑選國內通話方案或 **國內及國際通話方案**。</span><span class="sxs-lookup"><span data-stu-id="79d58-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![顯示授權指派的螢幕擷取畫面](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="79d58-152">如果您使用的是 Microsoft Phone System Direct Routing，則不需要指派通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="79d58-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="79d58-153">詳細資訊，請參閱指派 [授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="79d58-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="79d58-154">步驟 3 - 將電話號碼指派給公用區域電話使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="79d58-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="79d58-155">使用 Teams 系統管理中心將號碼指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="79d58-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="79d58-156">在 Teams 系統管理中心中，選取 **語音**  >  **電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="79d58-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="79d58-157">從電話號碼清單中選取一個數位，然後按一下 [ **指派**。</span><span class="sxs-lookup"><span data-stu-id="79d58-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="79d58-158">在 **指派** 頁面的語音使用者方塊中，輸入將會使用電話的使用者名稱，然後在選取語音使用者下拉式清單中選取使用者。 </span><span class="sxs-lookup"><span data-stu-id="79d58-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="79d58-159">接下來，您需要新增緊急位址。</span><span class="sxs-lookup"><span data-stu-id="79d58-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="79d58-160">從 **下拉** 式清單中，選擇按城市搜尋、按描述搜尋，或按位置搜尋，然後在文字方塊中輸入城市、描述或位置。</span><span class="sxs-lookup"><span data-stu-id="79d58-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="79d58-161">搜尋後，請在選取 **緊急位址** 下尋找，以挑選適合您的位址。</span><span class="sxs-lookup"><span data-stu-id="79d58-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="79d58-162">按一下 **[儲存** ，您的使用者應該看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="79d58-162">Click **Save** and your user should look like this:</span></span>

   ![顯示授權指派的螢幕擷取畫面](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="79d58-164">使用者只有在已申請電話系統授權時，才能顯示。</span><span class="sxs-lookup"><span data-stu-id="79d58-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="79d58-165">如果您只是這麼做，有時候使用者需要一點時間，才顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="79d58-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="79d58-166">詳細資訊，請參閱 [取得使用者的電話號碼](getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="79d58-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="79d58-167">您也可以將您擁有的電話號碼帶至其他電信公司，並「移轉」或移轉至 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="79d58-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="79d58-168">請參閱 [將電話號碼轉接至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="79d58-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>