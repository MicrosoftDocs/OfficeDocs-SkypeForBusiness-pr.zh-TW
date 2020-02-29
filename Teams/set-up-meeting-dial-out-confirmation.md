---
title: 在 Microsoft 團隊中設定會議撥出-確認使用者
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何設定團隊要求撥出確認，以防止語音信箱系統在來電者無法接聽通話時連線至會議。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339469"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>為您的 Microsoft 團隊中的使用者設定會議撥出確認

[會議撥出] 和 [呼叫我來電] 是非常實用的方法，可邀請參與者加入會議，而針對現有參與者加入使用傳統或行動電話的會議。 不過，當來電的人員無法接聽來電，且通話是由語音信箱系統所接聽時，語音信箱系統會連線至會議，而參與者將能夠聆聽該會議，直到它從會議中移除為止。

若要防止語音信箱系統在會議撥出時傳送給會議，而呼叫的人員無法接聽通話，您可以將團隊設定為向呼叫者要求給他們的確認加入會議。 如果呼叫的人員無法接聽來電，且通話是由語音信箱系統所接聽，則語音信箱系統不會連線至會議，因為它不會提供加入會議的確認。

當啟用此功能時，接收撥出或撥打電話給我通話的人，必須在其傳統或行動電話上按1，以確認要加入會議。

若要針對貴組織中的所有會議啟用這項功能```EnableDialOutJoinConfirmation``` ，請將[CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 的參數設定```true```為。 若要這樣做，請執行下列命令：

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相關主題

- [為您的使用者設定語音來電功能](set-up-the-call-me-feature-for-your-users.md)
- [團隊 PowerShell 概覽](teams-powershell-overview.md)