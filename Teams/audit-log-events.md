---
title: 在 [審核記錄] 中搜尋 Microsoft 團隊中的事件
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: 瞭解如何從 Office 365 審核記錄中檢索 Microsoft 團隊資料。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341621"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>在 [審核記錄] 中搜尋 Microsoft 團隊中的事件

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

審核記錄可協助您調查跨 Office 365 服務的特定活動。 針對團隊而言，以下是一些經過審核的活動：

- 小組建立

- 小組刪除

- 已新增頻道

- 已變更設定

> [!NOTE]
> 來自專用通道的審核事件也會記錄為針對團隊和標準通道的活動。

若要查看在 Office 365 中審核之活動的完整清單，請閱讀[在 office 365 安全性 & 合規性中心搜尋審核記錄](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="turn-on-auditing-in-teams"></a>在團隊中開啟審核

您必須先在[安全性 & 合規性中心](https://protection.office.com)開啟審核，然後才能查看審核資料。 如需有關開啟審核的協助，請參閱[開啟或關閉 Office 365 審核記錄搜尋](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。

> [!IMPORTANT]
> 審核資料只能從您開啟 [審計] 的位置使用。

## <a name="retrieve-teams-data-from-the-audit-log"></a>從審核記錄中取得團隊資料

1. 若要取得審核記錄，請移至[安全性 & 合規性中心](https://go.microsoft.com/fwlink/?linkid=855775)。 在 [**搜尋**] 底下，選取 [**審核記錄搜尋**]。
1. 使用 [**搜尋**] 篩選您想要審核的活動、日期和使用者。
1. 將結果匯出至 Excel 以進行進一步分析。

> [!IMPORTANT]
> 審核資料只有在已開啟審核的情況下，才會顯示在審核記錄中。

## <a name="external-user-scenario"></a>外部使用者案例

從商務角度來看，您可能會想要記住的一個案例，就是將外部使用者新增至您的小組環境。 如果已啟用外部使用者，則監視其目前狀態是一個不錯的主意。

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsExternalUserAddPolicy.png)

此策略的螢幕擷取畫面可讓您命名原則、根據您的業務需求來設定嚴重性、將嚴重性設定為（在此例中為單一活動），然後建立只會只監視加法的參數在非內部使用者，並將此活動限制為 Microsoft 團隊。

然後，就可以在活動記錄中查看來自此原則的結果：

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsExternalUserList.png)

您可以在這裡查看已設定的原則相符的專案，並視需要進行調整，或將結果匯出成在其他地方使用。

## <a name="mass-delete-scenario"></a>成批刪除案例

如上述所述，您可以監視刪除情況。 您可以建立可監視大量刪除小組網站的原則：

![[原則建立] 頁面的螢幕擷取畫面，其中顯示設定大量小組刪除偵測原則的原則](media/TeamsMassDeletePolicy.png)

如螢幕擷取畫面所示，您可以針對此原則設定許多不同的參數來監視團隊刪除，包括嚴重性、單一或重複動作，以及將此限制為小組和網站刪除的參數。 您可以根據組織的需求，從範本中獨立完成此操作，或者您可能會根據貴組織的需求而建立範本來建立基礎。

建立適用于您企業的原則之後，您就可以在觸發事件時查看活動記錄中的結果：

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsMassDeleteList.png)

您可以篩選到已設定的原則，以查看該原則的結果。 如果您在活動記錄中取得的結果不滿意（可能是您看到許多結果，或是根本沒有反應），這可能會協助您微調查詢，使其更符合您的需求。

## <a name="video-techtip-using-audit-log-search-in-teams"></a>影片： TechTip：在團隊中使用審核記錄搜尋

加入 Ansuman Acharya （一種小組的程式管理員），他示範如何在 Office 365 安全 & 規範中心中執行審核記錄搜尋小組。

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
