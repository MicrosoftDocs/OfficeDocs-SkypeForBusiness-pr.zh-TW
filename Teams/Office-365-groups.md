---
title: Microsoft 365 群組和 Microsoft Teams
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
description: 瞭解 Microsoft 365 群組和群組成員資格如何與 Microsoft Teams 合作。
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105239"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 群組和 Microsoft Teams

Microsoft 365 群組是 Microsoft 365 中的跨應用程式成員資格服務。 在基本層級上，Microsoft 365 群組是 Azure Active Directory 中的物件，包含成員清單，並聯結到相關的工作負載，包括 SharePoint 小組網站、共用 Exchange 信箱、Planner 和 Power BI 工作區。 您可以新增或移除人員至群組，就像在 Active Directory 中任何其他群組式安全性物件一樣。

![顯示 Microsoft 365 群組和相關服務的圖表](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

根據預設，Microsoft 365 中的使用者可以建立及管理群組。 如需 Microsoft 365 群組詳細資訊，請參閱瞭解 [Microsoft 365 群組](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 和 [Microsoft 365 IT 架構](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 版群組海報。

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 群組如何使用 Teams

當您建立團隊時，會建立 Microsoft 365 群組來管理團隊成員資格。 群組的相關服務 ，例如 SharePoint 網站、Power BI 工作區等，會同時建立。

建立團隊的人可以選擇使用現有的 Microsoft 365 群組 ，如果他們是該群組的擁有者。 團隊中的每個頻道在文件庫中都有個別的資料夾。 直接在文件庫中建立資料夾不會在團隊中建立頻道。

在 Outlook 或 SharePoint 中建立 Microsoft 365 群組時，群組信箱會顯示在 Outlook 中。 在 Teams 中建立團隊時，群組信箱預設為隱藏。 您可以使用 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 與 **HiddenFromExchangeClientsEnabled** 參數，讓信箱可見。

## <a name="group-membership"></a>群組成員資格

如果您移除團隊的成員，他們也從 Microsoft 365 群組中移除。 從群組移除會立即從 Teams 用戶端移除團隊和頻道。 如果您使用 Microsoft 365 系統管理中心將人員從群組移除，他們將不再能夠存取其他共同合作層面，例如 SharePoint Online 文件庫、Yammer 群組或共用的 OneNote。 不過，他們仍然可以存取團隊的聊天功能大約兩小時。

作為管理小組成員的最佳作法，請從 Teams 用戶端新增並移除成員，以確保其他群組連接工作負載的許可權更新快速發生。 如果您使用 Microsoft 365 系統管理中心、Azure AD 或 Exchange Online PowerShell) 在 Teams 用戶端 (之外新增或移除小組成員，則變更最多可能需要 24 小時才能反映在 Teams 中。

## <a name="deleting-groups-and-teams"></a>刪除群組和團隊

刪除 Microsoft 365 群組會移除永久 Outlook/OWA 交談和 Teams 會議邀請的信箱別名，並標記 SharePoint 網站以刪除。 移除團隊與團隊對 Outlook 的影響之間大約需要 20 分鐘。 從 Teams 用戶端刪除團隊，會立即將其從查看移除給團隊的所有成員。 如果您移除已啟用 Teams 功能的 Microsoft 365 群組成員，團隊在 Teams 用戶端中可能會延遲大約兩小時，才能在 Teams 用戶端中移除受影響的人員。

有關群組和團隊生命週期結束選項的詳細資訊，請參閱 Microsoft Teams 中群組、團隊和  [Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 的生命週期結束選項，以及存檔或刪除 [團隊](./archive-or-delete-a-team.md)。

## <a name="related-topics"></a>相關主題

[Microsoft Teams 的基礎 (影片) ](https://aka.ms/teams-foundations)

[還原已刪除的群組](/microsoft-365/admin/create-groups/restore-deleted-group)