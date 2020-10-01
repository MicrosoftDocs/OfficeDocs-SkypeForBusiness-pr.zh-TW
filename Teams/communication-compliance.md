---
title: 與 Microsoft 團隊進行溝通合規性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 瞭解溝通合規性（「測試人員-風險方案」方案集中的一部分）從 Microsoft 小組角度 (這是) 的 M365 通訊合規性功能的一部分。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328252"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="d5fcf-103">與 Microsoft 團隊進行溝通合規性</span><span class="sxs-lookup"><span data-stu-id="d5fcf-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="d5fcf-104">[溝通合規性] 是 Microsoft 365 中的測試人員風險解決方案，可協助您偵測、捕獲並對組織中不適當的訊息採取行動，協助將溝通風險降到最低。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="d5fcf-105">針對 Microsoft 團隊，溝通合規性可協助在團隊頻道中或1:1 和群組聊天中找出 [以下類型](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) 的不適當的內容：</span><span class="sxs-lookup"><span data-stu-id="d5fcf-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="d5fcf-106">冒犯性、褻瀆及 harassing 語言</span><span class="sxs-lookup"><span data-stu-id="d5fcf-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="d5fcf-107">成人、racy 和 gory 影像</span><span class="sxs-lookup"><span data-stu-id="d5fcf-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="d5fcf-108">共用機密資訊</span><span class="sxs-lookup"><span data-stu-id="d5fcf-108">Sharing of sensitive information</span></span>

<span data-ttu-id="d5fcf-109">如需溝通合規性的詳細資訊，以及如何為貴組織設定原則，請參閱 [Microsoft 365 中的通訊合規性](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="d5fcf-110">如何在 Microsoft 團隊中使用通訊合規性</span><span class="sxs-lookup"><span data-stu-id="d5fcf-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="d5fcf-111">溝通合規性與 Microsoft 團隊緊密整合，而且可協助將組織中的溝通風險降至最低。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="d5fcf-112">在您設定第一次通訊合規性原則之後，您可以積極管理不適當的 Microsoft 團隊訊息，以及自動標示為提醒的內容。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="d5fcf-113">快速入門</span><span class="sxs-lookup"><span data-stu-id="d5fcf-113">Getting started</span></span>

<span data-ttu-id="d5fcf-114">Microsoft 團隊中的通訊遵從性快速入門開始 [規劃](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) 及建立預先定義或自訂的原則，以找出小組頻道或1:1 和群組中不適當的使用者活動。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="d5fcf-115">請記住，您必須 [設定](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) 部分許可權和基本先決條件，才能做為配置程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="d5fcf-116">團隊管理員可以在下列層面設定通訊合規性原則：</span><span class="sxs-lookup"><span data-stu-id="d5fcf-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="d5fcf-117">**使用者層級**：此等級的原則適用于個別團隊使用者，或適用于您組織中的所有團隊使用者。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="d5fcf-118">這些原則會涵蓋這些使用者可以在1:1 或群組聊天中傳送的訊息。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="d5fcf-119">在使用者是其成員的所有 Microsoft 團隊中，系統會自動監視使用者的聊天通信。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="d5fcf-120">**團隊**階層：此等級的原則適用于 Microsoft 小組頻道。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="d5fcf-121">這些原則只會涵蓋在小組頻道中傳送的訊息。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="d5fcf-122">針對 Microsoft 團隊中不適當的郵件執行動作</span><span class="sxs-lookup"><span data-stu-id="d5fcf-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="d5fcf-123">在您設定原則並為 Microsoft 團隊訊息收到通訊合規性警報之後，就可以開始針對組織中的合規性審查程式，對這些訊息採取行動。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="d5fcf-124">檢閱者可以在 Microsoft 團隊中查看溝通合規性通知，並移除已標記的郵件，以協助保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![移除團隊中的郵件](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="d5fcf-126">已移除的郵件和內容會以通知者的通知取代，說明已移除該郵件或內容，以及適用于移除哪些原則。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="d5fcf-127">已移除的訊息或內容的寄件者也會收到移除狀態的通知，並隨附與移除相關之內容的原始訊息內容。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="d5fcf-128">寄件者也可以查看適用于郵件移除的特定原則情況。</span><span class="sxs-lookup"><span data-stu-id="d5fcf-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="d5fcf-129">由寄件者看到的原則提示範例：</span><span class="sxs-lookup"><span data-stu-id="d5fcf-129">Example of policy tip seen by sender:</span></span>

![寄件者的原則提示](./media/communication-compliance-warning-1.png)

<span data-ttu-id="d5fcf-131">寄件者看到的原則狀況通知範例：</span><span class="sxs-lookup"><span data-stu-id="d5fcf-131">Example of policy condition notification seen by the sender:</span></span>

![寄件者的原則狀況資訊](./media/communication-compliance-warning-2.png)

<span data-ttu-id="d5fcf-133">收件者看到的原則提示範例：</span><span class="sxs-lookup"><span data-stu-id="d5fcf-133">Example of policy tip seen by recipient:</span></span>

![[收件者] 的原則提示](./media/communication-compliance-warning-3.png)
