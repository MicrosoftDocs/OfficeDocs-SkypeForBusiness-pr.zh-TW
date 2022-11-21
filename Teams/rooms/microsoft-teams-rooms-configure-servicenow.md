---
title: 設定 ServiceNow for Teams 會議室
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 瞭解如何在 Teams 會議室專業版 管理入口網站中設定 ServiceNow
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: 2166332df2c4ea388256d32a9dbc35a709042041
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046852"
---
# <a name="configure-servicenow-for-teams-rooms"></a>設定 ServiceNow for Teams 會議室

本文將說明在Teams 會議室專業版管理入口網站中設定 ServiceNow 環境的必要條件和步驟。

## <a name="watch-microsoft-teams-rooms-pro-management--service-now-integration"></a>觀看：Microsoft Teams 會議室專業版管理 - 服務現在整合

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>Teams 會議室先決條件

- 您必須擁有指派的服務系統管理員角色。 如需詳細資訊，請參閱[使用Microsoft Teams 會議室專業版管理的角色型存取控制](rooms-pro-rbac.md)。

### <a name="servicenow-prerequisites"></a>ServiceNow 必要條件

- 基本授權登入或 [OAuth 登入](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) 。 如需詳細資訊，請參閱在 ServiceNow [中建立認證](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) 。
- ServiceNow 實例及其實例主機名稱和 API URI
- incident_manager或更新版本的角色
- 支援資料表 API 的 ServiceNow 軟體版本

## <a name="configure-your-environment"></a>設定您的環境

您的環境設定方式是高度可自訂的，而且會視貴組織的需求而定。 下列步驟將逐步說明如何將您在 ServiceNow 中的現有設定複製到Teams 會議室專業版管理入口網站。

1. 開啟您要複製的 ServiceNow 實例。 當您在Teams 會議室專業版管理入口網站中完成組態表單時，必須參照此資訊。
2. 在新的瀏覽器索引標籤中，移至 [[Teams 會議室專業版管理] 入口網站](https://portal.rooms.microsoft.com/)，然後移至 [**設定]**。 然後，在左側導覽功能表中選取 **[ServiceNow** ] 以開啟組態表單。
3. 選取驗證方法以登入並輸入您的 ServiceNow 實例主機和 API URI。
4. [欄位對應] 區段的 [ServiceNow 功能變數] 欄中的所有必要專案都應預先填入。 下表包含每個 ServiceNow 欄位及其對應的Microsoft Teams 會議室欄位。 完成 [欄位對應] 區段中每一列的動作。 如需每個 ServiceNow 欄位的定義，請參閱 [ServiceNow 欄位定義](#servicenow-field-definitions)。

| ServiceNow 功能變數 | Microsoft Teams 會議室欄位 | 動作 |
| --- | --- | --- |
| short_description | 事件描述 | 不需要採取任何動作。 Teams 會議室欄位會自動填滿。 |
| 描述 | 第一封郵件 | 不需要採取任何動作。 Teams 會議室欄位會自動填滿。 |
| assignment_group | [會議室] 群組 | 複製 ServiceNow 實例中的assignment_group值，並貼到組態表單中的 [ServiceNow 值] 欄位。 如果您有多個assignment_group，請針對每個額外的自訂值選取 [ **新增會議室群組** ]。 |
| 嚴重性 | 環 | 嚴重性是 ServiceNow 中的自訂值。 這是 ServiceNow 實例第二欄中的第四個專案。 複製值並貼到組態表單中的 ServiceNow 值欄位。 如果您有一個以上的嚴重性值，請針對每個額外的自訂值選取 [ **新增通道** ]。 |
| 批註 (選用)  | 自訂值* | 若要將批註欄位新增至組態表單，請選取欄位對應區段頂端的 [ **新增** ]。 複製 ServiceNow 實例中的批註值，並貼到組態表單中的 ServiceNow 欄位。 從下拉式功能表中指派 Microsoft Teams 會議室欄位，然後複製並貼上 ServiceNow 值。 |
| 已解決 ()  | 自訂值* | 從您的 ServiceNow 實例複製解析度狀態，並貼到組態表單中的 ServiceNow 值欄位。 |
| close_code | 自訂值* | 在 ServiceNow 實例的 [ **解析度資訊** ] 索引標籤中，複製關閉的程式碼，並將其貼到 [ServiceNow 值] 欄位的組態表單中。 |

*從下拉式功能表選取自訂值

>[!NOTE]
>如果您找不到自訂值，請連絡您的 ServiceNow 系統管理員。

若要新增其他必要欄位至 [解決事件] 區段，請選取 [ **新增]**。

## <a name="test-and-enable"></a>測試並啟用

完成組態表單後，選取頁面底部的 **[測試** ]。 您必須進行測試才能提交您的設定。

測試成功通過後，選取 [ **提交** ] 以儲存變更。 當您準備好為組織啟用 ServiceNow 後，將 [ **您要啟用 ServiceNow？** ] 切換為 [ **開啟]**。

## <a name="servicenow-field-definitions"></a>ServiceNow 欄位定義

- **short_description**：ServiceNow 中的簡短描述欄位是簡短的 160 個字元英數位元值，提供事件摘要。 簡短描述相當於Teams 會議室專業版管理入口網站中的事件描述。

- **描述**：ServiceNow 中的描述欄位是 ServiceNow 事件交談記錄中的第一個值。 描述相當於Teams 會議室專業版管理入口網站中的第一封郵件。

- **assignment_group**：ServiceNow 中的 [工作分派群組] 欄位是用來組織事件。 作業群組相當於Teams 會議室專業版管理入口網站中的 [會議室] 群組。 根據預設，有一個聊天室群組，而且可以新增更多聊天室群組。 您可以決定有多少個群組，以及如何將事件分組。 例如，您可以選擇依據位置來組織事件。

- **嚴重性**：ServiceNow 中的嚴重性欄位是用來依優先順序組織事件。 指定優先順序的值是可自訂的。 嚴重性相當於Teams 會議室專業版管理入口網站中的 [響鈴] 欄位。 若要自訂Teams 會議室專業版管理入口網站中的頻道，請移至左側導覽功能表中的 **更新**。 然後移至 [ **頻道] 索引卷** 標，然後選取 **[新增頻道]**。

- **批註**：[批註] 是 ServiceNow 中的選擇性欄位，用於在您的 Teams 會議室專業版 管理入口網站設定中包含來自 ServiceNow 實例的自訂必要欄位。 等同于批註是Teams 會議室專業版管理入口網站中的自訂值。

- **狀態 (解決了)**： ServiceNow 中的狀態 (解決了) 欄位，用來指定事件的解決方式，以及關閉事件的必要條件。 已解決) 值的狀態 (可自訂。 )  (解決狀態的對應值是Teams 會議室專業版管理入口網站中的自訂值。

- **close_code**：在事件完全解決之後，必須指派關閉代碼給事件。 這個值可在 ServiceNow 中自訂。 等同于關閉程式碼是Teams 會議室專業版管理入口網站中的自訂值。
