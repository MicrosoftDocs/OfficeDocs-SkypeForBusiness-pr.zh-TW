---
title: Microsoft Teams 中的來賓存取
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Microsoft Teams 中的來賓存取可將團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ccaf4cae1b82b206ebfd27b185dddaf2ab0eece
ms.sourcegitcommit: 9a6e59c0fa020656ed3e858d43e628c3122fc71a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "38746286"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的來賓存取
======================================

來賓存取可讓您將組織外部的個別使用者新增至 Microsoft Teams 中的團隊和頻道。 

若要比較外部存取 (同盟) 和來賓存取 (並決定您應使用的方式)，請閱讀[在 Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。

如果您已在組織中開啟來賓存取，請從[來賓存取檢查清單](guest-access-checklist.md)開始。

## <a name="guest-access-overview"></a>來賓存取概觀

來賓存取可將 Teams 中現有團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。 任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分參與 Teams，擁有小組聊天、會議及檔案的完整存取權。 身為 Teams 系統管理員的您可以控制來賓在 Teams 中可以 (和不可以) 使用的功能，請參閱[管理來賓存取](manage-guests.md)。

來賓存取在 Teams 中是全組織設定，依預設為關閉。 來賓存取受到 Azure AD 和 Office 365 的服務限制。


> [!IMPORTANT]
> 對於共存的升級模式，來賓存取遵循 Teams 的全組織設定。 這項設定無法變更。

## <a name="licensing-for-guest-access"></a>來賓存取的授權

來賓存取隨附於所有 Office 365 商務進階版、Office 365 企業版和 Office 365 教育版訂閱。 您不需要額外的 Office 365 授權。 Teams 未限制您可以新增的來賓數量。 然而，可以新增至租用戶的來賓總數會依據您 Azure AD 授權的允許量而定，通常是每位授權使用者允許 5 位來賓。 如需詳細資訊，請參閱 [Azure AD B2B 共同作業授權](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。


> [!NOTE]
> 僅擁有獨立版 Office 365 訂閱方案 (例如 Exchange Online Plan 2) 的組織使用者將無法受邀為貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。 若要讓這些使用者使用 Teams，這些使用者必須獲派 Office 365 商務進階版、Office 365 企業版或 Office 365 教育版訂閱。 

## <a name="who-is-a-guest"></a>何謂來賓？

來賓是不屬於員工、學生或組織成員的人員。 他們沒有貴組織的學校或公司帳戶。 例如，來賓可能包括有合作夥伴、廠商、供應商或顧問。 只要是不屬於貴組織成員的任何人都可以在 Teams 中新增為來賓。 這表示擁有商務帳戶 (也就是 Active Directory 帳戶) 或消費者電子郵件帳戶 (使用 Outlook.com、Gmail.com 或其他) 的任何人都能以來賓身分參與 Teams，擁有團隊和頻道體驗的完整存取權。

若要深入了解來賓可以和不可以使用的功能，請參閱[在 Microsoft Teams 中授權來賓存取](teams-dependencies.md)。 或請查看[比較團隊成員和來賓功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表格。 

最後，Teams 中的所有來賓與其他部分的 Office 365 一樣，都受到相同的合規性和稽核保護，可在 Azure AD 中安全地管理。

## <a name="why-use-guest-access"></a>為什麼要使用來賓存取？

透過來賓存取，使用 Teams 的組織可以向合作夥伴提供團隊、頻道中的文件、資源、聊天和應用程式的存取權，同時又能保有自身公司資料的完整控制權。 Teams 中的所有來賓與其他部分的 Office 365 一樣，都受到相同的合規性和稽核保護，可在 Azure AD 中安全地管理這些來賓。  

## <a name="understand-the-limitations-for-guests"></a>了解來賓的限制

來賓體驗有刻意設計的限制。 請確定您了解來賓體驗，這樣您才不會嘗試修正不是問題的項目。 例如，以下是 Microsoft Teams 來賓無法使用的部分功能清單：

- 商務用 OneDrive
- 在 Teams 外部執行人員搜尋
- 行事曆、排程會議或會議詳細資料
- PSTN
- 組織圖
- 建立或修改團隊
- 瀏覽團隊
- 將檔案上傳至個人對個人的聊天
- 如果來賓知道使用者的完整電子郵件識別碼，來賓仍然可以搜尋和尋找使用者 (不屬於其團隊)。 為避免發生這種情況，IT 系統管理員可以使用如[限域目錄搜尋](teams-scoped-directory-search.md)等模式的功能，將來賓限制在其自己的虛擬 GAL 中。
- 目前，Teams 僅支援由 [Azure B2B 所定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)來賓使用者的狀態 1 和狀態 2

如需來賓在 Teams 中可以和不可以使用的功能完整清單，請參閱[比較團隊成員和來賓功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表格。 若要深入了解 Office 365 等級的來賓存取，請參閱[將來賓新增至 Office 365 群組](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。


## <a name="more-information"></a>詳細資訊

[連絡商務產品的客戶支援 - 系統管理說明](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[Office 365 群組的來賓存取權](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
