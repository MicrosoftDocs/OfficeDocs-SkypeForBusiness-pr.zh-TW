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
ms.openlocfilehash: bd4c3cab1795ffcffe1cfd3ed1229f19e3ec80a243497ab13790e009878f9f35
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300749"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>將使用者從線上商務用 Skype升級至Microsoft Teams

> [!Note]
> 本文所述的命令是設計用來做為升級基本檢查清單 [的一](./upgrade-start-here.md) 部分。

升級的技術移移層面需要通知您的使用者，商務用 Skype升級至 Teams，然後將他們移動到 Teams **模式**。 這些步驟可以透過遠端商務用 Skype或Windows PowerShell系統管理中心Microsoft Teams完成。

我們正在系統管理中心積極推出升級Microsoft Teams工具，而且應該[](manage-teams-skypeforbusiness-admin-center.md)很快就會在租使用者上推出。 一旦提供，您可以在設定共存和升級設定中尋找移移使用者 [的資訊](./setting-your-coexistence-and-upgrade-settings.md)。

如果您準備好今天升級，您可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升級基本步驟# | 模式 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 通知商務用 Skype使用者<br> (如果使用者目前處於群島模式， (使用此命令) )  | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(例如，$SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | 商務用 Skype僅 + 通知商務用 Skype使用者 <br> (如果使用者目前處於僅商務用 Skype模式，請使用)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams只 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |