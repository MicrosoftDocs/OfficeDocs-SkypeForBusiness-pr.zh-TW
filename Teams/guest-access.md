---
title: Microsoft Teams 中的來賓存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams 中的來賓存取可將團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761239"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的來賓存取

來賓存取可將 Teams 中現有團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。 任何擁有商務或消費者電子郵件帳戶的人（例如 Microsoft 365、Outlook、Gmail 或其他人），都可以在擁有小組聊天、會議和檔案的完整存取權的小組中，以來賓的身分參與。 身為 Teams 系統管理員的您可以控制來賓在 Teams 中可以 (和不可以) 使用的功能，請參閱[管理來賓存取](manage-guests.md)。

若要比較外部存取 (同盟) 和來賓存取 (並決定您應使用的方式)，請閱讀[在 Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。

來賓存取在 Teams 中是全組織設定，依預設為關閉。  (您可以使用 [敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制對個別團隊的來賓存取權。 ) 

如果您準備好要開始邀請客人給小組，請閱讀下列其中一項：

- 若要設定供團隊使用的來賓存取權，請參閱 [與團隊中的來賓共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業。
- 若要與使用 Azure Active Directory 的合作夥伴組織共同作業，並允許來賓自行註冊小組存取，請參閱 [使用受管理的來賓建立 B2B extranet](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。

來賓存取受到 Azure AD 和 Microsoft 365 或 Office 365 服務的限制。

> [!IMPORTANT]
> 對於共存的升級模式，來賓存取遵循 Teams 的全組織設定。 這項設定無法變更。

## <a name="licensing-for-guest-access"></a>來賓存取的授權

來賓存取隨附於所有 Microsoft 365 商務標準版、Office 365 企業版和 Office 365 教育版訂閱。 您不需要額外的 Microsoft 365 或 Office 365 授權。 Teams 未限制您可以新增的來賓數量。 不過，可新增至您租用戶的來賓總數可能受到 Azure AD 的付費功能限制。 如需詳細資訊，請參閱 [Azure AD B2B 共同作業授權](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。


> [!NOTE]
> 僅擁有獨立版 Microsoft 365 或 Office 365 訂閱方案 (例如 Exchange Online Plan 2) 的組織使用者將無法受邀為貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。 若要讓這些使用者使用 Teams，這些使用者必須獲派 Microsoft 365 商務標準版、Office 365 企業版或 Office 365 教育版訂閱。 

## <a name="who-is-a-guest"></a>何謂來賓？

來賓是不屬於員工、學生或組織成員的人員。 他們沒有貴組織的學校或公司帳戶。 例如，來賓可能包括有合作夥伴、廠商、供應商或顧問。 只要是不屬於貴組織成員的任何人都可以在 Teams 中新增為來賓。 這表示擁有商務帳戶 (也就是 Active Directory 帳戶) 或消費者電子郵件帳戶 (使用 Outlook.com、Gmail.com 或其他) 的任何人都能以來賓身分參與 Teams，擁有團隊和頻道體驗的完整存取權。

若要深入了解來賓可以和不可以使用的功能，請參閱[在 Microsoft Teams 中授權來賓存取](teams-dependencies.md)。 或請查看[比較團隊成員和來賓功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表格。 

最後，小組中的所有來賓都涵蓋與 Microsoft 365 其餘的相容性和審核保護，而且可以在 Azure AD 中進行管理。

## <a name="why-use-guest-access"></a>為什麼要使用來賓存取？

透過來賓存取，使用 Teams 的組織可以向合作夥伴提供團隊、頻道中的文件、資源、聊天和應用程式的存取權，同時又能保有自身公司資料的完整控制權。 

## <a name="understand-the-limitations-for-guests"></a>了解來賓的限制

來賓體驗有刻意設計的限制。 請確定您了解來賓體驗，這樣您才不會嘗試修正不是問題的項目。 以下是 Microsoft 團隊中的來賓無法使用的一些功能清單：

- OneDrive
- 在 Teams 外部執行人員搜尋
- 行事曆、排程會議或會議詳細資料
- PSTN
- 組織圖
- 建立或修改團隊
- 瀏覽團隊
- 將檔案上傳至個人對個人的聊天
- 目前，團隊只支援 [狀態1和省2類型的來賓使用者](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

如需來賓在 Teams 中可以和不可以使用的功能完整清單，請參閱[比較團隊成員和來賓功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表格。 若要深入瞭解 Microsoft 365 層級的來賓存取權，請閱讀 [與組織外部人員](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)共同作業。


## <a name="related-topics"></a>相關主題

[連絡商務產品的客戶支援 - 系統管理說明](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[使用三層保護層級來設定團隊](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
