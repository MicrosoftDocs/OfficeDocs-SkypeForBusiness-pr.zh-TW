---
title: 在 Teams 系統管理中心管理稱讚應用程式
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: 瞭解如何在 Microsoft Teams 系統管理中心管理稱讚應用程式。
ms.openlocfilehash: ff9985025146136ae78d8e822dd5b61903443605
ms.sourcegitcommit: 73df40ce6fbd1d305fd381140f293a2feb0d27bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2022
ms.locfileid: "65359773"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理稱讚應用程式

Microsoft Teams中的 稱讚 應用程式可協助使用者表達對貴組織或教室成員的感謝。 稱讚中的徽章是專為協助辨識Teams使用者從教育人員到第一線工作人員所投入之各種工作所投入的工作所設計。 若要深入瞭解，請參閱[傳送稱讚給其他人](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)。

系統管理員必須擁有Teams授權才能存取此功能。 如果您嘗試在沒有Teams授權的情況下存取此功能，您會收到錯誤訊息。

> [!NOTE]
> 稱讚應用程式適用于GCC雲端環境，但不適用於 GCC High 或 DoD。

## <a name="enable-or-disable-praise-in-your-organization"></a>啟用或停用組織中的稱讚

稱讚預設會為貴組織中的所有Teams使用者啟用。 您可以在 Microsoft Teams 系統管理中心的[管理應用程式](manage-apps.md)頁面上關閉或開啟組織層級的應用程式。

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Teams系統管理中心中稱讚應用程式詳細資料頁面的螢幕擷取畫面，顯示 [狀態] 切換開關。":::

1. 在Microsoft Teams系統管理中心的左窗格中，移至 **Teams應用程式**  >  **管理應用程式。**
2. 在應用程式清單中，搜尋稱讚應用程式，選取它，然後將 **[狀態**] 切換為 [**已封鎖**] 或 [**允許]**。

請記住，此設定會同時影響 稱讚 應用程式以及 Teams 中 Viva Insights 應用程式中的稱讚功能。

如果您將 [狀態] 設為 [封鎖]，稱讚應用程式會在幾分鐘內針對Teams封鎖。 不過，Viva Insights中的稱讚可能需要 7-9 天才能被封鎖。

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>為貴組織中的特定使用者啟用或停用稱讚

若要允許或封鎖貴組織中的特定使用者使用稱讚，請確定貴組織已在 [[管理應用程式](manage-apps.md)] 頁面上開啟稱讚。 然後建立自訂應用程式許可權原則，並將它指派給這些使用者。 若要深入了解，請參閱[管理 Teams 中的應用程式權限原則](teams-app-permission-policies.md)。

## <a name="badges"></a>徽章

以下是 稱讚 中的預設徽章集合。 Teams組織中的使用者可以使用這些徽章來辨識同儕在工作上超越上手。

:::image type="content" source="media/default-set-praise.png" alt-text="預設徽章集中的徽章影像。":::

> [!NOTE]
> 自 2022 年 2 月開始，人員只能傳送和接收預設徽章。 自訂徽章已無法使用，自訂徽章的選項也已從Teams系統管理中心移除。

## <a name="related-articles"></a>相關文章

[在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
