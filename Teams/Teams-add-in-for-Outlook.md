---
title: 在 Outlook 中使用 Microsoft Teams 會議增益集
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 會在 Outlook 中安裝增益集，讓使用者從 Outlook 安排小組會議。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1cdd071dfe19c50650d6f18605a5aeed5b39300
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327845"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="0331c-103">在 Outlook 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="0331c-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="0331c-104">Teams 會議增益集可讓使用者從 Outlook 安排 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="0331c-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="0331c-105">您可以在 Windows、Mac、Web 和行動裝置上使用此增益集。</span><span class="sxs-lookup"><span data-stu-id="0331c-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="0331c-106">在 Windows 版 Outlook 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="0331c-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="0331c-107">如果使用者在 Windows 電腦上安裝了 Microsoft Teams 及 Office 2010、Office 2013 或 Office 2016，則系統就會自動為他們安裝 Teams 會議增益集。</span><span class="sxs-lookup"><span data-stu-id="0331c-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2010, Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="0331c-108">使用者會在 Outlook 行事曆功能區上看到 Teams 會議增益集。</span><span class="sxs-lookup"><span data-stu-id="0331c-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 功能區上的 Teams 會議增益集螢幕擷取畫面](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="0331c-110">若要在電腦上安裝 Teams 會議增益集，使用者必須具備執行 Regsvr32 .exe 檔案的權限。</span><span class="sxs-lookup"><span data-stu-id="0331c-110">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="0331c-111">如果使用者沒有看到 Teams 會議增益集，請指示他們關閉 Outlook 和 Teams，然後重新啟動 Teams 用戶端並登入 Teams，接著重新啟動 Outlook 用戶端 (須遵循特定順序)。</span><span class="sxs-lookup"><span data-stu-id="0331c-111">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="0331c-112">如果您使用的是 Microsoft Store 提供的 Office Outlook 安裝，則不支援 Teams 會議增益集。</span><span class="sxs-lookup"><span data-stu-id="0331c-112">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="0331c-113">針對需要此增益集的使用者，建議您安裝隨選即用的 Office，如 [Windows 10 S 模式上的 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)一文中所述。</span><span class="sxs-lookup"><span data-stu-id="0331c-113">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="0331c-114">在 Mac 版 Outlook 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="0331c-114">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="0331c-115">如果 Outlook 執行的是生產組建 16.24.414.0 及更新版本，且已透過 Office 365 用戶端訂閱啟用，則 Mac 版 Outlook 的 Teams 會議按鈕會出現在 Mac 版 Outlook 的功能區中。</span><span class="sxs-lookup"><span data-stu-id="0331c-115">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with an Office 365 client subscription.</span></span>

<span data-ttu-id="0331c-116">當使用者按一下 [傳送]\*\*\*\* 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="0331c-116">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="0331c-117">在 Outlook Web App 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="0331c-117">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="0331c-118">如果使用者使用最新 Outlook 網頁版的早期版本，則 Outlook Web App 中的 Teams 會議按鈕將會在建立新事件時顯示。</span><span class="sxs-lookup"><span data-stu-id="0331c-118">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="0331c-119">請參閱 [Outlook 部落格](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)，了解使用者如何試用最新 Outlook 網頁版的早期版本。</span><span class="sxs-lookup"><span data-stu-id="0331c-119">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App 中 Teams 會議增益集的螢幕擷取畫面](media/teams-meeting-add-in-web.png)

<span data-ttu-id="0331c-121">當使用者按一下 [傳送]\*\*\*\* 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="0331c-121">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="0331c-122">Outlook Mobile (iOS 和 Android) 中的 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="0331c-122">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="0331c-123">Teams 會議按鈕會顯示在 Outlook iOS 和 Android 應用程式的最新組建中。</span><span class="sxs-lookup"><span data-stu-id="0331c-123">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook Mobile 中 Teams 會議增益集的螢幕擷取畫面](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="0331c-125">當使用者按一下 [傳送]\*\*\*\* 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="0331c-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a><span data-ttu-id="0331c-126">Teams 會議增益集和適用於 Outlook 的 FindTime</span><span class="sxs-lookup"><span data-stu-id="0331c-126">Teams Meeting add-in in and FindTime for Outlook</span></span>
<span data-ttu-id="0331c-127">FindTime 是 Outlook 的增益集，可協助使用者在跨公司會議的時間安排上達成共識。</span><span class="sxs-lookup"><span data-stu-id="0331c-127">FindTime is an add-in for Outlook that helps users reach a consensus on a meeting time across companies.</span></span> <span data-ttu-id="0331c-128">當會議受邀者提供其偏好的時間後，FindTime 就會代表使用者傳送會議邀請。</span><span class="sxs-lookup"><span data-stu-id="0331c-128">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="0331c-129">如果 FindTime 中已選取 [線上會議]\*\*\*\* 選項，則 FindTime 會安排商務用 Skype 或 Microsoft Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="0331c-129">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="0331c-130">(FindTime 會使用由您組織設定的任何項目作為預設的線上會議頻道)。</span><span class="sxs-lookup"><span data-stu-id="0331c-130">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="0331c-131">如果您已在 [FindTime 儀表板](https://findtime.microsoft.com/UserDashboard)中儲存商務用 Skype 的設定，FindTime 就會使用該設定，而不是使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0331c-131">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="0331c-132">如果您想要使用 Microsoft Teams，請刪除儀表板中的商務用 Skype 設定。</span><span class="sxs-lookup"><span data-stu-id="0331c-132">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="0331c-133">如需詳細資訊，請參閱[使用 FindTime 安排會議](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。</span><span class="sxs-lookup"><span data-stu-id="0331c-133">See [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) for more information.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="0331c-134">驗證需求</span><span class="sxs-lookup"><span data-stu-id="0331c-134">Authentication requirements</span></span>

<span data-ttu-id="0331c-135">Teams 會議增益集需要使用者使用新式驗證來登入 Teams。</span><span class="sxs-lookup"><span data-stu-id="0331c-135">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="0331c-136">如果使用者不是使用此方法登入，他們仍然可以使用 Teams 用戶端，但是無法使用 Outlook 增益集來安排 Teams 線上會議。</span><span class="sxs-lookup"><span data-stu-id="0331c-136">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="0331c-137">若要修正此問題，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="0331c-137">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="0331c-138">如果您的組織未設定新式驗證，則您應設定新式驗證。</span><span class="sxs-lookup"><span data-stu-id="0331c-138">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="0331c-139">如果已設定新式驗證，但在對話方塊中將其取消，您應指示使用者使用多重要素驗證再次登入。</span><span class="sxs-lookup"><span data-stu-id="0331c-139">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="0331c-140">若要深入了解如何設定驗證，請參閱 [Microsoft Teams 中的身分識別模型與驗證](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="0331c-140">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="0331c-141">啟用私人會議</span><span class="sxs-lookup"><span data-stu-id="0331c-141">Enable private meetings</span></span>

<span data-ttu-id="0331c-142">必須在 Microsoft Teams 系統管理中心啟用 [允許私人會議排程]\*\*\*\*，才能部署此增益集。</span><span class="sxs-lookup"><span data-stu-id="0331c-142">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="0331c-143">在系統管理中心中，移至 [會議]\*\*\*\* > [會議原則]\*\*\*\*，並在 [一般]\*\*\*\* 區段中，將 [允許私人會議排程]\*\*\*\* 切換為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="0331c-143">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams 系統管理中心的設定螢幕擷取畫面。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="0331c-145">Teams 用戶端會藉由判斷使用者需要 32 位元或 64 位元版本，來安裝正確的增益集。</span><span class="sxs-lookup"><span data-stu-id="0331c-145">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="0331c-146">在安裝或升級 Teams 之後，使用者可能需要重新啟動 Outlook，才能取得最新的增益集。</span><span class="sxs-lookup"><span data-stu-id="0331c-146">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="0331c-147">Teams 升級原則和適用於 Outlook 的 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="0331c-147">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="0331c-148">客戶可以[選擇從商務用 Skype 升級到 Teams 的作業過程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0331c-148">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="0331c-149">租用戶系統管理員可以使用 Teams 共存模式來為使用者定義此過程。</span><span class="sxs-lookup"><span data-stu-id="0331c-149">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="0331c-150">租用戶系統管理員可以選擇讓使用者並行使用 Teams 和商務用 Skype (離島模式)。</span><span class="sxs-lookup"><span data-stu-id="0331c-150">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="0331c-151">當使用離島模式的使用者在 Outlook 中安排會議時，他們通常能夠選擇要安排商務用 Skype 或 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="0331c-151">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="0331c-152">在 Outlook 網頁版、Outlook Windows 和 Outlook Mac 中，使用者可在離島模式中看到商務用 Skype 和 Teams 增益集。</span><span class="sxs-lookup"><span data-stu-id="0331c-152">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode.</span></span> <span data-ttu-id="0331c-153">由於初次發行時的特定限制，Outlook Mobile 只能支援建立商務用 Skype **或** Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="0331c-153">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="0331c-154">請參閱下列資料表以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0331c-154">See the following table for details.</span></span>

| <span data-ttu-id="0331c-155">Teams 系統管理中心的共存模式</span><span class="sxs-lookup"><span data-stu-id="0331c-155">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="0331c-156">Outlook Mobile 中的預設會議提供者</span><span class="sxs-lookup"><span data-stu-id="0331c-156">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="0331c-157">離島</span><span class="sxs-lookup"><span data-stu-id="0331c-157">Islands</span></span> | <span data-ttu-id="0331c-158">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="0331c-158">Skype for Business</span></span> |
| <span data-ttu-id="0331c-159">僅商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="0331c-159">Skype for Business only</span></span> | <span data-ttu-id="0331c-160">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="0331c-160">Skype for Business</span></span> |
| <span data-ttu-id="0331c-161">商務用 Skype 搭配 Teams 共同作業</span><span class="sxs-lookup"><span data-stu-id="0331c-161">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="0331c-162">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="0331c-162">Skype for Business</span></span> |
| <span data-ttu-id="0331c-163">商務用 Skype 搭配 Teams 共同作業和會議</span><span class="sxs-lookup"><span data-stu-id="0331c-163">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="0331c-164">Teams</span><span class="sxs-lookup"><span data-stu-id="0331c-164">Teams</span></span> |
| <span data-ttu-id="0331c-165">僅 Teams</span><span class="sxs-lookup"><span data-stu-id="0331c-165">Teams only</span></span> | <span data-ttu-id="0331c-166">Teams</span><span class="sxs-lookup"><span data-stu-id="0331c-166">Teams</span></span> |

## <a name="other-considerations"></a><span data-ttu-id="0331c-167">其他考量事項</span><span class="sxs-lookup"><span data-stu-id="0331c-167">Other considerations</span></span>

<span data-ttu-id="0331c-168">Teams 會議增益集是仍在建置的功能，因此請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="0331c-168">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="0331c-169">此增益集適用於具有特定參與者的排程會議 (不適用於頻道中的會議)。</span><span class="sxs-lookup"><span data-stu-id="0331c-169">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="0331c-170">頻道會議必須從 Teams 內排程。</span><span class="sxs-lookup"><span data-stu-id="0331c-170">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="0331c-171">如果驗證 Proxy 位於使用者 PC 與 Teams 服務的網路路徑，則增益集將無法運作。</span><span class="sxs-lookup"><span data-stu-id="0331c-171">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="0331c-172">使用者無法從 Outlook 中安排即時活動。</span><span class="sxs-lookup"><span data-stu-id="0331c-172">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="0331c-173">請移至 Teams 以安排即時活動。</span><span class="sxs-lookup"><span data-stu-id="0331c-173">Go to Teams to schedule live events.</span></span> <span data-ttu-id="0331c-174">如需詳細資訊，請參閱[什麼是 Microsoft Teams 即時活動？](teams-live-events/what-are-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="0331c-174">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0331c-175">疑難排解</span><span class="sxs-lookup"><span data-stu-id="0331c-175">Troubleshooting</span></span>

<span data-ttu-id="0331c-176">如果您無法取得適用於 Outlook 的 Teams 會議增益集，請嘗試這些疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="0331c-176">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="0331c-177">請確定已套用所有適用於 Outlook 桌面版用戶端的更新。</span><span class="sxs-lookup"><span data-stu-id="0331c-177">Ensure all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="0331c-178">重新啟動 Teams 桌面版用戶端。</span><span class="sxs-lookup"><span data-stu-id="0331c-178">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="0331c-179">登出 Teams 桌面用戶端，然後重新登入。</span><span class="sxs-lookup"><span data-stu-id="0331c-179">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="0331c-180">重新啟動 Outlook 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="0331c-180">Restart the Outlook desktop client.</span></span> <span data-ttu-id="0331c-181">(請確定 Outlook 不是以 [系統管理員模式] 執行)。</span><span class="sxs-lookup"><span data-stu-id="0331c-181">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="0331c-182">請確認登入的使用者帳戶名稱不含空格。</span><span class="sxs-lookup"><span data-stu-id="0331c-182">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="0331c-183">(這是已知的問題，我們會在未來更新中修正。)</span><span class="sxs-lookup"><span data-stu-id="0331c-183">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="0331c-184">請確定已啟用單一登入 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="0331c-184">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="0331c-185">如果您的系統管理員已將 Microsoft Exchange 設定為[控制對 Exchange Web 服務器 (EWS) 的存取](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，代理人將無法代表老闆安排 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="0331c-185">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="0331c-186">此設定的解決方案正在開發中，即將在未來發行。</span><span class="sxs-lookup"><span data-stu-id="0331c-186">The solution for this configuration is under development and will be released in the future.</span></span> 

<span data-ttu-id="0331c-187">如需有關如何停用增益集的一般指導方針，請參閱[在 Office 程式中檢視、管理及安裝增益集](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。</span><span class="sxs-lookup"><span data-stu-id="0331c-187">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="0331c-188">深入了解 [Microsoft Teams 中的會議和通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="0331c-188">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
