---
title: 在 Microsoft Teams 系統管理中心的活動記錄中檢視您的原則指派
ms.author: mabond
author: mkbond007
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 系統管理中心的活動記錄中檢視您的原則指派活動。
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8243d60a2aca31a8b9158b922126c7c80a486eb
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562212"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>在活動記錄中檢視您的原則指派

當您在 Microsoft Teams 系統管理中心將原則指派給使用者時，您可以在 [活動] 記錄檔中檢視這些原則指派的狀態。 活動記錄會顯示過去 30 天內，透過 Microsoft Teams 系統管理中心分批指派給超過 20 個使用者的原則指派。 請記住，活動記錄檔不會顯示原則套件指派、透過 Microsoft Teams 系統管理中心分批給少於 20 個使用者的原則指派，或是透過 PowerShell 顯示原則指派。

![[活動記錄] 頁面的螢幕擷取畫面。](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>在活動記錄中檢視您的原則工作分派活動

若要在活動記錄中檢視您的原則指派：

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 [ **首頁**]，然後在 [ **活動記錄檔**] 底下，選 **取 [檢視詳細資料]**。
2. 您可以檢視所有原則指派，或依狀態篩選清單，只顯示 **尚未開始**、 **進行中** 或 **已完成** 的作業。 您會看到每個作業的下列相關資訊：
    - **名稱**：原則指派的名稱。 按一下連結以檢視更多詳細資料。 這包括獲指派原則的使用者數目，以及已完成、進行中且未開始的作業數目。 您也會看到批次中的使用者清單，以及每個使用者的狀態和結果。 以下是範例：

        ![的螢幕擷取畫面。](media/activity-log-policy-assignment-detail.png)

    - **已提交**：提交原則作業的日期和時間。
    - **完成時間**：原則指派完成的日期和時間。
    - **影響：** 批次中的使用者數目。
    - **整體狀態**：原則指派的狀態。

> [!NOTE]
> 您也可以從 [ **使用者** ] 頁面移至 [活動] 記錄檔。 按一下 [ **套** 用] 提交大量原則指派後，您會在頁面頂端看到橫幅。 按一下橫幅中的 **[活動記錄** 檔] 連結。

## <a name="related-topics"></a>相關主題

- [指派原則給使用者](policy-assignment-overview.md)
