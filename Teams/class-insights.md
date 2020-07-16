---
title: 適用於 IT 系統管理員的 Microsoft Teams [課堂分析]
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams [課堂分析] 的 IT系統管理員指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbf535c73bd1b23b22f368707bcbabe44c0cdf2d
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126187"
---
# <a name="class-insights-for-it-admins"></a>適用於 IT 系統管理員的 [課堂分析]

透過 Microsoft Teams [課堂分析]，授課者可以存取學生參與度和效能的分析資料。 [課堂分析] 以 Teams 收集學生活動，例如成績、作業、交流活動和檔案共同作業，以建立分析儀表板展示可操作的資料可觀化。

[課堂分析] 是在 Office 365 教育版 Sku A1、A3 和 A5 中使用。

> [!NOTE]
> 授課者，於[此處](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc) 瞭解如何使用 [課堂分析]。

## <a name="permissions"></a>權限

授課者可以透過瀏覽至 Teams 應用程式列中的 [應用程式] 並搜尋 [深入分析]，以將 [課堂分析] 添加到課堂團隊的公開頻道中。

- 授課者是由教職員授權所定義。 授課者必須擁有教職員授權，並成為課程小組擁有者，以新增和查看 [深入分析] 索引標籤。
- 學生是由其授權所識別，而 **無權存取 [深入分析] 索引標籤** （即使他們是小組的擁有者）。
- 該索引標籤會反映非擁有者的課程小組中所有人的活動（包括非小組擁有者的教師）。

## <a name="compliance"></a>合規性

[課堂分析]具備業界一流的合規性承諾，並被分類為 Office 365 合規性架構中的第一層服務。

> [!NOTE]
> 若要深入瞭解 Microsoft 如何保護您的資料，請造訪 [Microsoft 信任中心](https://www.microsoft.com/trust-center)。

## <a name="privacy"></a>隱私權

透過 [課堂分析] 收集和顯示的資訊，符合90多個監管和行業標準，包括 GDPR 和針對學生與兒童的家庭教育權利和隱私法案 (FERPA)，以及其他類似的，以隱私為導向的法規。 對於 IT系統管理員來說，重要的是明白在以每個學生為基礎所收集的資訊僅限用於課堂環境，以便教育者決定課堂行為。 收集這些資訊是為了提供有意義的學習活動，例如班級會議出席者、發布訊息、回應同學的貼文、寫作業、編輯檔案等等。 比如，我們不會顯示私人交談或 Teams 登入的資訊。

我們的目標是協助授課者瞭解參與情況，並聚焦在學生學習上。 雖然這些課程活動可以集中到學生層級的動作上，但 Microsoft Teams 對這些動作沒有意見評判，而且也不會根據準則對個別學生有身分判斷識別。 [課堂分析] 中的資訊會通知授課者，例如，學生在某段期間內未處於使用中的狀態，或已于上周完成所有作業。 授課者則得負責與學生和學生的家長或監護人進行互動，以找出任何有使用或沒有使用的基本原因。

## <a name="data-collection"></a>資料收集

當 [教育分析] 為租使用者開啟時，我們會為 [課堂分析] 收集資料。 資料會從 Teams 活動收集而來，以呈現可用於教學和學習的可操作資訊。

根據預設，[教育分析] **開啟**了。

目前，這項資料從課程小組中的學生和教師活動的以下方面提取的：

|Teams 元件  |收集的資料  |
|-----------------|------------------------|------------------------|
|作業 |打開、成交和評分作業。 |
|頻道參與 |造訪頻道、建立貼文、回復貼文並按讚（不包括聊天內容）。 |
|檔案 |上傳、下載、存取、修改、批註及共用檔案（不包括檔案內容）。 |
|會議 |出席（不含會議內容）。 |

## <a name="data-location"></a>資料位置

基於歐洲的租使用者的 [課堂分析] 資料會存在歐洲的伺服器上。 美國租使用者的資料儲存在美國的伺服器上。 如果您使用 [課堂分析]，而您的 Office 365 租使用者位於歐洲或美國以外的地區，您的資料將會儲存在適當的地理區域。

## <a name="performance-and-reliability"></a>效能和可靠性

[課堂分析]旨在處理從 Teams 活動收集的大量資料，並提供最佳效能和可靠性。

無論是否有安裝 Teams 的 [深入分析] 索引標籤，資料收集流程都會在不同的伺服器上進行。 [課堂分析] 索引標籤不會影響授課者和學生使用其餘 Teams 功能的應用程式效能或網路頻寬。

> [!TIP]
> 若要瞭解如何在頻寬不足時使用 [教育用 Teams]，請參閱 [這裡](edu-remote-low-bandwidth.md)。

## <a name="how-to-delete-your-data"></a>如何刪除資料

[教育] 服務會儲存課程小組上下文中的學生和教師動作。 這項資料視為是混合資料集，因此，一旦從組織中刪除了學生或授課者的使用者帳戶，就不會自動從服務中刪除了。

> [!NOTE]
> 刪除資料會對 [深入分析] 分析班級團隊參與度的能力產生負面影響。

- 在[[這裡]](https://edusupport.microsoft.com/support)開啟支援票證。 支援票證必須明確聲明對 [GDPR Delete DSR] 操作的請求，並包含要刪除的使用者物件識別碼。 無法限制刪除的資料集或時間窗口。
- 一旦歸檔，支援票證就會在佇列中等候一周，以符合合規性最低保留原則。 您可以在此期間取消該作業。
- 一周之後，[教育分析] 小組會採取行動，以確保與該使用者識別碼相關的所有資料都已從服務中刪除。 Microsoft 支援服務會監視 ICM 票證，並會在刪除程序完成後28天內通知您。

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>使用學校資料同步處理 (SDS) 關閉和開啟 [深入分析]。

學校資料同步處理 (SDS) 會協助自動化匯入和同步處理學生資訊系統 (SIS) 資料與 Office 365 的程序。

使用 [課堂分析] 不需要使用 SDS。 不過，您可以隨時通過關閉 SDS 管理中心 **[設定]** > **[管理教育分析]** 下的切換選項來退出 [教育分析]。

:::image type="content" source="media/class-insights-on-off.png" alt-text="啟用或停用 [課堂分析] 的開關。":::

根據預設，會開啟 [教育分析] 和 [課堂分析]。 當您退出 [分析] 時，我們會刪除為 [課堂分析] 索引標籤收集的所有資料。重新開啟 [分析]，我們會從重新啟用的時間開始收集資料。

深入瞭解：[適用於授課者的 [課堂分析]](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)
