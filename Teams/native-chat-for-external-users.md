---
title: Microsoft 團隊外部（同盟）使用者的原生聊天體驗
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解 Microsoft 團隊中外部存取（同盟）使用者的原生團隊聊天體驗，在兩個使用者都是 TeamsOnly 升級模式的外部使用者之間提供。
ms.openlocfilehash: 1a8cd038f8ff65ea24abb790e564d2cb30ef0ed1
ms.sourcegitcommit: 44e47c3b2eb44c38cb8d761befdc6c0cef7c61bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2020
ms.locfileid: "44842004"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="05c80-103">Microsoft 團隊外部（同盟）使用者的原生聊天體驗</span><span class="sxs-lookup"><span data-stu-id="05c80-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="05c80-104">當 Microsoft 團隊使用者與外部（同盟）使用者聊天時，聊天體驗會限制在文字上。</span><span class="sxs-lookup"><span data-stu-id="05c80-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="05c80-105">不過，如果您的小組使用者與外部使用者都是 TeamsOnly 升級模式，您可以使用「原生小組聊天體驗」，包括豐富的格式設定、@mentions 及其他聊天功能。</span><span class="sxs-lookup"><span data-stu-id="05c80-105">However, if both your Teams user and the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="05c80-106">換句話說，您可以使用與貴組織中的使用者一樣，與符合資格的外部使用者進行相同的豐富1:1 團隊交談體驗。</span><span class="sxs-lookup"><span data-stu-id="05c80-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="05c80-107">原生團隊與外部使用者的聊天，僅限於1:1 聊天（外部使用者無法進行群組聊天）。</span><span class="sxs-lookup"><span data-stu-id="05c80-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="05c80-108">外部使用者的原生聊天體驗已針對所有團隊承租人開啟，但並非所有使用者都符合資格。</span><span class="sxs-lookup"><span data-stu-id="05c80-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="05c80-109">若要提供原生聊天體驗，必須針對 TeamsOnly 升級模式設定傳送者和收件者。</span><span class="sxs-lookup"><span data-stu-id="05c80-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="05c80-110">若要深入瞭解升級原則，請參閱[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="05c80-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="05c80-111">若要查看小組中外部 access 使用者的功能清單，請參閱[比較外部與來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="05c80-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="05c80-112">如何知道我正在使用原生聊天嗎？</span><span class="sxs-lookup"><span data-stu-id="05c80-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="05c80-113">如果您只能在聊天中與外部使用者交換文字，則您是使用標準的外部存取（同盟）聊天。</span><span class="sxs-lookup"><span data-stu-id="05c80-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="05c80-114">如果您已有所有其他的聊天功能，包括格式設定、@mentions、emoji 等，您就是與外部使用者進行的原生團隊交談。</span><span class="sxs-lookup"><span data-stu-id="05c80-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="05c80-115">團隊會定期檢查外部使用者的升級模式，並在 TeamsOnly 升級模式中找到執行團隊的外部使用者時，系統會提示您切換到原生團隊聊天並鎖定原始聊天。</span><span class="sxs-lookup"><span data-stu-id="05c80-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="05c80-116">當您切換到原生團隊聊天時，團隊不會合並這兩個交談。</span><span class="sxs-lookup"><span data-stu-id="05c80-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="05c80-117">相反地，您會在聊天摘要中看到兩個聊天。</span><span class="sxs-lookup"><span data-stu-id="05c80-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="05c80-118">新的原生團隊聊天處於作用中狀態，但舊的純文字聊天功能已鎖定。</span><span class="sxs-lookup"><span data-stu-id="05c80-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="05c80-119">如果使用者不再處於 [只在團隊中] 模式中，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="05c80-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="05c80-120">如果您有原生團隊與外部使用者聊天，然後其中一個您的 TeamsOnly 升級模式，則團隊會封鎖原生團隊聊天，並為您提供有限的純文字聊天的連結。</span><span class="sxs-lookup"><span data-stu-id="05c80-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="05c80-121">您無法在原生團隊聊天中繼續進行。</span><span class="sxs-lookup"><span data-stu-id="05c80-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="05c80-122">您仍可閱讀原生團隊聊天，但無法在該處繼續交談。</span><span class="sxs-lookup"><span data-stu-id="05c80-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="05c80-123">如果團隊發現與外部使用者的舊純文字聊天，就會接收該聊天。</span><span class="sxs-lookup"><span data-stu-id="05c80-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="05c80-124">否則，小組會建立新的純文字聊天。</span><span class="sxs-lookup"><span data-stu-id="05c80-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="05c80-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="05c80-125">Related topics</span></span>

[<span data-ttu-id="05c80-126">管理團隊中的外部存取</span><span class="sxs-lookup"><span data-stu-id="05c80-126">Manage external access in Teams</span></span>](manage-external-access.md)
