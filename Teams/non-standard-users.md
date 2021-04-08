---
title: 適用于非標準使用者的 Teams 應用程式行為
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解 Microsoft Teams 中的應用程式對於非標準使用者的行為。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb4b5dfebabfcd0bc86006d93272c3901e7dcfc7
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617846"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="b5cae-103">適用于非標準使用者的 Microsoft Teams 應用程式行為</span><span class="sxs-lookup"><span data-stu-id="b5cae-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="b5cae-104">本文將說明 Teams 中的應用程式在來賓、外部 (、) 和匿名使用者在 Teams 環境中時的行為。</span><span class="sxs-lookup"><span data-stu-id="b5cae-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="b5cae-105">來賓 **使用者** 不是貴組織的員工、學生或成員。</span><span class="sxs-lookup"><span data-stu-id="b5cae-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="b5cae-106">他們沒有貴組織的學校或公司帳戶。</span><span class="sxs-lookup"><span data-stu-id="b5cae-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="b5cae-107">外部 **(使用者**) 屬於另一個網域，且無法存取貴組織的小組或小組資源。</span><span class="sxs-lookup"><span data-stu-id="b5cae-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="b5cae-108">有關來賓與外部使用者的詳細比較， [請參閱與來自其他組織的使用者通訊](./communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="b5cae-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="b5cae-109">匿名 **使用者** 是 Teams 會議中使用者透過連結加入會議的概念。</span><span class="sxs-lookup"><span data-stu-id="b5cae-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="b5cae-110">使用者尚未使用其 Microsoft 或組織帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b5cae-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="b5cae-111">來賓使用者存取權</span><span class="sxs-lookup"><span data-stu-id="b5cae-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="b5cae-112">為來賓使用者安裝、更新及刪除</span><span class="sxs-lookup"><span data-stu-id="b5cae-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="b5cae-113">來賓無法安裝、更新或刪除應用程式至共用內容，例如聊天、頻道或會議。</span><span class="sxs-lookup"><span data-stu-id="b5cae-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="b5cae-114">他們可以使用郵件副檔名和直接連結，將應用程式安裝、更新或刪除到其個人範圍。</span><span class="sxs-lookup"><span data-stu-id="b5cae-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="b5cae-115">來賓無法存取 Teams App Store。</span><span class="sxs-lookup"><span data-stu-id="b5cae-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="b5cae-116">來賓使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="b5cae-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="b5cae-117">如果應用程式是由原生使用者安裝，來賓可以使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5cae-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="b5cae-118">Bot 可以主動訊息給來賓使用者，但來賓無法與 Bot 互動。</span><span class="sxs-lookup"><span data-stu-id="b5cae-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="b5cae-119">來賓無法以 @提及 Bot 的方式訊息給 Bot 1：1，或與與 Bot 通訊的介面卡片互動。</span><span class="sxs-lookup"><span data-stu-id="b5cae-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="b5cae-120">來賓會遵循針對任何 App 的主機租使用者所設定之全域和全組織許可權原則。</span><span class="sxs-lookup"><span data-stu-id="b5cae-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="b5cae-121">換句話說，如果整個主機組織都封鎖了應用程式，則來賓也便無法使用此 App。</span><span class="sxs-lookup"><span data-stu-id="b5cae-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="b5cae-122">設定原則不適用於來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="b5cae-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="b5cae-123">這表示系統管理從預設策略釘寄的應用程式不會影響來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="b5cae-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="b5cae-124">外部 (聯合) 使用者存取</span><span class="sxs-lookup"><span data-stu-id="b5cae-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="b5cae-125">安裝、更新及刪除外部使用者</span><span class="sxs-lookup"><span data-stu-id="b5cae-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="b5cae-126">外部使用者無法在任何內容中安裝、更新或刪除應用程式，例如個人、聊天、頻道或會議。</span><span class="sxs-lookup"><span data-stu-id="b5cae-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="b5cae-127">他們無法存取 Teams App Store。</span><span class="sxs-lookup"><span data-stu-id="b5cae-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="b5cae-128">外部使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="b5cae-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="b5cae-129">外部使用者無法使用任何 Teams 應用程式，而且當外部使用者新增到原生使用者的上下文時，所有原生和外部使用者都無法再使用 App。</span><span class="sxs-lookup"><span data-stu-id="b5cae-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="b5cae-130">外部使用者不會受到應用程式政策的影響，因為他們無法使用 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5cae-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="b5cae-131">會議存取中的匿名使用者</span><span class="sxs-lookup"><span data-stu-id="b5cae-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="b5cae-132">為匿名使用者安裝、更新及刪除</span><span class="sxs-lookup"><span data-stu-id="b5cae-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="b5cae-133">匿名使用者無法安裝、更新或刪除會議中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5cae-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="b5cae-134">匿名使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="b5cae-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="b5cae-135">匿名使用者無法直接在會議中使用 App。</span><span class="sxs-lookup"><span data-stu-id="b5cae-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="b5cae-136">如果匿名使用者存在，原生使用者可以繼續使用會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5cae-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="b5cae-137">如果應用程式在聊天中傳送介面卡片，匿名使用者可以與卡片互動以瞭解更多資訊，請參閱允許匿名使用者 [加入會議](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)。</span><span class="sxs-lookup"><span data-stu-id="b5cae-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card For more information, see [Allow anonymous users to join meetings](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="b5cae-138">匿名使用者將繼承使用者層級全域預設權限原則。</span><span class="sxs-lookup"><span data-stu-id="b5cae-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="b5cae-139">如果使用者層級權限原則已啟用應用程式，他們可以與 Teams 會議中的應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="b5cae-139">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="b5cae-140">匿名使用者只能與會議中現有的應用程式互動，且無法取得和/或管理這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5cae-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
