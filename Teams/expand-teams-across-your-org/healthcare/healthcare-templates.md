---
title: 醫療保健組織的範本
author: serdarsoysal
ms.author: serdars
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
description: 使用 Microsoft Teams 範本與 Microsoft Graph，提供預先定義的設定、頻道和應用程式範本，以快速且輕鬆地建立團隊。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260335"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>開始使用醫療保健組織的 Teams 範本

Microsoft Teams 範本提供預先定義的設定、頻道和預先安裝應用程式的範本，讓您快速且輕鬆地建立團隊。

對醫療保健組織來說，範本特別強大，因為範本提供結構讓使用者熟悉如何有效地使用 Teams。 範本也允許系統管理員在組織中部署一致的團隊。 如果您負責規劃、部署和管理整個醫療保健組織的多個團隊，本文適合您。

我們目前提供兩種可用於各種情況的第一方醫療保健範本。 若要深入瞭解團隊範本，請參閱 Teams 範本 [入門](../../get-started-with-teams-templates.md)。

## <a name="ward-template"></a>範本範本

此範本適用于在小公司、容器或部門內進行通訊和共同合作。 此範本可用來協助病患管理，以及風險管理的運作需求。 例如，公告公告可以張貼在公告頻道中，而班次可以在 *Staffing 中管理*。 如果您想要簡化您的服務運作方式，則此範本適合您。

|基本範本類型 |baseTemplateId |比較基準範本通道|
|:--- |:---|:---|
|醫療保健 - 小品 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 公告\* <br> Huddles\* <br> 輪\* <br> 人手\* <br> 訓練\* |
|     | |         |

\* 自動將我的最愛

## <a name="hospital-template"></a>醫院範本

該醫院範本適用于醫院內多個醫院、容器和部門之間的通訊和共同合作。 此範本包含數個營運頻道，包括公告、小通和行銷，但我們也會在下方提供腳本，以各種額外的部門或以特殊為主的頻道延伸範本，您可以新增、刪除或編輯您喜歡的頻道。  例如，如果您有一個內鏈系，但不需要一個 *Ophthalmoph* 的頻道，則腳本可以調整為包含一個內文 *學* 通道，並移除 *Ophthalmoph 通道*。 建議您不要自動將這些特殊或以小動物模型模式使用的頻道做為我的最愛，以避免通知飽和度。 使用者通常會將任何他們覺得相關的頻道最愛。

|基本範本類型 |baseTemplateId |比較基準範本通道|
|:--- |:---|:---|
|醫療保健 - 醫院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 公告\* <br> 合規性\* <br> 保管 <br> 人力資源 <br> 藥學 |
| | |  |

\* 自動將我的最愛 

## <a name="how-to-use-first-party-templates"></a>如何使用第一方範本

若要使用這些範本，只要將要求內文中的 template@odata.bind' 屬性從 "standard" 變更為上述 TemplateIDs。  如何部署 Teams 範本，請參閱如何建立團隊的 Microsoft Graph [文章](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 範本中的頻道會自動在一般 Tab 下建立。

### <a name="example-hospital-template-extension-script"></a>範例：醫院範本擴充功能腳本

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

## <a name="related-topics"></a>相關主題

[開始使用 Teams 範本](../../get-started-with-teams-templates.md)

[開始使用適用於醫療保健組織的 Teams](teams-in-hc.md)

[在系統管理主控台中開始使用 Teams 範本](../../get-started-with-teams-templates-in-the-admin-console.md)
