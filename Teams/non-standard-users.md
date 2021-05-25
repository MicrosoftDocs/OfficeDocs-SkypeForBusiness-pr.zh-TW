---
title: Teams非標準使用者的應用程式行為
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解應用程式中的應用程式Microsoft Teams非標準使用者的行為。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c27a73928e0740eb325c269fd5ac625fa4c43086
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628922"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="eeab8-103">Microsoft Teams非標準使用者的應用程式行為</span><span class="sxs-lookup"><span data-stu-id="eeab8-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="eeab8-104">本文將說明當來賓、Teams外部使用者 (、) 和匿名使用者出現時，Teams的行為。</span><span class="sxs-lookup"><span data-stu-id="eeab8-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="eeab8-105">來賓 **使用者** 不是貴組織的員工、學生或成員。</span><span class="sxs-lookup"><span data-stu-id="eeab8-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="eeab8-106">他們沒有貴組織的學校或公司帳戶。</span><span class="sxs-lookup"><span data-stu-id="eeab8-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="eeab8-107">外部 **(使用者**) 屬於另一個網域，且無法存取貴組織的小組或小組資源。</span><span class="sxs-lookup"><span data-stu-id="eeab8-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="eeab8-108">有關來賓與外部使用者的詳細比較， [請參閱與來自其他組織的使用者通訊](./communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="eeab8-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="eeab8-109">匿名 **使用者** 是使用者透過連結加入Teams會議中的概念。</span><span class="sxs-lookup"><span data-stu-id="eeab8-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="eeab8-110">使用者尚未使用其 Microsoft 或組織帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="eeab8-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="eeab8-111">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="eeab8-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="eeab8-112">為來賓使用者安裝、更新及刪除</span><span class="sxs-lookup"><span data-stu-id="eeab8-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="eeab8-113">來賓無法安裝、更新或刪除應用程式至共用內容 ，例如聊天、頻道或會議，但他們可以使用訊息擴充功能與直接連結來進入個人範圍。</span><span class="sxs-lookup"><span data-stu-id="eeab8-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="eeab8-114">來賓無法從桌面應用程式存取 Teams應用程式Teams，但可以使用直接連結存取。</span><span class="sxs-lookup"><span data-stu-id="eeab8-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="eeab8-115">來賓使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="eeab8-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="eeab8-116">如果應用程式是由原生使用者安裝，來賓可以使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="eeab8-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="eeab8-117">安裝至頻道的 Bot</span><span class="sxs-lookup"><span data-stu-id="eeab8-117">Bots installed to a channel</span></span>

<span data-ttu-id="eeab8-118">Bot 可以主動訊息給來賓使用者，但來賓無法與 Bot 互動。</span><span class="sxs-lookup"><span data-stu-id="eeab8-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="eeab8-119">來賓無法一對一訊息給 Bot、提及 Bot，或與與 Bot 通訊的介面卡片互動。</span><span class="sxs-lookup"><span data-stu-id="eeab8-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="eeab8-120">使用策略安裝的個人 Bot</span><span class="sxs-lookup"><span data-stu-id="eeab8-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="eeab8-121">來賓會遵循針對任何應用程式的主機租使用者所設定之全域和全組織許可權原則。</span><span class="sxs-lookup"><span data-stu-id="eeab8-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="eeab8-122">如果整個主機組織的應用程式被封鎖，則來賓也無法使用此 App。</span><span class="sxs-lookup"><span data-stu-id="eeab8-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="eeab8-123">全域預設應用程式設定政策中包含的任何 Bot 也會為來賓安裝。</span><span class="sxs-lookup"><span data-stu-id="eeab8-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="eeab8-124">安裝 Bot 之後，Bot 可以主動與來賓通訊，而來賓可以與 Bot 重新通訊。</span><span class="sxs-lookup"><span data-stu-id="eeab8-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="eeab8-125">您無法從全域預設應用程式設定政策移除來賓。</span><span class="sxs-lookup"><span data-stu-id="eeab8-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="eeab8-126">若要避免來賓存取 Bot，您可以建立更多 App 設定策略、指派給內部使用者，以及使用自訂策略安裝 Bot。</span><span class="sxs-lookup"><span data-stu-id="eeab8-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="eeab8-127">外部 (聯合) 使用者</span><span class="sxs-lookup"><span data-stu-id="eeab8-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="eeab8-128">安裝、更新及刪除外部使用者</span><span class="sxs-lookup"><span data-stu-id="eeab8-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="eeab8-129">外部使用者無法在任何內容中安裝、更新或刪除應用程式，例如個人、聊天、頻道或會議。</span><span class="sxs-lookup"><span data-stu-id="eeab8-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="eeab8-130">他們無法存取 Teams App Store。</span><span class="sxs-lookup"><span data-stu-id="eeab8-130">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="eeab8-131">外部使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="eeab8-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="eeab8-132">外部使用者無法在任何應用程式Teams，當外部使用者新增到與原生使用者之間的內容時，所有原生和外部使用者都無法再使用 App。</span><span class="sxs-lookup"><span data-stu-id="eeab8-132">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>
- <span data-ttu-id="eeab8-133">外部使用者不會受到應用程式政策的影響，因為他們無法Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="eeab8-133">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="eeab8-134">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="eeab8-134">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="eeab8-135">為匿名使用者安裝、更新及刪除</span><span class="sxs-lookup"><span data-stu-id="eeab8-135">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="eeab8-136">匿名使用者無法安裝、更新或刪除會議中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="eeab8-136">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="eeab8-137">匿名使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="eeab8-137">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="eeab8-138">匿名使用者無法直接在會議中使用 App。</span><span class="sxs-lookup"><span data-stu-id="eeab8-138">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="eeab8-139">如果匿名使用者存在，原生使用者可以繼續使用會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="eeab8-139">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="eeab8-140">如果應用程式在聊天中傳送介面卡片，匿名使用者可以與卡片互動。</span><span class="sxs-lookup"><span data-stu-id="eeab8-140">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="eeab8-141">若要詳細資訊，請參閱 [允許匿名使用者加入會議](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。</span><span class="sxs-lookup"><span data-stu-id="eeab8-141">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="eeab8-142">匿名使用者將繼承使用者層級全域預設權限原則。</span><span class="sxs-lookup"><span data-stu-id="eeab8-142">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="eeab8-143">如果使用者層級許可權Teams啟用應用程式，他們可以與會議中的應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="eeab8-143">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="eeab8-144">匿名使用者只能與會議中現有的應用程式互動，且無法取得和/或管理這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="eeab8-144">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
