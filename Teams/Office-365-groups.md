---
title: Microsoft 365 群組和 Microsoft 團隊
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 瞭解 Microsoft 365 群組與群組成員資格如何與 Microsoft 團隊搭配使用。
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456077"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 群組和 Microsoft 團隊

Microsoft 365 群組是 Microsoft 365 中的跨應用程式成員資格服務。 在基本層面上，Microsoft 365 群組是 Azure Active Directory 中的一個物件，其中包含一份成員清單，以及與相關工作負載耦合，包括 SharePoint 小組網站、共用 Exchange 信箱、Planner 及 Power BI 工作區。 您可以將人員新增或移除至群組，就像在 Active Directory 中的任何其他群組安全物件一樣。

![顯示 Microsoft 365 群組和相關服務的圖表](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

根據預設，Microsoft 365 中的使用者可以建立及管理群組。 如需有關 Microsoft 365 群組的詳細資訊，請參閱 [瞭解 microsoft 365 群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) ，以及 [適用于 IT 架構師海報的 microsoft 365 中的群組](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 。

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 群組如何與團隊搭配運作

建立小組時，會建立 Microsoft 365 群組以管理團隊成員資格。 群組的相關服務（例如 SharePoint 網站、Power BI 工作區等）是同時建立的。

如果使用者是群組的擁有者，則建立小組的人員可以選擇使用現有的 Microsoft 365 群組。 小組中的每個頻道在文件庫中都有一個獨立的資料夾。 直接在文件庫中建立資料夾，不會在團隊中建立頻道。

在 Outlook 或 SharePoint 中建立 Microsoft 365 群組時，會在 Outlook 中看到群組信箱。 在小組中建立小組時，預設會隱藏群組信箱。 您可以將 [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 與 **HiddenFromExchangeClientsEnabled** 參數搭配使用，以顯示信箱。

## <a name="group-membership"></a>群組成員資格

如果您移除團隊的成員，也會從 Microsoft 365 群組中移除。 從群組中移除會立即從團隊用戶端移除團隊和頻道。 如果您使用 Microsoft 365 系統管理中心從群組中移除人員，他們將無法存取其他共同作業的內容，例如 SharePoint Online 文件庫、Yammer 群組或共用的 OneNote。 不過，他們仍可存取團隊的聊天功能大約兩小時的時間。

作為管理團隊成員的最佳做法，您可以在團隊用戶端新增及移除這些成員，以確保其他群組連線工作負載的許可權更新很快就會發生。 如果您是使用 Microsoft 365 系統管理中心、Azure AD 或 Exchange Online PowerShell) 在團隊用戶端 (新增或移除團隊成員，可能需要長達24小時才能反映在團隊中的變更。

## <a name="deleting-groups-and-teams"></a>刪除群組和小組

刪除 Microsoft 365 群組會移除持續性 Outlook/OWA 交談和團隊會議邀請的信箱別名，並標示要刪除的 SharePoint 網站。 在 Outlook 中移除團隊和其效果之間大約需要20分鐘的時間。 從小組用戶端刪除小組後，就會立即將其從 [查看] 移至團隊成員的所有人。 如果您移除已在其上啟用團隊功能的 Microsoft 365 群組成員，則在團隊用戶端中針對已移除的人員在團隊用戶端中移除該小組前，可能會有大約兩小時的延遲。

如需群組和小組的相關詳細資料，請參閱  [群組、團隊和 Yammer 的週期選項結束](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) ，以及 [在 Microsoft 團隊中封存或刪除小組](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)。

## <a name="related-topics"></a>相關主題

[Microsoft 團隊 (影片的基礎) ](https://aka.ms/teams-foundations)

[還原已刪除的群組](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)