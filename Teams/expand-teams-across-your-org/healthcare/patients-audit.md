---
title: '針對小組 IT 與合規性管理員審核患者應用程式 '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: 瞭解如何針對團隊管理員審核患者應用程式
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ce1851b6d424203f6a4aed8a871209e3a65ce5f8
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803511"
---
# <a name="audit-logs-for-patients-app"></a>病患應用程式的稽核記錄

> [!NOTE]
> 2020年10月30日生效，患者 app 已停用，且已由小組中的 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。 患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。 所有與患者 app 相關的資料都會保留在這個群組中，但無法再透過使用者介面存取。 使用者可以使用 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。
>
>透過清單，您的醫療保健組織中的 [護理小組] 可建立案例的患者清單，包括從倒圓角和 interdisciplinary 小組會議到一般患者監視。 查看清單中的患者範本以開始使用。 若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。

患者應用程式活動的審核記錄可讓您在事件回應小組審閱患者的電子醫療記錄 (EMR) 或患者保健資訊 (PHI) 並判斷是否需要在生產率工具中進行 PHI 存取的原則或程式的變更或改進。 審核記錄事件涵蓋透過患者 app 使用者介面執行的動作。

## <a name="meet-hipaa-requirements"></a>符合 HIPAA 需求

根據 HIPAA 準則，醫療保健供應商必須保留對 PHI 的所有存取權記錄，才能進行審核變更。 Microsoft 致力於使用 Microsoft 團隊的企業客戶，並協助他們滿足 HIPAA 需求與控制措施。 您可以透過患者 App 來取得對 PHI 的存取權，並在 Microsoft 365 合規性中心提供記錄，如 [ [審核記錄搜尋功能](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) ] 文章中所述。

> [!IMPORTANT]
> 在醫療保健供應商的法律上，維持患者隱私權的負擔。 法律對患者保密，且要求 IT 系統管理員或 HIPAA 控制器能輕鬆判斷哪些護士、clinician 或同事存取或變更了患者記錄。 [PHI 存取衝突] 最常見的其中一個範例是存取 VIP 患者。 必須具備審核記錄功能，才能對任何 PHI 存取違規進行調查，以及符合 HIPAA 需求。

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>啟用患者 App 的審核記錄

審計依賴于數個預先設定：

1. 系統管理員必須與他們的 FHIR 服務提供者合作，才能以患者 App 所使用的格式 EMR。 請參閱將 [電子醫療保健記錄整合至 Microsoft 團隊](patients-app.md)。
2. 醫療保健提供者管理員必須在小組系統管理中心啟用患者 app。 如需詳細資訊，請參閱 [管理 Microsoft 團隊和相關文章中的 app 設定原則](../../teams-app-setup-policies.md) 。
3. 系統管理員必須啟用活動審查，就與啟用任何活動記錄審核的方式相同，如 [您開始](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) 並 [開啟或關閉審核記錄搜尋](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)。 如果已開啟審核記錄，患者 App 不需要任何特殊的功能。 每當醫療保健提供者在小組中安裝並執行應用程式時，審核記錄會記錄其 PHI 活動。
4. 系統管理員接著需要宣告患者 app 的可用性，而醫療保健工人必須開始產生活動，才能納入審計。

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>執行審計

如需執行活動記錄檔搜尋的指示，請參閱 [搜尋審核記錄](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)。

## <a name="logged-activities-for-patients-app"></a>患者 app 的記錄活動

患者 app 有自己的記錄活動，列在下表中：

|好記的名稱 |一道|說明|
|:---|:---|:---|
| 已查看患者清單 | PatientListView | 使用者已查看患者清單。|
| 已刪除的患者清單 | PatientListDelete | 使用者已刪除患者清單。|
| 已新增患者至清單 | PatientListAddPatient | 患者已新增至患者清單。 |
| 已新增患者記事 | PatientNoteAdd | 已將記事新增至患者記錄。 |
| 已建立患者架構 | PatientSchemaCreate | 已建立患者記錄中使用的一組資料行。 |
| 使用者已開始匯出 | ExportInitiation | 患者資料已從患者 app 匯出到 Excel 檔案中。 檔案將會儲存在小組 sharepoint 網站上。 |
| 已建立患者清單 | PatientListCreate | 使用者建立患者清單。|
| 設定預設患者清單| PatientListDefaultSet| 使用者將特定清單設為預設清單。|
| 已從清單中移除患者| PatientListRemovePatient | 患者已從患者清單中移除。 |
| 已搜尋患者 | PatientSearch | 已在 EHR 服務中搜尋患者記錄。 |
| 更新的患者架構 | PatientSchemaUpdate  | 已更新患者記錄中使用的一組現有資料行。 |<!-- | 已將患者移至不同的清單| PatientMoved | 患者記錄是從某個清單移到另一個清單。 |-->
| 重新命名的患者清單 | PatientListRename | 已重新命名患者清單。 |
| 已編輯的患者清單中的欄 | PatientListEditColumns | 已編輯患者清單中的欄 (新增或移除) 。 |
| 已查看患者的詳細資料 | PatientView | 使用者查看患者記錄。|
| 已編輯的患者詳細資料 | PatientDetailsEdit | 已編輯患者記錄的詳細資料。 |
| 設定 EHR 連接 | EHRConnectionSet | 設定用來連接 EHR FHIR 服務連線的 URL。 範例： HTTPs://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

您可以視需要自訂您的審核，以搜尋或篩選任何記錄的活動。

Microsoft 團隊 [活動](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)中描述了一般的 microsoft 團隊記錄活動。

## <a name="related-topics"></a>相關主題

[搜尋審核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[將電子醫療保健記錄整合至 Microsoft Teams](patients-app.md)
