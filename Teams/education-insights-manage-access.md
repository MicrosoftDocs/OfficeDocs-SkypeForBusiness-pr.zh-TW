---
title: 管理 Education Insights 的使用者存取權
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 管理 Microsoft Teams 中 Education Insights 的使用者存取權。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7203c9bda1a6e5c2bf9d90b490492fe7bbc3f64c
ms.sourcegitcommit: 78fbfcf4a1aafce5d39eea79c9461a9fc1bb3d38
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2023
ms.locfileid: "69707805"
---
# <a name="manage-user-access-to-education-insights"></a>管理 Education Insights 的使用者存取權

本文件提供管理[Microsoft Teams 中的 Education Insights](class-insights.md) 使用者存取權的必要步驟。

You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists. Educators are *automatically* given permission when they own a class team.

若要提供組織層級 Insights，您必須[從學生資訊系統 (SIS) 匯入資訊](education-insights-sis-data-sync.md)，讓 Insights 會有正確對應的教育系統階層結構。

> [!NOTE]
> 只有全域系統管理員才能管理 Insights 的使用者存取權。

> [!TIP]
> 我們建議您為您的所有教育領導者啟用 Insights，讓他們有資料可以了解每所學校，並且可以快速識別問題並且為教育人員提供支援。 即使您正在執行試驗，為所有教育領導者保持 Insights 啟用仍然有幫助，但是僅將通訊目標限定為試驗使用者群組。

## <a name="manage-permissions"></a>管理權限

* 開啟 Insights 應用程式，按一下 **[設定]**，然後選取 **[使用者權限]**

:::image type="content" source="media/insights-user-permissions.png" alt-text="設定。":::

> [!NOTE]
> 當您提供組織層級的權限時，使用者可以在其下方查看所有組織單位。
> 
> 僅將權限提供給需要的教育領導者，並僅限他們負責的組織單位。 如果您不確定是否需要特定組織的使用者權限，請洽詢您機構的隱私權主題專家，例如法務或人力資源人員。

> [!IMPORTANT]
> 第一次指派許可權之後，只有至少有 **兩** 個使用者已存取應用程式，使用者才能在應用程式內檢視資料。 此需求有助於確保正確設定資料的時區，並為所有使用者正確顯示資料。 如果使用者在授與許可權後存取資料時發生問題，請檢查至少有兩個使用者是否已存取該應用程式。

## <a name="role-based-permissions"></a>角色權限

If you use [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) or [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format), you can import all roles and the full hierarchy of schools within the education system. This complete mapping enables you to assign permissions to roles. 

> [!NOTE]
> 當使用者獲派角色時，他們會自動收到正確的權限，以查看與使用者相關的資料。
>
> 如果使用者不再處於角色中，則該角色的權限會遭到自動撤銷其該角色的許可權 (雖然他們可能仍有個別權限)。

* 如有必要，請按一下 **角色權限**。

  您將可以在您的教育組織中查看角色清單，每個角色階層中的層級、指派給角色的使用者數量，和角色的權限等級。 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="角色型權限。":::
  
  如果角色具有多個組織層級，該角色會顯示多次，每個層級出現一次。 在螢幕擷取畫面中，我們在學校、學區和部門層級有主體，因此有三條線表示「主體」。
  
* 針對每個角色，按一下鉛筆圖示以選取權限等級。 預設值為角色沒有查看 Insights 的權限。
* 選取權限等級 - **檢視其組織的資料** 或 **無**。

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="角色型權限面板。":::
  
  如果您在清單上看到需要更細微權限等級的使用者，請在[從 SIS 匯入的資料](education-insights-sis-data-sync.md)調整他們的的角色和/或組織，並[將個別權限授予他們](#grant-individual-permission-to-a-user) (如有需要)。

* 按一下 **[儲存變更]**。

  現在會將此權限等級自動指派給具有此角色與組織層級的任何新使用者。 使用者會看到在其階層層級及以下的所有組織單位資料。  


## <a name="individual-permissions"></a>個別權限

如果您未使用 SDS V2 匯入組織的 SIS 資料,使用個別權限以調整使用者的權限或指定每個使用者的權限。

* 按一下 **個別權限** 分頁。
  
  您將看到您教育組織中的使用者已獲授予個別權限。 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="個別權限。":::
  
### <a name="grant-individual-permission-to-a-user"></a>將個別權限授予使用者
* 按一下畫面左側的 **授予個別權限**。
* 輸入每個使用者的使用者名稱或電子郵件地址。
* 選取權限等級：
  * **全部** 表示使用者會看到所有層級的所有組織單位。 這很少使用。
  * **特定組織** 表示使用者會看到選取的組織單位，以及其下的所有組織單位。 開始輸入，然後從清單中選取組織單位。
* 按一下 **[授與權限]** 以儲存。

### <a name="change-the-individual-permission-of-a-user"></a>變更使用者的個別權限
* 針對相關使用者，按一下鉛筆圖示以選取個別的權限等級。
* 選取權限等級：
  * **全部** 表示使用者會看到所有層級的所有組織單位。 這很少使用。
  * **特定組織** 表示使用者會看到選取的組織單位，以及其下的所有組織單位。 開始輸入，然後從清單中選取組織單位。
  * **無** 表示使用者只會看到由其角色自動指派的組織單位 (如果有)。
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="個別權限面板。":::

* 按一下 **[儲存變更]** 以儲存。
