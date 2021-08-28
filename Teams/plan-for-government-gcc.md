---
title: Microsoft 365政府 - GCC部署
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT 專業人員在處理受美國政府Microsoft 365之資料的實體中推動部署指南
ms.localizationpriority: medium
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
ms.openlocfilehash: bb39b2a123b4e997cb4e15f6f72e0193b41d9bee
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632007"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>規劃Microsoft 365 - GCC部署

本指南適用于在美國聯邦、州、地方、部落或地區政府機構中推動 Microsoft 365 部署的 IT 專業人員，或是處理受政府法規和需求規範之資料的其他實體，而其中 Microsoft 365 政府 - GCC 適合使用這些需求。 2020 年 3 月 26 日新[版](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)：請勿錯過我們可下載的快速入門手冊GCC。

> [!IMPORTANT]
> Microsoft Teams冠狀病毒和 COVID-19 大流行的冠狀病毒 (線上通話和音訊/視訊會議) 高峰。<br/>
> 
>為了因應前所未有的通話量增加，並確保持續性和可用性，Microsoft 允許 Microsoft Teams GCC 音訊/視像伺服器在我們的商業資料中心以及政府資料中心利用處理容量。<br/>
> 
>這些音訊/視Microsoft Azure位於 FedRAMP High 認證邊界伺服器內，且不會儲存任何客戶內容。 不過，這些伺服器正在處理電話和會議的音訊和視音訊，並在此期間由我們的商業人員操作。<br/>
> 
>合格、經篩選的人員會檢查這些伺服器，以檢查這些伺服器的任何互動式登入，以監控客戶資料的潛在存取權。 合格的人員GCC存取客戶內容的需求。 有關篩選需求的詳細資訊，請參閱GCC[描述](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。<br/>
> 
>感謝您的支援，我們採取一些步驟，確保我們的服務在非同尋常時期保持可用且可靠。<br/>


> [!NOTE]
> 如果貴組織已經符合Microsoft 365政府 - GCC資格要求，並申請並已被計畫接受，您可以略過步驟 1 和 2，直接前往步驟 3。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>步驟 1。 判斷貴組織是否需要Microsoft 365政府 - GCC並符合資格要求。 

Microsoft 365政府 - GCC環境符合美國政府雲端服務的需求，包括 FedRAMP 中度，以及犯罪審判和聯邦稅務資訊系統 (CJI 和 FTI 資料類型) 。

除了享受本組織的功能Microsoft 365，組織還受益于下列政府特有的功能 -Microsoft 365 - GCC：

-   貴組織的客戶內容會從邏輯上與 Microsoft 服務的商業Microsoft 365內容分隔。
-   貴組織的客戶內容會儲存在美國境內。
-   您組織客戶內容的存取權僅限於已篩選的 Microsoft 人員。
-   Microsoft 365政府 - GCC遵守美國公共部門客戶所需的認證和認證。

您可以在政府計畫或政府Microsoft 365中GCC美國政府客戶Microsoft 365方案 ，包括資格[要求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)。 [](https://products.office.com/government/compare-office-365-government-plans)

美國政府[Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)服務描述說明平臺的好處，其核心是符合美國國內的合規性需求。

> [!Tip]
> 您可能會想要將服務描述中的資訊表轉移到 Excel 活頁簿，並新增兩欄：與組織 **Y/N** 相關，以及符合組織 **Y/N 的需求**。 然後，您可以與同事一起查看這份清單，確認此服務符合貴組織的需求。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定Microsoft 365政府 - GCC是否適合貴組織。</li><li>確認貴組織符合資格要求。</li></ul> |

> [!Note]
> Microsoft 365政府 - GCC僅適用于美國。 非美國政府客戶可以從多個政府Microsoft 365[中選擇](https://products.office.com/en/government/compare-office-365-government-plans)。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>步驟 2. 申請政府Microsoft 365 - GCC

決定這項服務適合貴組織之後，請在這裡開始申請[這項服務。](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>步驟 3. 瞭解Microsoft 365政府 - GCC預設安全性設定。

建議您在修改管理員和安全性設定之前，先花[](enable-features-office-365.md)一些時間仔細檢查，並考慮對合規性的影響，然後再對預設安全性設定進行任何變更。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要修改任何預設的政府Microsoft 365 - GCC安全性設定，解決以先瞭解您可能進行的任何變更的影響。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>步驟 4. 瞭解預設目前無法使用或停用的功能。

為了配合我們政府雲端客戶的需求，政府與Microsoft 365方案GCC Enterprise差異。 請參閱下表，瞭解哪些功能可供使用。

[Microsoft Teams服務描述](/office365/servicedescriptions/teams-service-description)

> [!Note]
> 一旦其他工作負載在雲端GCC完全可用，當所有其他整合工作完成Teams這些工作負載就會在雲端中可用。


|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定Teams功能集是否符合貴組織的需求。</li></ul> |

## <a name="step-5-plan-for-governance"></a>步驟 5。 管理計畫

判斷您的監管需求，以及如何符合這些需求。 若要詳細資訊[，](plan-teams-governance.md)請前往 Teams 中規劃管理。

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>請遵循管理計畫中的指導方針，在 Teams 中判斷[並記錄您的Teams。](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>步驟 6. 部署Teams共同合作

在您加入政府 -Microsoft 365之後GCC，請遵循如何推出 Microsoft Teams 中概述[的建議部署路徑](./deploy-overview.md)。 請務必與採用與變更管理團隊互動，並Teams領軍者。

您也可以與合作夥伴或[FastTrack](https://www.microsoft.com/fasttrack)合作，以開始服務。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>步驟 7. 部署Teams和語音的語音

這也是與更廣泛的專案關係人Teams一起開始規劃會議與雲端語音功能[的時候](./cloud-voice-landing-page.md)。