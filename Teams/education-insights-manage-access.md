---
title: 管理 Education Insights 的使用者存取權
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 管理 Microsoft Teams 中 Education Insights 的使用者存取權。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145931"
---
# <a name="manage-user-access-to-education-insights"></a>管理 Education Insights 的使用者存取權

本文件提供管理[Microsoft Teams 中的 Education Insights](class-insights.md) 使用者存取權的必要步驟。

您必須為教育領導者、校區領導者、學校校長、首席教師、顧問、學習領域主任、計畫主任、社交工作者和心理學家提供權限。 當授課者擁有班級團隊時，系統就會 *自動* 提供其權限。

若要提供組織層級 Insights，您必須[從學生資訊系統 (SIS) 匯入資訊](education-insights-sis-data-sync.md)，讓 Insights 會有正確對應的教育系統階層結構。

> [!NOTE]
> 只有全域系統管理員才能管理 Insights 的使用者存取權。

> [!TIP]
> 我們建議您為您的所有教育領導者啟用 Insights，讓他們有資料可以了解每所學校，並且可以快速識別問題並且為教育人員提供支援。 即使您正在執行試驗，為所有教育領導者保持 Insights 啟用仍然有幫助，但是僅將通訊目標限定為試驗使用者群組。



## <a name="grant-permissions"></a>授與權限

* 開啟 Insights 應用程式，按一下 **[設定]**，然後選取 **[使用者權限]**

:::image type="content" source="media/insights-user-permissions.png" alt-text="設定":::

* 選取 **[新增使用者]**。
* 輸入每個使用者的使用者名稱或電子郵件地址。
* 選取權限等級：
  * **所有組織的存取權** 表示使用者會看到所有層級的所有組織單位。
  * **特定學校的存取權** 表示使用者會看到選取的學校。 開始輸入，然後從清單中選取學校。 您可以一併新增多所學校。
* 按一下 **[新增使用者]**。

:::image type="content" source="media/insights-add-users.png" alt-text="授與權限":::

> [!NOTE]
> 僅將權限提供給需要的教育領導者，並僅限他們負責的組織單位。 如果您不確定是否需要特定組織的使用者權限，請洽詢您機構的隱私權主題專家，例如法務或人力資源人員。

## <a name="edit-permissions"></a>編輯權限
* 選取特定使用者，然後選取 **[編輯]**。
* 更新權限等級或學校清單，然後按一下 **[更新權限]**。

:::image type="content" source="media/insights-edit-users.png" alt-text="編輯權限":::

## <a name="remove-permissions"></a>移除權限
* 選取您要移除的使用者，然後選取 **[移除使用者]**。
* 這些使用者無法再存取組織層級 Insights，但是如果他們擁有課程小組，仍然可以存取課程層級 Insights。

:::image type="content" source="media/insights-remove-users.png" alt-text="移除權限":::
