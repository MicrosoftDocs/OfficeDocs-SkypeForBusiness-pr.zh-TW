---
title: 開始使用適用于醫療保健組織的團隊
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 開始使用適用于醫療保健組織的團隊
ms.openlocfilehash: e4720b6c03c44128ba90db5fb1ade066360e19bf
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183687"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>開始使用適用于醫療保健組織的團隊

Microsoft 團隊提供許多適用于醫院和其他醫療保健組織的功能。 團隊功能正處於開發階段, 可協助醫院進行下列作業:

- 護理協調與共同作業
- 安全訊息
- Telehealth
- 電子醫療保健記錄 (EHR) 整合 
- 第一線員工 Worker 系統整合 

這與 Microsoft 團隊的基本功能 (例如會議/通話和訊息傳遞) 除了在外。 

## <a name="care-coordination---microsoft-teams-patients-app"></a>護理協調-Microsoft 團隊患者 app

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft 團隊現在有一個專門針對醫療保健組織的護理協調解決方案, 可協助他們提供最佳的患者治療。 Crux 的 [護理協調] 解決方案是「Microsoft 團隊患者 app」, 它是第一個與電子醫療記錄 (EHR) 系統整合的第一個參與方索引標籤 app[](https://www.hl7.org/fhir/), 可讓您有價值地使用。在內容中將醫療資訊納入 Microsoft 小組, 以實現臨床共同作業及通訊。  

護理協調方案可以與主要獨立軟體廠商 (Isv) 進行介面, 讓您可以使用現有的健康資料標準 (例如 HL7v2 和 FHIR), 將患者 app 連線至您的 EHR 系統。 具備下列業界領袖的 Microsoft 合作夥伴, 可與團隊建立電子健康情況記錄整合:

- Datica (透過其[CMI](https://datica.com/compliant-managed-integration/)產品)
- Infor Cloverleaf (透過[INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (透過[R ^ FHIR 伺服器](https://www.redoxengine.com/fhir/))
- Dapasoft (透過[Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

嘗試針對醫療保健提供者組織實施 Microsoft 團隊的 EHR 整合與互通性合作夥伴, 必須為患者 app 提供與醫療保健供應商組織 EHR 系統的安全且驗證的連線。 這可讓相關患者記錄的單向 (唯讀) 流程進入患者 app。 患者 app 可瞭解 FHIR 格式, 因此合作夥伴也負責將匯總資料從各種其他格式 (例如 HL7v2 等) 轉換成 FHIR DSTU2 或 STU3。

<br>

![圖示醒目提示護理協調與共同作業](../../media/ehr-1.png)

<br>

患者 app 整合了電子醫療記錄 (EHR) 系統, 並可讓護理提供者在小組安全的平臺中即時溝通患者治療。 患者 app 是護理協調區域中的第一項主要投資, 目的是解決下列難題:

- 在工作中保持不太高效, 且透過患者體驗進行重要溝通
- 產生管理負擔的各自為政資訊
- 使用複雜及零散共同作業工具的臨床醫師中的不滿
- 低效率的人員間護理協調, 可能會燒壞太昂貴的臨床時間

Microsoft 團隊可讓醫生、臨床醫師、護士及其他員工高效地進行共同作業:

- 成為可在 Office 檔上運作及共同合作的單一虛擬化小組的一部分
- 在其他患者需要注意的持續交談
- 使用頻道搭配索引標籤來組織其工作, 並提供可讓他們釘選資訊來源之索引標籤的其他說明
- 將頻道會議與團隊的威力、影片、螢幕共用、錄製和工具功能配合使用, 以管理每日會議
- 使用患者 app 來彙整必須監視的高風險患者清單, 並從 EHR 系統中拉回其最新詳細資料。 患者 app 本身會將下列功能新增至 Microsoft 團隊:

    - 能夠在單一頻道中建立多個患者清單。
    - 透過可設定的欄來查看和排序顯示的患者資訊的功能。
    - 透過小組範本自動進行應用程式的功能。
    - 可在 iOS 版和 Android 版的團隊 App 中使用, 可在適用于 iOS 和 Android 的小組應用程式中, 使用 Microsoft 團隊網頁與桌面用戶端。
    - 透過分析一致性語句來支援 FHIR DSTU2 和 STU3 版本。
    - 針對其使用者介面上的所有視圖和搜尋動作的審核記錄, 以保護每個 HIPAA 指引中的 PHI。

患者 app 是在小組擴充性平臺上建立, 並利用 [定位點架構] 在頻道中顯示豐富的患者內容。 若要深入瞭解其他團隊 app 和平臺本身, 請參閱[Microsoft 團隊相關應用程式](/microsoftteams/platform/concepts/apps/apps-overview)。  

> [!NOTE]
> 患者 app 是私人預覽, 且 FHIR 介面在 Beta 版中。 已發行的版本不應該是向後相容的。

![桌面和行動裝置上患者 app 的螢幕擷取畫面](../../media/ehr-2.png)

如需詳細資訊, 請參閱將[電子醫療保健記錄整合至 Microsoft 團隊](patients-app.md)。

## <a name="templates"></a>模版

我們已開發新的範本來建立小組, 以套用至醫院設定。 如此一來, 您就能更輕鬆地建立可讓醫療保健工人在不同部門或 wards 中與患者共同合作的小組。 請參閱[開始使用醫療保健組織的團隊範本](healthcare-templates.md)。 團隊可以針對內部部門 (例如心臟病科) 或 [護理 wards] 或 [開發中的其他範本] 進行啟動。

## <a name="secure-messaging"></a>安全訊息

安全訊息支援在護理小組中共同作業, 包括幾個新功能:

- 郵件寄件者可以為郵件設定特殊的優先順序, 所以收件者會反復收到通知, 直到他們閱讀郵件為止。
- 郵件寄件者可以要求讀信回條, 當郵件收件者閱讀郵件時, 就會收到通知。


總之, 這些功能可讓您更快速地注意到緊急訊息, 並確信郵件已被接收和讀取。 使用這些功能的新的護理團隊可以在每個患者上建立。 這些功能都是以原則為基礎, 而且可以指派給個人或整個團隊。

如需進一步的詳細資料, 請參閱[開始使用醫療保健組織的安全訊息原則](messaging-policies-hc.md)。

此外, 與安全訊息相關的功能, 也是由醫療保健組織聯盟的其他租使用者, 允許更豐富的租使用者通訊。 (請參閱[Microsoft 團隊中的 [管理外部存取 (同盟)](../../manage-external-access.md)])。

## <a name="firstline-worker-integration"></a>第一線員工工作人員整合

Microsoft 團隊會與第一線員工工作人員整合, 這可以用來共同調整倒班人員的功能。

 請參閱下列文章:

- [將 Microsoft StaffHub 小組移至 Microsoft 團隊中的倒班](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [在 Microsoft 團隊中為您的組織管理倒班應用程式](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
