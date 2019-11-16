---
title: 在 Outlook 中使用 Microsoft 團隊會議增益集
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft 團隊會在 Outlook 中安裝增益集，讓使用者從 Outlook 排程團隊會議。
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89f9ba68dd4fbd1cef271c0dd0a3fb73e10637a7
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38626979"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="50fec-103">在 Outlook 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="50fec-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="50fec-104">[團隊會議] 增益集可讓使用者從 Outlook 排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="50fec-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="50fec-105">您可以在 Windows 版、Mac 版、web 版和行動裝置上使用該增益集。</span><span class="sxs-lookup"><span data-stu-id="50fec-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="50fec-106">Windows 版 Outlook 中的團隊會議增益集</span><span class="sxs-lookup"><span data-stu-id="50fec-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="50fec-107">[團隊會議] 增益集會自動安裝在 Windows 電腦上安裝 Microsoft 團隊以及 Office 2010、Office 2013 或 Office 2016 的使用者。</span><span class="sxs-lookup"><span data-stu-id="50fec-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2010, Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="50fec-108">使用者會在 Outlook 行事曆功能區上看到 [團隊會議] 增益集。</span><span class="sxs-lookup"><span data-stu-id="50fec-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 功能區上 [團隊會議] 增益集的螢幕擷取畫面](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="50fec-110">執行 Regsvr32 檔案的使用者許可權對於要在電腦上安裝的小組會議增益集而言，是最低的需求。</span><span class="sxs-lookup"><span data-stu-id="50fec-110">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="50fec-111">如果使用者沒有看到 [團隊會議] 增益集，請指示他們關閉 Outlook 和團隊，然後先重新開機團隊用戶端，然後登入小組，然後以該特定順序重新開機 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="50fec-111">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="50fec-112">Windows 7 使用者必須在 Windows 的 windows 中安裝[通用 C 執行時間更新](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)，小組會議增益集才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="50fec-112">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) in Windows for the Teams Meeting add-in to work.</span></span>
> - <span data-ttu-id="50fec-113">如果您是從 Microsoft 網上商店使用 Office Outlook 安裝，則不支援 [團隊會議] 增益集。</span><span class="sxs-lookup"><span data-stu-id="50fec-113">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="50fec-114">建議需要此增益集的使用者安裝隨選即用版本的 Office，如[Windows 10 中的 office 在 S 模式](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)文章中所述。</span><span class="sxs-lookup"><span data-stu-id="50fec-114">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>


## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="50fec-115">Mac 版 Outlook 中的團隊會議增益集</span><span class="sxs-lookup"><span data-stu-id="50fec-115">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="50fec-116">如果 Outlook 執行 [生產組建16.24.414.0 及更新版本]，Mac 版 Outlook 中的 [小組會議] 按鈕就會出現在 Mac 版 Outlook 功能區中。</span><span class="sxs-lookup"><span data-stu-id="50fec-116">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running Production Build 16.24.414.0 and later.</span></span>

<span data-ttu-id="50fec-117">使用者按一下 [**傳送**] 之後，會議座標（團隊加入連結和撥入號碼）就會新增到會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="50fec-117">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="50fec-118">Outlook Web App 中的團隊會議增益集</span><span class="sxs-lookup"><span data-stu-id="50fec-118">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="50fec-119">如果使用者是在新版 Outlook 網頁版上，Outlook Web App 中的 [小組會議] 按鈕就會顯示為新的事件建立的一部分。</span><span class="sxs-lookup"><span data-stu-id="50fec-119">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="50fec-120">若要瞭解使用者如何試用新版 Outlook 網頁版的相關資訊，請參閱[Outlook 博客](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)。</span><span class="sxs-lookup"><span data-stu-id="50fec-120">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App 中的團隊會議增益集的螢幕擷取畫面](media/teams-meeting-add-in-web.png)

<span data-ttu-id="50fec-122">使用者按一下 [**傳送**] 之後，會議座標（團隊加入連結和撥入號碼）就會新增到會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="50fec-122">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="50fec-123">Outlook mobile 中的團隊會議增益集（iOS 版和 Android 版）</span><span class="sxs-lookup"><span data-stu-id="50fec-123">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="50fec-124">[團隊會議] 按鈕會顯示在最新的 Outlook iOS 和 Android 應用程式組建中。</span><span class="sxs-lookup"><span data-stu-id="50fec-124">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook mobile 中的團隊會議增益集的螢幕擷取畫面](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="50fec-126">使用者按一下 [**傳送**] 之後，會議座標（團隊加入連結和撥入號碼）就會新增到會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="50fec-126">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a><span data-ttu-id="50fec-127">Outlook 中的團隊會議增益集與 FindTime</span><span class="sxs-lookup"><span data-stu-id="50fec-127">Teams Meeting add-in in and FindTime for Outlook</span></span>
<span data-ttu-id="50fec-128">FindTime 是 Outlook 的增益集，可協助使用者在整個公司的會議時間達成共識。</span><span class="sxs-lookup"><span data-stu-id="50fec-128">FindTime is an add-in for Outlook that helps users reach a consensus on a meeting time across companies.</span></span> <span data-ttu-id="50fec-129">一旦會議受邀者提供其喜好的時間，FindTime 就會代表使用者傳送會議邀請。</span><span class="sxs-lookup"><span data-stu-id="50fec-129">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="50fec-130">如果您已在 FindTime 中選取 [**線上會議**] 選項，FindTime 將會安排商務用 Skype 或 Microsoft 團隊會議。</span><span class="sxs-lookup"><span data-stu-id="50fec-130">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="50fec-131">（FindTime 將使用貴組織設定為預設線上會議頻道的任何人）。</span><span class="sxs-lookup"><span data-stu-id="50fec-131">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="50fec-132">如果您已在[Findtime 儀表板](https://findtime.microsoft.com/UserDashboard)中儲存商務用 Skype 設定，Findtime 將會使用，而不是 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="50fec-132">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="50fec-133">如果您想要使用 Microsoft 團隊，請刪除儀表板中的 [商務用 Skype] 設定。</span><span class="sxs-lookup"><span data-stu-id="50fec-133">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="50fec-134">如需詳細資訊，請參閱[使用 FindTime 排程會議](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。</span><span class="sxs-lookup"><span data-stu-id="50fec-134">See [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) for more information.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="50fec-135">驗證需求</span><span class="sxs-lookup"><span data-stu-id="50fec-135">Authentication requirements</span></span>

<span data-ttu-id="50fec-136">團隊會議增益集需要使用者使用新式驗證登入小組。</span><span class="sxs-lookup"><span data-stu-id="50fec-136">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="50fec-137">如果使用者不使用此方法登入，他們仍能使用團隊用戶端，但無法使用 Outlook 增益集來排程小組線上會議。</span><span class="sxs-lookup"><span data-stu-id="50fec-137">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="50fec-138">您可以執行下列其中一項操作來修正此問題：</span><span class="sxs-lookup"><span data-stu-id="50fec-138">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="50fec-139">如果您的組織未設定新式驗證，您應該設定新式驗證。</span><span class="sxs-lookup"><span data-stu-id="50fec-139">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="50fec-140">如果已設定新式驗證，但它們在對話方塊中取消，您應該指示使用者使用多重要素驗證重新登入。</span><span class="sxs-lookup"><span data-stu-id="50fec-140">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="50fec-141">若要深入瞭解如何設定驗證，請參閱[Microsoft 團隊中的身分識別模型和驗證](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="50fec-141">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="50fec-142">啟用私人會議</span><span class="sxs-lookup"><span data-stu-id="50fec-142">Enable private meetings</span></span>

<span data-ttu-id="50fec-143">[**允許針對私人會議進行排程**] 必須在 Microsoft [團隊管理中心] 中啟用，才能部署該增益集。</span><span class="sxs-lookup"><span data-stu-id="50fec-143">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="50fec-144">在系統管理中心中，移至 [**會議** > **會議原則**]，然後在 [一般] 區段中，切換到 **[** **允許將私人會議排程**至]。）</span><span class="sxs-lookup"><span data-stu-id="50fec-144">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft 團隊系統管理中心中設定的螢幕擷取畫面。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="50fec-146">團隊用戶端可決定使用者是否需要32位或64位版本，以安裝正確的增益集。</span><span class="sxs-lookup"><span data-stu-id="50fec-146">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="50fec-147">在安裝或升級小組之後，使用者可能需要重新開機 Outlook，才能取得最新的增益集。</span><span class="sxs-lookup"><span data-stu-id="50fec-147">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="50fec-148">團隊升級原則與適用于 Outlook 的小組會議增益集</span><span class="sxs-lookup"><span data-stu-id="50fec-148">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="50fec-149">客戶可以[選擇從商務用 Skype 升級到團隊](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="50fec-149">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="50fec-150">租使用者管理員可以使用 [團隊共存] 模式來為使用者定義這種旅程。</span><span class="sxs-lookup"><span data-stu-id="50fec-150">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="50fec-151">租使用者系統管理員可以選擇讓使用者在商務用 Skype （孤島模式）中使用團隊。</span><span class="sxs-lookup"><span data-stu-id="50fec-151">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="50fec-152">當以孤島模式在 Outlook 中排程會議的使用者，他們通常會希望能夠選擇要排程商務用 Skype 或團隊會議。</span><span class="sxs-lookup"><span data-stu-id="50fec-152">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="50fec-153">在 Outlook 網頁版、Outlook 視窗和 Outlook Mac 版中，使用者會在孤島模式中同時看到 [商務用 Skype] 和 [團隊] 增益集。</span><span class="sxs-lookup"><span data-stu-id="50fec-153">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode.</span></span> <span data-ttu-id="50fec-154">由於初次發行中的某些限制，Outlook mobile 只支援建立商務用 Skype**或**團隊會議。</span><span class="sxs-lookup"><span data-stu-id="50fec-154">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="50fec-155">如需詳細資訊，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="50fec-155">See the following table for details.</span></span>

| <span data-ttu-id="50fec-156">[團隊管理中心] 中的共存模式</span><span class="sxs-lookup"><span data-stu-id="50fec-156">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="50fec-157">Outlook mobile 中的預設會議提供者</span><span class="sxs-lookup"><span data-stu-id="50fec-157">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="50fec-158">索羅門群島</span><span class="sxs-lookup"><span data-stu-id="50fec-158">Islands</span></span> | <span data-ttu-id="50fec-159">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="50fec-159">Skype for Business</span></span> |
| <span data-ttu-id="50fec-160">僅適用于商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="50fec-160">Skype for Business only</span></span> | <span data-ttu-id="50fec-161">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="50fec-161">Skype for Business</span></span> |
| <span data-ttu-id="50fec-162">商務用 Skype 與團隊共同作業</span><span class="sxs-lookup"><span data-stu-id="50fec-162">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="50fec-163">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="50fec-163">Skype for Business</span></span> |
| <span data-ttu-id="50fec-164">商務用 Skype 與團隊共同作業與會議</span><span class="sxs-lookup"><span data-stu-id="50fec-164">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="50fec-165">團隊</span><span class="sxs-lookup"><span data-stu-id="50fec-165">Teams</span></span> |
| <span data-ttu-id="50fec-166">僅限團隊</span><span class="sxs-lookup"><span data-stu-id="50fec-166">Teams only</span></span> | <span data-ttu-id="50fec-167">團隊</span><span class="sxs-lookup"><span data-stu-id="50fec-167">Teams</span></span> |

## <a name="other-considerations"></a><span data-ttu-id="50fec-168">其他考慮</span><span class="sxs-lookup"><span data-stu-id="50fec-168">Other considerations</span></span>

<span data-ttu-id="50fec-169">[團隊會議] 增益集仍在建立功能，因此請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="50fec-169">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="50fec-170">該增益集是針對特定參與者的排程會議，而不是頻道中的會議。</span><span class="sxs-lookup"><span data-stu-id="50fec-170">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="50fec-171">頻道會議必須在小組內排程。</span><span class="sxs-lookup"><span data-stu-id="50fec-171">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="50fec-172">如果驗證 Proxy 位於使用者的電腦和團隊服務的網路路徑中，增益集將無法運作。</span><span class="sxs-lookup"><span data-stu-id="50fec-172">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="50fec-173">使用者無法在 Outlook 中排程即時事件。</span><span class="sxs-lookup"><span data-stu-id="50fec-173">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="50fec-174">移至 [小組]，排程即時事件。</span><span class="sxs-lookup"><span data-stu-id="50fec-174">Go to Teams to schedule live events.</span></span> <span data-ttu-id="50fec-175">如需詳細資訊，請參閱[什麼是 Microsoft 團隊即時事件？](teams-live-events/what-are-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="50fec-175">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="50fec-176">疑難排解</span><span class="sxs-lookup"><span data-stu-id="50fec-176">Troubleshooting</span></span>

<span data-ttu-id="50fec-177">如果您無法取得供 Outlook 安裝的小組會議增益集，請嘗試這些疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="50fec-177">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="50fec-178">確保已套用所有適用于 Outlook 桌面用戶端的更新。</span><span class="sxs-lookup"><span data-stu-id="50fec-178">Ensure all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="50fec-179">重新開機團隊桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="50fec-179">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="50fec-180">登出，然後重新登入小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="50fec-180">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="50fec-181">重新開機 Outlook 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="50fec-181">Restart the Outlook desktop client.</span></span> <span data-ttu-id="50fec-182">（請確定 Outlook 未在系統管理員模式下執行）。</span><span class="sxs-lookup"><span data-stu-id="50fec-182">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="50fec-183">請確認登入的使用者帳戶名稱不包含空格。</span><span class="sxs-lookup"><span data-stu-id="50fec-183">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="50fec-184">（這是已知的問題，將于未來更新中修正。）</span><span class="sxs-lookup"><span data-stu-id="50fec-184">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="50fec-185">請確定已啟用單一登入（SSO）。</span><span class="sxs-lookup"><span data-stu-id="50fec-185">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="50fec-186">如果您的系統管理員已設定 Microsoft Exchange 來[控制 Exchange Web Server （EWS）的存取權](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，則代理人將無法代表老闆排程小組會議。</span><span class="sxs-lookup"><span data-stu-id="50fec-186">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="50fec-187">此設定的解決方案位於開發階段，未來將會發佈。</span><span class="sxs-lookup"><span data-stu-id="50fec-187">The solution for this configuration is under development and will be released in the future.</span></span> 

<span data-ttu-id="50fec-188">如需如何停用增益集的一般指導方針，請參閱[在 Office 程式中查看、管理及安裝增益集](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。</span><span class="sxs-lookup"><span data-stu-id="50fec-188">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="50fec-189">深入瞭解[Microsoft 團隊中的會議和通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="50fec-189">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
