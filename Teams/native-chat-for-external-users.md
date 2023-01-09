---
title: Microsoft Teams 中外部 (同盟) 使用者的原生聊天體驗
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解 Microsoft Teams 中的外部存取 (同盟) 使用者的原生 Teams 聊天體驗。這兩個使用者都處於 TeamsOnly 升級模式。
ms.openlocfilehash: 759ad4f03de099637df0e92a7a8925a7c18ae3fd
ms.sourcegitcommit: 8f26bf0ff88f1f6881de32914be00d5f0cc7396a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2023
ms.locfileid: "69740798"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams 中外部 (同盟) 使用者的原生聊天體驗

當 Microsoft Teams 使用者與外部 (同盟) 使用者聊天時，聊天體驗僅限於文字。 不過，如果您的 Teams 使用者和另一個組織中的人員都處於 TeamsOnly 升級模式，您可以擁有「原生-Teams 聊天體驗」，其中包括豐富的格式設定、@mentions和其他聊天功能。

其他組織中人員的原生聊天體驗會針對所有 Teams 租使用者開啟，但並非所有人員都符合資格。 若要提供原生聊天體驗，必須針對 TeamsOnly 升級模式設定寄件者和接收器。 若要深入瞭解升級原則，請參閱 [設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)。

若要查看 Teams 中外部存取使用者的功能清單，請參閱 [比較外部和來賓存取權](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。

> [!NOTE]
> 原生聊天體驗不適用於跨 Microsoft 365 雲端環境：Microsoft 365 全球 (包括從/到 GCC High 的 GCC) 、從/到 DoD 的 GCC High，或從/到 DoD 的 WW。

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>如何?知道我是否在原生聊天中嗎？

如果您只能在聊天中與其他組織中的人員交換文字，那麼您是在標準的外部存取 (同盟) 聊天中。 如果您有其他聊天功能，包括格式設定、@mentions、表情圖示等，則表示您正在原生 Teams 聊天中。 

Teams 會定期檢查其他組織中的人員的升級模式，當 Teams 在 Teams[快速升級] 模式中找到執行 Teams 的人員時，系統會提示您切換到原生 Teams 聊天並鎖定原始聊天。

當您切換到原生 Teams 聊天時，Teams 不會合並這兩個交談。 相反地，您會在聊天摘要中看到這兩個聊天。 新的原生 Teams 聊天已啟用，但舊的僅限文字聊天已鎖定。



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>如果使用者不再處於 Teams [僅限] 模式，會發生什麼情況？

如果您與其他組織中的人員進行原生 Teams 聊天，然後其中一人切換退出 TeamsOnly 升級模式，Teams 會鎖定原生 Teams 聊天，並提供一個僅限文字聊天的連結給您。 您將無法繼續在原生 Teams 聊天中。 您仍然可以閱讀原生 Teams 聊天，但無法繼續交談。

如果 Teams 找到與此人進行舊的僅限文字聊天，就會恢復該聊天。 否則，Teams 會建立新的僅限文字聊天。


## <a name="related-topics"></a>相關主題

[在 Teams 中管理外部存取](manage-external-access.md)
