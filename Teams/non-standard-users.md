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
ms.openlocfilehash: 6a8c3c842b47c4575779de4c0ae8301bededb632
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098299"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="97f05-103">適用于非標準使用者的 Microsoft Teams 應用程式行為</span><span class="sxs-lookup"><span data-stu-id="97f05-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="97f05-104">本文將說明 Teams 中的應用程式在來賓、外部 (、) 和匿名使用者在 Teams 環境中時的行為。</span><span class="sxs-lookup"><span data-stu-id="97f05-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="97f05-105">**來賓使用者** 不是貴組織的員工、學生或成員。</span><span class="sxs-lookup"><span data-stu-id="97f05-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="97f05-106">他們沒有貴組織的學校或公司帳戶。</span><span class="sxs-lookup"><span data-stu-id="97f05-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="97f05-107">外部 **(使用者**) 屬於另一個網域，且無法存取貴組織的小組或小組資源。</span><span class="sxs-lookup"><span data-stu-id="97f05-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="97f05-108">有關來賓與外部使用者的詳細比較， [請參閱與來自其他組織的使用者通訊](./communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="97f05-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="97f05-109">匿名 **使用者** 是 Teams 會議中使用者透過連結加入會議的概念。</span><span class="sxs-lookup"><span data-stu-id="97f05-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="97f05-110">使用者尚未使用其 Microsoft 或組織帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="97f05-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="97f05-111">來賓使用者存取權</span><span class="sxs-lookup"><span data-stu-id="97f05-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="97f05-112">為來賓使用者安裝、更新及刪除</span><span class="sxs-lookup"><span data-stu-id="97f05-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="97f05-113">來賓無法安裝、更新或刪除應用程式至共用內容，例如聊天、頻道或會議。</span><span class="sxs-lookup"><span data-stu-id="97f05-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="97f05-114">他們可以使用郵件副檔名和直接連結，將應用程式安裝、更新或刪除到其個人範圍。</span><span class="sxs-lookup"><span data-stu-id="97f05-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="97f05-115">來賓無法存取 Teams App Store。</span><span class="sxs-lookup"><span data-stu-id="97f05-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="97f05-116">來賓使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="97f05-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="97f05-117">如果應用程式是由原生使用者安裝，則來賓可以使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="97f05-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="97f05-118">Bot 可以主動訊息來賓使用者，但來賓無法與 Bot 互動。</span><span class="sxs-lookup"><span data-stu-id="97f05-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="97f05-119">來賓無法以 @提及 Bot 的方式訊息給 Bot 1：1，或與與 Bot 通訊的介面卡片互動。</span><span class="sxs-lookup"><span data-stu-id="97f05-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="97f05-120">來賓會遵循針對任何 App 的主機租使用者所設定之全域和全組織許可權原則。</span><span class="sxs-lookup"><span data-stu-id="97f05-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="97f05-121">換句話說，如果整個主機組織都封鎖了應用程式，則來賓也便無法使用此 App。</span><span class="sxs-lookup"><span data-stu-id="97f05-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="97f05-122">設定原則不適用於來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="97f05-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="97f05-123">這表示系統管理從預設策略釘寄的應用程式不會影響來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="97f05-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="97f05-124">外部 (聯合) 使用者存取</span><span class="sxs-lookup"><span data-stu-id="97f05-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="97f05-125">安裝、更新及刪除外部使用者</span><span class="sxs-lookup"><span data-stu-id="97f05-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="97f05-126">外部使用者無法在任何內容中安裝、更新或刪除應用程式，例如個人、聊天、頻道或會議。</span><span class="sxs-lookup"><span data-stu-id="97f05-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="97f05-127">他們無法存取 Teams App Store。</span><span class="sxs-lookup"><span data-stu-id="97f05-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="97f05-128">外部使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="97f05-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="97f05-129">外部使用者無法使用任何 Teams 應用程式，而且當外部使用者新增到原生使用者的上下文時，所有原生和外部使用者都無法再使用 App。</span><span class="sxs-lookup"><span data-stu-id="97f05-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="97f05-130">外部使用者不會受到應用程式政策的影響，因為他們無法使用 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="97f05-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="97f05-131">會議存取中的匿名使用者</span><span class="sxs-lookup"><span data-stu-id="97f05-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="97f05-132">為匿名使用者安裝、更新及刪除</span><span class="sxs-lookup"><span data-stu-id="97f05-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="97f05-133">匿名使用者無法安裝、更新或刪除會議中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="97f05-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="97f05-134">匿名使用者的使用行為與政策</span><span class="sxs-lookup"><span data-stu-id="97f05-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="97f05-135">匿名使用者無法直接在會議中使用 App。</span><span class="sxs-lookup"><span data-stu-id="97f05-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="97f05-136">如果匿名使用者存在，原生使用者可以繼續使用會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="97f05-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="97f05-137">如果應用程式在聊天中傳送介面卡片，匿名使用者可以與卡片互動。</span><span class="sxs-lookup"><span data-stu-id="97f05-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span>

<span data-ttu-id="97f05-138">匿名使用者將繼承使用者層級全域預設權限原則。</span><span class="sxs-lookup"><span data-stu-id="97f05-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="97f05-139">此控制項可讓匿名使用者與 Teams 會議中的應用程式互動 ，如果使用者層級權限原則已啟用應用程式。</span><span class="sxs-lookup"><span data-stu-id="97f05-139">This control allows anonymous users to interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="97f05-140">匿名使用者只能與會議中現有的應用程式互動，且無法取得和/或管理這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="97f05-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>