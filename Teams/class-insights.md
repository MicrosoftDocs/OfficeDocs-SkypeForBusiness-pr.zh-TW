---
title: Teams 教育版深入解析的IT 系統管理員指南
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版深入解析的 IT 系統管理員指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b63ea1a1a09a55d9a51fb2a110c024960f23f6f4
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803521"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a>Teams 教育版深入解析的IT 系統管理員指南

透過 Microsoft Teams 教育版深入解析，教育者和領導者可以存取有關數位參與、作業工作負載、成績、通訊等的分析資料。 深入解析是由道德原則所驅動，將教育者和學生擺在第一位，符合隱私權標準，並確保您的機構持續遵循法規。

深入解析會在 Office 365 教育版 SKU A1、A3 和 A5 中使用。

> [!NOTE]
> 教育者，請於此瞭解如何使用 [深入解析]： [Microsoft Teams 深入解析的教育者指南](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181)。

## <a name="use-insights"></a>使用 [深入解析]

### <a name="user-types"></a>使用者類型
- **學生** 是由其授權所識別，且  _無權存取_ [深入分析] 索引標籤 (即使他們是團隊的擁有者)。 
- **教育者** 由教職員授權所識別。 教育者必須擁有教職員授權，並成為課程小組擁有者，以新增和查看 [深入分析] 索引標籤所顯示的資料。 
- **領導者** 也由教職員授權所識別，但在某些狀況下，需取得 IT 全域系統管理員的明確授與的權限，才能檢視 [深入解析] 應用程式中的報告。
- 來賓帳戶 _不具備_ [深入解析] 存取權。

### <a name="entry-points"></a>進入點
教育者和領導者有不同的進入點，可讓他們探索並使用深入解析。

**教育者** 可以使用這兩個進入點：
- [索引標籤](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181) - 上方瀏覽功能表新增的索引標籤提供了適用於他們所擁有的每個班級的索引標籤。 [深入解析] 將會從班級團隊內的所有通道呈現活動資料，但只能新增為公用頻道的索引標籤。 該索引標籤會反映非擁有者的班級團隊中所有人的活動 (包括非團隊擁有者的教師)。
- [個人應用程式](https://support.microsoft.com/article/747fd8d9-00b0-43e6-bacc-a1bf030b1867) - 可從左側 Teams 應用程式列取得的所有作用中課程概覽。

**領導者** 可以使用 [深入解析] 作為 [個人應用程式](https://support.microsoft.com/article/8738d1b1-4e1c-49bd-9e8d-b5292474c347)。

### <a name="manage-setup-policy"></a>管理設定原則
如果您是系統管理員，您可以使用 [應用程式設定原則](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies)，在教育者和領導人啟動 Teams 時，根據預設為您的教職員安裝 [深入解析]。
使用該原則，您可以自訂 Teams 以強調 [深入解析]，並將它釘選在應用程式列中。

> [!TIP]
> 如需適用於教育界的 Teams 原則和原則套件的資訊，請參閱 [[適用於教育界的 Teams 原則和原則套件]](https://docs.microsoft.com/microsoftteams/policy-packages-edu)。



## <a name="compliance"></a>合規性

深入解析具備產業領先的合規性承諾，並被分類為 Office 365 合規性架構內的 C 層服務。

> [!NOTE]
> 若要深入瞭解 Microsoft 如何保護您的資料，請造訪 [Microsoft 信任中心](https://www.microsoft.com/trust-center)。

## <a name="privacy"></a>隱私權

透過深入解析收集和顯示的資訊，符合 90 多個監管和產業標準，其中包括 GDPR 和針對學生與兒童的「家庭教育權和隱私權法案 (FERPA)」，以及其他類似的、以隱私權為導向法規。 IT 系統管理員務必知道，以每個學生為基礎所收集的資訊僅限用於班級環境，以允許授課者和領導者判斷學生行為。 收集這些資訊是為了提供有意義的學習活動，例如班級會議出席者、發布訊息、回應同學的貼文、寫作業、編輯檔案等等。 比如，我們不會顯示私人交談或 Teams 登入的資訊。

我們的目標是協助授課者瞭解參與情況，並聚焦在學生學習上。 雖然這些課程活動可以集中到學生層級的動作上，但 Microsoft Teams 對這些動作沒有意見評判，而且也不會根據準則對個別學生有身分判斷識別。 深入解析中的資訊會通知授課者，例如，某個學生在某段期間內未在工具中處於使用中狀態，或他們已準時完成上週的所有作業。 授課者則得負責與學生和學生的家長或監護人進行互動，以找出任何有使用或沒有使用的基本原因。

## <a name="data-collection"></a>資料收集

- 為租用戶開啟「教育版分析」時，我們會收集「深入解析」的資料。 資料會從 Teams 活動收集而來，以呈現可用於教學和學習的可操作資訊。
- [深入解析] _不會_ 收集來賓資料。
- 根據預設，[教育分析] **開啟** 了。

目前，這項資料從課程小組中的學生和教師活動的以下方面提取的：

|Teams 元件  |收集的資料  |
|-----------------|------------------------|------------------------|
|作業 |打開、成交和評分作業。 |
|頻道參與 |造訪頻道、建立貼文、回復貼文並按讚（不包括聊天內容）。 |
|檔案 |上傳、下載、存取、修改、批註及共用檔案（不包括檔案內容）。 |
|會議 |出席（不含會議內容）。 |

## <a name="data-location"></a>資料位置

以歐洲租用戶為基礎的深入解析資料，會儲存在歐洲的伺服器上。 以美國租用戶為基礎的資料，則會儲存在美國的伺服器上。 如果您使用深入解析，而您的 Office 365 租用戶位於歐洲或美國以外的地區，則您的資料會儲存在適當的地理區域。

## <a name="performance-and-reliability"></a>效能和可靠性

深入解析的設計目的在於處理從 Teams 活動收集的大量資料，並具有最佳效能和可靠性。

無論 Teams 是否有安裝 [深入解析] 索引標籤，資料收集程序都會在不同的伺服器上進行。 [深入解析] 索引標籤或個人應用程式不會影響授課者和學生使用其餘 Teams 功能的應用程式效能或網路頻寬。

> [!TIP]
> 如需在頻寬不足時使用 Teams 教育版的資訊，請參閱 [[Teams 教育版在低頻寬情況下的說明]](edu-remote-low-bandwidth.md)。

## <a name="how-to-delete-your-data"></a>如何刪除資料

[教育] 服務會儲存課程小組上下文中的學生和教師動作。 這項資料視為是混合資料集，因此，一旦從組織中刪除了學生或授課者的使用者帳戶，就不會自動從服務中刪除了。

> [!NOTE]
> 刪除資料會對 [深入分析] 分析班級團隊參與度的能力產生負面影響。

- 在 [https://edusupport.microsoft.com/support](https://edusupport.microsoft.com/support) 開啟支員票證。 支援票證必須明確聲明對 [GDPR Delete DSR] 操作的請求，並包含要刪除的使用者物件識別碼。 無法限制刪除的資料集或時間窗口。
- 一旦歸檔，支援票證就會在佇列中等候一周，以符合合規性最低保留原則。 您可以在此期間取消該作業。
- 一周之後，[教育分析] 小組會採取行動，以確保與該使用者識別碼相關的所有資料都已從服務中刪除。 Microsoft 支援服務會監視 ICM 票證，並會在刪除程序完成後28天內通知您。

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>使用學校資料同步處理 (SDS) 關閉和開啟 [深入分析]。

學校資料同步處理 (SDS) 會協助自動化匯入和同步處理學生資訊系統 (SIS) 資料與 Office 365 的程序。

使用深入解析不需要使用 SDS。 不過，您可以隨時通過關閉 SDS 管理中心 **[設定]** > **[管理教育分析]** 下的切換選項來退出 [教育分析]。

:::image type="content" source="media/class-insights-on-off.png" alt-text="用來啟用或停用深入解析的切換。":::

預設會開啟「教育版分析」和「深入解析」。 當您選擇退出 [分析] 時，我們會刪除針對 [深入解析] 索引標籤收集的所有資料。重新開啟 [分析]，我們便會從重新啟用的時間開始收集資料。

## <a name="additional-resources"></a>其他資源
- [[深入解析] 的教育者指南](https://support.microsoft.com/office/27b56255-90c0-47aa-bac3-1c9f50157181)
