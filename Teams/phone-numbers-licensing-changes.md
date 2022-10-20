---
title: 電話號碼和授權變更
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: 瞭解授權變更會如何影響電話號碼管理。
ms.openlocfilehash: e023c1606157a5beeafedfa358e470555ba7f653
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614316"
---
# <a name="how-licensing-affects-phone-number-management"></a>授權如何影響電話號碼管理

移除和指派授權給使用者的方式可能會影響使用者在 Microsoft Teams 中撥打和接聽公用交換電話網路 (PSTN) 通話的能力。 本文說明如何管理授權變更，以確保使用者撥打和接聽 PSTN 通話的能力不會受到影響。

如需有關管理電話號碼的一般資訊，請參閱 [管理組織的電話號碼](manage-phone-numbers-landing-page.md)。 如需 Teams 附加元件授權的一般資訊，請參閱 [Microsoft Teams 附加元件授權](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。



## <a name="remove-a-license"></a>移除授權

如果您的使用者有指派的電話號碼，而且您移除一或多個必要條件授權，則移除授權也會取消指派使用者的電話號碼。 如果沒有指派的電話號碼，使用者在 Microsoft Teams 中撥打和接聽 PSTN 通話的能力會受到影響。

視使用者的 [PSTN 連線選項](pstn-connectivity.md)而定，移除授權會對電話語音參數產生下列影響：

- **移除使用通話方案電話號碼的使用者的 Microsoft 365 通話方案授權** ，將會：
  - 將 OnPremLineUri 中的任何值複製到 LineUri
  - 將 EnterpriseVoiceEnabled 設為 False
  - 將電話號碼指派狀態設定為 [電話號碼] 資料庫中的 [未指派]


- 移除具有運算子 **Connect 電話號碼之使用者的 Microsoft 365 手機系統授權**，將會：
  - Clear LineUri
  - 將 EnterpriseVoiceEnabled 設為 False
  - 將電話號碼的指派狀態設定為 [電話號碼] 資料庫中的 [未指派]


- **移除使用直接路由電話號碼的使用者的 Microsoft 365 手機系統授權** 將會：
  - Clear LineUri
  - 將 EnterpriseVoiceEnabled 設為 False
  - 從電話號碼資料庫移除電話號碼


## <a name="change-a-license"></a>變更授權

如果您需要變更涉及其中一個必要條件授權之使用者的授權，您應確保同時進行及儲存授權變更。 這個方法可確保使用者保留其指派的電話號碼，而且可以在 Microsoft Teams 中繼續撥打和接聽 PSTN 通話。 

例如，假設您要將Microsoft 365 E5授權指派給目前擁有Microsoft 365 E3授權的使用者。 

- 如果您使用的是 Teams 系統管理中心，請在使用者詳細資料的 [ **授權與應用程式** ] 索引標籤中，確定舊授權已移除，且已新增新授權，然後再按一下 [ **儲存變更]**。 

- 如果您使用的是 PowerShell Cmdlet、 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) 或 [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense)，請執行一次 Cmdlet，並同時使用 -AddLicenses 和 -RemoveLicenses 參數。

 (如果您移除舊授權並儲存變更，然後新增新授權並儲存變更，電話號碼將會取消指派，使用者可能會失去在 Microsoft Teams 中撥打和接聽 PSTN 通話的能力。 指派新授權之後，您必須重新指派電話號碼給使用者。) 










