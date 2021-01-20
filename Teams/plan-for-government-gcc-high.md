---
title: Microsoft 365 政府-GCC 高部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 適用于 IT 專業人員的指導方針，可在處理受美國政府法規制約之資料的實體中，驅動 Office 365 部署。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ced9f5cc68ce18bc7e1670db4031ff85b7c76ff2
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909267"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a>規劃 Office 365 政府-GCC 高部署

本指導方針適用于在美國聯邦政府機構中部署 Office 365 的 IT 專業人員，或其他處理受限於政府法規與需求之資料的實體，而在這些情況下，使用的是 Office 365 政府版-GCC 高，適合滿足這些需求。

> [!NOTE]
> 如果您的組織已符合 Office 365 政府版-GCC 優質資格要求，且已適用于並已接受程式，您可以跳過步驟1和2，然後直接移至步驟3。

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a>步驟1。 判斷您的組織是否需要 Office 365 政府-GCC 高且符合資格需求。 

Office 365 政府版-GCC 高環境提供與美國雲端服務的政府需求相符的規範。 除了享有 Office 365 的功能和功能之外，組織還能利用 Office 365 政府版所特有的下列功能帶來的好處：

- 貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。
- 貴組織的客戶內容會儲存在美國。
- 您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。
- Office 365 政府版-GCC 高 = 與美國公用事業部門客戶所需的認證與 accreditations。

您可以在 [office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括 [資格要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到有關 office 365 政府版產品的 office 政府版的詳細資訊。

[ [Office 365 美國政府服務描述](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) ] 描述的是平臺的優點，這些好處是在美國內滿足合規性需求的中心。


> [!Tip]
> 您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄： **與我的組織相關** ，並 **符合組織 y/n 的需求**。 然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定 Office 365 政府版-GCC 高是否適合您的組織。</li><li>確認您的組織符合資格需求。</li></ul> |

> [!Note]
> Office 365 政府-GCC 高版僅適用于美國。 非美國政府客戶可以從許多 [Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。

## <a name="step-2-apply-for-office-365-government---gcc-high"></a>步驟2。 適用于 Office 365 政府-GCC 高

如果您認為此服務適合您的組織，請開始 [申請此服務](https://products.office.com/government/eligibility-validation)的程式。


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a>步驟3。 瞭解 Office 365 政府-GCC 高預設安全性設定。

我們建議您在修改您的系統 [管理員和安全設定](enable-features-office-365.md) 之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要修改任何預設的 Office 365 政府版-GCC 高安全性設定，並解決以先瞭解您所做的任何變更對您造成的影響。</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a>步驟4。 瞭解 Office 365 政府-GCC 高版目前提供哪些團隊功能

若要符合政府雲端客戶的需求，Office 365 政府版中的小組與企業方案中的團隊會有一些差異。 請參閱下表，查看有哪些功能可供使用。

[Microsoft 團隊服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>步驟5。 規劃管理

決定您的管理需求，以及如何符合您的需求。 如需詳細資訊，請參閱 [小組中的管理方案](plan-teams-governance.md) 。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|決策點 |<ul><li>按照 [規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。 </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>步驟6。 部署團隊以進行共同作業

在您 onboarded 至 Office 365 政府-GCC 高版之後，請依照 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。 請務必與您的採納及變更管理小組和小組擁護者接洽。

您也可以與 [FastTrack](https://www.microsoft.com/fasttrack) 或您所選的合作夥伴合作，以進行服務的板載作業。

> [!NOTE]
> 目前尚不支援 GCCH 環境的 Mac 團隊用戶端。

