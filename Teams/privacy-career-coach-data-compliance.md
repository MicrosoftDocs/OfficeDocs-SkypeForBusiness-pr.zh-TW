---
title: 職涯教練資料和合規性資訊
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ''
search.appverid: MET150
f1keywords: ''
description: 瞭解教育用教育版或教育版職涯教練Microsoft所採取的隱私權、合規性及許可權措施。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 1a21f3337ca9255572c25fd152f928c6444dc317
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242487"
---
# <a name="career-coach-data-and-compliance"></a>職涯教練資料與合規性

本文討論如何使用應用程式內功能及其他工具，協助您尋找並處理個人資料或個人資訊，以符合您的 GDPR 義務來回應資料主體要求 (DSR) 。 職涯教練會將資料廣泛分類為兩種類別：客戶內容和系統產生的記錄。 在 [職涯教練] 中，客戶內容包含使用者資料、租使用者設定資料和學生活動資料，而系統產生的記錄包括記錄檔，以及Microsoft產生的相關資料，以協助Microsoft為使用者提供企業服務。

## <a name="customer-content"></a>客戶內容

### <a name="user-data"></a>使用者資料

[職涯教練] 所收集的使用者資料包括目標和活動進度、研究欄位、學校年度、儲存的技能、已儲存的職涯、上傳的履歷表和成績單等設定檔資訊。

#### <a name="deleting-user-data"></a>刪除使用者資料

請依照下列步驟刪除 [職涯教練] 中的使用者資料：

1. 全域系統管理員必須 [開啟支援票證](https://edusupport.microsoft.com/support?product_id=career_coach)   ，明確說明 GDPR 刪除 DSR 的要求， (資料主體要求) 作業。 **無法限制刪除的資料集或時間範圍**。
2. 要求應清楚說明需要刪除的資料類型：
    1. 租使用者的所有使用者資料。
    2. 特定使用者的使用者資料。 請在刪除要求中包含使用者的 OID (物件識別碼) 。
3. 提交之後，支援票證會在一周後解決，以符合合規性的最低保留原則。 您可以在這段期間取消作業。
4. 一周後，[職涯教練] 團隊會刪除與租使用者相關的所有資料。 Microsoft支援人員會監視票證，並在 **30 天內** 完成刪除程式後通知您。

#### <a name="exporting-user-data"></a>匯出使用者資料

請依照下列步驟匯出 [職涯教練] 中的使用者資料：

1. [開啟職涯教練](https://aka.ms/Career_Coach_App)  並檢視您的設定檔。
1. 捲動至 [隱私權和安全性] 區段。
1. 選取 [下載] 以匯出您帳戶的所有客戶資料。

### <a name="tenant-configuration-data"></a>租使用者設定資料

租使用者資料包括已上傳或產生的資訊，做為 Career Coach 應用程式設定的一部分。 此資料包括租使用者的品牌資訊、標誌和學習圖示、課程目錄、LinkedIn學校 URL、研究清單欄位，以及在 Teams 系統管理中心 [職涯教練] 租使用者設定期間新增的所有其他資料。

#### <a name="deleting-tenant-configuration-data"></a>刪除租使用者設定資料

請依照下列步驟刪除 [職涯教練] 中的租使用者組態資料：

1. 全域系統管理員必須 [開啟支援票證](https://edusupport.microsoft.com/support?product_id=career_coach) ，清楚說明刪除租使用者組態資料的要求。 **無法限制刪除的資料集或時間範圍**。
1. 提交之後，支援票證會在一周後解決，以符合合規性的最低保留原則。 您可以在這段期間取消作業。
1. 一周後，[職涯教練] 團隊會刪除與租使用者相關的所有資料。 Microsoft支援人員會監視票證，並在 **30 天內** 完成刪除程式後通知您。

### <a name="student-activity-data"></a>學生活動資料

職涯教練會將學生活動資料儲存在同一個位置 [教育版 Insights](class-insights.md)。 匯總的資料會顯示在 [職涯教練] 學生活動深入解析體驗中。 擷取為啟用此功能的學生使用狀況資料會儲存並保留一年。

#### <a name="deleting-student-activity-data"></a>刪除學生活動資料

若要移除個人或租使用者的學生活動資料，請依照 [如何從教育版深入解析刪除使用者資料](class-insights.md#how-to-delete-user-data-from-education-insights)中的步驟進行。

## <a name="system-generated-logs"></a>系統產生的記錄

系統產生的記錄包括記錄檔，以及由Microsoft產生的相關資料，以協助Microsoft為使用者提供企業服務。 系統產生的記錄主要包含假名資料，例如唯一識別碼 (系統所產生的數位) 無法自行識別個別人員，但用來將企業服務提供給使用者。 此資料的範例包括：

- 產品與服務使用狀況資料，例如使用者活動記錄檔。
- 使用者搜尋要求和查詢資料。
- 產品和服務所產生的資料，是系統功能和使用者或其他系統互動的結果。

> [!NOTE]
> 系統產生的記錄檔不支援限制或修正資料的能力。 系統產生的記錄中的資料構成在Microsoft雲端和診斷資料內進行的事實動作，而對這類資料的修改會損害動作的歷程記錄，並增加詐騙和安全性風險。 職涯教練會保留系統產生的記錄 30 天。

### <a name="exporting-and-deleting-system-generated-logs"></a>匯出和刪除系統產生的記錄

租使用者全域系統管理員是貴組織中唯一可以存取與特定使用者使用Office 365服務和應用程式相關聯之系統產生的記錄的人員。 職涯教練符合存 [取及匯出由Office 365提供的系統產生的記錄的程式](/compliance/regulatory/gdpr-dsr-Office365#accessing-and-exporting-system-generated-logs)。

## <a name="more-information"></a>詳細資訊

- [開始使用 Microsoft Teams 的職涯教練](career-coach.md)
- [隱私權常見問題](https://privacy.microsoft.com/faq)
- [Microsoft產品和您的資料 - Microsoft隱私權]](https://privacy.microsoft.com/privacy-in-our-products)
- [Microsoft帳戶隱私權設定]](https://account.microsoft.com/account/privacy?refd=privacy.microsoft.com&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2F%3Frefd%3Dprivacy.microsoft.com&destrt=privacy-dashboard)
