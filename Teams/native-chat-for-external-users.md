---
title: Microsoft Teams 中 (使用者) 原生聊天體驗
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
description: 瞭解本機 Teams 聊天體驗， (Microsoft Teams 中的) 使用者同時使用 TeamsOnly 升級模式。
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030113"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="97ce5-103">Microsoft Teams 中 (使用者) 原生聊天體驗</span><span class="sxs-lookup"><span data-stu-id="97ce5-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="97ce5-104">當 Microsoft Teams 使用者與來自 (使用者) 聊天時，聊天體驗僅限於文字。</span><span class="sxs-lookup"><span data-stu-id="97ce5-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="97ce5-105">不過，如果您的 Teams 使用者和另一個組織中的人員都採用 TeamsOnly 升級模式，您可以享有「原生-Teams 聊天體驗」，包括豐富的格式、@mentions和其他聊天功能。</span><span class="sxs-lookup"><span data-stu-id="97ce5-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="97ce5-106">原生 Teams 與其他組織人員聊天僅限 1：1 聊天。</span><span class="sxs-lookup"><span data-stu-id="97ce5-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="97ce5-107">所有 Teams 租使用者都開啟了其他組織人員原生聊天體驗，但並非所有人員都符合資格。</span><span class="sxs-lookup"><span data-stu-id="97ce5-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="97ce5-108">若要提供原生聊天體驗，寄件者和收件者都需要為 TeamsOnly 升級模式進行配置。</span><span class="sxs-lookup"><span data-stu-id="97ce5-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="97ce5-109">若要深入瞭解升級原則，請閱讀 [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="97ce5-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="97ce5-110">若要在 Teams 中查看外部存取使用者的功能清單，請參閱[比較外部和來賓存取。](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="97ce5-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="97ce5-111">如何知道我是否進行原生聊天？</span><span class="sxs-lookup"><span data-stu-id="97ce5-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="97ce5-112">如果您只能在聊天中與其他組織人員交換文字，表示您目前使用標準外部存取 (聊天) 聊天。</span><span class="sxs-lookup"><span data-stu-id="97ce5-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="97ce5-113">如果您有所有其他聊天功能，包括格式、@mentions、表情符號等，則您正進行原生 Teams 聊天。</span><span class="sxs-lookup"><span data-stu-id="97ce5-113">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="97ce5-114">Teams 會定期檢查其他組織中的人員升級模式，如果發現他們在 TeamsOnly 升級模式中執行 Teams，系統會提示您切換到原生 Teams 聊天並鎖定原始聊天。</span><span class="sxs-lookup"><span data-stu-id="97ce5-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="97ce5-115">當您切換到原生 Teams 聊天時，Teams 不會合並這兩個交談。</span><span class="sxs-lookup"><span data-stu-id="97ce5-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="97ce5-116">相反地，您將在聊天來源中看到這兩個聊天。</span><span class="sxs-lookup"><span data-stu-id="97ce5-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="97ce5-117">新的原生 Teams 聊天為使用中，但舊的純文字聊天已鎖定。</span><span class="sxs-lookup"><span data-stu-id="97ce5-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="97ce5-118">如果使用者不再使用 Teams Only 模式，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="97ce5-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="97ce5-119">如果您與其他組織中的人員進行原生 Teams 聊天，但其中一人已退出 TeamsOnly 升級模式，Teams 會鎖定原生 Teams 聊天，並為您提供僅限文字聊天的連結。</span><span class="sxs-lookup"><span data-stu-id="97ce5-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="97ce5-120">您將無法在原生 Teams 聊天中繼續。</span><span class="sxs-lookup"><span data-stu-id="97ce5-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="97ce5-121">您仍然可以閱讀原生 Teams 聊天，但無法繼續在那裡進行交談。</span><span class="sxs-lookup"><span data-stu-id="97ce5-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="97ce5-122">如果 Teams 找到與此人的舊文字聊天，就會重新恢復該聊天。</span><span class="sxs-lookup"><span data-stu-id="97ce5-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="97ce5-123">否則，Teams 會建立一個新的純文字聊天。</span><span class="sxs-lookup"><span data-stu-id="97ce5-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="97ce5-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="97ce5-124">Related topics</span></span>

[<span data-ttu-id="97ce5-125">在 Teams 中管理外部存取</span><span class="sxs-lookup"><span data-stu-id="97ce5-125">Manage external access in Teams</span></span>](manage-external-access.md)
