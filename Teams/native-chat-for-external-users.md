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
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams 中 (使用者) 原生聊天體驗

當 Microsoft Teams 使用者與來自 (使用者) 聊天時，聊天體驗僅限於文字。 不過，如果您的 Teams 使用者和另一個組織中的人員都採用 TeamsOnly 升級模式，您可以享有「原生-Teams 聊天體驗」，包括豐富的格式、@mentions和其他聊天功能。 原生 Teams 與其他組織人員聊天僅限 1：1 聊天。

所有 Teams 租使用者都開啟了其他組織人員原生聊天體驗，但並非所有人員都符合資格。 若要提供原生聊天體驗，寄件者和收件者都需要為 TeamsOnly 升級模式進行配置。 若要深入瞭解升級原則，請閱讀 [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。

若要在 Teams 中查看外部存取使用者的功能清單，請參閱[比較外部和來賓存取。](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何知道我是否進行原生聊天？

如果您只能在聊天中與其他組織人員交換文字，表示您目前使用標準外部存取 (聊天) 聊天。 如果您有所有其他聊天功能，包括格式、@mentions、表情符號等，則您正進行原生 Teams 聊天。 

Teams 會定期檢查其他組織中的人員升級模式，如果發現他們在 TeamsOnly 升級模式中執行 Teams，系統會提示您切換到原生 Teams 聊天並鎖定原始聊天。

當您切換到原生 Teams 聊天時，Teams 不會合並這兩個交談。 相反地，您將在聊天來源中看到這兩個聊天。 新的原生 Teams 聊天為使用中，但舊的純文字聊天已鎖定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果使用者不再使用 Teams Only 模式，會發生什麼情況？

如果您與其他組織中的人員進行原生 Teams 聊天，但其中一人已退出 TeamsOnly 升級模式，Teams 會鎖定原生 Teams 聊天，並為您提供僅限文字聊天的連結。 您將無法在原生 Teams 聊天中繼續。 您仍然可以閱讀原生 Teams 聊天，但無法繼續在那裡進行交談。

如果 Teams 找到與此人的舊文字聊天，就會重新恢復該聊天。 否則，Teams 會建立一個新的純文字聊天。


## <a name="related-topics"></a>相關主題

[在 Teams 中管理外部存取](manage-external-access.md)
