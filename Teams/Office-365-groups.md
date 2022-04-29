---
title: Microsoft 365 群組和Microsoft Teams
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
description: 瞭解Microsoft 365群組和群組成員資格如何與Microsoft Teams搭配運作。
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125428"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 群組和Microsoft Teams

Microsoft 365 群組是 Microsoft 365 中的跨應用程式成員資格服務。 在基本層級，Microsoft 365群組是Azure Active Directory中的物件，具有成員清單和相關工作負載的組合，包括SharePoint小組網站、共用Exchange信箱、Planner 和OneNote筆記本。 您可以新增或移除群組中的人員，就像在 Active Directory 中新增或移除其他任何群組式安全性物件一樣。

![顯示Microsoft 365 群組及相關服務的圖表。](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

根據預設，Microsoft 365中的使用者可以建立和管理群組。 如需Microsoft 365 群組的詳細資訊，請參閱[瞭解 IT 架構海報Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)[中的Microsoft 365 群組和群組](teams-architecture-solutions-posters.md#groups-in-microsoft-365)。

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 群組如何使用 Teams

當您建立團隊時，會建立一個Microsoft 365群組來管理團隊成員資格。 群組的相關服務，例如SharePoint網站、信箱等，會同時建立。

建立團隊的人員可以選擇使用現有的Microsoft 365群組，如果他們是該群組的擁有者。 團隊中的每個頻道在文件庫中都有個別的資料夾。 直接在文件庫中建立資料夾並不會在團隊中建立頻道。

在 Outlook 或 SharePoint 中建立Microsoft 365群組時，群組信箱會顯示在Outlook中。 在 Teams 中建立團隊時，預設會隱藏群組信箱。 您可以使用 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 搭配 **HiddenFromExchangeClientsEnabled** 參數來顯示信箱。

## <a name="group-membership"></a>群組成員資格

如果您移除團隊的成員，也會從Microsoft 365群組中移除。 從群組移除後，會立即從Teams用戶端移除團隊和頻道。 如果您使用Microsoft 365 系統管理中心從群組中移除人員，他們將無法再存取其他共同作業層面，例如 SharePoint Online 文件庫、Yammer群組或共用OneNote。 不過，他們仍可存取團隊的聊天功能約兩小時。

最佳作法是管理小組成員，請從Teams用戶端新增和移除他們，以確保其他群組連線工作負載的許可權更新能快速執行。 如果您使用 Microsoft 365 系統管理中心、Azure AD 或 Exchange Online PowerShell) ，在Teams用戶端 (外部新增或移除小組成員，最多可能需要 24 小時，變更才會反映在 Teams 中。

## <a name="deleting-groups-and-teams"></a>刪除群組和團隊

刪除Microsoft 365群組會移除持續性Outlook/OWA 交談和Teams會議邀請的信箱別名，並將SharePoint網站標示為刪除。 從團隊移除到對Outlook的影響，大約需要 20 分鐘。 從Teams用戶端中刪除團隊時，會立即從檢視中移除該團隊，使其全部移除為團隊成員。 如果您移除已啟用Teams功能的Microsoft 365群組成員，在Teams用戶端中移除受影響人員的小組之前，可能會有大約兩小時的延遲。

如需群組和團隊生命週期結束選項的詳細資料，請參閱[群組、團隊和Yammer的結束生命週期選項](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)和[封存或刪除Microsoft Teams中的團隊](./archive-or-delete-a-team.md)。

## <a name="related-topics"></a>相關主題

[Microsoft Teams (影片) 的基礎](https://aka.ms/teams-foundations)

[還原已刪除的群組](/microsoft-365/admin/create-groups/restore-deleted-group)
