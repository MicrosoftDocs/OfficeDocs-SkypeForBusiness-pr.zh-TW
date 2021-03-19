---
title: Microsoft Teams 應用程式的許可權與考慮
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 系統管理員可以瞭解 Microsoft Teams 應用程式向組織要求哪些資料和許可權。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1e6628467d4300130c39a3bade87919fb064a14f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874703"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="e61ce-103">Microsoft Teams 應用程式的許可權與考慮</span><span class="sxs-lookup"><span data-stu-id="e61ce-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="e61ce-104">Microsoft Teams 應用程式是一種將一或多個功能匯總到可安裝、升級和卸載的應用程式套件的方法。</span><span class="sxs-lookup"><span data-stu-id="e61ce-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="e61ce-105">這些功能包括：</span><span class="sxs-lookup"><span data-stu-id="e61ce-105">The capabilities include:</span></span>

- <span data-ttu-id="e61ce-106">機器人</span><span class="sxs-lookup"><span data-stu-id="e61ce-106">Bots</span></span>
- <span data-ttu-id="e61ce-107">訊息擴充功能</span><span class="sxs-lookup"><span data-stu-id="e61ce-107">Messaging extensions</span></span>
- <span data-ttu-id="e61ce-108">索引標籤</span><span class="sxs-lookup"><span data-stu-id="e61ce-108">Tabs</span></span>
- <span data-ttu-id="e61ce-109">連接器</span><span class="sxs-lookup"><span data-stu-id="e61ce-109">Connectors</span></span>

<span data-ttu-id="e61ce-110">應用程式是由使用者同意，由 IT 從策略角度進行管理。</span><span class="sxs-lookup"><span data-stu-id="e61ce-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="e61ce-111">不過，應用程式的許可權和風險設定檔大部分是由應用程式包含的許可權和風險設定檔所定義。</span><span class="sxs-lookup"><span data-stu-id="e61ce-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="e61ce-112">因此，本文著重于功能層級的許可權與考慮。</span><span class="sxs-lookup"><span data-stu-id="e61ce-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="e61ce-113">下列以大寫字母列出的許可權 ，例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE，不會顯示在 [Microsoft Teams](https://aka.ms/teamsdevdocs) 開發人員檔或 [Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)的許可權中。</span><span class="sxs-lookup"><span data-stu-id="e61ce-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="e61ce-114">它們只是本文目的的描述性簡寫。</span><span class="sxs-lookup"><span data-stu-id="e61ce-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="e61ce-115">標題</span><span class="sxs-lookup"><span data-stu-id="e61ce-115">Title</span></span>   | <span data-ttu-id="e61ce-116">描述</span><span class="sxs-lookup"><span data-stu-id="e61ce-116">Description</span></span>    |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="e61ce-118">決策點</span><span class="sxs-lookup"><span data-stu-id="e61ce-118">Decision point</span></span>|<ul><li><span data-ttu-id="e61ce-119">使用下表做為指南，瞭解您調查的應用程式要求哪些許可權。</span><span class="sxs-lookup"><span data-stu-id="e61ce-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="e61ce-121">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e61ce-121">Next step</span></span>|<ul><li><span data-ttu-id="e61ce-122">研究應用程式或服務本身，決定是否要允許在貴組織中存取它。</span><span class="sxs-lookup"><span data-stu-id="e61ce-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="e61ce-123">例如，Bot 會傳送和接收來自使用者的訊息，而且除了企業自訂 Bot 之外，它們位於合規性邊界之外。</span><span class="sxs-lookup"><span data-stu-id="e61ce-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="e61ce-124">因此，任何包含 Bot 的應用程式都需要這些許可權，且至少具備該風險設定檔。</span><span class="sxs-lookup"><span data-stu-id="e61ce-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="e61ce-125">另請參閱 [要求 Microsoft Teams 選項卡的裝置許可權](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)。</span><span class="sxs-lookup"><span data-stu-id="e61ce-125">See also [Request device permissions for your Microsoft Teams tab](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="e61ce-126">全域應用程式許可權與考慮</span><span class="sxs-lookup"><span data-stu-id="e61ce-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="e61ce-127">必要的許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-127">Required permissions</span></span>

<span data-ttu-id="e61ce-128">無</span><span class="sxs-lookup"><span data-stu-id="e61ce-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="e61ce-129">選擇性許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-129">Optional permissions</span></span>

<span data-ttu-id="e61ce-130">無</span><span class="sxs-lookup"><span data-stu-id="e61ce-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="e61ce-131">考量</span><span class="sxs-lookup"><span data-stu-id="e61ce-131">Considerations</span></span>

- <span data-ttu-id="e61ce-132">應用程式必須公開其使用哪些資料，以及資料在使用條款和隱私權政策連結中的用途。</span><span class="sxs-lookup"><span data-stu-id="e61ce-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="e61ce-133">[特定資源同意](resource-specific-consent.md) 提供一組應用程式可要求的許可權，這些許可權會顯示在應用程式的安裝畫面上。</span><span class="sxs-lookup"><span data-stu-id="e61ce-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="e61ce-134">若要深入瞭解資源特定同意許可權，請參閱 [圖形許可權參照](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)。</span><span class="sxs-lookup"><span data-stu-id="e61ce-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="e61ce-135">應用程式可能也需要資源特定同意許可權外的許可權。</span><span class="sxs-lookup"><span data-stu-id="e61ce-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="e61ce-136">安裝 App 之後，應用程式可能會透過同意提示要求 Graph 許可權。</span><span class="sxs-lookup"><span data-stu-id="e61ce-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="e61ce-137">若要深入瞭解，請參閱 [瞭解 Azure AD 應用程式同意體驗](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)。</span><span class="sxs-lookup"><span data-stu-id="e61ce-137">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="e61ce-138">您可以在 Azure 入口網站中設定 API 許可權和同意。</span><span class="sxs-lookup"><span data-stu-id="e61ce-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="e61ce-139">若要深入瞭解，請參閱 [Azure Active Directory 同意架構](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)。</span><span class="sxs-lookup"><span data-stu-id="e61ce-139">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="e61ce-140">Bot 和訊息擴充功能</span><span class="sxs-lookup"><span data-stu-id="e61ce-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="e61ce-141">必要的許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-141">Required permissions</span></span>

- <span data-ttu-id="e61ce-142">RECEIVE_MESSAGE，REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="e61ce-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="e61ce-143">Bot 可以接收使用者的郵件並回復使用者。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e61ce-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="e61ce-144">POST_MESSAGE_USER。</span><span class="sxs-lookup"><span data-stu-id="e61ce-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="e61ce-145">在使用者傳送郵件給 Bot 之後，bot 可以傳送使用者直接 (或稱為 *主動* 式訊息。</span><span class="sxs-lookup"><span data-stu-id="e61ce-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="e61ce-146">GET_CHANNEL_LIST。</span><span class="sxs-lookup"><span data-stu-id="e61ce-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="e61ce-147">新加入團隊的 Bot 可以取得團隊中頻道的名稱和 ID 清單。</span><span class="sxs-lookup"><span data-stu-id="e61ce-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="e61ce-148">選擇性許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-148">Optional permissions</span></span>

- <span data-ttu-id="e61ce-149">身份。</span><span class="sxs-lookup"><span data-stu-id="e61ce-149">IDENTITY.</span></span> <span data-ttu-id="e61ce-150">在頻道中使用時，App 的 Bot 可以存取小組成員的基本身分識別資訊 (名字、姓氏、使用者主體名稱 [UPN]、電子郵件地址) ;當 Bot 用於個人或群組聊天時，Bot 可以存取這些使用者的相同資訊。</span><span class="sxs-lookup"><span data-stu-id="e61ce-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="e61ce-151">POST_MESSAGE_TEAM。</span><span class="sxs-lookup"><span data-stu-id="e61ce-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="e61ce-152">允許 App 的 bot 隨時 (主動) 傳送訊息給任何團隊成員，即使使用者之前從未與 Bot 交談過。</span><span class="sxs-lookup"><span data-stu-id="e61ce-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="e61ce-153">下列不是明確許可權，但由 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 以及可在其中使用 bot 的範圍所隱含，在清單中宣告：</span><span class="sxs-lookup"><span data-stu-id="e61ce-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="e61ce-154">RECEIVE_MESSAGE_PERSONAL，REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="e61ce-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="e61ce-155">RECEIVE_MESSAGE_GROUPCHAT，REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="e61ce-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="e61ce-156">RECEIVE_MESSAGE_TEAM，REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="e61ce-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="e61ce-157">SEND_FILES，RECEIVE_FILES。<sup>2</sup> 控制 Bot 是否可以在個人聊天中傳送 (尚未支援群組聊天或頻道) 。</span><span class="sxs-lookup"><span data-stu-id="e61ce-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="e61ce-158">考量</span><span class="sxs-lookup"><span data-stu-id="e61ce-158">Considerations</span></span>

- <span data-ttu-id="e61ce-159">Bot 只能存取已新增到的團隊或已安裝這些團隊的使用者。</span><span class="sxs-lookup"><span data-stu-id="e61ce-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="e61ce-160">Bot 只會收到使用者明確提及的訊息。</span><span class="sxs-lookup"><span data-stu-id="e61ce-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="e61ce-161">此資料會離開公司網路。</span><span class="sxs-lookup"><span data-stu-id="e61ce-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="e61ce-162">Bot 只能回復提及這些聊天的交談。</span><span class="sxs-lookup"><span data-stu-id="e61ce-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="e61ce-163">在使用者與 Bot 進行交談之後，如果 Bot 儲存該使用者的識別碼，它隨時都可以傳送該使用者的直接訊息。</span><span class="sxs-lookup"><span data-stu-id="e61ce-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="e61ce-164">從理論上來說，Bot 郵件可能包含網路釣魚或惡意程式碼網站的連結，但 Bot 可能會由使用者、租使用者系統管理員或 Microsoft 全域封鎖。</span><span class="sxs-lookup"><span data-stu-id="e61ce-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="e61ce-165">Bot 可以 (應用程式) 小組成員，或個人或群組聊天中的個別使用者，儲存最基本的身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="e61ce-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="e61ce-166">若要取得這些使用者的進一步資訊，Bot 必須要求他們以 Azure AD 帳戶 (Azure Active Directory) 。</span><span class="sxs-lookup"><span data-stu-id="e61ce-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="e61ce-167">Bot 可以 (，並) 團隊中的頻道清單;此資料會離開公司網路。</span><span class="sxs-lookup"><span data-stu-id="e61ce-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="e61ce-168">當檔案送到 Bot 時，檔案會離開公司網路。</span><span class="sxs-lookup"><span data-stu-id="e61ce-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="e61ce-169">傳送和接收檔案需要使用者針對每個檔案核准。</span><span class="sxs-lookup"><span data-stu-id="e61ce-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="e61ce-170">根據預設，Bot 無法代表使用者採取行動，但 Bot 可以要求使用者進行登錄;使用者一旦登錄，Bot 就會有一個存取權杖，可以執行其他工作。</span><span class="sxs-lookup"><span data-stu-id="e61ce-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="e61ce-171">這些額外專案究竟是什麼，取決於 Bot 和使用者登錄位置：Bot 是註冊在 Azure AD App，而且可以擁有自己的一組 https://apps.dev.microsoft.com/ 許可權。</span><span class="sxs-lookup"><span data-stu-id="e61ce-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="e61ce-172">每當使用者新加入或刪除團隊時，就會通知 Bot。</span><span class="sxs-lookup"><span data-stu-id="e61ce-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="e61ce-173">Bot 不會看到使用者的 IP 位址或其他參考資訊。</span><span class="sxs-lookup"><span data-stu-id="e61ce-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="e61ce-174">所有資訊都來自 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="e61ce-174">All information comes from Microsoft.</span></span> <span data-ttu-id="e61ce-175"> (有一個例外：如果 Bot 實現自己的登錄體驗，則登錄 UI 會看到使用者的 IP 位址和參照者資訊。) </span><span class="sxs-lookup"><span data-stu-id="e61ce-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="e61ce-176">另一方面，訊息擴充功能則會看到使用者的 IP 位址和參照者資訊。</span><span class="sxs-lookup"><span data-stu-id="e61ce-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="e61ce-177">應用程式指導方針 (我們的 AppSource 審查程式) 需要謹慎處理，才能透過 (許可權POST_MESSAGE_TEAM使用者) 張貼個人聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="e61ce-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="e61ce-178">萬一遭到濫用，使用者可以封鎖 Bot，租使用者系統管理員可以封鎖應用程式，而 Microsoft 可以視需要集中封鎖 Bot。</span><span class="sxs-lookup"><span data-stu-id="e61ce-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="e61ce-179"><sup>1</sup> 部分 Bot 只會傳送 (POST_MESSAGE_USER) 。</span><span class="sxs-lookup"><span data-stu-id="e61ce-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="e61ce-180">它們稱為「僅通知」Bot，但這個術語並未提及允許或不允許 Bot 執行什麼操作，這表示 Bot 不想公開交談體驗。</span><span class="sxs-lookup"><span data-stu-id="e61ce-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="e61ce-181">Teams 會使用此欄位來停用 UI 中通常會啟用的功能;與公開交談體驗的 Bot 相比，Bot 不會受限於允許執行什麼操作。</span><span class="sxs-lookup"><span data-stu-id="e61ce-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="e61ce-182"><sup>2</sup> 受應用程式檔案中 bot 物件上的支援Files Boolean 屬性manifest.js管理。</span><span class="sxs-lookup"><span data-stu-id="e61ce-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="e61ce-183">如果 Bot 擁有自己的登錄，使用者第一次登錄時，第二個同意體驗會有所不同。</span><span class="sxs-lookup"><span data-stu-id="e61ce-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="e61ce-184">目前，與 Teams App (bot、Tab、連接器或訊息延伸模組) 內任何功能相關聯的 Azure AD 許可權與此處所列的 Teams 許可權完全分開。</span><span class="sxs-lookup"><span data-stu-id="e61ce-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="e61ce-185">索引標籤</span><span class="sxs-lookup"><span data-stu-id="e61ce-185">Tabs</span></span>

<span data-ttu-id="e61ce-186">Tab 是在 Teams 內運作的網站。</span><span class="sxs-lookup"><span data-stu-id="e61ce-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="e61ce-187">必要的許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-187">Required permissions</span></span>

<span data-ttu-id="e61ce-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="e61ce-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="e61ce-189">選擇性許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-189">Optional permissions</span></span>

<span data-ttu-id="e61ce-190">目前 (沒有) </span><span class="sxs-lookup"><span data-stu-id="e61ce-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="e61ce-191">考量</span><span class="sxs-lookup"><span data-stu-id="e61ce-191">Considerations</span></span>

- <span data-ttu-id="e61ce-192">一個定位停駐點的風險設定檔幾乎與在瀏覽器選項卡中運行的同一個網站相同。</span><span class="sxs-lookup"><span data-stu-id="e61ce-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="e61ce-193">一個 Tab 也會獲得其執行內容，包括目前使用者的登錄名稱和 UPN、目前使用者的 Azure AD 物件識別碼、其所在 Microsoft 365 群組的識別碼 (如果是團隊) 、租使用者識別碼，以及使用者的目前地區設置。</span><span class="sxs-lookup"><span data-stu-id="e61ce-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="e61ce-194">不過，若要將這些 ID 與使用者的資訊進行比對，該選項卡必須讓使用者登錄 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="e61ce-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="e61ce-195">連接器</span><span class="sxs-lookup"><span data-stu-id="e61ce-195">Connectors</span></span>

<span data-ttu-id="e61ce-196">當外部系統發生事件時，連接器會將訊息張貼到頻道。</span><span class="sxs-lookup"><span data-stu-id="e61ce-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="e61ce-197">必要的許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-197">Required permissions</span></span>

<span data-ttu-id="e61ce-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="e61ce-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="e61ce-199">選擇性許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-199">Optional permissions</span></span>

<span data-ttu-id="e61ce-200">REPLYTO_CONNECTOR_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="e61ce-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="e61ce-201">某些連接器支援可採取動作的郵件，允許使用者將目標回復張貼到連接器訊息，例如新增 GitHub 問題的回復，或新增日期至 Trello 卡片。</span><span class="sxs-lookup"><span data-stu-id="e61ce-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="e61ce-202">考量</span><span class="sxs-lookup"><span data-stu-id="e61ce-202">Considerations</span></span>

- <span data-ttu-id="e61ce-203">張貼連接器郵件的系統不知道郵件的張貼物件或接收郵件者：不會公開收件者的資訊。</span><span class="sxs-lookup"><span data-stu-id="e61ce-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="e61ce-204"> (Microsoft 是實際的收件者，而不是租使用者;Microsoft 會實際張貼到 channel.) </span><span class="sxs-lookup"><span data-stu-id="e61ce-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="e61ce-205">當連接器訊息張貼到頻道時，沒有任何資料會離開公司網路。</span><span class="sxs-lookup"><span data-stu-id="e61ce-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="e61ce-206">支援可採取動作 (REPLYTO_CONNECTOR_MESSAGE具有) 許可權的連接器，也看不到 IP 位址和參照者資訊;這項資訊會傳送至 Microsoft，然後路由至先前在連接器入口網站中向 Microsoft 註冊的 HTTP 端點。</span><span class="sxs-lookup"><span data-stu-id="e61ce-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="e61ce-207">每次為通道配置連接器時，即會建立該連接器實例的唯一 URL。</span><span class="sxs-lookup"><span data-stu-id="e61ce-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="e61ce-208">如果刪除該連接器實例，就無法再使用 URL。</span><span class="sxs-lookup"><span data-stu-id="e61ce-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="e61ce-209">連接器郵件不能包含檔案附件。</span><span class="sxs-lookup"><span data-stu-id="e61ce-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="e61ce-210">連接器實例 URL 應視為機密/機密：任何擁有該 URL 的人都可以張貼至該 URL，例如電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e61ce-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="e61ce-211">因此，有一些垃圾郵件或網路釣魚或惡意網站連結的風險。</span><span class="sxs-lookup"><span data-stu-id="e61ce-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="e61ce-212">如果發生這種情況，團隊擁有者可以刪除連接器實例。</span><span class="sxs-lookup"><span data-stu-id="e61ce-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="e61ce-213">如果傳送連接器郵件的服務遭到入侵，並開始傳送垃圾郵件/網路釣魚/惡意程式碼連結，租使用者系統管理員可以防止建立新的連接器實例，而 Microsoft 可以集中封鎖它們。</span><span class="sxs-lookup"><span data-stu-id="e61ce-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="e61ce-214">目前無法知道哪些連接器支援可採取動作的郵件 (REPLYTO_CONNECTOR_MESSAGE許可權) 。</span><span class="sxs-lookup"><span data-stu-id="e61ce-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="e61ce-215">外發網頁連結</span><span class="sxs-lookup"><span data-stu-id="e61ce-215">Outgoing webhooks</span></span>

<span data-ttu-id="e61ce-216">*待發網頁連結* 是由團隊擁有者或小組成員在飛航中建立。</span><span class="sxs-lookup"><span data-stu-id="e61ce-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="e61ce-217">它們不是 Teams 應用程式的功能;這項資訊會包含完整性。</span><span class="sxs-lookup"><span data-stu-id="e61ce-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="e61ce-218">必要的許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-218">Required permissions</span></span>

<span data-ttu-id="e61ce-219">RECEIVE_MESSAGE，REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="e61ce-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="e61ce-220">可以接收來自使用者的訊息並回復他們。</span><span class="sxs-lookup"><span data-stu-id="e61ce-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="e61ce-221">選擇性許可權</span><span class="sxs-lookup"><span data-stu-id="e61ce-221">Optional permissions</span></span>

<span data-ttu-id="e61ce-222">無</span><span class="sxs-lookup"><span data-stu-id="e61ce-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="e61ce-223">考量</span><span class="sxs-lookup"><span data-stu-id="e61ce-223">Considerations</span></span>

- <span data-ttu-id="e61ce-224">外發網頁連結與 Bot 類似，但許可權較少。</span><span class="sxs-lookup"><span data-stu-id="e61ce-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="e61ce-225">它們必須明確提及，就像 Bot 一樣。</span><span class="sxs-lookup"><span data-stu-id="e61ce-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="e61ce-226">當已註冊外寄網頁搖動時，會產生一個機密，可讓待發網頁搖動驗證寄件者是 Microsoft Teams，而不是惡意攻擊者。</span><span class="sxs-lookup"><span data-stu-id="e61ce-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="e61ce-227">此機密應維持為機密;任何有存取權的人都可以模仿 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e61ce-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="e61ce-228">如果機密遭到入侵，可以刪除並重新建立待發網頁連結，並產生新的密碼。</span><span class="sxs-lookup"><span data-stu-id="e61ce-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="e61ce-229">雖然您可以建立未驗證機密的外發網頁連結，但我們建議您不要這樣做。</span><span class="sxs-lookup"><span data-stu-id="e61ce-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="e61ce-230">除了接收和回復郵件之外，外寄網頁連結無法執行許多操作：無法主動傳送郵件、無法傳送或接收檔案、除了接收和回復郵件之外，他們無法執行 Bot 可以執行的其他工作。</span><span class="sxs-lookup"><span data-stu-id="e61ce-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
