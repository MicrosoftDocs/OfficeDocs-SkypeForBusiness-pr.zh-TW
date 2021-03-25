---
title: 基本升級 PowerShell|Microsoft Teams|授予升級交互操作策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解當系統管理中心尚未在租使用者中亮起時，升級至 Microsoft Teams 的停止區。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120536"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>將使用者從商務用 Skype Online 升級至 Microsoft Teams

> [!Note]
> 本文所述的命令是設計用來做為升級基本檢查清單 [的一](./upgrade-start-here.md) 部分。

升級的技術移移層面需要通知您的使用者商務用 Skype 將會升級至 Teams，然後將他們移至 **Teams 模式** 。 這些步驟可以透過商務用 Skype 遠端 Windows PowerShell 會話或透過 Microsoft Teams 系統管理中心完成。

我們正在 Microsoft [Teams](manage-teams-skypeforbusiness-admin-center.md)系統管理中心積極推出升級工具，而且應該很快就會在租使用者上推出。 一旦推出，您可以在設定共存和升級設定中尋找移移使用者 [的資訊](./setting-your-coexistence-and-upgrade-settings.md)。

如果您今天準備好升級，可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升級基本步驟# | 模式 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 通知商務用 Skype 使用者<br> (如果使用者目前處於群島模式， (使用此命令) )  | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(例如，$SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | 僅適用于商務用 Skype + 通知商務用 Skype 使用者 <br> (如果使用者目前處於商務用 **Skype** 模式，請使用此命令)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | 僅 Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |