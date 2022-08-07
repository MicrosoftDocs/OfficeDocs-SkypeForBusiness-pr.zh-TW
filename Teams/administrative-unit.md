---
title: 使用系統管理單位管理裝置
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 Microsoft Teams 中的系統管理單位
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ccc079617a1ae58b3881da8ae48c8a993d5863
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269468"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>使用系統管理單位在 Teams 系統管理中心管理裝置

Teams 系統管理中心的系統管理單位提供管理 Teams 裝置的詳細角色型存取權。 系統管理單位會授與 Teams 系統管理員特定資源的存取權，但限制該管理員對其他資源的存取權。 如果您在不同國家或地區有本機 Teams 系統管理員，這個功能就特別實用。

例如，Contoso 在世界各地都有作業。 王恩是位於倫敦全域的 IT 系統管理員，而 Prashant 是位於印度班加羅爾的本機 IT 系統管理員。 今天，當 Prashant 以裝置系統管理員身分登入 Teams 系統管理中心時，他可以看到世界各地的 Teams 裝置。 劉德標想要限制 Prashant 只能在班加羅爾存取 Teams 裝置。 系統管理單位可讓她執行此動作。 若要深入瞭解，請參閱 [Azure Active Directory 中的系統管理單位](/azure/active-directory/roles/administrative-units)。

> [!NOTE]
> Teams 系統管理中心目前僅提供 Teams 裝置系統管理員角色的系統管理單位。

## <a name="add-administrative-units"></a>新增系統管理單位

您必須是全域系統管理員，才能新增系統管理單位。 若要瞭解做法，請參閱 [新增系統管理單位](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit)。

## <a name="assign-admins-to-administrative-units"></a>將系統管理員指派給系統管理單位

您也必須是全域系統管理員，才能指派系統管理單位。 您可以使用 Azure 入口網站、PowerShell 或 Microsoft 圖形 API 指派系統管理單位。 若要深入瞭解，請參閱 [使用系統管理單位範圍指派 Azure AD 角色](/azure/active-directory/roles/admin-units-assign-roles)。

## <a name="select-administrative-units"></a>選取系統管理單位

如果您是 Teams 裝置系統管理員，當全域系統管理員指派您給系統管理單位之後，您就可以登入 Teams 系統管理中心來管理裝置。 如果您只指派給一個系統管理單位，您只會看到指派給該系統管理單位的裝置。 如果您被指派多個系統管理單位，您可以在這些系統管理單位之間切換，而不需從 Teams 系統管理中心登出。 

1. 登入 [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 在 [ **您的系統管理單位** ] 對話方塊中，依照下列其中一個步驟進行：
    - 選取您要管理的系統管理單位，或 
    - 如果您有權管理貴組織的所有裝置，請選取 [ **所有裝置** ]。

3. 選取 [儲存 **]**。

## <a name="switch-administrative-units"></a>切換系統管理單位

如果您是 Teams 裝置系統管理員，如果您登入 Teams 系統管理中心，就可以在系統管理單位之間切換。 若要切換到其他系統管理單位：

1. 登入 [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 在左側導覽畫面中，選 **取 [Teams 裝置]**。

3. 在右窗格的左上角，選取顯示的系統管理單位。

4. 在 [ **您的系統管理單位** ] 對話方塊中，依照下列其中一個步驟進行：
    - 選取您要管理的系統管理單位，或 
    - 如果您有權管理貴組織的所有裝置，請選取 [ **所有裝置** ]。

5. 選取 [儲存 **]**。

## <a name="related-topics"></a>相關主題

- [將使用者或群組新增至系統管理單位](/azure/active-directory/roles/admin-units-members-add)
