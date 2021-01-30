---
title: Microsoft 團隊中的外部 (聯盟) 使用者的原生聊天體驗
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解在 TeamsOnly 升級模式的 Microsoft 團隊中，外部 access (聯盟) 使用者的「本機小組聊天」體驗。
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055655"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="941e3-103">Microsoft 團隊中的外部 (聯盟) 使用者的原生聊天體驗</span><span class="sxs-lookup"><span data-stu-id="941e3-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="941e3-104">當 Microsoft 團隊使用者與外部 (聯盟) 使用者聊天時，聊天體驗會限制為文字。</span><span class="sxs-lookup"><span data-stu-id="941e3-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="941e3-105">不過，如果您的小組使用者和其他組織中的人員都處於 TeamsOnly 升級模式，您可以使用「原生小組聊天體驗」，其中包括豐富的格式設定、@mentions 及其他聊天功能。</span><span class="sxs-lookup"><span data-stu-id="941e3-105">However, if both your Teams user and the person in another organization is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="941e3-106">換句話說，您可以在與組織中的使用者一樣，與其他組織中的合格人員進行相同的豐富的1:1 團隊交談體驗。</span><span class="sxs-lookup"><span data-stu-id="941e3-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible people in other organizations as you'd have with users in your organization.</span></span> <span data-ttu-id="941e3-107">原生團隊與其他組織中的人員聊天僅限1:1 聊天。</span><span class="sxs-lookup"><span data-stu-id="941e3-107">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="941e3-108">針對其他組織中的人員開啟的原生聊天體驗已針對所有團隊承租人開啟，但並非所有人員都符合資格。</span><span class="sxs-lookup"><span data-stu-id="941e3-108">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="941e3-109">若要提供原生聊天體驗，必須針對 TeamsOnly 升級模式設定傳送者和收件者。</span><span class="sxs-lookup"><span data-stu-id="941e3-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="941e3-110">若要深入瞭解升級原則，請參閱 [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="941e3-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="941e3-111">若要查看小組中外部 access 使用者的功能清單，請參閱 [比較外部與來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="941e3-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="941e3-112">如何知道我正在使用原生聊天嗎？</span><span class="sxs-lookup"><span data-stu-id="941e3-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="941e3-113">如果您只能與其他組織中的人員共用您的聊天中的文字，您就可以使用標準的外部存取 (聯盟) 聊天。</span><span class="sxs-lookup"><span data-stu-id="941e3-113">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="941e3-114">如果您已擁有所有其他聊天功能，包括格式設定、@mentions、emoji 等，則您就是在本機團隊聊天中。</span><span class="sxs-lookup"><span data-stu-id="941e3-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="941e3-115">團隊會定期針對其他組織中的人員檢查升級模式，並在 TeamsOnly 升級模式中找到他們正在執行的小組時，系統會提示您切換到原生團隊聊天並鎖定原始聊天。</span><span class="sxs-lookup"><span data-stu-id="941e3-115">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="941e3-116">當您切換到原生團隊聊天時，團隊不會合並這兩個交談。</span><span class="sxs-lookup"><span data-stu-id="941e3-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="941e3-117">相反地，您會在聊天摘要中看到兩個聊天。</span><span class="sxs-lookup"><span data-stu-id="941e3-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="941e3-118">新的原生團隊聊天處於作用中狀態，但舊的純文字聊天功能已鎖定。</span><span class="sxs-lookup"><span data-stu-id="941e3-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="941e3-119">如果使用者不再處於 [只在團隊中] 模式中，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="941e3-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="941e3-120">如果您有原生團隊與其他組織中的人員交談，然後其中一個您的 TeamsOnly 升級模式，則團隊會封鎖原生團隊聊天，並為您提供受限制且僅限文字聊天的連結。</span><span class="sxs-lookup"><span data-stu-id="941e3-120">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="941e3-121">您無法在原生團隊聊天中繼續進行。</span><span class="sxs-lookup"><span data-stu-id="941e3-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="941e3-122">您仍可閱讀原生團隊聊天，但無法在該處繼續交談。</span><span class="sxs-lookup"><span data-stu-id="941e3-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="941e3-123">如果團隊發現與此人的舊純文字聊天，就會接收該聊天。</span><span class="sxs-lookup"><span data-stu-id="941e3-123">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="941e3-124">否則，小組會建立新的純文字聊天。</span><span class="sxs-lookup"><span data-stu-id="941e3-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="941e3-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="941e3-125">Related topics</span></span>

[<span data-ttu-id="941e3-126">管理團隊中的外部存取</span><span class="sxs-lookup"><span data-stu-id="941e3-126">Manage external access in Teams</span></span>](manage-external-access.md)
