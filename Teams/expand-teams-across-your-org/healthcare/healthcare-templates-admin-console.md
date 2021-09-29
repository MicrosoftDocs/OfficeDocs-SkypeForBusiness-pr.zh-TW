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
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: 瞭解如何在 Teams 系統管理中心管理及使用醫療保健小組範本, 以及使用 Microsoft Graph 快速且輕鬆地為醫療保健組織建立團隊。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 00da42e4e573306a3737b1d35e89292b04df4fa4
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991122"
---
# <a name="use-healthcare-team-templates"></a>使用醫療保健團隊範本

Microsoft Teams 的團隊範本提供預先定義的設定、頻道和預先安裝應用程式的團隊結構, 讓您快速且輕鬆地建立團隊。

對於醫療保健組織來說, 團隊範本可能功能特別強大, 因為它們可協助您在整個組織中快速部署一致的團隊。 範本也可以協助職員瞭解如何有效地使用 Teams。

Teams 中包括專為醫療保健組織設計的範本。 使用這些預先建立的範本快速建立團隊, 讓職員在病患照護或營運需求上溝通及共同作業。 本文將介紹各個 Teams 範本, 並建議如何使用範本。

管理及使用團隊範本的方式取決於您是系統管理員或開發人員。

|如果您是: | 那麼, 您: |
| ---- | --------- |
| 系統管理員或 IT 專業人員 |[在 Teams 系統管理中心管理團隊範本](#manage-team-templates-in-the-teams-admin-center)。 查看團隊範本並申請範本原則, 以控制職員在 Teams 中建立團隊時可使用的範本。 |
| 開發人員 | [使用 Microsoft Graph](#use-team-templates-with-microsoft-graph)從團隊範本建立團隊。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>在系統管理中心管理團隊範本

身為系統管理員, 您可以在 Microsoft Teams 系統管理中心管理團隊範本。 您可以在這裡檢視每個範本的詳細資訊。 您也可以[建立及指派範本原則](../../templates-policies.md)給職員, 以控制他們在 Teams 中[建立團隊](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)時看到的範本。 

若要深入瞭解一般團隊範本, 請參閱[在 Teams 系統管理中心開始使用團隊範本](../../get-started-with-teams-templates-in-the-admin-console.md)。

我們目前提供下列預先建立的醫療保健團隊範本。 若要查看, 請前往 Teams 系統管理中心左側版面配置, 前往 **Teams** > **團隊範本**。
### <a name="patient-care"></a>病患照護

 此範本適用於在病房、配藥處或部門內進行通訊和共同作業。 您可以使用此範本來協助病患管理和病房的運作需求。 例如, 在 *公告* 頻道中張貼病房公告, 並在 *人員* 頻道中管理職員班次。

| 範本類型 |TemplateId| 此範本提供的屬性 |
| ------------------ |---|----------------------------------------------------- |
| 病患照護 |`healthcareWard` | 頻道：<ul><li>一般</li><li>公告<ul><li>布告欄&sup1;</li></ul></li><li>小型會議<ul><li>清單 (病患清單)&sup1;</li></ul></li><li>輪班<ul><li>檢查&sup1;</li></ul></li><li>人員</li><li>訓練</li></ul> 應用程式： <ul><li>Wiki</li><li>清單</li><li>工作</li><li>核准</li><li>班次</li><li>佈告欄</li><li>檢查</li></ul>|
||||

&sup1;應用程式已新增到頻道做為索引標籤。
### <a name="hospital"></a>醫院

此範本適用於醫院內多個病房、配藥處或部門的通訊和共同作業。 此範本包含一組用於醫院作業的基本頻道, 且可延伸供進一步自訂。

| 範本類型 |TemplateId | 此範本提供的屬性 |
| ------------------|-- |----------------------------------------------------- |
|醫院|`healthcareHospital`|頻道： <ul><li>一般<ul><li>清單&sup1;</li></ul></li><li>公告<ul><li>布告欄&sup1;</li></ul></li><li>合規性</li><ul><li>檢查&sup1;</li></ul></li><li>監管</li><li>人力資源<ul><li>構想&sup1;</li></ul></li><li>藥品部</li></ul> 應用程式： <ul><li>Wiki</li><li>工作</li><li>清單</li><li>核准</li><li>班次</li><li>佈告欄</li><li>檢查</li><li>構想</li></ul>|
||||

&sup1;應用程式已新增到頻道做為索引標籤。
## <a name="use-team-templates-with-microsoft-graph"></a>以 Microsoft Graph 使用團隊範本

開發人員可以使用 Microsoft Graph 從預先建立的團隊範本建立團隊。 若要深入瞭解以 Microsoft Graph 使用團隊範本, 請參閱[開始用 Microsoft Graph 使用團隊範本](../../get-started-with-teams-templates.md), [Microsoft Teams API 概觀](/graph/teams-concept-overview?view=graph-rest-1.0), 和[團隊範本資源類型](/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

以下是預先建立的醫療保健團隊範本。
### <a name="ward"></a>病房

病房範本適用於在病房、配藥處或部門內進行通訊和共同作業。 此範本可用來協助病患管理和病房的運作需求。 例如，您可以在 *[公告]* 頻道中張貼病房公告，而班次可以在 *[人員]* 中管理。 如果您想要簡化您的病房作業，則此範本適合您。

|範本類型 |TemplateId |範本頻道|
|:--- |:---|:---|
|醫療保健 - 病房 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 一般<br>公告&sup2; <br> 小型會議&sup2; <br> 輪班&sup2; <br> 人員配置&sup2; <br> 訓練&sup2; |
|     | |         |

&sup2;自動將頻道加入我的最愛

### <a name="hospital"></a>醫院

醫院範本適用於醫院內多個病房、配藥處或部門的通訊和共同作業。 此範本包含數個操作頻道, 例如 *公告*、*監護人*, 和 *藥局*。 我們也提供指令碼, 您可以使用此指令碼來擴充範本, 以含其他部門或特殊頻道。 您可以編輯它以配合您的需求。

例如, 如果您有一個 *內科* 部門, 但不需要用於 *眼科* 的頻道, 指令碼可以調整為包含一個 *內分泌學* 頻道, 並移除 *眼科* 頻道。  建議您不要將這些專科或病房模型頻道自動加入我的最愛，以避免通知飽和。 使用者通常會將任何他們覺得相關的頻道加入最愛。

|範本類型 |TemplateId |範本頻道|
|:--- |:---|:---|
|醫療保健 - 醫院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 一般<br>公告&sup2; <br> 合規性&sup2; <br> 監管 <br> 人力資源 <br> 藥品部 |
| | |  |

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

[在 Teams 系統管理中心開始使用團隊範本](../../get-started-with-teams-templates-in-the-admin-console.md)

[開始用 Microsoft Graph 使用團隊範本](../../get-started-with-teams-templates.md)

[開始使用適用於醫療保健組織的 Teams](teams-in-hc.md)