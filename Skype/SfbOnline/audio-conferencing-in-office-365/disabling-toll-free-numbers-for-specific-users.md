---
title: 停用特定線上使用者的免付費商務用 Skype號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 系統管理員可以控制召集人如何為會議使用免付費號碼。
ms.openlocfilehash: aabc72f5e413b8f760981b8fac364afc836be5ce058d5999e2c19f96109141b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310272"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>停用特定線上使用者的免付費商務用 Skype號碼

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> 有關停用使用者免Teams號碼的資訊，請參閱停用特定使用者的免付費[Teams號碼](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)。

如果貴組織在其 Microsoft 音訊會議橋接器中擁有免付費號碼，您可以允許或禁止在特定的召集人會議中使用。  

根據預設，貴組織的所有使用者都可以使用免付費號碼，也就是說，參與者可以使用這些號碼來加入他們的會議 。如果可用的話， 如果貴組織中某些使用者不是想要的行為，您可以透過免付費號碼啟用控制項，限制特定使用者在會議中使用這些號碼。 

當為給定的召集人停用免付費號碼時： 
 - 免付費號碼將不再包含在其會議邀請中。 
 - 免付費號碼將不再列在其會議邀請中參照的「尋找當地號碼」頁面上。 
 - 如果參與者撥打組織的任何免付費號碼，他們將無法加入該召集人的會議。 
 - 召集人的所有會議都會自動重新排期，免付費號碼也會從它們中移除。  

    > [!IMPORTANT]
    > 這會將召集人的所有電子郵件邀請重新發回給這些會議的所有參與者。 

 - 參與者可以使用付費號碼繼續加入召集人的會議。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>停用特定使用者的免付費電話號碼 

從 Microsoft Teams **系統管理中心**：

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 在 [ **音訊會議」 旁**，按一下 [ **編輯>**。

3. 將 **此使用者的會議要求包含** 免付費號碼設定為 **關閉**。 

4. 按一下 **[儲存。** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**使用 PowerShell**  

您可以使用 Cmdlet 的 AllowTollFreeDialIn 參數Set-CsOnlineDialInConferencingUser啟用或停用此控制項。 例如： 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
