---
title: Teams 中的 Shifts
description: 取得在 Teams 中設定和管理排程管理工具 Shifts 所需的系統管理指導方針。
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: f8980116dab90abd3c9c96ac17b577e6abf64f90
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2022
ms.locfileid: "65598306"
---
# <a name="shifts-for-teams"></a>Teams 中的 Shifts

班次是Teams中的排程管理工具，可讓前線員工保持聯繫並保持同步。這是第一個針對快速且有效的排程管理和通訊所建置的行動裝置。 透過班次，第一線主管和工作人員可以順暢地管理排程並保持聯繫。

主管可以建立、更新和管理小組的班次排程。 他們可以指派班次、新增空班，以及核准員工的排程要求。 員工可以檢視自己的排程和小組的排程、設定他們的顯示狀態、調班或丟班要求、要求休假，以及上班打卡。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

使用下列資源來協助您在組織中設定和管理班次。

## <a name="set-up-and-manage-shifts"></a>設定和管理班次

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[管理班次](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** 瞭解如何管理組織的班次。         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[管理班次管理排程擁有者](shifts/schedule-owner-for-shift-management.md)** 這項功能可讓您將小組成員的許可權提升為排程擁有者，而不讓該員工成為團隊擁有者。         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Shifts 資料常見問題](shifts/shifts-data-faq.md)** 瞭解班次資料的儲存位置，以及與 Shifts 資料相關的其他主題，包括保留、擷取和加密。        |

## <a name="shifts-connectors"></a>Shifts 連接器

如果您使用協力廠商員工管理 (WFM) 系統來排程，您可以透過受管理的 Shifts 連接器直接與 Shifts 整合。 設定連線之後，第一線工作人員就可以從 Shifts 中順暢地在 WFM 系統中檢視和管理他們的排程。

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Shifts 連接器概觀](shifts/shifts-connectors.md)** 概略瞭解 Shifts 連接器及其運作方式。 瞭解可用的受管理連接器以及支援的 WFM 系統。   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[受管理的 Shifts 連接器](shifts/shifts-connectors.md#managed-shifts-connectors)** 經管理的 Shifts 連接器是與我們的合作夥伴共同開發，由我們或我們的合作夥伴託管和管理。 若要深入瞭解，請[參閱Microsoft Teams Blue Yonder 的 Shifts 連接器](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)，以及[適用于 Microsoft Teams 的 Reflexis Shifts 連接器](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams)。    |
|   | **[使用 Shifts 連接器精靈將 Shifts 連線到 Blue Yonder 員工管理](shifts/shifts-connector-wizard.md)** Microsoft 365 系統管理中心中的 Shifts 連接器精靈可協助您快速設定與 WFM 系統的連線。 目前精靈支援適用于 Blue Yonder 的 Teams Shifts 連接器，以整合 Shifts 與 Blue Yonder 員工管理。
|  | **[使用 PowerShell 將班次連線到 Blue Yonder 員工管理](shifts/shifts-connector-blue-yonder-powershell-setup.md)** 瞭解如何使用 PowerShell，透過適用于 Blue Yonder 的 Teams Shifts 連接器來設定與 Blue Yonder 員工管理的連線。         |
|   | **[使用 PowerShell 管理您與 Blue Yonder 員工管理的 Shifts 連線](shifts/shifts-connector-powershell-manage.md)** 透過 Shifts 連接器精靈或 PowerShell 進行設定後，取得如何使用 PowerShell 管理 Blue Yonder 員工管理的 Shifts 連線的指導方針。

## <a name="shifts-extensions"></a>Shifts 擴充功能

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph API](/graph/api/resources/shift)** Shifts Graph API 可讓您整合 Shifts 資料與外部員工管理 (WFM) 系統。 您可以在後端以彈性建立自訂的 Shifts 體驗，同時在Teams中為使用者提供豐富的前端體驗。             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate可讓您從 Shifts 取得資訊，並與其他應用程式建立自訂工作流程，並以縮放比例執行作業。 只要不使用任何程式碼，即可自動化金鑰程式。 觸發程式和範本支援各種情況，例如不需要主管核准時，啟用班次要求的自動核准。 |

## <a name="featured-training"></a>精選訓練

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [影片：什麼是班次？](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [影片：建立班次排程](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [影片：管理班次排程](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
