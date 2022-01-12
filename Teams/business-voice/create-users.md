---
title: 建立Microsoft 365使用者、新增Teams 電話通話方案授權，以及指派電話號碼
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00eb2842b063399f69563571180197de0238588e
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766186"
---
# <a name="create-and-license-teams-phone-with-calling-plan-users-and-assign-them-phone-numbers"></a>與通話方案Teams 電話建立和授權，並指派電話號碼給他們

若要使用 :::no-loc text="Microsoft 365 Teams Phone with Calling Plan":::，您需要具備 :::no-loc text="Microsoft 365 Teams Phone with Calling Plan"::: 授權的 :::no-loc text="Microsoft 365"::: 帳戶。 具備帳戶和授權後，您就可以為其指派電話號碼。

## <a name="create-and-license-users"></a>建立並授權使用者

按照以下 [個別新增或大量新增使用者](/microsoft-365/admin/add-users/add-users)，與 [指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)之步驟。

> [!NOTE]
> 在 **[指派產品授權]** 窗格中，選取 **:::no-loc text="Microsoft 365 Teams Phone with Calling Plan":::**。

## <a name="assign-phone-numbers-to-users"></a>將電話號碼指派給使用者

建立使用者並指派 :::no-loc text="Microsoft 365 Teams Phone with Calling Plan"::: 授權後，您就可以為其指派電話號碼。 針對需要撥打或接聽外部電話號碼的使用者，每位使用者皆需要一個未指派的電話號碼。 如果您未指派的電話號碼不夠，請參閱本文稍後的[取得更多電話號碼](#get-more-phone-numbers)。

1. 移至https://admin.teams.microsoft.com。
2. 輸入電話號碼要求的名稱和描述。
3. 選取 [**語音** > **電話號碼]**。
4. 選取您要指派給使用者的電話號碼，然後選取 **[編輯]**。
5. 在 **[編輯]** 面板的 **[指派至]** 中輸入要指派電話號碼的使用者名稱。 然後選取 **[指派]**。
6. 在 **[緊急位置]** 中，輸入使用者所在的位置，然後選取 **[套用]**

## <a name="get-more-phone-numbers"></a>取得更多電話號碼

如果您沒有足夠的電話號碼可以指派給新使用者，您可以取得更多。 可能需要最多 24 小時的時間才能讓號碼使用。

1. 移至https://admin.teams.microsoft.com。
2. 輸入電話號碼要求的名稱和描述。
3. 選取 **[語音]** > **[電話號碼]** > **[新增]**。
4. 選擇電話號碼的國家或地區。
5. 在 **[號碼類型]** 中，選取 **[使用者 (訂閱者)]**。
6. 在 **[位置]** 中，搜尋使用者的位置並選取。 您也可以選擇 **[新增位置]**。
7. 選擇區號、輸入需要的電話號碼數，然後選取 **[下一步]**。
8. 等待保留電話號碼，然後檢視取得的號碼。 如果均已確認，請選取 **[下單]**，然後選取 **[完成]**。
