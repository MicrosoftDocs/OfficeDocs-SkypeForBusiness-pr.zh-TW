---
title: 規劃 Microsoft 365 政府-GCC 部署-Microsoft 團隊
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 適用于 IT 專業人員的指導方針, 可在處理受美國政府法規制約之資料的實體中, 驅動 Office 365 部署
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: baeb60f00602052d28a85337387cb0024979360e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237661"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>規劃 Microsoft 365 政府版-GCC 部署

本指導方針適用于在美國聯邦、州、當地、tribal 或 territorial 政府機構中的 Office 365 部署, 或其他處理受限於政府法規與需求之資料的其他實體, 這些專業人員使用 Microsoft365政府-GCC 適用于符合這些需求。

> [!NOTE]
> 如果您的組織已符合 Microsoft 365 政府版 GCC 資格要求, 且適用于並已接受程式, 您可以跳過步驟1和 2, 然後直接移至步驟3。 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>步驟1。 判斷貴組織是否需要 Microsoft 365 政府-GCC 並符合資格需求。 

Microsoft 365 政府版-GCC 環境提供對雲端服務 (包括 FedRAMP 適中版, 以及刑事審判與聯邦稅務資訊系統的需求 (CJI 與 FTI 資料類型) 的美國政府需求的規範。

除了享受 Office 365 的功能和功能之外, 組織還能利用 Microsoft 365 政府-GCC 所特有的下列功能帶來的好處:

-   貴組織的客戶內容會從 Microsoft 的商業版 Office 365 服務中, 以邏輯方式與客戶內容隔離。
-   貴組織的客戶內容會儲存在美國。
-   您組織的客戶內容的存取權受到限制, 無法篩選 Microsoft 人員。
-   Microsoft 365 政府-GCC 符合美國公有事業部門客戶所需的認證與 accreditations。

您可以在[Office 365 政府版方案](https://products.office.com/government/compare-office-365-government-plans)(包括[資格需求](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)) 中, 找到適用于美國政府客戶的 Microsoft 365 政府版產品的詳細資訊。

[Office 365 美國政府服務描述](https://technet.microsoft.com/library/mt774581.aspx)說明平臺的優點, 這些好處是圍繞在美國的會議規範需求中心。

> [!Tip]
> 您可能會想要將服務描述中的資訊表格傳輸至 Excel 活頁簿, 並新增兩欄:**與我的組織相關**, 並**符合組織 y/n 的需求**。 然後, 您可以與同事核對此清單, 以確認此服務符合貴組織的需求。

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定 Microsoft 365 政府版-GCC 是否適合您的組織。</li><li>確認您的組織符合資格需求。</li></ul> |

> [!Note]
> Microsoft 365 政府版-GCC 僅適用于美國。 非美國政府客戶可以從許多[Office 365 政府方案](https://products.office.com/en/government/compare-office-365-government-plans)中選擇。


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>步驟2。 適用于 Microsoft 365 政府-GCC

如果決定此服務適合您的組織, 請在[這裡開始申請此服務](https://products.office.com/government/eligibility-validation)的程式。

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>步驟3。 瞭解 Microsoft 365 政府-GCC 預設安全性設定。

我們建議您在修改您的系統[管理員和安全設定](enable-features-office-365.md)之前, 先仔細檢查, 並考慮對規範的影響, 然後再變更預設的安全性設定。

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定是否要修改任何預設的 Microsoft 365 政府版-GCC 安全設定, 並解決以首先瞭解您所做的任何變更對您造成的影響。</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>步驟4。 瞭解哪些功能目前無法使用或預設為停用。 

為了滿足政府雲端客戶的需求, Microsoft 365 政府版與企業版方案之間有一些差異。 請參閱下表, 查看有哪些功能可供使用。

|                             | 功能                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| 基本 | Id | 離線 |
| | 平臺 | 離線 |
| | 整合的目前狀態 (商務用 Skype 和小組已統一) | 離線 |
| 操作 | 複製 | 離線 |
|  | 我的活動 | 離線 |
| 交流 | 交談 | 離線 |
| | Files | 離線 |
| | 組織結構 | 離線 |
| | 操作 | 離線 |
| | 互通性 (1:1 團隊-商務用 Skype 聊天) | 離線 |
| 協同 | 頻道訊息 | 離線 |
| | 頻道檔案 | 離線 |
| | [OneNote] 索引標籤 | 在政府積壓工作 |
| | 透過電子郵件傳送頻道 | 無法使用 |
| | 新增成員 | 離線 |
| | 來賓存取 | 離線 |
| 舉行 | 排程會議 | 離線 |
| | 加入會議 | 離線 |
| | VoIP 會議 | 離線 |
| | 桌面共用 | 離線 |
| | 在共用中提供控制權並加以控制 | 離線 |
| | 從會議室連接 | 離線 |
| | 匿名加入 | 離線 |
| | 雲端錄製 | 在政府積壓工作 |
| | 會議記事 | 離線 |
| | 廣播會議 | 在政府積壓工作 |
| | 同盟會議 | 離線 |
| | Surface Hub 支援 | 無法使用 |
| 撥 | 聯絡 | 離線 |
| | 歷程記錄 | 離線 |
| | 語音信箱 | 離線 |
| | VoIP 通話 | 離線 |
| | 商務用 Skype-小組通話 | 離線 |
| | 通話方案 | 離線 |
| | 音訊會議 (透過允許會議參與者透過 PSTN 加入) | 離線 |
| | Microsoft Phone 系統直向路由 | 離線 |
| | PSTN 呼叫者的大廳 | 離線 |
| | 通話佇列 | 離線 |
| | 老闆及代理人支援 | 離線 |
| | 顧問式與安全轉接 | 離線 |
| | 請勿打擾突破 | 離線 |
| | 區別性鈴聲 | 離線 |
| | 1:1 至團隊、商務用 Skype 和 PSTN 參與者的群組通話升級 | 離線 |
| | [轉寄至] 群組 | 離線 |
| | 轉接至 PSTN 通話 | 離線 |
| | 緊急電話撥打電話方案 | 離線 |
| | 現有的認證 SIP 手機支援 | 離線 |
| | USB HID | 離線 |
| | 通話和會議的 eDiscovery | 離線 |
| | 組織自動語音應答 | 離線 |
| | Skype 消費者-小組通話支援 | 離線 |
| Files | 近 | 離線 |
| | Microsoft 團隊 | 離線 |
| 存放 | App Store | 在政府積壓工作 |
| 檢索 | 錯誤資訊 | 離線 |
| | 連絡人 | 離線 |
| | Files | 離線 |
| | 斜杠命令 | 離線 |
| 從屬 | 合規性內容搜尋 | 離線 |
| | 留成 | 離線 |
| | 審核記錄搜尋 | 離線 |
| | 法律封存 | 離線 |
| | eDiscovery | 離線 |

> [!Note]

> 當所有其他工作負載在 GCC 雲端中都是完整的, 當所有其他的整合作業完成後, 就能在小組中使用它們。


|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>決定 [小組] 功能集是否符合貴組織的需求。</li></ul> |

## <a name="step-5-plan-for-governance"></a>步驟5。 規劃管理

決定您的管理需求, 以及如何符合您的需求。 如需詳細資訊, 請參閱[小組中的管理方案](plan-teams-governance.md)。

|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>按照[規劃團隊中的管轄](plan-teams-governance.md)原則, 決定並記錄您的管理需求。</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>步驟6。 部署團隊以進行共同作業

在您 onboarded 至 Microsoft 365 政府-GCC 之後, 您可以遵循使用[FastTrack](https://www.microsoft.com/fasttrack)和您所選的合作夥伴的標準部署做法來實現服務的板載。

當您準備好時, 請部署團隊以[透過團隊和頻道在您的組織內](teams-overview.md)共同作業。 請務必與您的採納及變更管理團隊或團隊擁護者接洽。

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>步驟7。 為會議和語音部署團隊

這也是將小組與較大的風險承擔者群組搭配使用以開始規劃會議和[雲端語音功能](cloud-voice-deployment.md)的絕佳時機。

