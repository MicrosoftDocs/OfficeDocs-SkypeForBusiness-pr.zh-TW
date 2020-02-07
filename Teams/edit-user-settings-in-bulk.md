---
title: 大量編輯 Microsoft 團隊使用者設定
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何大量在 Microsoft 團隊系統管理中心管理 Microsoft 團隊使用者設定。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6177a463bee481812323b2334461f20e7021af84
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832643"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>大量編輯 Microsoft 團隊使用者設定

做為管理員，您可以在 Microsoft 團隊系統管理中心管理團隊使用者設定。 在 [**使用者**] 頁面上，您可以查看相關資訊，例如帳戶和授權詳細資料，以及編輯原則及其他設定。 您可以個別或多位使用者編輯使用者的設定。

## <a name="edit-user-settings-in-bulk"></a>大量編輯使用者設定

使用 Microsoft 團隊系統管理中心來一次編輯多位使用者的設定。 我們建議您一次編輯20個使用者的設定。 若要編輯大量使用者的設定，請使用 PowerShell。 如需詳細資訊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。

1. 在 Microsoft [團隊管理中心] 的左導覽中，選取 [**使用者**]。
2. 搜尋您要編輯的使用者，或篩選該視圖，以顯示您要編輯的使用者。
3. 在 [ **&#x2713;** （核取符號）] 欄中，執行下列其中一項動作來選取 [使用者]：
    - 一次選取一個使用者。 您所選取的每位使用者旁邊都會顯示 **&#x2713;** 。 如果您選取超過20個使用者，將不會封鎖您，但請記住，您選取的使用者越多，就會花更長的時間才能完成。

        ![顯示使用者選取範圍之 [使用者] 頁面的螢幕擷取畫面](media/bulk-edit-user-settings-select-users.png)

    - 按一下表格頂端的 [&#x2713; （核取標記）來選取 [所有使用者（最多20個使用者）]，然後在 [**選取範圍限制**] 對話方塊中，按一下 [**繼續選取 [全部**] 以完成選取專案。

        ![顯示選取範圍限制的 [使用者] 頁面螢幕擷取畫面](media/bulk-edit-user-settings-select-all-limit.png) <br> 選取的使用者旁邊會顯示 **&#x2713;** 。

        ![[使用者] 頁面的螢幕擷取畫面，顯示已選取20個使用者](media/bulk-edit-user-settings-select-all.png)
4. 按一下 [**編輯設定**]，進行您想要的變更，然後按一下 [**儲存**]。

    ![[編輯設定] 窗格的螢幕擷取畫面](media/bulk-edit-user-settings-edit-settings.png)
