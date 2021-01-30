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
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft 團隊中的外部 (聯盟) 使用者的原生聊天體驗

當 Microsoft 團隊使用者與外部 (聯盟) 使用者聊天時，聊天體驗會限制為文字。 不過，如果您的小組使用者和其他組織中的人員都處於 TeamsOnly 升級模式，您可以使用「原生小組聊天體驗」，其中包括豐富的格式設定、@mentions 及其他聊天功能。 換句話說，您可以在與組織中的使用者一樣，與其他組織中的合格人員進行相同的豐富的1:1 團隊交談體驗。 原生團隊與其他組織中的人員聊天僅限1:1 聊天。

針對其他組織中的人員開啟的原生聊天體驗已針對所有團隊承租人開啟，但並非所有人員都符合資格。 若要提供原生聊天體驗，必須針對 TeamsOnly 升級模式設定傳送者和收件者。 若要深入瞭解升級原則，請參閱 [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。

若要查看小組中外部 access 使用者的功能清單，請參閱 [比較外部與來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何知道我正在使用原生聊天嗎？

如果您只能與其他組織中的人員共用您的聊天中的文字，您就可以使用標準的外部存取 (聯盟) 聊天。 如果您已擁有所有其他聊天功能，包括格式設定、@mentions、emoji 等，則您就是在本機團隊聊天中。 

團隊會定期針對其他組織中的人員檢查升級模式，並在 TeamsOnly 升級模式中找到他們正在執行的小組時，系統會提示您切換到原生團隊聊天並鎖定原始聊天。

當您切換到原生團隊聊天時，團隊不會合並這兩個交談。 相反地，您會在聊天摘要中看到兩個聊天。 新的原生團隊聊天處於作用中狀態，但舊的純文字聊天功能已鎖定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果使用者不再處於 [只在團隊中] 模式中，會發生什麼情況？

如果您有原生團隊與其他組織中的人員交談，然後其中一個您的 TeamsOnly 升級模式，則團隊會封鎖原生團隊聊天，並為您提供受限制且僅限文字聊天的連結。 您無法在原生團隊聊天中繼續進行。 您仍可閱讀原生團隊聊天，但無法在該處繼續交談。

如果團隊發現與此人的舊純文字聊天，就會接收該聊天。 否則，小組會建立新的純文字聊天。


## <a name="related-topics"></a>相關主題

[管理團隊中的外部存取](manage-external-access.md)
