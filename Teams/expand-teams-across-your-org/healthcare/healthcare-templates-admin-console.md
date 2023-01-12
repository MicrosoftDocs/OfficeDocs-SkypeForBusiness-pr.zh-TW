---
title: 使用醫療保健團隊範本
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: 瞭解如何在 Teams 系統管理中心管理及使用醫療保健小組範本, 以及使用 Microsoft Graph 快速且輕鬆地為醫療保健組織建立團隊。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 17f5ce2774dd163f5f244bea0e685623f64ed59f
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778963"
---
# <a name="use-healthcare-team-templates"></a>使用醫療保健團隊範本

Microsoft Teams 的團隊範本提供預先定義的設定、頻道和預先安裝應用程式的團隊結構, 讓您快速且輕鬆地建立團隊。

對於醫療保健組織來說, 團隊範本可能功能特別強大, 因為它們可協助您在整個組織中快速部署一致的團隊。 範本也可以協助職員瞭解如何有效地使用 Teams。

Teams 中包括專為醫療保健組織設計的範本。 使用這些預先建立的範本快速建立團隊, 讓職員在病患照護或營運需求上溝通及共同作業。 本文將介紹各個 Teams 範本, 並建議如何使用範本。

管理及使用團隊範本的方式取決於您是系統管理員或開發人員。

|如果您是: | 那麼, 您: |
| ---- | --------- |
| 系統管理員或 IT 專業人員 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 開發人員 | [使用 Microsoft Graph](#use-team-templates-with-microsoft-graph)從團隊範本建立團隊。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>在系統管理中心管理團隊範本

身為系統管理員, 您可以在 Microsoft Teams 系統管理中心管理團隊範本。 您可以在這裡檢視每個範本的詳細資訊。 您也可以[建立及指派範本原則](../../templates-policies.md)給職員, 以控制他們在 Teams 中[建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)時看到的範本。

若要深入瞭解一般團隊範本, 請參閱[在 Teams 系統管理中心開始使用團隊範本](../../get-started-with-teams-templates-in-the-admin-console.md)。

我們目前提供下列預先建立的醫療保健團隊範本。 若要查看, 請前往 Teams 系統管理中心左側版面配置, 前往 **Teams** > **團隊範本**。

### <a name="patient-care"></a>病患照護

簡化病房、配藥處或部門內的醫療保健通訊和共同作業。 使用此範本可促進病患管理和操作需求。 例如, 在 *公告* 頻道中張貼病房公告, 並在 *人員* 頻道中管理職員班次。

>[!div class="mx-tdBreakAll"]
>| 範本類型 |TemplateId| 此範本提供的屬性 |
>| ------------------ |---|----------------------------------------------------- |
>| 病患照護 |`healthcareWard` | 頻道：<ul><li>一般</li><li>公告</li><li>過程中討論</li><li>輪次</li><li>人員</li><li>訓練</li></ul> 應用程式： <ul><li>核准</li><li>佈告欄</li><li>檢查</li><li>清單</li><li>班次</li><li>Planner 和 To Do 的工作</li><li>Wiki</li></ul>|

### <a name="hospital"></a>醫院

簡化醫院內多個病房、配藥處或部門之間的通訊和共同作業。 此範本包含一組用於醫院作業的基本頻道, 且可延伸供進一步自訂。

>[!div class="mx-tdBreakAll"]
>| 範本類型 |TemplateId | 此範本提供的屬性 |
>| ------------------|-- |----------------------------------------------------- |
>|醫院|`healthcareHospital`|頻道： <ul><li>一般</li><li>公告</li><li>合規性</li></li><li>監管</li><li>人力資源</li><li>藥品部</li></ul>  應用程式： <ul><li>核准</li><li>佈告欄</li><li>員工想法</li><li>檢查</li><li>清單</li><li>班次</li><li>Planner 和 To Do 的工作</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>以 Microsoft Graph 使用團隊範本

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview), and [teamsTemplate resource type](/graph/api/resources/teamstemplate).

以下是預先建立的醫療保健團隊範本。

### <a name="patient-care"></a>病患照護

此範本適用於在病房、配藥處或部門內進行通訊和共同作業。 使用此範本可促進病患管理和操作需求。 例如，您可以在 *[公告]* 頻道中張貼病房公告，而班次可以在 *[人員]* 中管理。 如果您想要簡化您的病房作業，則此範本適合您。

>[!div class="mx-tdBreakAll"]
>|範本類型 |TemplateId |範本頻道|
>|:--- |:---|:---|
>|醫療保健 - 病房 | `https://graph.microsoft.com/beta/teamsTemplates('healthcareWard')`   | 一般<br>公告&sup2; <br> 小型會議&sup2; <br> 輪班&sup2; <br> 人員配置&sup2; <br> 訓練&sup2; |

&sup2;自動將頻道加入我的最愛

### <a name="hospital"></a>醫院

此範本適用於醫院內多個病房、配藥處或部門的通訊和共同作業。 它包含數個營運通道，例如 *宣告*、*監護和信**道*。 我們也提供腳本，讓您可以將範本延伸至更多部門或特殊頻道。 您可以編輯它以配合您的需求。

例如，如果您有 *一個內分學* 部門，但不需要 *Ophthalmology* 的通道，您可以調整腳本以包含 *尾分詞* 通路，並移除眼 *科頻道。* 建議您不要將這些專科或病房模型頻道自動加入我的最愛，以避免通知飽和。 使用者通常會將任何他們覺得相關的頻道加入最愛。

>[!div class="mx-tdBreakAll"]
>|範本類型 |TemplateId |範本頻道|
>|:--- |:---|:---|
>|醫療保健 - 醫院 | `https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')`   | 一般<br>公告&sup2; <br> 合規性&sup2; <br> 監管 <br> 人力資源 <br> 藥品部 |

&sup2;自動將頻道加入我的最愛

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>如何用 Microsoft Graph 使用團隊範本

若要使用這些範本, 請將要求主體中的 'template@odata.bind' 屬性從 'standard' 變更為上述的 TemplateIds。 若要瞭解如何部署團隊範本, 請參閱 Microsoft Graph 如何[建立團隊](/graph/api/team-post?view=graph-rest-beta)一文。

> [!NOTE]
> 範本中的頻道會自動建立在 **[一般]** 索引標籤下。

#### <a name="example-hospital-template-extension-script"></a>範例: 醫院範本延伸模組指令碼

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-articles"></a>相關文章

- [從範本建立團隊](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [在 Teams 系統管理中心開始使用團隊範本](../../get-started-with-teams-templates-in-the-admin-console.md)
- [開始用 Microsoft Graph 使用團隊範本](../../get-started-with-teams-templates.md)
- [開始使用適用於醫療保健組織的 Teams](/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)