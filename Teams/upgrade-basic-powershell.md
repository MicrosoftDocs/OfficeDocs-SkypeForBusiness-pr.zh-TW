---
title: 基本升級 PowerShell|Microsoft Teams|授予升級交互操作策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解當系統管理中心尚未在租使用者中亮起時Microsoft Teams升級至帳戶的停止區。
ms.localizationpriority: medium
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
ms.openlocfilehash: 61201e52eabd9a921da432ac7081329a643664c7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628215"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>將使用者從線上商務用 Skype升級至Microsoft Teams

> [!Note]
> 本文所述的命令是設計用來做為升級基本檢查清單 [的一](./upgrade-start-here.md) 部分。

升級的技術移商務用 Skype需要通知您的使用者，商務用 Skype升級至 Teams，然後將他們Teams **模式**。 這些步驟可以透過遠端商務用 Skype或Windows PowerShell系統管理中心Microsoft Teams完成。

我們正在系統管理中心積極推出升級Microsoft Teams工具，而且應該[](manage-teams-skypeforbusiness-admin-center.md)很快就會在租使用者上推出。 一旦推出，您可以在設定共存和升級設定中尋找移移使用者 [的資訊](./setting-your-coexistence-and-upgrade-settings.md)。

如果您今天準備好升級，可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升級基本步驟# | 模式 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 通知商務用 Skype使用者<br> (如果使用者目前處於群島模式， (使用) )  | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(例如，$SipAddress='TestUser@contoso.com )* |
| [5](upgrade-basic.md#step-5) | 商務用 Skype僅 + 通知商務用 Skype使用者 <br> (如果使用者目前處於僅商務用 Skype **模式**，請使用)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams只 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |