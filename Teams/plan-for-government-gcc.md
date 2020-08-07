---
title: Office 365 政府-GCC 部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 適用于 IT 專業人員的指導方針，可在處理受美國政府法規制約之資料的實體中，驅動 Office 365 部署
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb916b30a26694debf8d699fc05cc3fcc8c8c77
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581244"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a>規劃 Office 365 政府版-GCC 部署

本指導方針適用于在美國聯邦、州、當地、tribal 或 territorial 政府機構中的 Office 365 部署，或其他處理受限於政府法規與需求之資料的實體，也就是使用 Office 365 政府-GCC 來符合這些需求的 IT 專業人員。 新的2020年3月26日：請不要錯過我們可下載[的適用于 GCC 的快速入門手冊](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)。

> [!IMPORTANT]
> Microsoft 團隊在線上通話和音訊/視訊會議中遇到大量的高峰，因為 coronavirus (COVID-19) pandemic。<br/>
> 
>為了應對通話中的空前增加，並確保連續性和可用性，Microsoft 允許 Microsoft 團隊擁有音訊/視訊伺服器來利用商業資料中心中的處理能力，以及在我們的政府資料中心中。<br/>
> 
>這些音訊/視訊伺服器位於 Microsoft Azure FedRAMP 在美國的高資格鑒定邊界伺服器內，且不會儲存任何客戶內容。 不過，這些伺服器正在處理通話與會議的音訊和視頻，且在這段期間內是在我們的商業員工中運作。<br/>
> 
>經確認，已遮罩的人員會透過審查這些伺服器的任何互動式登入，來監視這些伺服器以取得客戶資料的潛在存取權。 合格的人員符合您存取客戶內容的 GCC 需求。 如需有關篩選需求的詳細資訊，請參閱[GCC 服務描述](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。<br/>
> 
>感謝您的支援人員，因為我們採取步驟來確保我們的服務在這些特別時間內保持可用且可靠。<br/>


> [!NOTE]
> 如果您的組織已符合 Office 365 政府版 GCC 資格要求，且已在計畫中套用並接受，您可以跳過步驟1和2，然後直接移至步驟3。 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a>步驟1。 判斷您的組織是否需要 Office 365 政府-GCC 並符合資格需求。 

Office 365 政府版-GCC 環境提供對雲端服務（包括 FedRAMP 適中版，以及刑事審判與聯邦稅務資訊系統的需求） (CJI 與 FTI 資料類型) 的符合政府需求。

除了享有 Office 365 的功能和功能之外，組織還能利用 Office 365 政府-GCC 所特有的下列功能帶來的好處：

-   貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中，以邏輯方式與客戶內容隔離。
-   貴組織的客戶內容會儲存在美國。
-   您組織的客戶內容的存取權受到限制，無法篩選 Microsoft 人員。
-   Office 365 政府-GCC 符合美國公有事業部門客戶所需的認證與 accreditations。

您可以在[office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)（包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)）中找到適用于美國政府客戶的 office 365 政府版產品的詳細資訊。

[Office 365 美國政府服務描述](https://technet.microsoft.com/library/mt774581.aspx)說明平臺的優點，這些好處是圍繞在美國的會議規範需求中心。

> [!Tip]
> 您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿，並新增兩欄：**與我的組織相關**，並**符合組織 y/n 的需求**。 然後，您可以與同事核對此清單，以確認此服務符合貴組織的需求。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定 Office 365 政府版-GCC 是否適合您的組織。</li><li>確認您的組織符合資格需求。</li></ul> |

> [!Note]
> Office 365 政府版-GCC 僅適用于美國。 非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。


## <a name="step-2-apply-for-office-365-government---gcc"></a>步驟2。 適用于 Office 365 政府-GCC

如果決定此服務適合您的組織，請在[這裡開始申請此服務](https://products.office.com/government/eligibility-validation)的程式。

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a>步驟3。 瞭解 Office 365 政府-GCC 預設安全性設定。

我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前，先仔細檢查，並考慮對規範的影響，然後再變更預設的安全性設定。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要修改任何預設的 Office 365 政府版-GCC 安全設定，並解決以首先瞭解您所做的任何變更對您造成的影響。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>步驟4。 瞭解哪些功能目前無法使用或預設為停用。

為了符合政府雲端客戶的需求，Office 365 政府版與企業版方案之間有一些差異。 請參閱下表，查看有哪些功能可供使用。

[Microsoft 團隊服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> 當所有其他工作負載在 GCC 雲端中都是完整的，當所有其他的整合作業完成後，就能在小組中使用它們。


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定 [小組] 功能集是否符合貴組織的需求。</li></ul> |

## <a name="step-5-plan-for-governance"></a>步驟5。 規劃管理

決定您的管理需求，以及如何符合您的需求。 如需詳細資訊，請參閱[小組中的管理方案](plan-teams-governance.md)。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>按照[規劃團隊中的管轄](plan-teams-governance.md)原則，決定並記錄您的管理需求。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>步驟6。 部署團隊以進行共同作業

在您 onboarded 至 Office 365 政府– GCC 之後，請依照[如何推出 Microsoft 團隊](How-to-roll-out-teams.md)中的建議部署路徑進行。 請務必與您的採納及變更管理小組和小組擁護者接洽。

您也可以與[FastTrack](https://www.microsoft.com/fasttrack)或您所選的合作夥伴合作，以進行服務的板載作業。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>步驟7。 為會議和語音部署團隊

這也是將小組與較大的風險承擔者群組搭配使用以開始規劃會議和[雲端語音功能](cloud-voice-deployment.md)的絕佳時機。

