---
title: 為會議中的使用者設定會議撥出Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何設定Teams要求撥出確認，以防止語音信箱系統在被叫者無法接聽電話時，連接到會議。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f72641742101a84c572335f2416599fccb6c809bdece75eb75c4db6ff95067c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299073"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>為使用者設定會議撥出確認Microsoft Teams

會議撥出和撥打電話給我是邀請參與者加入會議以及現有參與者使用傳統或行動電話加入會議非常有用的方式。 不過，當通話者無法接聽來電，且語音信箱系統接聽來電時，語音信箱系統會連接到會議，參與者將能夠聆聽，直到會議移除。

若要防止語音信箱系統在撥出會議時連到會議，而電話撥入者無法接聽電話，您可以設定 Teams，要求被叫人確認他們加入會議。 如果來電者無法接聽來電，且語音信箱系統接聽來電，語音信箱系統將不會連接到會議，因為它不會提供加入會議的確認。

啟用此功能時，收到撥出或撥打給我電話的人必須在傳統或行動電話上按 1 來確認他們想要加入會議。

若要為貴組織的所有會議啟用此功能，請設定 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 的參數為 ```true``` 。 若要這麼做，請執行下列命令：

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相關主題

- [為您的使用者設定語音來電功能](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)