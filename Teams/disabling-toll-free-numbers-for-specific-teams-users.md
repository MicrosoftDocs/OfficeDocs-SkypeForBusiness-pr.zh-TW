---
title: 停用特定使用者的免付費Teams號碼
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解如何控制召集人如何針對音訊會議橋接器會議使用免付費號碼。
ms.openlocfilehash: fe9542ba13595d393e31ad86dcdbe7bc8e6f40afd127975d465d76d57ec9352b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319986"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>停用特定使用者的免付費Teams號碼

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

3. 將 **此使用者的會議要求包含** 免付費號碼設為 **關閉**。 

4. 按一下 **[儲存。** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**使用 PowerShell**  

請參閱[powerShell Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)參考資料以瞭解更多資訊。