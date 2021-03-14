---
title: 使用 Teams 醫療保健範本建立團隊
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 在系統管理中心或 Microsoft Graph 使用 Microsoft Teams 範本，提供預先定義的設定、頻道和應用程式範本，以快速且輕鬆地建立團隊。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260305"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>使用 Teams 醫療保健範本建立團隊

Microsoft Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。

對醫療保健組織來說，範本特別強大，因為它們提供結構，讓使用者以如何有效地使用 Teams 為導向。 範本也可讓系統管理員在組織中部署一致的小組。 如果您負責規劃、部署和管理整個醫療保健組織的多個團隊，本文適合您。

選擇使用 Teams 醫療保健範本建立團隊的方法：

| 誰 | 使用方法： |
| ---- | --------- |
| 系統管理員和 IT 專業人員 | [使用 Teams 系統管理中心](#use-the-teams-templates-in-the-teams-admin-center)根據醫療保健 Teams 範本建立團隊。|
| 開發人員和系統整合者 | [使用 Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) 根據醫療保健 Teams 範本建立團隊。 |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>使用 Teams 系統管理中心的 Teams 範本

Microsoft Teams 系統管理員可以使用 Teams 系統管理中心，並透過 Teams 範本建立團隊。 我們目前提供兩種第一方醫療保健範本，可用於各種情況。 若要深入了解一般小組範本，請參閱[管理中心網站中的 Teams 範本入門](../../get-started-with-teams-templates-in-the-admin-console.md)。

### <a name="collaborate-on-patient-care"></a>在病患照護上共同作業

 簡化病房、配藥處或部門內的醫療保健通訊和共同作業。 範本可用來協助病患管理和醫院的操作需求。

| 範本類型 |baseTemplateId| 此基本範本提供的屬性 |
| ------------------ |---|----------------------------------------------------- |
| 在病患照護上共同作業 |`healthcareWard` | 頻道：<ul><li>一般</li><li>公告</li><li>過程中討論</li><li>輪次</li><li>人員</li><li>訓練</li></ul> 應用程式： <ul><li>Wiki</li><li>清單</li></ul>|
||||

### <a name="hospital"></a>醫院

簡化醫院內多個病房、配藥處或部門之間的通訊和共同作業。 此範本包含一組用於醫院作業的基本頻道，且可自我擴充以包含專科、臨時特別項目等。

| 範本類型 |baseTemplateId | 此基本範本提供的屬性 |
| ------------------|-- |----------------------------------------------------- |
|醫院|`healthcareHospital`|頻道： <ul><li>一般</li><li>公告</li><li>合規性</li><li>監管</li><li>人力資源</li><li>藥品部</li></ul> 應用程式： <ul><li>Wiki</li><li>清單 </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>使用 Teams 範本與 Microsoft Graph

開發人員可以使用 Microsoft Graph 搭配 Teams 範本建立團隊。 我們目前提供兩種第一方醫療保健範本，可用於各種情況。 如需深入了解一般小組範本，請參閱 [Teams 範本入門](../../get-started-with-teams-templates.md)。 而有關 Teams 範本和 Microsoft Graph 的資訊，請參閱 [Microsoft Teams API 概觀](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) 和 [teamsTemplate 資源類型](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

### <a name="ward-template"></a>Word 範本

病房範本適用於在病房、配藥處或部門內進行通訊和共同作業。 範本可用來協助病患管理，以及病房的操作需求。 例如，您可以在 *[公告]* 頻道中張貼病房公告，而班次可以在 *[人員]* 中管理。 如果您想要簡化您的病房作業，則此範本適合您。

|範本類型 |baseTemplateId |基準範本頻道|
|:--- |:---|:---|
|醫療保健 - 病房 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 公告\* <br> 過程中討論\* <br> 輪次\* <br> 人員\* <br> 訓練\* |
|     | |         |

\*自動加入我的最愛

### <a name="hospital-template"></a>醫院範本

醫院範本適用於醫院內多個病房、配藥處或部門的通訊和共同作業。 此範本包含數個操作頻道，包括 *[公告]*、 *[監管]* 和 *[藥品部]*。我們還提供指令碼，可讓您以各種額外的部門或專科為主的頻道來延伸範本，且您可以新增、刪除或編輯您喜歡的頻道。 例如，如果您有 *[內科]* 部門，但不需要 *[眼科]* 的頻道，則指令碼可以調整為包含 *[內科]* 頻道，並移除 *[眼科]* 頻道。 建議您不要將這些專科或病房模型頻道自動加入我的最愛，以避免通知飽和。 使用者通常會將任何他們覺得相關的頻道加入最愛。

|範本類型 |baseTemplateId |基準範本頻道|
|:--- |:---|:---|
|醫療保健 - 醫院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 公告\* <br> 合規性\* <br> 監管 <br> 人力資源 <br> 藥品部 |
| | |  |

\*自動加入我的最愛 

### <a name="how-to-use-first-party-templates"></a>如何使用第一方範本

若要使用這些範本，只需將要求主體中的 'template@odata.bind' 屬性從 'standard' 變更為上述的 TemplateDs。  如需了解如何部署 Teams 範本，請參閱 Microsoft Graph 文章，以了解如何[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 範本中的頻道會自動在 [一般] 索引標籤下建立。

#### <a name="example-hospital-template-extension-script"></a>範例：醫院範本延伸模組指令碼

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

### <a name="related-topics"></a>相關主題

[開始使用 Teams 範本](../../get-started-with-teams-templates.md)

[開始使用適用於醫療保健組織的 Teams](teams-in-hc.md)
