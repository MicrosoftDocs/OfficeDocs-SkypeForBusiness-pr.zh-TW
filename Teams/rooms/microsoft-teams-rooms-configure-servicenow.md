---
title: 設定 ServiceNow Teams 會議室
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 瞭解如何在入口網站中Teams 會議室 進階版 ServiceNow
f1keywords: ''
ms.openlocfilehash: deca4f8111dec958b19d9a6fa2651fca34f4050f
ms.sourcegitcommit: 9caa3131e9896b140afe10edea2b1e599eacd02b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2022
ms.locfileid: "62082209"
---
# <a name="configure-servicenow-for-teams-rooms"></a>設定 ServiceNow Teams 會議室

本文將說明在入口網站中設定 ServiceNow 環境的先決條件Teams 會議室 進階版步驟。

## <a name="before-you-begin"></a>開始之前

### <a name="teams-rooms-prerequisites"></a>Teams 會議室先決條件

- 您必須有指派的服務系統管理員角色。 有關詳細資訊，請參閱[使用受](microsoft-teams-rooms-premium-rbac.md)管理服務Microsoft Teams 會議室存取控制。

### <a name="servicenow-prerequisites"></a>ServiceNow 先決條件

- 基本授權登錄或 [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) 登錄。 詳細資訊 [請參閱在](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) ServiceNow 中建立認證。
- ServiceNow 實例及其實例主機名稱稱和 API URI
- 使用者或incident_manager角色
- 支援資料表 API 的軟體版本 ServiceNow

## <a name="configure-your-environment"></a>設定您的環境

您的環境配置方式高度可自訂，並視貴組織的需求而決定。 下列步驟將瞭解如何在 ServiceNow 中將現有的組Teams 會議室 進階版入口網站。

1. 開啟您想要複製的 ServiceNow 實例。 當您在入口網站中完成組Teams 會議室 進階版參照。
2. 在新的瀏覽器選項卡中，前往 Teams 會議室 進階版 [入口網站](https://portal.rooms.microsoft.com/)，**然後前往** 設定。 接著，選取左側流覽功能表中的 **ServiceNow** 以開啟組式表單。
3. 選取要登錄的驗證方法，然後輸入您的 ServiceNow 實例主機和 API URI。
4. 欄位映射區段的 ServiceNow 欄位欄中的所有所需專案都應該預先填入。 下表包含每個 ServiceNow 欄位及其對應的Microsoft Teams 會議室欄位。 完成欄位地圖區段每一列的動作。 有關每個 ServiceNow 欄位的定義，請參閱 [ServiceNow 欄位定義](#servicenow-field-definitions)。

| ServiceNow 欄位 | Microsoft Teams 會議室欄位 | 動作 |
| --- | --- | --- |
| short_description | 事件描述 | 不需要任何動作。 自動Teams 會議室欄位。 |
| 描述 | 第一封郵件 | 不需要任何動作。 自動Teams 會議室欄位。 |
| assignment_group | 會議室群組 | 複製assignment_group實例中的值，並貼到組式表單中的 ServiceNow 值欄位。 如果您擁有多個自訂assignment_group， **請針對每個** 額外的自訂值選取新增會議室群組。 |
| 嚴重性 | 環 | 嚴重性是 ServiceNow 中的自訂值。 這是 ServiceNow 實例第二欄中的第四個專案。 複製值並貼到組式表單中的 ServiceNow 值欄位。 如果您的嚴重性值超過一個， **請針對每個** 額外的自訂值選取 [新增響鈴>。 |
| 批註 (選)  | 自訂值* | 若要新增批註欄位至組塊表單， **請選取欄位** 映射區段頂端的新增。 複製 ServiceNow 實例中的批註值，並貼到組式表單中的 ServiceNow 欄位。 從下拉式功能表Microsoft Teams會議室欄位，然後複製並貼上 ServiceNow 值。 |
| 已 (狀態)  | 自訂值* | 從 ServiceNow 實例複製解析狀態，然後將其貼到組態表單中的 ServiceNow 值欄位。 |
| close_code | 自訂值* | 在 **ServiceNow** 實例的解析度資訊選項卡中，複製關閉程式碼，然後將它貼到 ServiceNow 值欄位至組組表單。 |

*從下拉式功能表選取自訂值

>[!NOTE]
>如果您找不到自訂值，請連連您的 ServiceNow 系統管理員。

若要在解決事件區段新增其他必要的欄位， **請選取** 新增 。

## <a name="test-and-enable"></a>測試和啟用

完成組式表單之後 **，選取頁面** 底部的測試。 需要測試才能提交您的組配置。

成功通過測試後， **請選取提交** 以儲存您的變更。 準備好為貴組織啟用 ServiceNow 後，請切換至開啟 。 

## <a name="servicenow-field-definitions"></a>ServiceNow 欄位定義

- **** short_description：ServiceNow 中的簡短描述欄位是一個簡短、160 個字元的英數位元值，可提供事件摘要。 簡短描述相當於入口網站中的事件Teams 會議室 進階版描述。

- **描述**：ServiceNow 中的描述欄位是 ServiceNow 事件交談記錄的第一個值。 描述相當於入口網站中的第一Teams 會議室 進階版訊息。

- **** assignment_group：ServiceNow 中的作業群組欄位是用來組織事件。 作業群組相當於入口網站中的會議室Teams 會議室 進階版群組。 根據預設，有一個會議室群組，而且可以新增更多。 您可以決定有多少群組，以及如何將事件分組。 例如，您可以選擇根據位置來組織事件。

- **嚴重性**：ServiceNow 中的嚴重性欄位會用來根據優先順序來組織事件。 指定優先順序的值可自訂。 嚴重性相當於入口網站中的 [響鈴Teams 會議室 進階版欄位。 若要自訂入口網站中的Teams 會議室 進階版，**請前往左側** 流覽功能表中的更新。 接著，請前往的 **響鈴標籤** ，然後選取 **新增響鈴**。

- **批註**：批註是 ServiceNow 中的一個選擇性欄位，用來在入口網站組Teams 會議室 進階版包含 ServiceNow 實例的自訂Teams 會議室 進階版欄位。 批註的等同值是入口網站中的Teams 會議室 進階版值。

- **狀態 (** 解決) ：ServiceNow (已解決) 欄位的狀態會用來指定事件的解決方式，並需要該狀態才能關閉事件。 已解析 (的狀態) 可自訂。 已解析 (的狀態) 是網站入口網站中的自訂Teams 會議室 進階版值。

- **close_code：** 完全解決事件後，必須指派關閉代碼給事件。 此值在 ServiceNow 中可自訂。 相當於關閉程式碼的是入口網站中的Teams 會議室 進階版值。
