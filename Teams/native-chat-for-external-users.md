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
description: 瞭解 Microsoft 團隊中外部存取（同盟）使用者的原生團隊聊天體驗，在兩個使用者都是 TeamsOnly 升級模式的外部使用者之間提供。
ms.openlocfilehash: 572087d86672294b566cd99365599dbead1aa3e7
ms.sourcegitcommit: 1448bb2e66074322b8f4bf234fce36ea9c8f9913
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39966756"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft 團隊外部（同盟）使用者的原生聊天體驗
======================================

當 Microsoft 團隊使用者與外部（同盟）使用者聊天時，聊天體驗會限制在文字上。 不過，如果您的小組租使用者與外部使用者都是 TeamsOnly 升級模式，您可以使用「原生團隊聊天體驗」，其中包括豐富的格式設定、@mentions 及其他聊天功能。 換句話說，您可以使用與貴組織中的使用者一樣，與符合資格的外部使用者進行相同的豐富1:1 團隊交談體驗。 原生團隊與外部使用者的聊天，僅限於1:1 聊天（外部使用者無法進行群組聊天）。

外部使用者的原生聊天體驗已針對所有團隊承租人開啟，但並非所有使用者都符合資格。 若要提供原生聊天體驗，寄件者和收件者都必須在執行 TeamsOnly 升級模式的小組租使用者。 若要深入瞭解升級原則，請參閱[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。

若要查看小組中外部 access 使用者的功能清單，請參閱[比較外部與來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何知道我正在使用原生聊天嗎？

如果您只能在聊天中與外部使用者交換文字，則您是使用標準的外部存取（同盟）聊天。 如果您已有所有其他的聊天功能，包括格式設定、@mentions、emoji 等，您就是與外部使用者進行的原生團隊交談。 

團隊會定期檢查外部使用者的升級模式，並在 TeamsOnly 升級模式中找到執行團隊的外部使用者時，系統會提示您切換到原生團隊聊天並鎖定原始聊天。

當您切換到原生團隊聊天時，團隊不會合並這兩個交談。 相反地，您會在聊天摘要中看到兩個聊天。 新的原生團隊聊天處於作用中狀態，但舊的純文字聊天功能已鎖定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果使用者不再處於 [只在團隊中] 模式中，會發生什麼情況？

如果您有原生團隊與外部使用者聊天，然後其中一個您的 TeamsOnly 升級模式，則團隊會封鎖原生團隊聊天，並為您提供有限的純文字聊天的連結。 您無法在原生團隊聊天中繼續進行。 您仍可閱讀原生團隊聊天，但無法在該處繼續交談。

如果團隊發現與外部使用者的舊純文字聊天，就會接收該聊天。 否則，小組會建立新的純文字聊天。


## <a name="related-topics"></a>相關主題

[管理團隊中的外部存取](manage-external-access.md)
