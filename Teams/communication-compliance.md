---
title: Microsoft Teams 的通訊合規性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 從 Microsoft Teams 的觀點瞭解通訊合規性，這是測試人員風險解決方案集的一部分 (這是 M365 通訊合規性功能的一) 。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf032669edc7255571e2501774ac0d0ee0df47d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121531"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="f49dc-103">Microsoft Teams 的通訊合規性</span><span class="sxs-lookup"><span data-stu-id="f49dc-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="f49dc-104">通訊合規性是 Microsoft 365 中的內部人員風險解決方案，可協助偵測、捕獲及處理貴組織中不當的郵件，協助將通訊風險降到最低。</span><span class="sxs-lookup"><span data-stu-id="f49dc-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="f49dc-105">對於 Microsoft Teams，通訊合規性可協助[](/microsoft-365/compliance/communication-compliance-feature-reference)識別 Teams 頻道或 1：1 和群組聊天中的下列不當內容類型：</span><span class="sxs-lookup"><span data-stu-id="f49dc-105">For Microsoft Teams, communication compliance helps identify the [following types](/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="f49dc-106">令人反感、褻褻和騷擾的語言</span><span class="sxs-lookup"><span data-stu-id="f49dc-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="f49dc-107">成人、雷斯和 gory 影像</span><span class="sxs-lookup"><span data-stu-id="f49dc-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="f49dc-108">共用敏感性資訊</span><span class="sxs-lookup"><span data-stu-id="f49dc-108">Sharing of sensitive information</span></span>

<span data-ttu-id="f49dc-109">有關通訊合規性以及如何為貴組織設定策略的資訊，請參閱 [Microsoft 365 中的通訊合規性](/microsoft-365/compliance/communication-compliance)。</span><span class="sxs-lookup"><span data-stu-id="f49dc-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="f49dc-110">如何在 Microsoft Teams 中使用通訊合規性</span><span class="sxs-lookup"><span data-stu-id="f49dc-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="f49dc-111">通訊合規性與 Microsoft Teams 緊密整合，有助於將貴組織的通訊風險降到最低。</span><span class="sxs-lookup"><span data-stu-id="f49dc-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="f49dc-112">在您建立第一個通訊合規性政策之後，您可以主動管理在通知中自動標出不當的 Microsoft Teams 訊息和內容。</span><span class="sxs-lookup"><span data-stu-id="f49dc-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="f49dc-113">快速入門</span><span class="sxs-lookup"><span data-stu-id="f49dc-113">Getting started</span></span>

<span data-ttu-id="f49dc-114">開始使用 Microsoft Teams 中的通訊合規性，首先[](/microsoft-365/compliance/communication-compliance-plan)規劃及建立預先定義的或自訂的政策，以識別 Teams 頻道或 1：1 和群組中的不當使用者活動。</span><span class="sxs-lookup"><span data-stu-id="f49dc-114">Getting started with communication compliance in Microsoft Teams begins with [planning](/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="f49dc-115">請記住，您必須在設定過程中設定一些[](/microsoft-365/compliance/communication-compliance-configure)許可權和基本先決條件。</span><span class="sxs-lookup"><span data-stu-id="f49dc-115">Keep in mind that you'll need to [configure](/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="f49dc-116">Teams 系統管理員可以在下列層級設定通訊合規性政策：</span><span class="sxs-lookup"><span data-stu-id="f49dc-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="f49dc-117">**使用者層級**：此層級原則適用于個別的 Teams 使用者，或可能適用于貴組織的所有 Teams 使用者。</span><span class="sxs-lookup"><span data-stu-id="f49dc-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="f49dc-118">這些策略涵蓋這些使用者可能會以 1：1 或群組聊天傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="f49dc-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="f49dc-119">使用者聊天通訊會自動監控使用者為成員的所有 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="f49dc-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="f49dc-120">**Teams 層級**：此層級原則適用于 Microsoft 小組頻道。</span><span class="sxs-lookup"><span data-stu-id="f49dc-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="f49dc-121">這些策略僅涵蓋在 Teams 頻道中送出的郵件。</span><span class="sxs-lookup"><span data-stu-id="f49dc-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="f49dc-122">在 Microsoft Teams 中處理不當郵件</span><span class="sxs-lookup"><span data-stu-id="f49dc-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="f49dc-123">在您已針對 Microsoft Teams 郵件已建立策略並收到通訊合規性通知之後，組織中的合規性審查者可以針對這些郵件採取行動。</span><span class="sxs-lookup"><span data-stu-id="f49dc-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="f49dc-124">在 Microsoft Teams 中，校閱通訊合規性通知，以及移除已標出的郵件，以協助保護貴組織。</span><span class="sxs-lookup"><span data-stu-id="f49dc-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![在 Teams 中移除郵件](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="f49dc-126">移除的郵件和內容會以通知取代，讓檢視器瞭解郵件或內容已移除，以及哪些政策適用于移除。</span><span class="sxs-lookup"><span data-stu-id="f49dc-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="f49dc-127">已移除郵件或內容的寄件者也會收到移除狀態的通知，並且提供原始郵件內容，以瞭解其移除相關內容。</span><span class="sxs-lookup"><span data-stu-id="f49dc-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="f49dc-128">寄件者也可以查看適用于郵件移除的特定原則條件。</span><span class="sxs-lookup"><span data-stu-id="f49dc-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="f49dc-129">寄件者看到之策略提示範例：</span><span class="sxs-lookup"><span data-stu-id="f49dc-129">Example of policy tip seen by sender:</span></span>

![寄件者的策略提示](./media/communication-compliance-warning-1.png)

<span data-ttu-id="f49dc-131">寄件者看到之策略條件通知範例：</span><span class="sxs-lookup"><span data-stu-id="f49dc-131">Example of policy condition notification seen by the sender:</span></span>

![寄件者的政策條件資訊](./media/communication-compliance-warning-2.png)

<span data-ttu-id="f49dc-133">收件者看到之策略提示範例：</span><span class="sxs-lookup"><span data-stu-id="f49dc-133">Example of policy tip seen by recipient:</span></span>

![收件者的政策提示](./media/communication-compliance-warning-3.png)