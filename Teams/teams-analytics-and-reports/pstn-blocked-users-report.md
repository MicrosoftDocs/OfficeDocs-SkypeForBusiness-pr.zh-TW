---
title: Microsoft TeamsPSTN 封鎖的使用者報告
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
description: 在系統管理中心Microsoft Teams PSTN 封鎖的使用者報告，以概觀您組織Teams無法撥打 PSTN 通話的使用者。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809333"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft TeamsPSTN 封鎖的使用者報告

系統管理中心中的 PSTN 封鎖使用者報告Microsoft Teams顯示貴組織中禁止在 Teams 中撥打 PSTN Teams。 您可以查看每個封鎖使用者的資訊，包括他們指派的電話號碼，以及他們無法撥打電話的原因。

## <a name="view-the-pstn-blocked-users-report"></a>查看 PSTN 封鎖的使用者報告

在系統管理中心的左側導Microsoft Teams，按一下 [**分析&報告**  >  **使用方式報告**。 在 [ **查看報表」** 選項卡的 [ **報表**> 下，選取 **[PSTN 封鎖的使用者**，然後按一下 [ **執行報表**> 。

![系統管理中心中 PSTN 封鎖的使用者報告報告的螢幕擷取畫面](../media/teams-reports-pstn-blocked-users-with-callouts.png "系統管理中心中 PSTN 封鎖使用者報告的螢幕擷取畫面Microsoft Teams編號圖說說義")

## <a name="interpret-the-report"></a>解譯報表

|標注 |描述  |
|--------|-------------|
|**1**   |每個報表都有產生日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**2**   |X 軸是日期。 Y 軸是使用者數目。 <br>將游標停留在給定日期的點上方，以查看該日期被封鎖的使用者數目。 |
|**3**   |下表列出所有禁止進行 PSTN 通話的使用者明細。  它會顯示已指派電話系統或音訊會議的所有使用者，並為您提供每個使用者的更多相關資訊。 <ul><li>**顯示名稱** 是使用者的顯示名稱。 您可以按一下顯示名稱，前往系統管理中心中的使用者Microsoft Teams頁面。 </li> <li>**電話** 是指派給使用者的號碼。</li> <li>**封鎖的原因** 就是使用者被封鎖撥打電話的原因。</li><li>**封鎖的動作** 會告訴您使用者是否已被封鎖或禁止在 Teams。</li> <li>**封鎖時間** 是使用者 () 的日期和時間。</li></li> </ul>若要在表格中查看您想要的資訊，請務必新增欄至資料表。 |
|**4**   |選取 **編輯欄** 以新增或移除表格中的欄。|
|**5**   |選取 **全螢幕** 以全螢幕模式來查看報表。|

## <a name="related-topics"></a>相關主題

- [Teams分析與報告](teams-reporting-reference.md)