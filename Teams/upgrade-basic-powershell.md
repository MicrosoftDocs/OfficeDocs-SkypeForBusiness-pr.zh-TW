---
title: 基本升級 PowerShell |Microsoft 團隊 |授與升級交互操作原則
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 如果系統管理中心未在您的租使用者中亮起，請進一步瞭解升級至 Microsoft 團隊的 stopgap。
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
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809093"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>將您的使用者從商務用 Skype Online 升級至 Microsoft 團隊

> [!Note]
> 本文所述的命令是專門用來做為 [升級基本](https://aka.ms/UpgradeBasic) 檢查清單的一部分。

您升級的技術遷移層面會通知您的使用者商務用 Skype 將升級至小組，然後將他們移至 [ **僅限團隊** ] 模式。 您可以透過商務用 Skype 遠端 Windows PowerShell 會話或透過 Microsoft 團隊系統管理中心來完成這些步驟。

我們正積極推出 [Microsoft 團隊系統管理中心](manage-teams-skypeforbusiness-admin-center.md)的升級工具，而且您的租使用者應該會在您的租使用者提供此功能。 只要提供，您就可以在 [設定您的共存和升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)中找到遷移使用者的相關資訊。

如果您已準備好要立即升級，您可以使用下表所列的 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升級基本步驟# | 下 | PowerShell 命令 |
|---|---|---|
| [500](upgrade-basic.md#step-5) | Islands + 通知商務用 Skype 使用者<br>如果使用者目前處於 **孤島** 模式 (預設) # A3， (使用此命令 | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(例如，$SipAddress = ' TestUser@contoso.com」 )* |
| [500](upgrade-basic.md#step-5) | 僅限商務用 skype + 通知商務用 Skype 使用者 <br>如果使用者目前處於 [ **僅商務用 Skype** ] 模式中， (使用此命令)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [utf-7](upgrade-basic.md#step-7) | 僅限團隊 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
