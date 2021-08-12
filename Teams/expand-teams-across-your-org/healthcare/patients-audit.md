---
title: '針對 IT 和合規性系統管理員Teams病患應用程式 '
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
description: 瞭解為系統管理員稽核病患Teams應用程式
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 288877032c662ee03e0fd575a1f9ce2e96d1b4336c290899e98eeef92a11fecf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308732"
---
# <a name="audit-logs-for-patients-app"></a>病患應用程式的稽核記錄

> [!NOTE]
> 自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。 病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。 所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。 使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。
>
>使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。 請查看清單中的病患範本以開始使用。 若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。

病患應用程式活動的稽核記錄可讓事件後回應小組審查對病患電子病歷 (EMR) 或病患醫療保健資訊 (PHI) 的變更，並決定是否需要變更或改善生產力工具中 PHI 存取的政策或程式。 稽核記錄事件涵蓋透過病患應用程式使用者介面執行的動作。

## <a name="meet-hipaa-requirements"></a>符合 HIPAA 需求

根據 HIPAA 指導方針，醫療保健提供者必須保留所有 PHI 存取的記錄，以便對變更進行稽核。 Microsoft 承諾使用 MICROSOFT TEAMS企業客戶，並協助他們符合 HIPAA 需求和控制措施。 透過病患 App 存取 PHI 的功能會完全追蹤，Microsoft 365合規性中心提供記錄，如稽核記錄搜尋功能一文[所述](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

> [!IMPORTANT]
> 根據法律，維護病患隱私權的重任是由醫療保健提供者承擔。 法律賦予病患隱私權，並規定 IT 系統管理員或 HIPAA 控制者能輕鬆判斷哪些護士、醫師或社會工作人員存取或變更病患記錄。 違反 PHI 存取權最常見的範例之一是存取至VIP 病患。 需要稽核記錄功能，才能針對任何 PHI 存取違規進行調查，並符合 HIPAA 需求。

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>啟用病患應用程式的稽核記錄

稽核取決於幾個先前的配置：

1. 系統管理員必須和 FHIR 服務提供者合作，以病患 App 所使用的格式使用 EMR。 
2. 醫療保健提供者系統管理員必須啟用系統管理中心Teams App。 請參閱[管理應用程式設定Microsoft Teams](../../teams-app-setup-policies.md)相關文章以瞭解更多資訊。
3. 系統管理員必須啟用活動稽核，就像啟用任何活動記錄稽核的方式一樣，如您開始之前和開啟[](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin)或關閉稽核記錄[搜尋](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)中所述。 如果稽核記錄已經啟動，則病患應用程式不需要任何特殊功能。 每次醫療保健提供者在小組中安裝及執行應用程式時，稽核記錄會記錄其 PHI 活動。
4. 然後系統管理員必須宣佈病患應用程式的可用性，而醫療保健工作者必須開始產生活動，才能納入稽核。

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>執行稽核

有關執行活動記錄搜尋的指示，請參閱 [搜尋稽核記錄](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)。

## <a name="logged-activities-for-patients-app"></a>病患應用程式的記錄活動

病患應用程式擁有自己的記錄活動，如下表所列：

|好用的名稱 | 操作 | 描述|
|:---|:---|:---|
| 已查看病患清單 | PatientListView | 使用者已查看病患清單。|
| 已刪除的病患清單 | PatientListDelete | 使用者刪除了病患清單。|
| 新增病患到清單 | PatientListAddPatient | 病患已新加入病患清單。 |
| 新增病患記事 | PatientNoteAdd | 已新增記事至病患記錄。 |
| 建立病患架構 | PatientSchemaCreate | 已建立病患記錄中使用的一組資料行。 |
| 使用者啟動匯出 | ExportInitiation | 病患資料從病患應用程式匯出至Excel檔案。 檔案會儲存于小組 sharepoint 網站。 |
| 已建立病患清單 | PatientListCreate | 使用者建立了病患清單。|
| 設定預設病患清單| PatientListDefaultSet| 使用者將特定清單設定為預設清單。|
| 從清單中移除病患| PatientListRemovePatient | 一位病患已從病患清單中移除。 |
| 搜尋病患 | PatientSearch | 在 EHR 服務中搜尋病患記錄。 |
| 更新病患架構 | PatientSchemaUpdate  | 更新病患記錄中使用的一組現有資料行。 |<!-- | 將病患移至其他清單| PatientMoved | 病患記錄從一份清單移到另一份清單。 |-->
| 重新命名病患清單 | PatientListRename | 已重新命名病患清單。 |
| 病患清單中的已編輯欄 | PatientListEditColumns | 已編輯病患清單中的欄， (或移除) 。 |
| 已查看病患詳細資料 | PatientView | 使用者已查看病患記錄。|
| 已編輯病患詳細資料 | PatientDetailsEdit | 已編輯病患記錄的詳細資料。 |
| 設定 EHR 連接 | EHRConnectionSet | 設定用來連接到 EHR FHIR 服務連接的 URL。 範例<span>：HTTPs:// api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |

您可以自訂您的稽核，以搜尋或篩選任何這些記錄的活動。

一般而言，Microsoft Teams記錄的活動會以 Microsoft Teams[描述](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)。

## <a name="related-topics"></a>相關主題

[搜尋稽核記錄](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
