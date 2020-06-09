---
title: Microsoft 團隊 app 許可權和考慮
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
description: 系統管理員可以瞭解 Microsoft 團隊 app 從其組織要求哪些資料和許可權。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d2e43c3125421189303d106cfd3bdde66815309
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2020
ms.locfileid: "44611012"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="1eafe-103">Microsoft 團隊 app 許可權和考慮</span><span class="sxs-lookup"><span data-stu-id="1eafe-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="1eafe-104">Microsoft 團隊 app 是一種將一或多項功能匯總成_應用程式套件_的方法，可供安裝、升級及卸載。</span><span class="sxs-lookup"><span data-stu-id="1eafe-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="1eafe-105">這些功能包括：</span><span class="sxs-lookup"><span data-stu-id="1eafe-105">The capabilities include:</span></span>

- <span data-ttu-id="1eafe-106">Bot</span><span class="sxs-lookup"><span data-stu-id="1eafe-106">Bots</span></span>
- <span data-ttu-id="1eafe-107">郵件擴充功能</span><span class="sxs-lookup"><span data-stu-id="1eafe-107">Messaging extensions</span></span>
- <span data-ttu-id="1eafe-108">索引標籤</span><span class="sxs-lookup"><span data-stu-id="1eafe-108">Tabs</span></span>
- <span data-ttu-id="1eafe-109">連接器</span><span class="sxs-lookup"><span data-stu-id="1eafe-109">Connectors</span></span>

<span data-ttu-id="1eafe-110">應用程式受到使用者的同意，且由策略的觀點加以管理。</span><span class="sxs-lookup"><span data-stu-id="1eafe-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="1eafe-111">不過，在大多數情況下，應用程式的許可權和風險設定檔是由 app 所包含之功能的許可權和風險設定檔所定義。</span><span class="sxs-lookup"><span data-stu-id="1eafe-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="1eafe-112">因此，本文著重說明功能層級的許可權和考慮。</span><span class="sxs-lookup"><span data-stu-id="1eafe-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="1eafe-113">下列是大寫字母（例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE）中所列的許可權，不會出現在[Microsoft 團隊開發人員檔](https://aka.ms/teamsdevdocs)中的任何位置或[microsoft Graph 的許可權](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)中。</span><span class="sxs-lookup"><span data-stu-id="1eafe-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="1eafe-114">它們只是本文用途的描述性簡寫。</span><span class="sxs-lookup"><span data-stu-id="1eafe-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="1eafe-116">決策點</span><span class="sxs-lookup"><span data-stu-id="1eafe-116">Decision point</span></span>|<ul><li><span data-ttu-id="1eafe-117">您可以使用下表做為說明，瞭解您正在調查哪些應用程式要求哪些許可權。</span><span class="sxs-lookup"><span data-stu-id="1eafe-117">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="1eafe-119">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1eafe-119">Next step</span></span>|<ul><li><span data-ttu-id="1eafe-120">研究 app 或服務本身，決定是否要允許您組織中的存取權。</span><span class="sxs-lookup"><span data-stu-id="1eafe-120">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="1eafe-121">例如，bot 會從使用者傳送及接收訊息，除了企業自訂機器人之外，它們位於合規性界限外。</span><span class="sxs-lookup"><span data-stu-id="1eafe-121">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="1eafe-122">因此，任何包含 bot 的 app 都需要這些許可權，並至少擁有該風險設定檔。</span><span class="sxs-lookup"><span data-stu-id="1eafe-122">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="1eafe-123">全域 app 許可權和考慮</span><span class="sxs-lookup"><span data-stu-id="1eafe-123">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="1eafe-124">所需許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-124">Required permissions</span></span>

<span data-ttu-id="1eafe-125">無</span><span class="sxs-lookup"><span data-stu-id="1eafe-125">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="1eafe-126">選用許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-126">Optional permissions</span></span>

<span data-ttu-id="1eafe-127">無</span><span class="sxs-lookup"><span data-stu-id="1eafe-127">None</span></span>

### <a name="considerations"></a><span data-ttu-id="1eafe-128">考量</span><span class="sxs-lookup"><span data-stu-id="1eafe-128">Considerations</span></span>

- <span data-ttu-id="1eafe-129">應用程式必須披露它所使用的資料，以及資料在其使用條款和隱私權原則連結中的用途。</span><span class="sxs-lookup"><span data-stu-id="1eafe-129">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="1eafe-130">[資源特定的同意](resource-specific-consent.md)提供應用程式可要求的一組許可權，該許可權會出現在 app 的安裝畫面上。</span><span class="sxs-lookup"><span data-stu-id="1eafe-130">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="1eafe-131">若要深入瞭解資源特定的同意許可權，請參閱[圖表許可權參考](https://docs.microsoft.com/graph/permissions-reference)。</span><span class="sxs-lookup"><span data-stu-id="1eafe-131">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference).</span></span>

- <span data-ttu-id="1eafe-132">App 也可能需要除資源特定的同意許可權之外的許可權。</span><span class="sxs-lookup"><span data-stu-id="1eafe-132">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="1eafe-133">安裝應用程式後，應用程式可能會透過同意提示要求圖表許可權。</span><span class="sxs-lookup"><span data-stu-id="1eafe-133">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="1eafe-134">若要深入瞭解，請參閱[瞭解 AZURE AD 應用程式同意體驗](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)。</span><span class="sxs-lookup"><span data-stu-id="1eafe-134">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="1eafe-135">您可以在 Azure 入口網站中設定 API 許可權和同意。</span><span class="sxs-lookup"><span data-stu-id="1eafe-135">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="1eafe-136">若要深入瞭解，請參閱[Azure Active Directory 同意架構](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)。</span><span class="sxs-lookup"><span data-stu-id="1eafe-136">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="1eafe-137">Bot 和訊息擴充功能</span><span class="sxs-lookup"><span data-stu-id="1eafe-137">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="1eafe-138">所需許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-138">Required permissions</span></span>

- <span data-ttu-id="1eafe-139">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="1eafe-139">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="1eafe-140">Bot 可以接收來自使用者的訊息並回復。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1eafe-140">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="1eafe-141">POST_MESSAGE_USER]。</span><span class="sxs-lookup"><span data-stu-id="1eafe-141">POST_MESSAGE_USER.</span></span> <span data-ttu-id="1eafe-142">在使用者將訊息傳送至 bot 之後，bot 可以隨時傳送使用者的直接訊息（也稱為*預先訊息*）。</span><span class="sxs-lookup"><span data-stu-id="1eafe-142">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="1eafe-143">GET_CHANNEL_LIST]。</span><span class="sxs-lookup"><span data-stu-id="1eafe-143">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="1eafe-144">新增至團隊的 bot 可以取得團隊中頻道的名稱和識別碼清單。</span><span class="sxs-lookup"><span data-stu-id="1eafe-144">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="1eafe-145">選用許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-145">Optional permissions</span></span>

- <span data-ttu-id="1eafe-146">等.</span><span class="sxs-lookup"><span data-stu-id="1eafe-146">IDENTITY.</span></span> <span data-ttu-id="1eafe-147">在頻道中使用時，應用程式的機器人可以存取小組成員的基本身分識別資訊（名字、姓氏、使用者主體名稱 [UPN]、電子郵件地址）;在個人或群組聊天中使用時，bot 可以為這些使用者存取相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="1eafe-147">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="1eafe-148">POST_MESSAGE_TEAM]。</span><span class="sxs-lookup"><span data-stu-id="1eafe-148">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="1eafe-149">可讓 app 的 bot 隨時將直接（主動）訊息傳送給任何小組成員，即使使用者之前從未與 bot 交談也一樣。</span><span class="sxs-lookup"><span data-stu-id="1eafe-149">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="1eafe-150">下列內容不是明確的許可權，但會顯示在資訊清單中，RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 以及可以使用 bot 的範圍（在資訊清單中宣告）：</span><span class="sxs-lookup"><span data-stu-id="1eafe-150">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="1eafe-151">RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="1eafe-151">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="1eafe-152">RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="1eafe-152">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="1eafe-153">RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="1eafe-153">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="1eafe-154">SEND_FILES、RECEIVE_FILES。<sup>2</sup>控制 bot 是否可以在個人聊天中傳送和接收檔案（群組聊天或頻道尚不支援此功能）。</span><span class="sxs-lookup"><span data-stu-id="1eafe-154">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="1eafe-155">考量</span><span class="sxs-lookup"><span data-stu-id="1eafe-155">Considerations</span></span>

- <span data-ttu-id="1eafe-156">Bot 只能存取已新增給他們的小組，或是已安裝他們的使用者。</span><span class="sxs-lookup"><span data-stu-id="1eafe-156">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="1eafe-157">Bot 只會接收使用者明確提及的訊息。</span><span class="sxs-lookup"><span data-stu-id="1eafe-157">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="1eafe-158">這個資料離開了公司網路。</span><span class="sxs-lookup"><span data-stu-id="1eafe-158">This data leaves the corporate network.</span></span>

- <span data-ttu-id="1eafe-159">Bot 只能回復提到的交談。</span><span class="sxs-lookup"><span data-stu-id="1eafe-159">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="1eafe-160">在使用者與 bot conversed 之後，如果 bot 儲存該使用者的識別碼，就可以隨時將該使用者傳送給該使用者。</span><span class="sxs-lookup"><span data-stu-id="1eafe-160">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="1eafe-161">在理論上，bot 郵件可能會包含網路釣魚或惡意程式碼網站的連結，但使用者、租使用者管理員或由 Microsoft 全域封鎖機器人。</span><span class="sxs-lookup"><span data-stu-id="1eafe-161">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="1eafe-162">Bot 可以針對應用程式新增至的小組成員，或針對個人或群組聊天中的個別使用者，取得（且可能會儲存）基本身分識別資訊。</span><span class="sxs-lookup"><span data-stu-id="1eafe-162">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="1eafe-163">若要取得這些使用者的進一步資訊，bot 必須要求他們登入 Azure Active Directory （Azure AD）。</span><span class="sxs-lookup"><span data-stu-id="1eafe-163">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="1eafe-164">Bot 可以在小組中檢索（且可能會儲存）頻道清單;這個資料離開了公司網路。</span><span class="sxs-lookup"><span data-stu-id="1eafe-164">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="1eafe-165">當檔案傳送至 bot 時，檔案會離開公司網路。</span><span class="sxs-lookup"><span data-stu-id="1eafe-165">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="1eafe-166">傳送和接收檔案需要針對每個檔案進行使用者核准。</span><span class="sxs-lookup"><span data-stu-id="1eafe-166">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="1eafe-167">根據預設，bot 無法代表使用者執行動作，但機器人可以要求使用者登入;只要使用者登入，bot 就會有存取權杖，讓它可以執行其他專案。</span><span class="sxs-lookup"><span data-stu-id="1eafe-167">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="1eafe-168">這些額外的專案取決於 bot 以及使用者登入的位置： bot 是已註冊的 Azure AD app https://apps.dev.microsoft.com/ ，而且可以有自己的許可權集。</span><span class="sxs-lookup"><span data-stu-id="1eafe-168">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="1eafe-169">每當在小組中新增或刪除使用者時，系統會通知機器人。</span><span class="sxs-lookup"><span data-stu-id="1eafe-169">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="1eafe-170">Bot 看不到使用者的 IP 位址或其他推薦的資訊。</span><span class="sxs-lookup"><span data-stu-id="1eafe-170">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="1eafe-171">所有資訊都來自 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="1eafe-171">All information comes from Microsoft.</span></span> <span data-ttu-id="1eafe-172">（有一個例外狀況：如果 bot 實現自己的登入體驗，登入 UI 就會看到使用者的 IP 位址和引用資訊。）</span><span class="sxs-lookup"><span data-stu-id="1eafe-172">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="1eafe-173">另一方面，訊息擴充功能請參閱使用者的 IP 位址和引用資訊。</span><span class="sxs-lookup"><span data-stu-id="1eafe-173">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="1eafe-174">應用程式指導方針（以及我們的 AppSource 審查程式）需要在將個人聊天訊息張貼給使用者時加以決定（透過 POST_MESSAGE_TEAM 許可權）來保證有效的目的。</span><span class="sxs-lookup"><span data-stu-id="1eafe-174">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="1eafe-175">在使用不當的情況下，使用者可以封鎖機器人，租使用者系統管理員可以封鎖 app，而且 Microsoft 可以視需要集中封鎖機器人。</span><span class="sxs-lookup"><span data-stu-id="1eafe-175">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="1eafe-176"><sup>1</sup>部分機器人只傳送郵件（POST_MESSAGE_USER）。</span><span class="sxs-lookup"><span data-stu-id="1eafe-176"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="1eafe-177">它們稱為「只通知」機器人，但該詞彙並未參照允許或不允許 bot 執行的動作，這表示 bot 不想公開會話中的體驗。</span><span class="sxs-lookup"><span data-stu-id="1eafe-177">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="1eafe-178">團隊使用此欄位來停用通常會啟用的 UI 中的功能;bot 與確實會公開會話體驗的 bot 相比，未受到任何允許的限制。</span><span class="sxs-lookup"><span data-stu-id="1eafe-178">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="1eafe-179"><sup>2</sup>是由應用程式的資訊清單 .csv 檔案中 bot 物件上的 SupportsFiles 布林值屬性所管轄。</span><span class="sxs-lookup"><span data-stu-id="1eafe-179"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="1eafe-180">如果 bot 有自己的登入，在使用者第一次登入時，會有另一個不同的方式：同意體驗。</span><span class="sxs-lookup"><span data-stu-id="1eafe-180">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="1eafe-181">目前，與團隊應用程式（bot、索引標籤、連接器或訊息延伸）內任何功能相關聯的 Azure AD 許可權，都與此處所列的小組許可權完全不同。</span><span class="sxs-lookup"><span data-stu-id="1eafe-181">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="1eafe-182">索引標籤</span><span class="sxs-lookup"><span data-stu-id="1eafe-182">Tabs</span></span>

<span data-ttu-id="1eafe-183">[索引標籤] 是在團隊內執行的網站。</span><span class="sxs-lookup"><span data-stu-id="1eafe-183">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="1eafe-184">所需許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-184">Required permissions</span></span>

<span data-ttu-id="1eafe-185">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="1eafe-185">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="1eafe-186">選用許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-186">Optional permissions</span></span>

<span data-ttu-id="1eafe-187">None （目前）</span><span class="sxs-lookup"><span data-stu-id="1eafe-187">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="1eafe-188">考量</span><span class="sxs-lookup"><span data-stu-id="1eafe-188">Considerations</span></span>

- <span data-ttu-id="1eafe-189">索引標籤的風險設定檔與在瀏覽器索引標籤上執行的相同網站幾乎完全相同。</span><span class="sxs-lookup"><span data-stu-id="1eafe-189">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="1eafe-190">索引標籤也會取得執行中的內容，包括目前使用者的登入名稱和 UPN、目前使用者的 Azure AD 物件識別碼、其所在的 Microsoft 365 群組的識別碼（如果是團隊）、租使用者識別碼，以及使用者目前的地區設定。</span><span class="sxs-lookup"><span data-stu-id="1eafe-190">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="1eafe-191">不過，若要將這些識別碼對應至使用者的資訊，索引標籤會必須讓使用者登入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1eafe-191">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="1eafe-192">連接器</span><span class="sxs-lookup"><span data-stu-id="1eafe-192">Connectors</span></span>

<span data-ttu-id="1eafe-193">當外部系統中的事件發生時，連接器會將訊息張貼到頻道。</span><span class="sxs-lookup"><span data-stu-id="1eafe-193">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="1eafe-194">所需許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-194">Required permissions</span></span>

<span data-ttu-id="1eafe-195">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="1eafe-195">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="1eafe-196">選用許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-196">Optional permissions</span></span>

<span data-ttu-id="1eafe-197">REPLYTO_CONNECTOR_MESSAGE]。</span><span class="sxs-lookup"><span data-stu-id="1eafe-197">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="1eafe-198">某些連接器支援可操作的訊息，讓使用者能夠將回應傳送給連接器訊息，例如新增對 GitHub 問題的回復或將日期新增至 Trello 卡片。</span><span class="sxs-lookup"><span data-stu-id="1eafe-198">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="1eafe-199">考量</span><span class="sxs-lookup"><span data-stu-id="1eafe-199">Considerations</span></span>

- <span data-ttu-id="1eafe-200">傳送連接器訊息的系統不會知道要傳送給哪個人或誰接收訊息：不透露給收件者的任何資訊。</span><span class="sxs-lookup"><span data-stu-id="1eafe-200">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="1eafe-201">（Microsoft 是實際的收件者，不是租使用者;Microsoft 會執行實際的頻道張貼。）</span><span class="sxs-lookup"><span data-stu-id="1eafe-201">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="1eafe-202">將連接器郵件張貼到頻道時，任何資料都不會離開公司網路。</span><span class="sxs-lookup"><span data-stu-id="1eafe-202">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="1eafe-203">支援可操作之訊息的連接器（REPLYTO_CONNECTOR_MESSAGE 許可權）也看不到 IP 位址與引用資訊，請參閱此資訊會傳送至 Microsoft，然後路由至先前已在連接器入口網站中向 Microsoft 註冊的 HTTP 端點。</span><span class="sxs-lookup"><span data-stu-id="1eafe-203">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="1eafe-204">每次為頻道設定連接器時，就會建立該連接器實例的唯一 URL。</span><span class="sxs-lookup"><span data-stu-id="1eafe-204">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="1eafe-205">如果該連接器實例已刪除，就不能再使用該 URL。</span><span class="sxs-lookup"><span data-stu-id="1eafe-205">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="1eafe-206">連接器郵件不能包含檔附件。</span><span class="sxs-lookup"><span data-stu-id="1eafe-206">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="1eafe-207">連接器實例 URL 應該視為機密/機密：任何擁有該 URL 的人都可以張貼到該 url，例如電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1eafe-207">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="1eafe-208">因此，有一些垃圾郵件或連結至網路釣魚網站或惡意程式碼的威脅。</span><span class="sxs-lookup"><span data-stu-id="1eafe-208">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="1eafe-209">如果發生這種情況，小組擁有者可以刪除連接器實例。</span><span class="sxs-lookup"><span data-stu-id="1eafe-209">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="1eafe-210">如果傳送連接器訊息的服務遭到破壞並開始傳送垃圾郵件/網路釣魚/惡意程式碼連結，租使用者管理員可以避免建立新的連接器實例，而且 Microsoft 可以集中封鎖它們。</span><span class="sxs-lookup"><span data-stu-id="1eafe-210">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="1eafe-211">目前不可能知道哪些連接器支援可操作的訊息（REPLYTO_CONNECTOR_MESSAGE 許可權）。</span><span class="sxs-lookup"><span data-stu-id="1eafe-211">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="1eafe-212">外寄 webhooks</span><span class="sxs-lookup"><span data-stu-id="1eafe-212">Outgoing webhooks</span></span>

<span data-ttu-id="1eafe-213">*外寄 webhooks*是由小組擁有者或團隊成員動態建立。</span><span class="sxs-lookup"><span data-stu-id="1eafe-213">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="1eafe-214">它們不是團隊 app 的功能;包含此資訊是為了提供完整功能。</span><span class="sxs-lookup"><span data-stu-id="1eafe-214">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="1eafe-215">所需許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-215">Required permissions</span></span>

<span data-ttu-id="1eafe-216">RECEIVE_MESSAGE、REPLYTO_MESSAGE。</span><span class="sxs-lookup"><span data-stu-id="1eafe-216">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="1eafe-217">可以接收來自使用者的訊息並回復。</span><span class="sxs-lookup"><span data-stu-id="1eafe-217">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="1eafe-218">選用許可權</span><span class="sxs-lookup"><span data-stu-id="1eafe-218">Optional permissions</span></span>

<span data-ttu-id="1eafe-219">無</span><span class="sxs-lookup"><span data-stu-id="1eafe-219">None</span></span>

### <a name="considerations"></a><span data-ttu-id="1eafe-220">考量</span><span class="sxs-lookup"><span data-stu-id="1eafe-220">Considerations</span></span>

- <span data-ttu-id="1eafe-221">外寄 webhooks 與 bot 類似，但許可權較少。</span><span class="sxs-lookup"><span data-stu-id="1eafe-221">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="1eafe-222">您必須明確提及它們，就像機器人一樣。</span><span class="sxs-lookup"><span data-stu-id="1eafe-222">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="1eafe-223">註冊外寄 webhook 後，會產生秘密，這可讓傳出 webhook 驗證寄件者是否為 Microsoft 團隊，而不是惡意攻擊者。</span><span class="sxs-lookup"><span data-stu-id="1eafe-223">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="1eafe-224">這個秘密應該會保密;有權存取的任何人都可以模仿 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="1eafe-224">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="1eafe-225">如果機密遭到破壞，就可以刪除並重新建立傳出 webhook，並產生新的密碼。</span><span class="sxs-lookup"><span data-stu-id="1eafe-225">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="1eafe-226">雖然您可以建立無法驗證密碼的傳出 webhook，但我們建議您不要使用它。</span><span class="sxs-lookup"><span data-stu-id="1eafe-226">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="1eafe-227">除了接收和回復郵件以外，待發 webhooks 無法進行許多動作：他們無法主動傳送郵件、無法傳送或接收檔案，除了接收和回復郵件以外，其他人也無法進行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="1eafe-227">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
