---
title: 外部使用者與 (使用者) 原生聊天Microsoft Teams
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
description: 瞭解在兩Teams TeamsOnly 升級模式中 () 使用者Microsoft Teams外部存取的原生聊天體驗。
ms.openlocfilehash: 02bf09a7623079eb207ffca1b122bc03bf07c5c8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240459"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>外部使用者與 (使用者) 原生聊天Microsoft Teams

當Microsoft Teams使用者與 (使用者) 聊天時，聊天體驗僅限於文字。 不過，如果您的 Teams 使用者和另一個組織中的人員都採用 TeamsOnly 升級模式，您可以擁有「原生 Teams 聊天體驗」，包括豐富的格式、@mentions 和其他聊天功能。 原生Teams與其他組織人員聊天僅限 1：1 聊天。

針對所有租使用者開啟其他組織人員原生聊天體驗Teams，但並非所有人員都符合資格。 若要提供原生聊天體驗，寄件者和收件者都需要為 TeamsOnly 升級模式進行配置。 若要深入瞭解升級原則，請閱讀 [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。

若要查看外部存取使用者在 Teams 的功能清單，請參閱[比較外部和來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何知道我是否進行原生聊天？

如果您只能與其他組織人員在聊天中交換文字，表示您目前使用標準外部存取 (聊天) 聊天。 如果您有其他聊天功能，包括格式、@mentions、表情符號等，表示您用原生聊天Teams聊天。 

Teams定期檢查其他組織中的人員升級模式，如果發現他們在 TeamsOnly 升級模式中執行 Teams，系統會提示您切換到原生 Teams 聊天並鎖定原始聊天。

當您切換到原生聊天Teams，Teams不會合並這兩個交談。 相反地，您將在聊天來源中看到這兩個聊天。 新的原生聊天Teams使用中，但舊的純文字聊天已鎖定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果使用者不再使用僅Teams模式，會發生什麼情況？

如果您與其他組織Teams原生 Teams 聊天，然後其中一人被切換出 TeamsOnly 升級模式，Teams 會鎖定原生 Teams 聊天，並為您提供僅限文字聊天的連結。 您無法繼續原生聊天Teams聊天。 您仍然可以讀取原生Teams聊天，但無法繼續交談。

如果Teams找到與此人的舊文字聊天，就會重新恢復該聊天。 否則，Teams建立一個新的純文字聊天。


## <a name="related-topics"></a>相關主題

[管理外部存取Teams](manage-external-access.md)
