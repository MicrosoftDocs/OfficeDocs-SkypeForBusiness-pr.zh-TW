---
title: Office 365 群組和 Microsoft 團隊
ms.reviewer: phlouie
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: 瞭解 Office 365 群組與群組成員資格如何與 Microsoft 團隊搭配使用。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1bd45d942784f9454acff5636359e172059f22cc
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834333"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 群組和 Microsoft 團隊
=====================================

> [!Tip]
> 觀看下列會話，瞭解團隊如何與 Azure Active Directory （Azure AD）、Office 365 群組、Exchange、SharePoint 和商務用 OneDrive 進行互動： [Microsoft 團隊基礎](https://aka.ms/teams-foundations)

Office 365 群組是 Office 365 中的跨應用程式成員資格服務。 在基本層級，Office 365 群組是 Azure Active Directory 中的一個物件，其中包含一份成員清單，以及與相關工作負載鬆散耦合，包括 SharePoint 小組網站、Yammer 群組、共用 Exchange 信箱資源、Planner、Power BI 和 OneNote。 您可以將人員新增或移除至群組，就像在 Active Directory 中的任何其他群組安全物件一樣。

Office 365 管理員可以定義 Office 365 群組、新增成員，以及從功能（例如 Exchange 共用信箱、SharePoint 文件庫、Yammer 群組等）獲益。 如需 Office 365 群組的詳細資訊，請參閱[瞭解 office 365 群組](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

[在 Microsoft 365 中，不要錯過 IT 架構師](teams-architecture-solutions-posters.md#groups-in-microsoft-365)的海報群組。

<a name="how-office-365-groups-work"></a>Office 365 群組的運作方式
--------------------------

當您建立小組時，在後端，您要建立 Office 365 群組，以及關聯的 SharePoint 文件庫和 OneNote 筆記本，以及與其他 Office 365 雲端應用程式的關聯。 如果建立小組的人員是現有的 Office 365 公用或私人群組的擁有者，但如果該組的人員少於5000人，也可以新增小組功能給小組。 這會建立一個預設的**一般**頻道，讓聊天訊息、檔、OneNote 及其他物件都駐留在其中。 查看頻道的文件庫會顯示代表小組中頻道的 **[一般**] 資料夾。 更重要的是，如果您在文件庫中建立自己的資料夾結構，**它不會**以頻道傳播給團隊;目前，它只會從小組流向 SharePoint。

> [!NOTE]
> 根據客戶的意見反應，由於在 Microsoft 團隊中建立小組而產生的新 Office 365 群組，預設不會在 Outlook 中顯示。 針對想要繼續在 Outlook 中顯示這些群組之現有行為的客戶，將會提供 Exchange Online PowerShell Cmdlet，讓您能夠啟用 Outlook 體驗的群組。 透過 Outlook 建立的群組，且稍後啟用的小組將會繼續在 Outlook 和小組中顯示。 此更新將會在未來幾個月內逐步推出給 Outlook 和小組。

> [!NOTE]
> 刪除 Office 365 群組會移除持續性 Outlook/OWA 交談和團隊會議邀請的信箱別名，並標示要刪除的 SharePoint 網站。 在 Outlook 中移除團隊和其效果之間大約需要20分鐘的時間。 從小組用戶端刪除小組後，就會立即將其從 [查看] 移至團隊成員的所有人。 如果您移除已啟用團隊功能之 Office 365 群組的成員，則在團隊用戶端中針對已移除的人員在團隊用戶端中移除該小組之前，可能會有大約兩小時的延遲。
>
>若要瞭解如何還原已刪除的 Office 365 群組，請閱讀[此](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)資訊。

<a name="group-membership"></a>群組成員資格
----------------

使用者的群組功能和功能取決於您驅動群組成員資格的位置。 例如，如果您移除團隊的成員，也會從 Office 365 群組中移除。 從群組中移除會立即從團隊用戶端移除團隊和頻道。 如果您使用 Microsoft 365 系統管理中心從群組中移除人員，他們將無法存取其他共同作業的內容，例如 SharePoint Online 文件庫、Yammer 群組或共用的 OneNote。 不過，他們仍可存取團隊的聊天功能大約兩小時的時間。

作為管理團隊成員的最佳做法，請在團隊用戶端新增和移除成員，以確保已套用對其他相依雲端應用程式的正確的級聯存取控制。 此外，您也可以避免因您的使用者仍然有權存取其所使用的資源（直到下一個同步處理週期新增或廢除服務特定元件的存取權）時才有脫節的體驗。 如果您在團隊用戶端之外新增或移除團隊成員（使用 Microsoft 365 系統管理中心、Azure AD 或 Exchange Online PowerShell），最多可能需要兩個小時才能反映在團隊中的變更。
