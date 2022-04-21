---
title: 針對特定Teams使用者停用免付費電話號碼
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解如何控制召集人如何在音訊會議橋接器會議中使用免付費電話號碼。
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016625"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>針對特定Teams使用者停用免付費電話號碼

如果貴組織在其 Microsoft 音訊會議橋接器中有免付費電話號碼，您可以允許或防止其在特定召集人的會議中使用。  

根據預設，貴組織中的所有使用者都可使用免付費電話號碼，這表示如果可以，參與者可以使用這些號碼加入其會議。 如果這不是貴組織中某些使用者想要的行為，您可以透過免付費號碼啟用控制，限制特定使用者在會議中使用這些號碼。

為指定召集人停用免付費電話號碼時：

- 他的會議邀請中將不再包含免付費電話號碼。
- 免付費電話號碼將不再列在會議邀請中所參照的 [尋找當地號碼] 頁面上。
- 如果參與者撥打組織的任何免付費電話號碼，就無法加入指定召集人的會議。
- 參與者可以使用付費電話號碼繼續加入召集人的會議。

## <a name="disabling-toll-free-numbers-for-specific-users"></a>停用特定使用者的免付費電話號碼

您可以在指派給這些使用者的 *TeamsAudioConferencingPolicy* 中，將 *AllowTollFreeDialIn* 的設定變更為 **[關閉**]，以停用特定使用者的免付費電話號碼。 關閉由這類使用者建立的任何新會議後，將不會包含任何免付費電話號碼。 [付費和免付費電話號碼的音訊會議原則設定](audio-conferencing-toll-free-numbers-policy.md) 有更多資訊。

> [!IMPORTANT]
> 舊的和先前排定的週期性會議可能仍會顯示免付費電話號碼，而參與者將無法使用免付費電話號碼加入這類會議。 您可以重新排程這些使用者的所有舊和週期性會議，並使用多媒體簡訊從中移除免付費電話號碼。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
