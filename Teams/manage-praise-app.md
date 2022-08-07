---
title: 在 Teams 系統管理中心管理稱讚應用程式
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: 瞭解如何在 Microsoft Teams 系統管理中心管理稱讚應用程式。
ms.collection:
- M365-collaboration
ms.openlocfilehash: 0f30a508fd1c0f2e82dcab3c22d3ade94d4e0118
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269418"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理稱讚應用程式

Microsoft Teams 中的 [稱讚] 應用程式可協助使用者對貴組織或教室的成員表示感謝。 [稱讚] 中的徽章旨在協助辨識 Teams 使用者在從教育人員到前線工作者等各種工作中所投入的工作。 若要深入瞭解，請參閱 [傳送稱讚給其他人](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)。

系統管理員必須具備 Teams 授權才能存取此功能。 如果您嘗試在沒有 Teams 授權的情況下存取此功能，您會收到錯誤訊息。

> [!NOTE]
> [稱讚] 應用程式適用于 GCC 雲端環境，但不適用於 GCC High 或 DoD。

## <a name="enable-or-disable-praise-in-your-organization"></a>啟用或停用貴組織中的稱讚

貴組織中的所有 Teams 使用者預設會啟用稱讚。 您可以在 Microsoft Teams 系統管理中心的[管理應用程式](manage-apps.md)頁面上關閉或開啟組織層級的應用程式。

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Teams 系統管理中心 [稱讚] 應用程式詳細資料頁面的螢幕擷取畫面，顯示 [狀態] 切換開關。":::

1. 在 Microsoft Teams 系統管理中心的左窗格中，移至 **Teams 應用程式**  >  **管理應用程式**。
2. 在應用程式清單中，搜尋 [稱讚] 應用程式，選取它，然後將 **[狀態** ] 切換為 [ **封鎖** ] 或 [ **允許]**。

請記住，這項設定會同時影響 Teams 中Viva Insights應用程式中的稱讚應用程式和稱讚功能。

如果您將 [狀態] 設為 [封鎖]，Teams 的 [稱讚] 應用程式會在幾分鐘內遭到封鎖。 不過，Viva Insights中的稱讚可能需要 7-9 天才能被封鎖。

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>啟用或停用貴組織中特定使用者的稱讚

若要允許或封鎖貴組織中的特定使用者使用「稱讚」，請確定已在 [ [管理應用程式](manage-apps.md) ] 頁面上為貴組織開啟 [稱讚]。 然後建立自訂應用程式許可權原則，並將它指派給這些使用者。 若要深入了解，請參閱[管理 Teams 中的應用程式權限原則](teams-app-permission-policies.md)。

## <a name="badges"></a>徽章

以下是 [稱讚] 中的預設徽章集合。 貴組織中的 Teams 使用者可以使用這些徽章來辨識同儕在工作上超越上手。

:::image type="content" source="media/default-set-praise.png" alt-text="預設徽章集中的徽章影像。":::

> [!NOTE]
> 自 2022 年 2 月開始，人員只能傳送和接收預設徽章。 自訂徽章已不再提供使用，且已從 Teams 系統管理中心移除自訂徽章的選項。

## <a name="related-articles"></a>相關文章

[在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
