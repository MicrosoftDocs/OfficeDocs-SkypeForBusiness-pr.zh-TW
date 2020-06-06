---
title: 在 Outlook 中使用 Microsoft Teams 會議增益集
author: LanaChin
ms.author: v-lanac
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
ms.openlocfilehash: de92e52b50ce863ba940badbdeff32c90f083fde
ms.sourcegitcommit: 8395f91205bde549a0a92999ef00c5f5fb03fb80
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2020
ms.locfileid: "44583436"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="6ec8b-103">在 Outlook 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="6ec8b-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="6ec8b-104">Teams 會議增益集可讓使用者從 Outlook 安排 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="6ec8b-105">您可以在 Windows、Mac、Web 和行動裝置上使用此增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="6ec8b-106">在 Windows 版 Outlook 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="6ec8b-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="6ec8b-107">[團隊會議] 增益集會自動安裝在 Windows 電腦上安裝 Microsoft 團隊以及 Office 2013、Office 2016 或 Office 2019 的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013, Office 2016, or Office 2019 installed on their Windows PC.</span></span> <span data-ttu-id="6ec8b-108">使用者會在 Outlook 行事曆功能區上看到 Teams 會議增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 功能區上的 Teams 會議增益集螢幕擷取畫面](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="6ec8b-110">沒有連結至 [團隊] 增益集的**直接 URL** 。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-110">There is **no direct URL** that links to the Teams add-in.</span></span>
> - <span data-ttu-id="6ec8b-111">如果您的組織同時執行 [團隊] 和 [商務用 Skype]，也會有其他的考慮。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-111">There are additional considerations if your organization runs both Teams and Skype for Business.</span></span> <span data-ttu-id="6ec8b-112">在某些情況下，Outlook 中不提供 [團隊] 增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-112">Under some circumstances, the Teams add-in is not available in Outlook.</span></span> <span data-ttu-id="6ec8b-113">如需詳細資訊，請參閱[從商務用 Skype 升級至小組](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-113">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for details.</span></span>
> - <span data-ttu-id="6ec8b-114">若要在電腦上安裝 Teams 會議增益集，使用者必須具備執行 Regsvr32 .exe 檔案的權限。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-114">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="6ec8b-115">如果使用者沒有看到 Teams 會議增益集，請指示他們關閉 Outlook 和 Teams，然後重新啟動 Teams 用戶端並登入 Teams，接著重新啟動 Outlook 用戶端 (須遵循特定順序)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-115">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="6ec8b-116">如果您使用的是 Microsoft Store 提供的 Office Outlook 安裝，則不支援 Teams 會議增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-116">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="6ec8b-117">針對需要此增益集的使用者，建議您安裝隨選即用的 Office，如 [Windows 10 S 模式上的 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)一文中所述。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-117">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="6ec8b-118">在 Mac 版 Outlook 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="6ec8b-118">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="6ec8b-119">Outlook for Mac 中的 [小組會議] 按鈕會顯示在 outlook for Mac 功能區中（如果 Outlook 執行的是「生產」組建16.24.414.0 及更新版本），且是使用 Microsoft 365 或 Office 365 用戶端訂閱啟動。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-119">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with a Microsoft 365 or Office 365 client subscription.</span></span>

<span data-ttu-id="6ec8b-120">當使用者按一下 [傳送]\*\*\*\* 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-120">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="6ec8b-121">在 Outlook Web App 中使用 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="6ec8b-121">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="6ec8b-122">如果使用者使用最新 Outlook 網頁版的早期版本，則 Outlook Web App 中的 Teams 會議按鈕將會在建立新事件時顯示。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-122">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="6ec8b-123">請參閱 [Outlook 部落格](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)，了解使用者如何試用最新 Outlook 網頁版的早期版本。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-123">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App 中 Teams 會議增益集的螢幕擷取畫面](media/teams-meeting-add-in-web.png)

<span data-ttu-id="6ec8b-125">當使用者按一下 [傳送]\*\*\*\* 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="6ec8b-126">Outlook Mobile (iOS 和 Android) 中的 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="6ec8b-126">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="6ec8b-127">Teams 會議按鈕會顯示在 Outlook iOS 和 Android 應用程式的最新組建中。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-127">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook Mobile 中 Teams 會議增益集的螢幕擷取畫面](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="6ec8b-129">當使用者按一下 [傳送]\*\*\*\* 之後，會議座標 (Teams 的加入連結和撥入號碼) 將會新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-129">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a><span data-ttu-id="6ec8b-130">Teams 會議增益集和適用於 Outlook 的 FindTime</span><span class="sxs-lookup"><span data-stu-id="6ec8b-130">Teams Meeting add-in in and FindTime for Outlook</span></span>

<span data-ttu-id="6ec8b-131">FindTime 是 Outlook 的增益集，可協助使用者在整個公司的會議時間達成共識。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-131">FindTime is an add-in for Outlook that helps users reach consensus on a meeting time across companies.</span></span> <span data-ttu-id="6ec8b-132">當會議受邀者提供其偏好的時間後，FindTime 就會代表使用者傳送會議邀請。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-132">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="6ec8b-133">如果 FindTime 中已選取 [線上會議]\*\*\*\* 選項，則 FindTime 會安排商務用 Skype 或 Microsoft Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-133">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="6ec8b-134">(FindTime 會使用由您組織設定的任何項目作為預設的線上會議頻道)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-134">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="6ec8b-135">如果您已在 [FindTime 儀表板](https://findtime.microsoft.com/UserDashboard)中儲存商務用 Skype 的設定，FindTime 就會使用該設定，而不是使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-135">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="6ec8b-136">如果您想要使用 Microsoft Teams，請刪除儀表板中的商務用 Skype 設定。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-136">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="6ec8b-137">如需詳細資訊，請參閱[使用 FindTime 排程會議](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-137">For more information, see [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="6ec8b-138">驗證需求</span><span class="sxs-lookup"><span data-stu-id="6ec8b-138">Authentication requirements</span></span>

<span data-ttu-id="6ec8b-139">Teams 會議增益集需要使用者使用新式驗證來登入 Teams。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-139">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="6ec8b-140">如果使用者不使用此方法登入，他們仍能使用團隊用戶端，但無法使用 Outlook 增益集來排程小組線上會議。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-140">If users do not use this method to sign in, they'll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="6ec8b-141">若要修正此問題，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="6ec8b-141">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="6ec8b-142">如果您的組織未設定新式驗證，則您應設定新式驗證。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-142">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="6ec8b-143">如果已設定新式驗證，但在對話方塊中將其取消，您應指示使用者使用多重要素驗證再次登入。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-143">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="6ec8b-144">若要深入了解如何設定驗證，請參閱 [Microsoft Teams 中的身分識別模型與驗證](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-144">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="6ec8b-145">啟用私人會議</span><span class="sxs-lookup"><span data-stu-id="6ec8b-145">Enable private meetings</span></span>

<span data-ttu-id="6ec8b-146">必須在 Microsoft Teams 系統管理中心啟用 [允許私人會議排程]\*\*\*\*，才能部署此增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-146">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="6ec8b-147">在系統管理中心中，移至 [會議]\*\*\*\* > [會議原則]\*\*\*\*，並在 [一般]\*\*\*\* 區段中，將 [允許私人會議排程]\*\*\*\* 切換為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-147">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams 系統管理中心的設定螢幕擷取畫面。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="6ec8b-149">Teams 用戶端會藉由判斷使用者需要 32 位元或 64 位元版本，來安裝正確的增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-149">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="6ec8b-150">在安裝或升級 Teams 之後，使用者可能需要重新啟動 Outlook，才能取得最新的增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-150">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="6ec8b-151">Teams 升級原則和適用於 Outlook 的 Teams 會議增益集</span><span class="sxs-lookup"><span data-stu-id="6ec8b-151">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="6ec8b-152">客戶可以[選擇從商務用 Skype 升級到 Teams 的作業過程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-152">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="6ec8b-153">租用戶系統管理員可以使用 Teams 共存模式來為使用者定義此過程。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-153">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="6ec8b-154">租用戶系統管理員可以選擇讓使用者並行使用 Teams 和商務用 Skype (離島模式)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-154">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="6ec8b-155">當使用離島模式的使用者在 Outlook 中安排會議時，他們通常能夠選擇要安排商務用 Skype 或 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-155">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="6ec8b-156">在 Outlook 網頁版、Outlook Windows 版和 Outlook Mac 版中，使用者會在預設使用孤島模式時，看到 [商務用 Skype] 和 [團隊] 增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-156">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode by default.</span></span> <span data-ttu-id="6ec8b-157">您可以設定 [團隊會議原則] 設定來控制 [孤島] 模式中的使用者只能使用 [團隊會議] 增益集，或是同時使用 [團隊會議] 和 [商務用 Skype 會議] 增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-157">You can configure a Teams meeting policy setting to control whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins.</span></span>

<span data-ttu-id="6ec8b-158">由於初次發行時的特定限制，Outlook Mobile 只能支援建立商務用 Skype **或** Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-158">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="6ec8b-159">請參閱下列資料表以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-159">See the following table for details.</span></span>

| <span data-ttu-id="6ec8b-160">Teams 系統管理中心的共存模式</span><span class="sxs-lookup"><span data-stu-id="6ec8b-160">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="6ec8b-161">Outlook Mobile 中的預設會議提供者</span><span class="sxs-lookup"><span data-stu-id="6ec8b-161">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="6ec8b-162">離島</span><span class="sxs-lookup"><span data-stu-id="6ec8b-162">Islands</span></span> | <span data-ttu-id="6ec8b-163">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="6ec8b-163">Skype for Business</span></span> |
| <span data-ttu-id="6ec8b-164">僅商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="6ec8b-164">Skype for Business only</span></span> | <span data-ttu-id="6ec8b-165">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="6ec8b-165">Skype for Business</span></span> |
| <span data-ttu-id="6ec8b-166">商務用 Skype 搭配 Teams 共同作業</span><span class="sxs-lookup"><span data-stu-id="6ec8b-166">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="6ec8b-167">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="6ec8b-167">Skype for Business</span></span> |
| <span data-ttu-id="6ec8b-168">商務用 Skype 搭配 Teams 共同作業和會議</span><span class="sxs-lookup"><span data-stu-id="6ec8b-168">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="6ec8b-169">Teams</span><span class="sxs-lookup"><span data-stu-id="6ec8b-169">Teams</span></span> |
| <span data-ttu-id="6ec8b-170">僅 Teams</span><span class="sxs-lookup"><span data-stu-id="6ec8b-170">Teams only</span></span> | <span data-ttu-id="6ec8b-171">Teams</span><span class="sxs-lookup"><span data-stu-id="6ec8b-171">Teams</span></span> |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a><span data-ttu-id="6ec8b-172">設定 [孤島] 模式中的使用者是否只能使用 [團隊會議] 增益集，或同時使用團隊會議增益集及商務用 Skype 會議增益集</span><span class="sxs-lookup"><span data-stu-id="6ec8b-172">Set whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins</span></span>

<span data-ttu-id="6ec8b-173">身為系統管理員，您可以設定團隊會議原則設定，以控制將哪個 Outlook 會議增益集用於使用*孤島模式的使用者*。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-173">As an admin, you can configure a Teams meeting policy setting to control which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="6ec8b-174">您可以指定使用者是否只能使用 [團隊會議] 增益集，或是同時使用 [團隊會議] 和 [商務用 Skype 會議] 增益集，在 Outlook 中排程會議。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-174">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="6ec8b-175">您只能將此原則套用到使用孤島模式的使用者，並在其團隊會議原則中，將**AllowOutlookAddIn**參數設定為**True** 。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-175">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span> <span data-ttu-id="6ec8b-176">如需如何設定此原則的步驟，請參閱以[孤島模式為使用者設定會議提供者](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-176">For steps on how to set this policy, see [set the meeting provider for users in Islands mode](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode).</span></span>

## <a name="other-considerations"></a><span data-ttu-id="6ec8b-177">其他考量事項</span><span class="sxs-lookup"><span data-stu-id="6ec8b-177">Other considerations</span></span>

<span data-ttu-id="6ec8b-178">Teams 會議增益集是仍在建置的功能，因此請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="6ec8b-178">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="6ec8b-179">此增益集適用於具有特定參與者的排程會議 (不適用於頻道中的會議)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-179">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="6ec8b-180">頻道會議必須從 Teams 內排程。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-180">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="6ec8b-181">如果驗證 Proxy 位於使用者電腦和團隊服務的網路路徑中，增益集將無法運作。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-181">The add-in will not work if an Authentication Proxy is in the network path of the user's PC and Teams Services.</span></span>
- <span data-ttu-id="6ec8b-182">使用者無法從 Outlook 中安排即時活動。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-182">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="6ec8b-183">請移至 Teams 以安排即時活動。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-183">Go to Teams to schedule live events.</span></span> <span data-ttu-id="6ec8b-184">如需詳細資訊，請參閱[什麼是 Microsoft Teams 即時活動？](teams-live-events/what-are-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-184">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

<span data-ttu-id="6ec8b-185">深入了解 [Microsoft Teams 中的會議和通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-185">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6ec8b-186">疑難排解</span><span class="sxs-lookup"><span data-stu-id="6ec8b-186">Troubleshooting</span></span>

<span data-ttu-id="6ec8b-187">使用下列步驟來疑難排解團隊會議增益集的相關問題。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-187">Use the following steps to troubleshoot issues with the Teams Meeting add-in.</span></span>

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a><span data-ttu-id="6ec8b-188">Windows 版 Outlook 中的 [團隊會議增益集] 不會顯示</span><span class="sxs-lookup"><span data-stu-id="6ec8b-188">Teams Meeting add-in in Outlook for Windows does not show</span></span>

<span data-ttu-id="6ec8b-189">如果您無法取得適用於 Outlook 的 Teams 會議增益集，請嘗試這些疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-189">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="6ec8b-190">Windows 7 使用者必須[在 Windows 中安裝通用 C 運行](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)時間的更新，小組會議增益集才能運作。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-190">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>
- <span data-ttu-id="6ec8b-191">確認使用者擁有小組升級原則，可在小組中排程會議。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-191">Check that the user has a Teams Upgrade policy which enables scheduling meetings in Teams.</span></span> <span data-ttu-id="6ec8b-192">如需詳細資訊，請參閱[從商務用 Skype 升級至團隊](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-192">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for more details.</span></span>
- <span data-ttu-id="6ec8b-193">確認使用者擁有允許 Outlook 增益集的小組會議原則。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-193">Check that the user has a Teams Meeting policy that permits the Outlook Add-in.</span></span> <span data-ttu-id="6ec8b-194">如需詳細資訊，請參閱[在團隊中管理會議原則](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-194">See [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) for more details.</span></span>
- <span data-ttu-id="6ec8b-195">確定使用者已安裝 [團隊桌面用戶端]。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-195">Ensure the user has the Teams desktop client installed.</span></span> <span data-ttu-id="6ec8b-196">只有使用團隊網頁用戶端時，才能安裝會議增益集。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-196">The meeting add-in will not be installed when only using the Teams web client.</span></span>
- <span data-ttu-id="6ec8b-197">確定使用者已安裝 Outlook 2013 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-197">Ensure the user has Outlook 2013 or later installed.</span></span>
- <span data-ttu-id="6ec8b-198">確認使用者有權執行 regsvr32。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-198">Make sure the user has permission to execute regsvr32.exe.</span></span>
- <span data-ttu-id="6ec8b-199">確認已套用所有適用于 Outlook 桌面用戶端的更新。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-199">Ensure that all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="6ec8b-200">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6ec8b-200">Follow these steps:</span></span>
  - <span data-ttu-id="6ec8b-201">重新啟動 Teams 桌面版用戶端。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-201">Restart the Teams desktop client.</span></span>
  - <span data-ttu-id="6ec8b-202">登出 Teams 桌面用戶端，然後重新登入。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-202">Sign out and then sign back in to the Teams desktop client.</span></span>
  - <span data-ttu-id="6ec8b-203">重新啟動 Outlook 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-203">Restart the Outlook desktop client.</span></span> <span data-ttu-id="6ec8b-204">（請確定 Outlook 未在系統管理員模式下執行）。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-204">(Make sure Outlook isn't running in admin mode.)</span></span>

<span data-ttu-id="6ec8b-205">如果您仍然沒有看到增益集，請確認它沒有在 Outlook 中停用。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-205">If you still don't see the add-in, make sure that it isn't disabled in Outlook.</span></span>

- <span data-ttu-id="6ec8b-206">在 Outlook 中，**選擇 [檔案]，然後**選擇 [**選項**]。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-206">In Outlook, choose **File** and then **Options**.</span></span>
- <span data-ttu-id="6ec8b-207">選取 [ **Outlook 選項**] 對話方塊的 [**增益集**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-207">Select the **Add-ins** tab of **Outlook Options** dialog box.</span></span>
- <span data-ttu-id="6ec8b-208">確認 microsoft **Office 的 Microsoft 團隊會議載入**宏已列于 [作用中的**應用程式增益集**] 清單中</span><span class="sxs-lookup"><span data-stu-id="6ec8b-208">Confirm that **Microsoft Teams Meeting Add-in for Microsoft Office** is listed in the **Active Application Add-ins** list</span></span>
- <span data-ttu-id="6ec8b-209">如果 [團隊會議] 增益集列于 [**停用的應用程式增益集**] 清單中，請選取 [**管理**] 中**的 [COM 增益集**]，然後選取 [執行 **...** ]。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-209">If the Teams Meeting Add-in is listed in the **Disabled Application Add-ins** list, select **COM Add-ins** in **Manage** and then select **Go…**</span></span>
- <span data-ttu-id="6ec8b-210">在**Microsoft Office 的 [Microsoft 團隊會議增益集**] 旁，設定核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-210">Set the checkbox next to **Microsoft Teams Meeting Add-in for Microsoft Office**.</span></span>
- <span data-ttu-id="6ec8b-211">在所有對話方塊中選擇 **[確定]** ，然後重新開機 Outlook。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-211">Choose **OK** on all dialog boxes and restart Outlook.</span></span>

<span data-ttu-id="6ec8b-212">如需有關如何管理增益集的一般指導方針，請參閱[在 Office 程式中查看、管理及安裝增益集](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-212">For general guidance about how to manage add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="6ec8b-213">如果該增益集仍未顯示，請使用下列步驟驗證登錄設定。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-213">If the add-in still does not show, use the following steps to verify the registry settings.</span></span>

> [!NOTE]
> <span data-ttu-id="6ec8b-214">不正確地編輯註冊表可能會嚴重損壞您的系統。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-214">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="6ec8b-215">在變更註冊表之前，您應該先備份電腦上任何有價值的資料。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-215">Before making changes to the registry, you should back up any valued data on the computer.</span></span>
- <span data-ttu-id="6ec8b-216">啟動 RegEdit</span><span class="sxs-lookup"><span data-stu-id="6ec8b-216">Launch RegEdit.exe</span></span>
- <span data-ttu-id="6ec8b-217">流覽至 HKEY_CURRENT_USER \Software\Microsoft\Office\Outlook\Addins</span><span class="sxs-lookup"><span data-stu-id="6ec8b-217">Navigate to HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins</span></span>
- <span data-ttu-id="6ec8b-218">確認 TeamsAddin 已存在。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-218">Verify TeamsAddin.FastConnect exists.</span></span>
- <span data-ttu-id="6ec8b-219">在 TeamsAddin 中，確認 LoadBehavior 存在並設定為3。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-219">Within TeamsAddin.FastConnect, verify LoadBehavior exists and is set to 3.</span></span>
  - <span data-ttu-id="6ec8b-220">如果 LoadBehavior 的值不是3，請將它變更為3，然後重新開機 Outlook。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-220">If LoadBehavior has a value other than 3, change it to 3 and restart Outlook.</span></span>

### <a name="delegate-scheduling-does-not-work"></a><span data-ttu-id="6ec8b-221">代理人排程無法運作</span><span class="sxs-lookup"><span data-stu-id="6ec8b-221">Delegate scheduling does not work</span></span>

<span data-ttu-id="6ec8b-222">如果您的系統管理員已將 Microsoft Exchange 設定為[控制對 Exchange Web 服務器 (EWS) 的存取](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，代理人將無法代表老闆安排 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-222">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="6ec8b-223">此設定的解決方案正在開發中，即將在未來發行。</span><span class="sxs-lookup"><span data-stu-id="6ec8b-223">The solution for this configuration is under development and will be released in the future.</span></span> 
