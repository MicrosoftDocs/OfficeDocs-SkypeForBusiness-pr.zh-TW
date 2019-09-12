---
title: 開始使用適用于醫療保健組織的團隊範本
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 開始使用適用于醫療保健組織的團隊範本
ms.openlocfilehash: 9a00d0d707867d009a9bc724d88fd4f9d8e6997f
ms.sourcegitcommit: 113c00a26c5a6ad22ef24b1bdcd830e7c2cd14ff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852836"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>開始使用適用于醫療保健組織的團隊範本

Microsoft 團隊範本可讓您透過提供預先定義的設定、頻道及預先安裝應用程式範本，快速且輕鬆地建立小組。

針對醫療保健組織而言，範本特別實用，因為它們為使用者提供結構，以瞭解如何有效地利用團隊。 範本也可讓系統管理員在組織中部署一致的團隊。 本文適用于您負責規劃、部署及管理整個醫療保健組織中的多個小組。

我們目前提供兩個您可以在各種情況下利用的第一方醫療保健範本。 若要深入瞭解小組範本的整體資訊，請參閱[開始使用團隊範本](../../get-started-with-teams-templates.md)。

## <a name="ward-template"></a>Ward 範本

Ward 範本適用于 ward、pod 或部門中的通訊與共同作業。 範本可用於協助患者管理，以及 ward 的運作需求。 例如，您可以在*宣告*頻道中張貼 ward 宣告，並在*人員*集中管理班次。 如果您想要簡化您的 ward 作業，這個範本適合您。

|基底範本類型 |baseTemplateId |比較基準範本頻道|
|:--- |:---|:---|
|醫療保健-Ward | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 公告\* <br> Huddles\* <br> 輪\* <br> 人員\* <br> 訓練\* |
|     | |         |

\*自動將

## <a name="hospital-template"></a>醫院範本

醫院範本適用于醫院中的多個 wards、箱與部門之間進行通訊與共同作業。 此範本中包含幾個作業通道，包括*宣告*、 *Custodial*和*藥房*，但我們也提供下列腳本，此腳本會以不同的其他部門擴充範本，或以專業為中心的頻道，您可以根據自己的喜好來新增、刪除或編輯。 例如，如果您有*Endocrinology*部門，但不需要*Ophthalmology*的頻道，則可以調整腳本以納入*Endocrinology*通道並移除*Ophthalmology*通道。 我們建議您不要將這些專業或 ward 模型的通道自動將，以免出現通知的飽和情況。 使用者通常會最愛他們找到的任何頻道。

|基底範本類型 |baseTemplateId |比較基準範本頻道|
|:--- |:---|:---|
|醫療保健-醫院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 公告\* <br> 從屬\* <br> Custodial <br> 人力資源 <br> 藥房 |
| | |  |

\*自動將 

## <a name="how-to-use-first-party-templates"></a>如何使用第一方範本

若要使用這些範本，只要將申請主體中的 ' template@odata.bind」屬性從「標準」變更為上述 TemplateIDs。  如需如何部署團隊範本的詳細資訊，請參閱 Microsoft Graph 文章，瞭解如何[建立團隊](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> 範本中的頻道會自動建立在 [一般] 索引標籤底下。

### <a name="example-hospital-template-extension-script"></a>範例：醫院範本延伸腳本

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
              "displayName": "Women’s Health",
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

[團隊範本快速入門](../../get-started-with-teams-templates.md)

[開始使用適用于醫療保健組織的團隊](teams-in-hc.md)
