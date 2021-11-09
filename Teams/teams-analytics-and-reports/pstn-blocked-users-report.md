---
title: Microsoft TeamsPSTN 封鎖的使用者報告
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: 在系統管理中心Microsoft Teams PSTN 封鎖的使用者報告，以概觀您組織Teams無法撥打 PSTN 通話的使用者。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a89e7ead560e3782d7120884a047110118d2ecd0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840685"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft TeamsPSTN 封鎖的使用者報告

系統管理中心中的 PSTN 封鎖使用者Microsoft Teams顯示貴組織中禁止在 Teams 中撥打 PSTN Teams。 您可以查看每個封鎖使用者的資訊，包括他們指派的電話號碼，以及他們無法撥打電話的原因。

## <a name="view-the-pstn-blocked-users-report"></a>查看 PSTN 封鎖的使用者報告

在系統管理中心的左側導Microsoft Teams，按一下 [分析&**報告**  >  **使用方式報告**。 在 [ **查看報表」** 選項卡的 [ **報表**> 下，選取 **[PSTN 封鎖的使用者**，然後按一下 [ **執行報表**> 。

![系統管理中心中 PSTN 封鎖的使用者報告報告的螢幕擷取畫面。](../media/teams-reports-pstn-blocked-users-with-callouts.png "系統管理中心中 PSTN 封鎖使用者報告的螢幕擷取畫面Microsoft Teams編號圖說說義")

## <a name="interpret-the-report"></a>解譯報表

|標注 |描述  |
|--------|-------------|
|**1**   |每個報表都有產生日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**2**   |X 軸是日期。 Y 軸是使用者數目。 <br>將游標停留在給定日期的點上方，以查看該日期被封鎖的使用者數目。 |
|**3**   |下表列出所有被封鎖進行 PSTN 通話的使用者明細。  它會顯示已指派電話系統或音訊會議的所有使用者，並為您提供每個使用者的更多相關資訊。 <ul><li>**顯示名稱** 是使用者的顯示名稱。 您可以按一下顯示名稱，以前往系統管理中心中的使用者Microsoft Teams頁面。 </li> <li>**電話** 是指派給使用者的號碼。</li> <li>**封鎖的原因** 就是使用者被封鎖撥打電話的原因。</li><li>**封鎖的動作** 會告訴您使用者是否已被封鎖或無法在 Teams 中撥打 PSTN 通話。</li> <li>**封鎖時間** 是使用者 (UTC) 的日期和時間。</li></li> </ul>若要在表格中查看您想要的資訊，請務必新增欄至資料表。 |
|**4**   |選取 **編輯欄** 以新增或移除表格中的欄。|
|**5**   |選取 **全螢幕** 以全螢幕模式來查看報表。|

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)