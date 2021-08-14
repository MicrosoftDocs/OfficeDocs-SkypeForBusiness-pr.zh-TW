---
title: 管理班管理的排程擁有者
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 瞭解如何管理輪班擁有者進行排程管理。 您可以設定一個策略，將團隊成員的許可權提升為排程擁有者。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9c0bc75e15439cf5fa7c3989bb0854521a1c45b8
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235746"
---
# <a name="schedule-owner-for-shift-management"></a>輪班管理的排程擁有者

## <a name="overview"></a>概觀

排程擁有者是一項功能，可讓您將團隊成員的許可權提升為排程擁有者，而不需要讓員工成為團隊擁有者。 這表示員工有權管理小組的排程，而不必修改任何其他小組屬性，例如更新、編輯或刪除小組頻道。

具有排程擁有者許可權的使用者可以做什麼？

- 建立、編輯及發佈排程，以管理小組的班分派。
- 查看及核准班要求，包括調班和輪班要求。
- 在 Shifts 中管理設定，為小組啟用特定功能。
- 查看及修改其小組的時程表，以處理員工薪資。

## <a name="why-schedule-owner"></a>為什麼排程擁有者？

如果沒有排程擁有者功能，日常商務功能可能會中斷。 當團隊擁有者協助執行團隊時，他們未必是負責日常排程的人。 在這種情況下，只將排程管理責任移轉到另一個小組成員，可簡化小組內的每日作業，並消除兩個擁有相同存取許可權的小組成員的混淆。

## <a name="scenario"></a>案例

以下是貴組織如何使用排程擁有者功能範例。

您工作在大型組織中，部門主管直接向市管理人員報告。 商店管理員在貴公司中擁有更多權力，且是 Shifts 中的團隊擁有者。 另一方面，部門主管則只會新增為小組成員至 Shifts。 雖然市售經理比部門經理的年長還要高，但部門主管處理小組員工日常排程的方式較為合理。

*若沒有排* 程擁有者，部門主管必須獲得與團隊擁有者完全相同的許可權。 最近，部門主管一直在移動資訊，並變更頻道名稱，這導致商店管理員的工作發生複雜問題。 商店管理員希望部門主管能夠組織其排程，但不希望他們變更小組中班次以外的任何專案。

*有了排程* 擁有者，部門主管就可以獲得排程許可權，而不需要任何其他團隊擁有者許可權。

## <a name="manage-schedule-ownership"></a>管理排程擁有權

做為系統管理員，您可以使用策略來控制組織中排程管理擁有權。 您可以使用下列 PowerShell Cmdlet 管理這些策略：

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>範例 1

在此，我們建立名為 ScheduleOwnerPolicy 的新策略，並開啟了排程擁有者功能。

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>範例 2

在此範例中，我們將名為 ScheduleOwnerPolicy 的策略指派給名為 remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>相關文章

- [在 Teams 中管理貴組織的 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
- [管理公司中前線員工以班為基礎的Teams](manage-shift-based-access-flw.md) 
