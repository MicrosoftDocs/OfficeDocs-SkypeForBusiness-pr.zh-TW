---
title: Microsoft Teams EHR 連接器虛擬約會報告
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 瞭解如何在 Microsoft Teams 系統管理中心使用 Teams EHR 連接器虛擬約會報告，以取得貴組織中 EHR 整合式虛擬約會使用方式的概觀。
ms.openlocfilehash: 0e78b89c934eac101b863bd7b5ba9957939f994b
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883536"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Microsoft Teams EHR 連接器虛擬約會報告

Microsoft Teams 系統管理中心的 Microsoft Teams 電子健康情況記錄 (EHR) 連接器虛擬約會報告，可讓您快速輕鬆地檢視組織中的 Teams EHR 整合式虛擬約會使用量。

若要檢視報表，您必須是全域系統管理員、Teams 系統管理員、全域助讀程式或報表讀者。

## <a name="view-the-report"></a>檢視報表

在 Teams 系統管理中心有兩種方式可以存取和檢視報告。

- 透過儀表板中的[EHR 連接器使用卡](#the-ehr-connector-usage-card)
- 直接透過在分析中選擇 [**EHR 連接器虛擬約會**](#the-teams-ehr-connector-virtual-appointments-report)**&報告**  >  **使用方式報告**

### <a name="the-ehr-connector-usage-card"></a>EHR 連接器使用卡

在 Microsoft Teams 系統管理中心的左側導覽畫面中，選擇 **[儀表板**]，然後移至 **[EHR 連接器虛擬約會]** 卡片。

您可以在這裡快速檢視 Teams EHR 整合式虛擬約會活動，視您擁有的授權) 而定，包括完成的約會、剩餘的配置，以及是否已超過每月 (限制。

:::image type="content" source="../../media/ehr-connector-report-card.png" alt-text="Teams 系統管理中心儀表板中 EHR 連接器使用卡片的螢幕擷取畫面。" lightbox="../../media/ehr-connector-report-card.png":::

選擇 **[檢視詳細資料** ] 以查看報表詳細資料。 若要購買更多授權，請選擇 **[購買更多]**。

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Teams EHR 連接器虛擬約會報告

1. 在 Teams 系統管理中心的左側導覽中，移至 **分析&報告**  >  **使用方式報告**。
1. 在 [ **檢視報表]** 索引標籤上，選擇 **[EHR 連接器虛擬約會** ] 和 [日期範圍]。 然後，選取 [ **執行報表]**。

    :::image type="content" source="../../media/ehr-connector-report.png" alt-text="Teams 系統管理中心中 Teams EHR 連接器虛擬約會報告的螢幕擷取畫面。" lightbox="../../media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |每個報告都會顯示報告的產生日期以及您選擇的日期範圍。|
|**2**   |表格提供您在所選日期範圍內所進行的每個約會的詳細資訊。 請記住，您不會看到教職員成員或病患未加入的約會專案。 <ul><li>**開始時間 (UTC)** 是教職員成員和參與者同時參與約會的日期和時間。  </li> <li>**持續時間** 是指開始時間與最後一個人離開約會的時間差異。</li> <li>**主要** 是會議召集人的名稱。 <li>**主要的電子郵件** 是會議召集人的電子郵件地址。</li> <li> **部門** 是約會的部門資訊。 如果資訊未正確顯示，請連絡您的 EHR 支援小組。 若要與 Epic 整合，請確定 ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` 是提供者整合記錄的一部分。 </li></li> <li>**語音應答** 是約會中教職員成員和參與者的總數。</li> <li>**在限制內** 表示約會是否在配置限制內。 </li> </ul> |
|**3**   |您可以將報表匯出為 CSV 檔案以進行離線分析。 選 **取 [匯出至 Excel** ] 以下載報表。 |
|**4**   |選 **取 [篩選** ] 以篩選報表詳細資料檢視。 |
|**5**   |選取 **[全螢幕** ] 以全螢幕模式檢視報表。 |
|**6**   |選取 **[編輯欄]** 以新增或移除表格中的欄 |

> [!NOTE]
> 如需 Teams EHR 整合式虛擬約會的詳細分析，請參閱 [虛擬造訪使用方式報告](../../teams-analytics-and-reports/virtual-visits-usage-report.md)。 透過虛擬造訪使用方式報告，您可以檢視主要指派，例如總約會、大廳等候時間、約會持續時間，以及不顯示。 使用此資訊以深入瞭解使用趨勢，協助您優化虛擬約會，以提供更好的商務成果。

## <a name="related-articles"></a>相關文章

- [使用 Teams 的虛擬約會 - 整合至 Cerner EHR](ehr-admin-cerner.md)
- [使用 Teams 進行虛擬約會 - 整合至 EHR](ehr-admin.md) 
