---
title: 針對特定團隊使用者停用免付費電話號碼
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
- NOCSH
ms.custom:
- Audio Conferencing
description: 系統管理員可以控制召集人如何在會議中使用免付費電話號碼。
ms.openlocfilehash: e6a62473c2db2e2a36a0b0302831afe0b4877f8f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707268"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>針對特定團隊使用者停用免付費電話號碼

如果您的組織在其 Microsoft 音訊會議橋中有免付費電話號碼，您可以在特定召集人的會議中允許或避免使用。  

根據預設，貴組織中的所有使用者都可以使用免付費電話號碼，這表示這些號碼（如果有的話）可供參與者加入其會議。 如果這不是貴組織中的部分使用者所需的行為，您可以透過免付費號碼啟用控制，限制特定使用者在會議中使用這些號碼。 

針對指定的召集人停用免付費電話號碼時： 
 - 免付費電話號碼將不再包含在他或她的會議邀請中。 
 - 免付費電話號碼將不再列在他或她的會議邀請中所參照的 [尋找當地電話號碼] 頁面上。 
 - 如果您的召集人撥打任何免付費電話號碼，參與者將無法加入指定召集人的會議。 
 - 召集人的所有會議都會自動重新安排，且免付費電話號碼將會從他們中移除。  

    > [!IMPORTANT]
    > 這會將召集人的所有電子郵件邀請重新傳送給這些會議的所有參與者。 

 - 參與者可以使用電話號碼繼續加入召集人的會議。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>停用特定使用者的免付費電話號碼 

從**Microsoft [團隊管理中心**]：

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下 [**音訊會議**] 旁的 [**編輯**]。

3. [設定] 會將**此使用者的會議邀請中的免付費電話號碼**設為 [**關閉**]。 

4. 按一下 [**儲存]。** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**使用 PowerShell**  

如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
