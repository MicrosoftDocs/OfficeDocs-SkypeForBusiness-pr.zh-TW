---
title: 在 Microsoft 團隊中新增私人聊天和頻道的機器人
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: 瞭解如何在 Microsoft 團隊中新增機器人, 以進行個人聊天、群組聊天和頻道, 以及上傳您自己的機器人來進行個人聊天、群組聊天和頻道。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f5f031b01837980897f2c1f8ad5d306e056257b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239477"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="a623f-103">在 Microsoft 團隊中新增個人聊天、群組聊天和頻道的機器人</span><span class="sxs-lookup"><span data-stu-id="a623f-103">Add bots for personal chats, group chats, and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a623f-104">Bot 是能回應查詢或提供更新和通知的自動程式, 讓使用者覺得有趣或想要掌握相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a623f-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="a623f-105">Bot 可讓使用者透過 Microsoft 團隊中的聊天交談, 與工作管理、排程及輪詢等雲端服務互動。</span><span class="sxs-lookup"><span data-stu-id="a623f-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="a623f-106">小組的 bot 是在[Microsoft Bot 架構](https://go.microsoft.com/fwlink/?linkid=854370)中建立的。</span><span class="sxs-lookup"><span data-stu-id="a623f-106">Bots for Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="a623f-107">您可以輕鬆地為團隊啟用使用這個架構開發的 bot。</span><span class="sxs-lookup"><span data-stu-id="a623f-107">The bots that are developed using this framework can be enabled easily for Teams.</span></span> <span data-ttu-id="a623f-108">如需詳細資訊, 請參閱[管理貴組織的 Microsoft 團隊設定](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a623f-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="a623f-109">目前, 團隊在小組中支援個人聊天、群組聊天和頻道中的 bot。</span><span class="sxs-lookup"><span data-stu-id="a623f-109">Currently, Teams supports bots in personal chats, group chats, and channels within a team.</span></span> <span data-ttu-id="a623f-110">系統管理員可以控制是否允許或禁止在 Office 365 租使用者內使用 bot。<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="a623f-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="a623f-111">您可以在團隊中利用社區開發的 bot。</span><span class="sxs-lookup"><span data-stu-id="a623f-111">Bots developed by the community can be leveraged within Teams.</span></span> <span data-ttu-id="a623f-112">您必須先在租使用者層級啟用 bot 的功能和上傳自訂應用程式 (也稱為側載), 才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="a623f-112">The bot's functionality and the ability to upload custom apps (also known as sideloading) must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="a623f-113">您可以在個人聊天、群組聊天和頻道中使用機器人。</span><span class="sxs-lookup"><span data-stu-id="a623f-113">Bots can be used in personal chats, group chats, and channels.</span></span> <span data-ttu-id="a623f-114">對於頻道, 小組擁有者或成員可以新增機器人。</span><span class="sxs-lookup"><span data-stu-id="a623f-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="a623f-115">如需詳細資訊, 請參閱[應用程式和服務](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)。</span><span class="sxs-lookup"><span data-stu-id="a623f-115">For more information, see [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a623f-116">建議您不要針對除測試用途以外的任何專案, 依 GUID 新增 bot。</span><span class="sxs-lookup"><span data-stu-id="a623f-116">Adding a bot by GUID, for anything other than testing purposes, is not recommended.</span></span> <span data-ttu-id="a623f-117">這麼做會嚴重限制 bot 的功能。</span><span class="sxs-lookup"><span data-stu-id="a623f-117">Doing so severely limits the functionality of a bot.</span></span> <span data-ttu-id="a623f-118">您應該將在生產中使用的 bot 新增至團隊做為應用程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="a623f-118">Bots in production use should be added to Teams as part of an app.</span></span> <span data-ttu-id="a623f-119">請參閱[建立 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create)並[測試及調試 Microsoft 團隊 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)</span><span class="sxs-lookup"><span data-stu-id="a623f-119">See [Create a bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) and [Test and debug your Microsoft Teams bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)</span></span>

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="a623f-120">建立 Microsoft 團隊的自訂 bot</span><span class="sxs-lookup"><span data-stu-id="a623f-120">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="a623f-121">您可以使用 Microsoft Bot 架構, 輕鬆建立與 LOB 應用程式整合的 bot。</span><span class="sxs-lookup"><span data-stu-id="a623f-121">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="a623f-122">若要瞭解如何開發及發佈自己的機器人, 請參閱[建立及測試 Microsoft 團隊的 bot](https://go.microsoft.com/fwlink/?linkid=854371) 。</span><span class="sxs-lookup"><span data-stu-id="a623f-122">See the [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="a623f-123">當您建立 bot 並將它註冊至 Bot 架構時, 您可以選擇發佈它。</span><span class="sxs-lookup"><span data-stu-id="a623f-123">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="a623f-124">如果您沒有發佈, bot 會保持為私人。</span><span class="sxs-lookup"><span data-stu-id="a623f-124">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="a623f-125">您也可以在使用 bot 前, 要求使用者登入。</span><span class="sxs-lookup"><span data-stu-id="a623f-125">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="a623f-126">如果需要登入, 只需確認貴組織的員工就能存取 bot, 即使 bot 的應用程式識別碼變成已知也一樣。</span><span class="sxs-lookup"><span data-stu-id="a623f-126">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="a623f-127">如需如何使用 bot 針對您的 Active Directory 進行驗證的程式碼範例, 請參閱 GitHub 上的[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) 。</span><span class="sxs-lookup"><span data-stu-id="a623f-127">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="a623f-128">您可以在將 bot 部署到您的小組之前, 使用[Bot 架構模擬器](https://go.microsoft.com/fwlink/?linkid=854373)來測試機器人。</span><span class="sxs-lookup"><span data-stu-id="a623f-128">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="upload-your-bot-for-personal-chat"></a><span data-ttu-id="a623f-129">上傳您的 bot 以進行個人聊天</span><span class="sxs-lookup"><span data-stu-id="a623f-129">Upload your bot for personal chat</span></span>
---------------------------------------

1. <span data-ttu-id="a623f-130">建立您的 bot 之後, 請移至您所開發 bot 的 [**應用程式設定**], 然後在 [**應用程式設定**] 底下, 複製**MicrosoftAppId**設定的值。![Bot 的 [應用程式設定] 頁面的螢幕擷取畫面](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="a623f-130">After you create your bot, go to the **Application Settings** for the bot you developed, and then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>

2.  <span data-ttu-id="a623f-131">在 [團隊] 的 [**聊天**] 窗格中, 選取 [**新增聊天] 圖示**。</span><span class="sxs-lookup"><span data-stu-id="a623f-131">In Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="a623f-132">在**To**中, 貼上您 Bot 的**MICROSOFT 應用程式識別碼**。</span><span class="sxs-lookup"><span data-stu-id="a623f-132">In **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="a623f-133">![醒目提示 [聊天] 窗格的螢幕擷取畫面, 其中顯示 Microsoft 應用程式識別碼](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="a623f-133">![Screenshot of a chat pane with Microsoft app ID highlighted](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>

3. <span data-ttu-id="a623f-134">應用程式識別碼將解析到您的**bot 名稱,** 然後您就可以開始與該 bot 進行聊天交談。</span><span class="sxs-lookup"><span data-stu-id="a623f-134">The app ID will resolve to your **bot name,** and then you can start a chat conversation with that bot.</span></span>

<a name="upload-your-bot-for-group-chats-or-channels"></a><span data-ttu-id="a623f-135">上傳 [群組聊天] 或 [頻道] 的 bot</span><span class="sxs-lookup"><span data-stu-id="a623f-135">Upload your bot for group chats or channels</span></span>
-----------------------------------

<span data-ttu-id="a623f-136">如果您想要與同事共用您的 bot, 以下說明如何將其新增至群組聊天或不同小組的頻道:</span><span class="sxs-lookup"><span data-stu-id="a623f-136">If you want to share your bot with your colleagues, here's how to add it to group chats or channels of different teams:</span></span>

1. <span data-ttu-id="a623f-137">在您[為 bot 建立應用程式套件](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)之後, 請開啟 [小組], 然後流覽至您要上傳 bot 的小組。</span><span class="sxs-lookup"><span data-stu-id="a623f-137">After you [create an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be uploading the bot.</span></span>
2. <span data-ttu-id="a623f-138">將**[應用程式製作](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)** 者、app 新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="a623f-138">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Teams.</span></span>
3. <span data-ttu-id="a623f-139">在 App Studio 中, 選取 [**資訊清單編輯器**] 索引標籤。 ![[資訊清單編輯器] 索引標籤的螢幕擷取畫面](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="a623f-139">In App Studio, select the **Manifest Editor** Tab. ![Screenshot of the Manifest Editor Tab.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="a623f-140">若要新增您的 bot, 請在 [功能] 中選取 bot, 然後選擇 [新增現有的 bot]。</span><span class="sxs-lookup"><span data-stu-id="a623f-140">To add your bot, in capabilities, select the bot and choose to add an existing bot.</span></span> <span data-ttu-id="a623f-141">然後, 選擇現有的 bot, 或輸入現有 bot 的 Id。</span><span class="sxs-lookup"><span data-stu-id="a623f-141">Then, choose an existing bot or enter the Id of an existing bot.</span></span>
<span data-ttu-id="a623f-142">![顯示選取您已建立的 bot。](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="a623f-142">![Shows selecting the bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="a623f-143">流覽至您的應用程式套件的位置, 選取它, 然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="a623f-143">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="a623f-144">選取您 bot 的名稱。</span><span class="sxs-lookup"><span data-stu-id="a623f-144">Select your bot's name.</span></span> <span data-ttu-id="a623f-145">(請不要忘記選取 [範圍] 區段底下的 [**群組聊天**] 或 [**小組**] 核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="a623f-145">(Don't forget to select the **Group chat** or **Team** check box under the scope section).</span></span>
7. <span data-ttu-id="a623f-146">選取 [**測試併發布**]。</span><span class="sxs-lookup"><span data-stu-id="a623f-146">Select **Test and distribute**.</span></span>
8. <span data-ttu-id="a623f-147">選取您要將 bot 連線至其中的群組聊天或團隊。</span><span class="sxs-lookup"><span data-stu-id="a623f-147">Select the group chat or team where you want to connect your bot to.</span></span>

    <span data-ttu-id="a623f-148">您的 bot 將可在小組中的群組聊天或團隊中使用。</span><span class="sxs-lookup"><span data-stu-id="a623f-148">Your bot will be available in your group chat or team in Teams.</span></span>
