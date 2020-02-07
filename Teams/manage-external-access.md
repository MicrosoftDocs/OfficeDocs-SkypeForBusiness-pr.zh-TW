---
title: 在 Microsoft 團隊中管理外部存取（同盟）
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
description: 您的小組或 IT 系統管理員可以為其他網域設定外部存取（同盟），讓來自這些網域的使用者參與團隊。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: eb0b252f2df1deb3e2a92bfada9a04b1df561316
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836893"
---
<a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="105a7-103">在 Microsoft 團隊中管理外部存取</span><span class="sxs-lookup"><span data-stu-id="105a7-103">Manage external access in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="105a7-104">外部存取是從整個網域中的外部團隊使用者尋找、通話、聊天，以及在團隊中設定會議的一種方式。</span><span class="sxs-lookup"><span data-stu-id="105a7-104">External access is a way for external Teams users from an entire domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="105a7-105">您也可以使用外部存取來與仍在使用商務用 Skype （線上和內部部署）及 Skype （即將2020）的外部使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-105">You can also use external access to communicate with external users who are still using Skype for Business (online and on premises) and Skype (coming in early 2020).</span></span>

<span data-ttu-id="105a7-106">如果您想讓外部使用者存取團隊和頻道，來賓存取可能是更好的作法。</span><span class="sxs-lookup"><span data-stu-id="105a7-106">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="105a7-107">如需外部存取與來賓存取之間差異的詳細資訊，請參閱[比較外部與來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="105a7-107">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="105a7-108">在下列情況中使用外部存取：</span><span class="sxs-lookup"><span data-stu-id="105a7-108">Use external access when:</span></span>
  
- <span data-ttu-id="105a7-109">您在不同網域中擁有需要共同作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="105a7-109">You have users in different domains who need to collaborate.</span></span> <span data-ttu-id="105a7-110">例如，Rob@contoso.com 和 Ann@northwindtraders.com 是與其他人一起與 contoso.com 和 northwindtraders.com 網域中的部分專案共同作業。</span><span class="sxs-lookup"><span data-stu-id="105a7-110">For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="105a7-111">您希望貴組織中的人員可以使用團隊與組織外部的特定企業中的人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="105a7-111">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="105a7-112">您希望世界各地的其他人都能使用您的電子郵件地址，找出並與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="105a7-112">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 




> [!IMPORTANT]
> <span data-ttu-id="105a7-113">目前，若要將 Microsoft 團隊應用程式內的外部使用者聯盟到您組織外部的外部使用者（目前不是 Azure Active Directory （Azure AD）或租使用者的來賓），您必須正確地設定混合式並移至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="105a7-113">Currently, to federate within the Microsoft Teams app to an external user outside of your organization who's not currently a guest of your Azure Active Directory (Azure AD) or tenant, you must be correctly set up for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="105a7-114">從2019年2月25日起，小組不支援原生同盟，且不需要 SIP 設定檔的使用者駐留在商務用 Skype Online 中。</span><span class="sxs-lookup"><span data-stu-id="105a7-114">As of February 25, 2019, Teams doesn't support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="105a7-115">如需進一步瞭解如何將您的帳戶設定成混合式，然後移至小組，請參閱將[商務用 Skype 混合式部署升級至團隊](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。</span><span class="sxs-lookup"><span data-stu-id="105a7-115">For more on setting up your account for hybrid and then moving to Teams, see [Upgrade Skype for Business hybrid deployment to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>






## <a name="plan-for-external-access"></a><span data-ttu-id="105a7-116">規劃外部存取</span><span class="sxs-lookup"><span data-stu-id="105a7-116">Plan for external access</span></span>

<span data-ttu-id="105a7-117">根據預設，會開啟 [小組] 中的外部存取，這表示您的組織可以與所有外部網域進行通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-117">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="105a7-118">如果您新增封鎖的網域，則允許所有其他網域;而且如果您新增 [允許的網域]，所有其他網域都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="105a7-118">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="105a7-119">在 [小組管理中心] 中設定外部存取的情況有三種（**全組織設定** > **外部存取**）：</span><span class="sxs-lookup"><span data-stu-id="105a7-119">There are three scenarios for setting up external access in the Teams admin center (**Org-wide settings** > **External access**):</span></span>

- <span data-ttu-id="105a7-120">**開啟同盟**：這是團隊中的預設設定，可讓組織中的人員找出、通話、聊天，以及在任何網域中與組織外部的人員進行會議。</span><span class="sxs-lookup"><span data-stu-id="105a7-120">**Open federation**: This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="105a7-121">在此案例中，您的使用者可以與執行團隊或商務用 Skype 的所有外部網域進行通訊，並使用開啟的同盟，或已將您的網域新增至其允許清單。</span><span class="sxs-lookup"><span data-stu-id="105a7-121">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="105a7-122">[**允許特定網域**]：若要將網域新增至 [**允許**] 清單，您只需將外部存取許可權制為 [允許的網域]。</span><span class="sxs-lookup"><span data-stu-id="105a7-122">**Allow specific domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="105a7-123">一旦您設定了允許的網域清單，所有其他網域都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="105a7-123">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="105a7-124">若要允許特定網域，按一下 [**新增網域**]，新增功能變數名稱，按一下 [**動作] 以在這個網域上執行**，然後選取 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-124">To allow specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Allowed**.</span></span>

- <span data-ttu-id="105a7-125">**封鎖特定網域**-只要將網域新增至**封鎖**清單，您就可以與所有外部網域通訊，*除了*您封鎖的以外。</span><span class="sxs-lookup"><span data-stu-id="105a7-125">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="105a7-126">若要封鎖特定網域，按一下 [**新增網域**]，新增功能變數名稱，按一下 [**動作] 以在這個網域上執行**，然後選取 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-126">To block specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Blocked**.</span></span> <span data-ttu-id="105a7-127">一旦您設定封鎖網域的清單，所有其他網域都會被允許。</span><span class="sxs-lookup"><span data-stu-id="105a7-127">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="105a7-128">允許或封鎖網域</span><span class="sxs-lookup"><span data-stu-id="105a7-128">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="105a7-129">步驟 1-讓您的組織與其他小組組織溝通</span><span class="sxs-lookup"><span data-stu-id="105a7-129">Step 1 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="105a7-130">![](media/teams-logo-30x30.png)**使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示  </span><span class="sxs-lookup"><span data-stu-id="105a7-130">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="105a7-131">在左側導覽中，移至 [**全組織性設定** > **外部存取**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-131">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="105a7-132">切換**使用者可以與商務用 Skype 通訊，並將小組使用者**切換到 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-132">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On**.</span></span>

     ![開啟外部訪問切換開關的螢幕擷取畫面](media/manage-external-access-2.png)<span data-ttu-id="105a7-134">.</span><span class="sxs-lookup"><span data-stu-id="105a7-134">.</span></span>

3. <span data-ttu-id="105a7-135">如果您想要讓所有團隊組織都與您組織中的使用者通訊，請跳至步驟5。</span><span class="sxs-lookup"><span data-stu-id="105a7-135">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="105a7-136">如果您想要限制可與您組織中的使用者通訊的組織，您可以允許除部分網域以外全部，或只允許特定的網域。</span><span class="sxs-lookup"><span data-stu-id="105a7-136">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="105a7-137">若要允許除部分網域以外的所有網域，請按一下 [**新增網域**]，新增您要封鎖的網域。</span><span class="sxs-lookup"><span data-stu-id="105a7-137">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="105a7-138">在 [**新增網域**] 窗格中，輸入功能變數名稱，按一下 [**封鎖**]，然後按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-138">In the **Add a domain** pane, type the domain name, click **Blocked**, and then click **Done**.</span></span> 
    - <span data-ttu-id="105a7-139">若要限制特定組織的通訊，請將這些網域新增至狀態為 [**允許**] 的清單中。</span><span class="sxs-lookup"><span data-stu-id="105a7-139">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="105a7-140">一旦您將任何網域新增至 [允許] 清單，與其他組織的通訊就會受到限制，僅限那些網域位於 [允許] 清單中的組織。</span><span class="sxs-lookup"><span data-stu-id="105a7-140">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="105a7-141">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-141">Click **Save**.</span></span>

6. <span data-ttu-id="105a7-142">確定其他小組組織中的系統管理員完成這些相同的步驟。</span><span class="sxs-lookup"><span data-stu-id="105a7-142">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="105a7-143">例如，在他們的 [**允許的網域**] 清單中，他們的系統管理員必須在限制可與使用者通訊的組織時，才能為您的企業輸入網域。</span><span class="sxs-lookup"><span data-stu-id="105a7-143">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="105a7-144">步驟 2-測試</span><span class="sxs-lookup"><span data-stu-id="105a7-144">Step 2 - Test it</span></span>

<span data-ttu-id="105a7-145">若要測試您的設定，您需要不在防火牆後的小組使用者。</span><span class="sxs-lookup"><span data-stu-id="105a7-145">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="105a7-146">在您與組織的管理員變更**外部存取**設定之後，您就應該可以開始使用。</span><span class="sxs-lookup"><span data-stu-id="105a7-146">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="105a7-147">在 [團隊] 應用程式中，搜尋人員的電子郵件地址，然後傳送要求到聊天。</span><span class="sxs-lookup"><span data-stu-id="105a7-147">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="105a7-148">請您的小組連絡人向您傳送聊天的要求。</span><span class="sxs-lookup"><span data-stu-id="105a7-148">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="105a7-149">如果您沒有收到他們的要求，問題就是您的防火牆設定（假設他們已確認其防火牆設定正確）。</span><span class="sxs-lookup"><span data-stu-id="105a7-149">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="105a7-150">測試問題是否為您防火牆的另一種方法，就是移至不在防火牆背後的 WiFi 位置。</span><span class="sxs-lookup"><span data-stu-id="105a7-150">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="105a7-151">例如咖啡廳，然後使用小組將要求傳送給您的連絡人進行聊天。</span><span class="sxs-lookup"><span data-stu-id="105a7-151">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="105a7-152">如果郵件是在 WiFi 位置進行，但不在您工作時，您知道問題是您的防火牆。</span><span class="sxs-lookup"><span data-stu-id="105a7-152">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="105a7-153">如果您與另一位使用者同時開啟外部存取並允許其他人的網域，這將會運作。</span><span class="sxs-lookup"><span data-stu-id="105a7-153">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="105a7-154">如果沒有作用，則其他使用者必須確定其設定沒有封鎖您的網域。</span><span class="sxs-lookup"><span data-stu-id="105a7-154">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="105a7-155">在商務用 Skype Online 組織中與使用者通訊</span><span class="sxs-lookup"><span data-stu-id="105a7-155">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="105a7-156">如果您要設定 [外部存取]，讓您的小組使用者在商務用 Skype 組織中找到並與使用者聯繫，以限制誰可以與其使用者聯繫，請依照步驟將您的網域中的外部存取權設定為其他組織的網域。</span><span class="sxs-lookup"><span data-stu-id="105a7-156">If you're setting up external access to let your Teams users find and contact users in a Skype for Business organization that limits who can contact their users, follow the steps to set up external access from your domain to the other organization's domain.</span></span> <span data-ttu-id="105a7-157">然後要求其他組織中的系統管理員，按照下列步驟來設定商務用 Skype Online 的外部存取。</span><span class="sxs-lookup"><span data-stu-id="105a7-157">Then ask the admin in the other organization to follow the steps below to configure external access for Skype for Business Online.</span></span> 

<span data-ttu-id="105a7-158">如需一般的商務用 Skype Online 案例的相關指導，請參閱以下[常見的外部存取案例](#common-external-access-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="105a7-158">For specific guidance on common Skype for Business Online scenarios, see [Common external access scenarios](#common-external-access-scenarios) below.</span></span>

<span data-ttu-id="105a7-159">![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="105a7-159">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="105a7-160">讓該組織中的系統管理員執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="105a7-160">Have the admin in that organization do these steps:</span></span>

1. <span data-ttu-id="105a7-161">在 Microsoft 365 系統管理中心，移至 [系統**管理中心** > ]**團隊 & Skype** > **舊版入口網站**。</span><span class="sxs-lookup"><span data-stu-id="105a7-161">In the Microsoft 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="105a7-162">在**商務用 Skype 系統管理中心**中，選擇 [**組織** > **外部通訊**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-162">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>

3. <span data-ttu-id="105a7-163">若要設定與特定企業或其他網域中的使用者通訊，請在下拉式方塊中，選擇 [**只對允許的網域開啟**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-163">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="105a7-164">或者，如果他們想要啟用與世界上已開啟商務用 Skype 原則的其他人通訊，請選擇 [**封鎖的網域除外**]。</span><span class="sxs-lookup"><span data-stu-id="105a7-164">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="105a7-165">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="105a7-165">This is the default setting.</span></span>

4. <span data-ttu-id="105a7-166">在 [**封鎖或允許**的網域**+**] 下，選擇 []，然後新增您想要允許的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="105a7-166">Under **Blocked or allowed domains**, choose **+**, and then add the name of the domain you want to allow.</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="105a7-167">常見的外部存取案例</span><span class="sxs-lookup"><span data-stu-id="105a7-167">Common external access scenarios</span></span>

|<span data-ttu-id="105a7-168">**如果您想要 .。。**</span><span class="sxs-lookup"><span data-stu-id="105a7-168">**If you want to....**</span></span>  |<span data-ttu-id="105a7-169">**執行此動作**</span><span class="sxs-lookup"><span data-stu-id="105a7-169">**Do this**</span></span>  |
|---------|-----------------------|
|<span data-ttu-id="105a7-170">讓您組織中的**小組使用者**與另一個（外部）組織中的**小組使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-170">Let **Teams users** in your organization communicate with **Teams users** in another (external) organization.</span></span>|<span data-ttu-id="105a7-171">在 [外部存取] 中，將外部網域新增至 [允許] 清單或使用 [開啟同盟]。</span><span class="sxs-lookup"><span data-stu-id="105a7-171">In External Access, add the external domain to the Allowed list or use open federation.</span></span> <span data-ttu-id="105a7-172">然後讓其他團隊組織中的系統管理員執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="105a7-172">Then have the administrator in the other Teams organization do the same thing.</span></span>      |
|<span data-ttu-id="105a7-173">讓您組織中的**小組使用者**與同一個組織中的**商務用 Skype Online 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-173">Let **Teams users**  in your organization  communicate with **Skype for Business Online users**  in the same organization.</span></span>  |<span data-ttu-id="105a7-174">啟用共存模式，或選擇孤島升級模式，以支援貴組織中的商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="105a7-174">Enable Coexistence mode or choose the Islands upgrade mode to support Skype for Business users in your organization.</span></span>   |
|<span data-ttu-id="105a7-175">讓您組織中的**小組使用者**與另一個（外部）組織中的**商務用 Skype Online 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-175">Let **Teams users** in your organization communicate with **Skype for Business Online users** in another (external) organization.</span></span>      |<span data-ttu-id="105a7-176">在 [外部存取] 中，將外部網域新增至 [允許] 清單或使用 [開啟同盟]。</span><span class="sxs-lookup"><span data-stu-id="105a7-176">In External Access, add the external domain to the Allowed list or use open federation.</span></span> <br><br><span data-ttu-id="105a7-177">開啟 [**使用者可以與商務用 Skype 和小組使用者通訊]，並**在外部存取中設定。</span><span class="sxs-lookup"><span data-stu-id="105a7-177">Turn on **Users can communicate with Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="105a7-178">然後讓其他團隊組織中的系統管理員執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="105a7-178">Then have the administrator in the other Teams organization do the same thing.</span></span> <br><br><span data-ttu-id="105a7-179">**注意**：與商務用 skype 使用者的外部網域必須啟用共存模式，或選擇孤島升級模式，以支援該組織中的商務用 skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="105a7-179">**NOTE**: The external domain with Skype for Business users must enable Coexistence mode or choose the Islands upgrade mode to support Skype for Business users in that organization.</span></span>|
|<span data-ttu-id="105a7-180">讓您組織中的**小組使用者**與您組織內部或外部的**Skype**使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-180">Let **Teams users** in your organization  communicate with **Skype** users from inside or outside your organization.</span></span>   | <span data-ttu-id="105a7-181">此案例即將推出。</span><span class="sxs-lookup"><span data-stu-id="105a7-181">This scenario is coming soon.</span></span> <br><br><span data-ttu-id="105a7-182">**重要**：您的小組使用者還無法與 Skype 使用者通訊，但您的商務用 skype 使用者可以繼續與貴組織內部或外部的 skype 使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-182">**IMPORTANT**: Your Teams users are not able to communicate with Skype users yet, but your Skype for Business users can continue to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="105a7-183">開啟**使用者可以使用商務用 Skype 與團隊使用者**，以及**商務用 skype 使用者可以**與外部存取中的 skype 使用者設定進行通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-183">Turn on the  **Users can communicate with Skype for Business and Teams users** and **Skype for Business users can communicate with Skype users** settings in External Access.</span></span> |
|<span data-ttu-id="105a7-184">讓您的**商務用 Skype Online 使用者**與另一個 Office 365 組織中的**小組使用者**進行通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-184">Let your **Skype for Business Online users** communicate with **Teams users** in another Office 365 organization.</span></span>| <span data-ttu-id="105a7-185">如果您的使用者是下列其中一種升級模式，您的商務用 Skype Online 使用者就可以與其他組織中的小組使用者通訊： Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他組織的團隊使用者都在 TeamsOnly 模式中。</span><span class="sxs-lookup"><span data-stu-id="105a7-185">Your Skype for Business Online users can communicate with Teams users in another organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Teams users are in TeamsOnly mode.</span></span> <br><br><span data-ttu-id="105a7-186">開啟 [**使用者可以與商務用 Skype 和小組使用者通訊**] 的 [外部存取] 中的 [設定]。</span><span class="sxs-lookup"><span data-stu-id="105a7-186">Turn on the **Users can communicate with Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="105a7-187">然後讓其他團隊組織中的系統管理員執行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="105a7-187">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="105a7-188">讓您的**商務用 Skype online 使用者**與其他 Office 365 組織中的**商務用 skype online 使用者**進行通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-188">Let your **Skype for Business Online users** communicate with **Skype for Business Online users** from another Office 365 organization.</span></span>    | <span data-ttu-id="105a7-189">如果您的使用者是下列其中一種升級模式，您的商務用 Skype Online 使用者可以與其他組織中的商務用 Skype Online 使用者通訊： Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他組織的商務用 Skype Online 使用者是下列其中一種升級模式： Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="105a7-189">Your Skype for Business Online users can communicate with Skype for Business Online users in another organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Skype for Business Online users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.</span></span><br><br><span data-ttu-id="105a7-190">開啟 [**使用者可以與商務用 Skype 和小組使用者通訊**] 的 [外部存取] 中的 [設定]。</span><span class="sxs-lookup"><span data-stu-id="105a7-190">Turn on the **Users can communicate with Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="105a7-191">然後讓其他團隊組織中的系統管理員執行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="105a7-191">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="105a7-192">讓您的**商務用 Skype Online 使用者**與內部部署組織中的**商務用 skype 使用者**進行通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-192">Let your **Skype for Business Online users** communicate with **Skype for Business users** from an on-premises organization.</span></span>     |<span data-ttu-id="105a7-193">如果您的使用者是下列其中一種升級模式，您的商務用 Skype Online 使用者可以與商務用 Skype 使用者進行通訊：孤島、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他組織的商務用 Skype Online 使用者是下列其中一種升級模式： Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="105a7-193">Your Skype for Business Online users can communicate with Skype for Business users from an on-premises organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Skype for Business Online users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.</span></span><br><br><span data-ttu-id="105a7-194">開啟 [**使用者可以與商務用 Skype 和小組使用者通訊**] 的 [外部存取] 中的 [設定]。</span><span class="sxs-lookup"><span data-stu-id="105a7-194">Turn on the **Users can communicate with Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="105a7-195">然後讓其他團隊組織中的系統管理員執行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="105a7-195">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="105a7-196">讓您的**商務用 Skype Online 使用者**與**skype 使用者**通訊（在您的組織內部或外部）。</span><span class="sxs-lookup"><span data-stu-id="105a7-196">Let your **Skype for Business Online users** communicate with **Skype users** (inside or outside your organization).</span></span>   |<span data-ttu-id="105a7-197">開啟 [**商務用 skype] 使用者可以與**[外部存取] 中的 [skype 使用者通訊] 設定。</span><span class="sxs-lookup"><span data-stu-id="105a7-197">Turn on the **Skype for Business users can communicate with Skype users** setting in External Access.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="105a7-198">您不需要將任何**Skype 網域**新增為 [允許的網域]，就能讓小組或商務用 Skype Online 使用者與貴組織內部或外部的 skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="105a7-198">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="105a7-199">所有**Skype 網域**都是白名單，這表示所有這些網域都被視為允許。</span><span class="sxs-lookup"><span data-stu-id="105a7-199">All **Skype domains** are whitelisted, which means all of these domains are considered ALLOWED.</span></span>



## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="105a7-200">外部存取與來賓存取有何不同？</span><span class="sxs-lookup"><span data-stu-id="105a7-200">How does external access compare with guest access?</span></span>

<span data-ttu-id="105a7-201">若要瞭解外部存取與來賓存取權之間的差異，請閱讀[與其他組織的使用者進行通訊](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="105a7-201">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="105a7-202">相關主題</span><span class="sxs-lookup"><span data-stu-id="105a7-202">Related topics</span></span>

[<span data-ttu-id="105a7-203">外部（同盟）使用者的原生聊天體驗</span><span class="sxs-lookup"><span data-stu-id="105a7-203">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
