---
title: 為會議中的使用者設定會議撥出Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何設定Teams要求撥出確認，以防止語音信箱系統在被叫者無法接聽電話時連接到會議。
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9db8d3882ea7d05b1bc3600682c0c803040b4c10
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055653"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>為會議中的使用者設定會議撥出Microsoft Teams

會議撥出和撥打電話是邀請參與者加入會議，以及讓現有參與者使用傳統或行動電話加入會議的實用方式。 不過，當通話者無法接聽來電，且語音信箱系統接聽來電時，語音信箱系統會連接到會議。 參與者將能夠聆聽，直到會議移除。

若要防止語音信箱系統在撥出會議時連到會議，而電話撥入者無法接聽電話，您可以設定 Teams，要求被叫人確認他們加入會議。 如果來電者無法接聽來電，且語音信箱系統接聽來電，語音信箱系統將不會連接到會議，因為它不會提供加入會議的確認。

啟用這項功能後，收到撥出電話或撥打電話給我的人，必須按傳統電話或行動電話上的 1，或說「好的」，以確認他們想要加入會議。

若要為貴組織的所有會議啟用此功能，請設定 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 的參數為 ```true``` 。 若要設定此參數，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>相關主題

- [為您的使用者設定語音來電功能](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
