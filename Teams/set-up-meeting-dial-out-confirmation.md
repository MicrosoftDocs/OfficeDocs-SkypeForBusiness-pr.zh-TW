---
title: 在 Microsoft Teams 中設定使用者的會議撥出確認
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何設定 Teams 要求撥出確認，以防止語音信箱系統在來電者無法接聽電話時連線至會議。
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271558"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>在 Microsoft Teams 中設定使用者的會議撥出確認

會議撥出和撥號給我是邀請參與者加入會議以及讓現有參與者使用傳統或行動電話加入會議的實用方式。 不過，當來電者無法接聽電話，且語音信箱系統接聽來電時，語音信箱系統就會連線到會議。 參與者將能夠聆聽，直到會議移除為止。

若要防止語音信箱系統在會議撥出傳送至電話號碼，且來電者無法接聽電話時連線至會議，您可以設定 Teams 向來電者要求確認，讓他們加入會議。 如果來電者無法接聽電話，而且語音信箱系統已接聽電話，則語音信箱系統將無法連線至會議，因為語音信箱系統不會提供加入會議的確認。

啟用這項功能時，收到撥出電話或 [撥號給我] 的人員必須透過傳統電話或行動電話按 1 鍵或說「確定」來確認是否要加入會議。 確認會防止使用者的語音信箱訊息加入會議。

若要為組織中的所有會議啟用這項功能，請將[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 的參數設 ```EnableDialOutJoinConfirmation``` 為 ```true``` 。 若要設定此參數，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相關主題

- [為您的使用者設定語音來電功能](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
