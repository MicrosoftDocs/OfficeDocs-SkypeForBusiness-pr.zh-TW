---
title: Microsoft 365群組和Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 瞭解如何使用Microsoft 365群組和群組成員資格Microsoft Teams。
ms.openlocfilehash: e74e2e8c11753fbf97ef1161e8443f57dbb6146d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631557"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365群組和Microsoft Teams

Microsoft 365群組是應用程式中的跨應用程式成員資格Microsoft 365。 在基本層級，Microsoft 365群組是 Azure Active Directory 中的物件，包含成員清單，並聯結到相關的工作負載，包括 SharePoint 小組網站、共用 Exchange 信箱、Planner 和 Power BI 工作區。 您可以新增或移除人員至群組，就像在 Active Directory 中任何其他群組式安全性物件一樣。

![顯示群組Microsoft 365相關服務的圖表](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

根據預設，Microsoft 365使用者可以建立及管理群組。 如需有關群組Microsoft 365，請參閱瞭解 it[](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)架構Microsoft 365中群組Microsoft 365[群組](teams-architecture-solutions-posters.md#groups-in-microsoft-365)。

## <a name="how-microsoft-365-groups-work-with-teams"></a>群組Microsoft 365群組如何Teams

當您建立團隊時，會建立Microsoft 365群組來管理團隊成員資格。 群組的相關服務 ，例如SharePoint網站、Power BI工作區等，會同時建立。

建立團隊的人可以選擇使用現有的Microsoft 365群組擁有者。 團隊中的每個頻道在文件庫中都有個別的資料夾。 直接在文件庫中建立資料夾不會在團隊中建立頻道。

在 Microsoft 365 或 Outlook 中SharePoint群組群組時，群組信箱會顯示在 Outlook。 在 Teams中建立團隊時，群組信箱預設會隱藏。 您可以使用 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 與 **HiddenFromExchangeClientsEnabled** 參數，讓信箱可見。

## <a name="group-membership"></a>群組成員資格

如果您移除團隊的成員，他們Microsoft 365群組中移除。 從群組移除會立即從用戶端移除團隊Teams頻道。 如果您使用 Microsoft 365 系統管理中心 移除群組中的人員，他們將不再能夠存取其他共同SharePoint，例如 SharePoint Online 文件庫、Yammer群組或共用OneNote。 不過，他們仍然可以存取團隊的聊天功能大約兩小時。

管理小組成員的最佳作法是從 Teams 用戶端新增和移除成員，以確保其他群組連接工作負載的許可權更新快速發生。 如果您使用 Microsoft 365 系統管理中心、Azure AD 或 Exchange Online PowerShell) 在 Teams 用戶端 (之外新增或移除小組成員，最多可能需要 24 小時才能在 Teams 中反映變更。

## <a name="deleting-groups-and-teams"></a>刪除群組和團隊

刪除Microsoft 365群組會移除永久 Outlook/OWA 交談和 Teams 會議邀請的信箱別名，並SharePoint網站進行刪除。 移除團隊及其對團隊的影響大約需要 20 分鐘Outlook。 從用戶端刪除團隊Teams將會立即將其從視圖移除給團隊的所有成員。 如果您移除已啟用 Teams 功能的 Microsoft 365 群組成員，則團隊在 Teams 用戶端中可能會延遲大約兩小時，才能在 Teams 用戶端中移除已移除的受影響人員。

有關群組和團隊生命週期結束選項的詳細資訊，請參閱群組、[](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)團隊和團隊的生命週期結束選項Yammer及在 Microsoft Teams 中存檔[或刪除Microsoft Teams。](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>相關主題

[影片Microsoft Teams (基礎) ](https://aka.ms/teams-foundations)

[還原已刪除的群組](/microsoft-365/admin/create-groups/restore-deleted-group)