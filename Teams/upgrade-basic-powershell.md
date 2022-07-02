---
title: 基本升級 PowerShell|Microsoft Teams|授與升級 Interop 原則
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如果您的租使用者尚未亮起管理員中心，升級至 Microsoft Teams 的停止增益集。
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
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606032"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>將您的使用者從 商務用 Skype Online 升級至 Microsoft Teams

> [!Note]
> 本文所述的命令是設計來做為 [升級基本](./upgrade-start-here.md) 檢查清單的一部分。

升級的技術移轉層麵包括通知您的使用者商務用 Skype將升級至 Teams，然後將它們移至 **僅限 Teams** 模式。 這些步驟可透過商務用 Skype遠端Windows PowerShell會話或透過 Microsoft Teams 系統管理中心來完成。

我們正在 [Microsoft Teams 系統管理中心](manage-teams-skypeforbusiness-admin-center.md)積極推出升級工具，應該很快就會在您的租使用者上提供。 一旦可用，您就可以在 [ [設定共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md)] 中找到移轉使用者的相關資訊。

如果您現在已準備好升級，可以使用下表中列出的 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 命令。

| 升級基本步驟# | 模式 | PowerShell 命令 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 通知商務用 Skype使用者<br> (如果使用者目前處於 **群島** 模式 (預設值 ，請使用此命令) )  | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*例如 (，$SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | 僅商務用 Skype + 通知商務用 Skype使用者 <br> (如果使用者目前 **僅處於商務用 Skype模式，** 請使用此命令)  | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | 僅限 Teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |