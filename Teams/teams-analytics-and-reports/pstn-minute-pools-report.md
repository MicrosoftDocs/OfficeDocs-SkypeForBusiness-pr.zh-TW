---
title: Microsoft TeamsPSTN 分鐘數庫報告
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
description: 如何在系統管理中心Teams PSTN 分鐘Microsoft Teams報表來查看貴組織目前月份內使用的分鐘數。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d28e33ae820407ffe8c9561cae8c79863532417
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305987"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft TeamsPSTN 分鐘數庫報告

Microsoft Teams 系統管理中心中的 Teams PSTN 分鐘數庫報告，顯示您當月所耗用分鐘數，讓您概觀貴組織的音訊會議和通話活動。 您可以查看活動明細，包括通話使用授權、通話總分鐘數、已用分鐘數，以及授權使用量 。根據位置。

## <a name="view-the-pstn-minute-pools-report"></a>查看 PSTN 分鐘數庫報告

在系統管理中心的左側導Microsoft Teams，按一下 [分析&**報告**  >  **使用方式報告**。 在 [ **查看報表>** 選項卡的 [ **報表>** 下，選取 **[PSTN 分鐘數庫**，然後按一下 [ **執行報表**> 。

![系統管理中心Teams PSTN 分鐘數庫報表的螢幕擷取畫面](../media/teams-reports-pstn-minute-pools-with-callouts.png "系統管理中心Teams PSTN 分鐘Microsoft Teams包含編號圖說義的螢幕擷取畫面")

## <a name="interpret-the-report"></a>解譯報表

|標注 |描述  |
|--------|-------------|
|**1**   |每個報表都有產生日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**2**   |按一下授權 (功能) 以查看該功能的活動。 |
|**3**   |X 軸是國家/地區。 Y 軸是分鐘數。 <br>將游標停留在圖表上的橫條圖上，以查看該使用位置的活動。  |
|**4**   |您可以按一下圖例中的專案來篩選圖表上看到的專案。 例如，按一下 [ **未使用的**、 **國內** 使用者、沒有 **資料** 或 **國際資料，** 只用來查看每個使用者的資訊。 |
|**5**   |表格提供您根據功能及使用位置細分的分鐘數。 <ul><li>**國家/地區是** 使用位置。 </li><li>**功能描述** 是通話使用之授權的描述。  您可能會在此報告中看到的功能描述包括： <ul><li>國內及國際通話方案 (1200 分鐘) </li><li>國內及國際通話方案 (3000 分鐘) </li><li>國內及國際通話方案 (600 分鐘) </li></ul></li><br><li>**總分鐘** 數是一個月的總可用分鐘數。</li><li>**使用分鐘** 數是每個月使用的分鐘數</li> <li>**可用的分鐘** 數是該月的剩餘分鐘數。</li><li>**功能** 是通話所使用的授權。 您可能會看到下列授權：<ul><li>**MCOPSTN1** - 國內通話方案 (3000 分鐘美國 / 1200 分鐘的歐盟方案) </li><li>**MCOPSTN2** - 國際通話方案</li><li>**MCOPSTN5** - 國內通話方案 (120 分鐘的通話方案) </li><li>**MCOPSTN6** - 國內通話方案 (240 分鐘的通話方案) </li><li>**MCOMEETADD** - 音訊會議</li></ul></li> </ul> 若要在表格中查看您想要的資訊，請務必新增欄至資料表。|
|**6**   |選取 **編輯欄** 以新增或移除表格中的欄。|
|**7**   |選取 **全螢幕** 以全螢幕模式來查看報表。|

## <a name="related-topics"></a>相關主題

- [Teams分析與報告](teams-reporting-reference.md)
