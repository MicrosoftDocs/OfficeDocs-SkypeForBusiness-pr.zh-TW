---
title: 在 Microsoft 團隊系統管理中心的活動記錄中查看您的原則指派
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊系統管理中心的活動記錄中查看原則指派活動。
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374291"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>在活動記錄記錄中查看您的原則指派

當您在 Microsoft 團隊系統管理中心將原則指派給使用者時，您可以在活動記錄中查看這些原則指派的狀態。 活動記錄會顯示在過去30天內，透過 Microsoft [小組系統管理中心] 向超過20名使用者批次的原則作業。 請記住，活動記錄不會顯示原則套件指派、原則指派，透過 Microsoft 團隊系統管理中心的使用者數目少於20個，或透過 PowerShell 進行原則作業。

![[活動記錄] 頁面的螢幕擷取畫面](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>在活動記錄記錄中查看原則指派活動

若要在活動記錄中查看您的原則指派：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**儀表板**]，然後在 [**活動記錄**] 底下，選取 [**查看詳細資料**]。
2. 您可以查看所有原則指派，或依狀態篩選清單，只顯示**未開始**、**進行中**或**已完成**的作業。 您將會看到有關每個作業的下列相關資訊：
    - **Name （名稱**）：原則指派的名稱。 按一下連結以查看更多詳細資料。 這包括指派給該原則的使用者數目，以及已完成的作業數、進行中以及尚未開始的人數。 您也會看到批次中的使用者清單，以及每個使用者的狀態和結果。 以下是一個範例：

        ![的螢幕擷取畫面](media/activity-log-policy-assignment-detail.png)

    - 已**提交**：提交原則指派的日期和時間。
    - **完成時間**：已完成原則指派的日期和時間。
    - **影響**：批次中的使用者數目。
    - **整體狀態**：原則指派的狀態。

> [!NOTE]
> 您也可以從 [**使用者**] 頁面取得活動記錄。 **按一下 [** 套用] 以提交大量原則指派之後，您就會在頁面頂端看到橫幅。 按一下橫幅中的 [**活動記錄**] 連結。

## <a name="related-topics"></a>相關主題

- [指派原則給使用者](assign-policies.md)
