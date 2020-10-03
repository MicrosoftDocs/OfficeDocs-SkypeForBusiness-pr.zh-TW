---
title: 將來賓新增至團隊
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 系統管理員可以了解如何將新的來賓使用者新增至 Microsoft Teams 桌面版和網頁用戶端中的組織，以及 Azure Active Directory B2B 共同作業入口網站。
ms.openlocfilehash: e74819ba46af8a9f6bcf3b2198f78354bf7bfb79
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346174"
---
# <a name="add-a-guest-to-a-team"></a>將來賓新增至團隊

任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分加入 Teams。

身為系統管理員，您可以透過幾種方式將新來賓使用者新增至組織：

- 全域系統管理員或 Teams 系統管理員與團隊擁有者可在 Teams 用戶端或 Teams 系統管理中心中，將來賓新增至團隊。 若要深入瞭解，請參閱[將來賓新增至團隊](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。 如果您尚未設定來賓存取，請透過[在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)步驟設定。

- 透過 Azure Active Directory (Azure AD) B2B 共同作業，將來賓新增到您的組織。 如需詳細資訊，請參閱 [快速入門：在 Azure 入口網站中將來賓使用者新增至您的目錄](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。

系統管理員還可以透過指派 [來賓邀請者] 角色，將新增來賓到組織的權限委派給其他人。 如需詳細資訊，請參閱[啟用 B2B 外部共同作業和管理可以邀請來賓的使用者](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) (部分機器翻譯)。

透過 Azure AD B2B 共同作業功能，組織可為 B2B 使用者強制執行條件式存取和多重要素驗證 (MFA) 原則。 這些原則可以在租用戶層級、應用程式或個別使用者層級強制執行，與為組織全職員工和成員啟用原則的方式相同。 這類原則會在資源組織強制執行。 如需詳細資訊，請參閱[適用於 B2B 共同作業使用者的條件式存取](https://go.microsoft.com/fwlink/?linkid=857454)。 無法封鎖個別來賓使用者。

您已透過 Azure AD B2B、Microsoft 365 群組或 SharePoint 新增的來賓使用者已可以開始使用。 Microsoft 365 管理員或團隊擁有者可以將這些來賓新增至其各自的小組。 如果您直接將來賓新增到與團隊相關聯的 Microsoft 365 群組，來賓就會取得該小組的存取權，但 Microsoft 365 群組不會產生邀請電子郵件給訪客，所以小組中的人員應該通知訪客。

> [!NOTE]
> 來賓須遵守 [Microsoft 365 或 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 的服務限制。

您可以在 Azure AD 或 Microsoft 365 安全性中心追蹤來賓的新增狀態。 在 Microsoft Teams 中新增來賓將經過稽核並記錄為「已新增成員至群組」的 Azure AD 群組管理活動。 如需詳細資訊，請參閱 [審核與報告 B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) 共同作業使用者，並 [在規範中心搜尋審核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。


## <a name="related-topics"></a>相關主題

[在 Microsoft Teams 中授權來賓存取](teams-dependencies.md)

[在 Microsoft Teams 中開啟或關閉來賓存取](set-up-guests.md)
