---
title: 使用系統管理單元Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在系統管理單元Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 556f220c9ca250f014ae604c96cabf9ef0b0ca0f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636789"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>裝置管理中的系統管理單元功能Teams

使用系統管理中心，以更精細的角色為基礎存取裝置管理Microsoft Teams存取。 我們已透過系統管理中心，為裝置管理Teams概念。

使用系統管理單元概念，您將確保專屬系統管理員能夠存取一組特定資源。 系統管理單位會限制所有資源的存取權。 您可以為裝置管理擴展相同的Teams功能。

> [!NOTE]
> 系統管理單元概念目前僅適用于Teams系統管理員角色。

例如，Contoso 在不同地理位置都有作業。 艾莉華是倫敦的全域 IT 系統管理員，而 Prashant 是印度 IT 系統管理員。 現在，當 Prashant 以Teams管理員角色進入系統管理中心時，他們會看到全球的裝置。 艾莉想要將 Prashant 的存取許可權制于那些目前存在於印度中的裝置。 系統管理單位概念可協助解決此問題。 深入瞭解 [系統管理單元概念](/azure/active-directory/roles/administrative-units)。

![顯示案例的圖表](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>建立系統管理單位

在 Azure 入口網站中建立系統管理單位，並指派各個系統管理單位的系統管理員。 深入瞭解在管理系統管理單位 [指派系統管理單位](/azure/active-directory/roles/admin-units-manage)。

![範例公司管理單位](media/au-example.png)

建立之後，全域 IT 系統管理員就可以新增對應到該系統管理單位的裝置使用者。

![具有使用者預覽的範例公司](media/au-example2.png)

角色的指派可以透過 PowerShell 使用 [Add-AzureADMSScopedRoleMembership](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0) Cmdlet 完成。

將角色指派給系統管理單位的使用者之後，使用者必須Teams系統管理中心，才能開始管理有範圍之裝置。

## <a name="experience-for-administrative-unit-admin"></a>系統管理單元系統管理員的體驗

如果相同的系統管理員被指派負責多個系統管理單位，他們可以在系統管理單位之間切換，而不必從入口網站退出。 在變更的系統管理單位視圖中，他們只會看到與新的系統管理單位相關聯的一組裝置。
