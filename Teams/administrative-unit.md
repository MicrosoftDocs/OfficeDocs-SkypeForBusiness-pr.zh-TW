---
title: 使用系統管理單位管理裝置
author: mahoffman
ms.author: v-mahoffman
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a4130cbd9493a37d84f0b15160adcaeb03c9edd
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056174"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>使用系統管理Teams管理中心管理裝置

系統管理中心的系統Teams提供詳細的角色式存取權，以管理Teams裝置。 系統管理Teams授予系統管理員特定資源的存取權，但限制該系統管理員對其他資源的存取權。 如果您在不同的國家/地區Teams當地系統管理員，這項功能就特別實用。

例如，Contoso 在全球都有作業。 艾莉是位於倫敦的全域 IT 系統管理員，而 Prashant 是位於印度班加羅爾的當地 IT 系統管理員。 現在，當 Prashant 以Teams管理員的登錄至系統管理中心時，Teams看到全球的裝置。 艾莉華想要限制 Prashant 只Teams班加羅爾的裝置存取權。 系統管理單位允許她這麼做。 若要深入瞭解，請參閱管理[單元中的 Azure Active Directory。](/azure/active-directory/roles/administrative-units)

> [!NOTE]
> 系統管理單位目前僅適用于Teams系統管理員角色Teams系統管理中心。

## <a name="add-administrative-units"></a>新增系統管理單位

您必須是全域系統管理員才能新增系統管理單位。 若要瞭解如何進行，請參閱 [新增系統管理單元](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit)。

## <a name="assign-admins-to-administrative-units"></a>指派系統管理員給系統管理單位

您也需要全域系統管理員才能指派系統管理單位。 您可以使用 Azure 入口網站、PowerShell 或 Microsoft Graph API 指派系統管理單位。 若要深入瞭解，請參閱指派[Azure AD管理單元範圍的角色](/azure/active-directory/roles/admin-units-assign-roles)。

## <a name="select-administrative-units"></a>選取系統管理單位

如果您是一名Teams系統管理員，在全域系統管理員將您指派給系統管理單位之後，您可以Teams系統管理中心來管理裝置。 如果您只指派給一個系統管理單位，則只會看到指派給該系統管理單位的裝置。 如果您被指派給多個系統管理單位，您可以在這些系統管理單位之間切換，而不必從系統管理中心Teams退出。 

1. 請Teams[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 在 [ **您的系統管理單位** ） 對話方塊中，遵循下列其中一個步驟：
    - 選取您想要管理的系統管理單位，或 
    - 如果您有 **許可權** 管理貴組織的所有裝置，請選取所有裝置。

3. 選取 [儲存 **]**。

## <a name="switch-administrative-units"></a>切換系統管理單位

如果您是裝置系統管理員Teams，如果您已登錄系統管理中心，可以在系統管理Teams切換。 若要切換到不同的系統管理單元：

1. 請Teams[系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 在左側流覽中，選取 **Teams裝置**。

3. 在右側窗格的左上角，選取顯示的系統管理單位。

4. 在 [ **您的系統管理單位** ） 對話方塊中，遵循下列其中一個步驟：
    - 選取您想要管理的系統管理單位，或 
    - 如果您有 **許可權** 管理貴組織的所有裝置，請選取所有裝置。

5. 選取 [儲存 **]**。
