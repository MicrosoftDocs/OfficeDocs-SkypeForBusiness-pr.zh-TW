---
title: Microsoft 團隊 PSTN 分鐘池報告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: 如何使用 Microsoft 團隊系統管理中心中的 [團隊 PSTN 分鐘數] 報告，以查看您在當月期間在貴組織內消耗的分鐘數。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8df0c1201f963a1c00742532f80089b523ca79aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809343"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft 團隊 PSTN 分鐘池報告

Microsoft [小組系統管理中心] 的 [團隊 PSTN 分鐘數] 報告可讓您在當月中，為您提供音訊會議和通話活動的概覽。 您可以查看活動的細目，包括通話所用的授權、可用的總分鐘數、使用的分鐘數，以及依位置的授權使用方式。

## <a name="view-the-pstn-minute-pools-report"></a>查看 PSTN 分鐘池報告

在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**分析] & 報告**  >  **使用方式報告**。 在 [ **查看報表** ] 索引標籤的 [ **報表**] 底下，選取 [ **PSTN minute pool**]，然後按一下 [ **執行報表**]。

![系統管理中心 [團隊 PSTN 分鐘數] 報表的螢幕擷取畫面](../media/teams-reports-pstn-minute-pools-with-callouts.png "[Microsoft 團隊管理中心] 中的 [團隊 PSTN 分鐘數] 報表的螢幕擷取畫面，其中包含編號標注")

## <a name="interpret-the-report"></a>解讀報表

|圖說文字 |描述  |
|--------|-------------|
|**1**   |每個報告都有產生的日期。 報告通常會反映來自啟用時間的24到48小時延遲時間。 |
|**2**   |按一下 (授權) 的功能，以查看該功能的活動。 |
|**3**   |X 軸是 [國家] 或 [地區]。 Y 軸是分鐘數。 <br>將游標暫留在圖表上的橫條圖上，即可查看該使用位置的活動。  |
|**4**   |您可以按一下圖例中的專案，篩選您在圖表上看到的內容。 例如，按一下 [**未使用** 的、**國內的使用者**、不 **使用****資料**] 或 [國際]，只會看到與每個專案相關的資訊。 |
|**500**   |此表格提供依功能和使用位置來細分的分鐘數。 <ul><li>[**國家或地區**] 是使用位置。 </li><li>[**功能描述**] 是通話使用之授權的描述。  您可能會在此報告中看到的功能描述包括： <ul><li>國內和國際通話方案 (1200 國內分鐘) </li><li>國內和國際通話方案 (3000 國內分鐘) </li><li>國內和國際通話方案 (600 國際通話時間) </li></ul></li><br><li>[**總分鐘** 數] 是指月份中可用的總分鐘數。</li><li>**使用的分鐘** 數是每個月使用的分鐘數</li> <li>[**可用分鐘** 數] 是月份剩餘的分鐘數。</li><li>**功能** 是通話使用的授權。 您可能會看到的授權包括：<ul><li>**MCOPSTNPP** -通訊點數</li><li>**MCOPSTN1** -國內通話方案 (3000 分美元/1200 分歐盟方案) </li><li>**MCOPSTN2** -國際通話方案</li><li>**MCOPSTN5** -國內通話方案 (120 最小通話方案) </li><li>**MCOPSTN6** -國內通話方案 (240 最小通話方案) </li><li>**MCOMEETADD** -音訊會議</li><li>**MCOMEETACPEA** -每分鐘付款音訊會議</li></ul></li> </ul> 若要在表格中查看您想要的資訊，請務必將資料行新增至資料表。|
|**6**   |選取 [ **編輯欄** ] 以新增或移除表格中的欄。|
|**utf-7**   |選取 [ **全螢幕** ]，以全螢幕模式查看報告。|

## <a name="related-topics"></a>相關主題

- [團隊分析和報告](teams-reporting-reference.md)