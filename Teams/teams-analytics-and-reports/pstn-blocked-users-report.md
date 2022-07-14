---
title: Microsoft Teams PSTN 封鎖使用者報告
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: 使用 Microsoft Teams 系統管理中心的 PSTN 封鎖使用者報告，概略瞭解貴組織的 Teams 使用者無法撥打 PSTN 電話。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d689d2696a20f51e232a581d45032d55da6deb6d
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794141"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams PSTN 封鎖使用者報告

Microsoft Teams 系統管理中心的 PSTN 封鎖使用者報告會顯示貴組織中禁止在 Teams 中撥打 PSTN 通話的使用者。 您可以檢視每個被封鎖使用者的詳細資訊，包括他們獲指派的電話號碼，以及他們遭到封鎖而無法撥打電話的原因。

## <a name="view-the-pstn-blocked-users-report"></a>檢視 PSTN 封鎖的使用者報告

在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[分析&報告**  >  **使用方式報告。** 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選取 **[PSTN 封鎖的使用者**]，然後按一下 [ **執行報表]**。

![系統管理中心中 PSTN 封鎖使用者報告的螢幕擷取畫面。](../media/teams-reports-pstn-blocked-users-with-callouts.png "Microsoft Teams 系統管理中心的 PSTN 封鎖使用者報告有編號圖說文字的螢幕擷取畫面")

## <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |每個報告都有產生報告的日期。 報告通常會反映啟用時間的 24 到 48 小時延遲。 |
|**2**   |X 軸是日期。 Y 軸是使用者數目。 <br>將游標停留在指定日期的點上，以查看該日期封鎖的使用者數目。 |
|**3**   |下表列出所有遭到封鎖而無法撥打 PSTN 通話的使用者。  它會顯示已指派電話系統或音訊會議的所有使用者，並提供您每個使用者的詳細資訊。 <ul><li>**顯示名稱** 是使用者的顯示名稱。 您可以按一下顯示名稱，移至 Microsoft Teams 系統管理中心的使用者設定頁面。 </li> <li>**手機** 是指派給使用者的號碼。</li> <li>**封鎖的原因** 就是使用者無法撥打電話的原因。</li><li>**封鎖動作會**  告訴您使用者是否在 Teams 中遭到封鎖或解除封鎖，無法撥打 PSTN 電話。</li> <li>**封鎖時間** 是使用者) 禁止撥打電話 (UTC 的日期和時間。</li></li> </ul>若要在資料表中查看您要的資訊，請務必將欄新增至資料表。 |
|**4**   |選取 **[編輯欄]** 以新增或移除表格中的欄。|
|**5**   |選取 **[全螢幕** ] 以全螢幕模式檢視報表。|

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)