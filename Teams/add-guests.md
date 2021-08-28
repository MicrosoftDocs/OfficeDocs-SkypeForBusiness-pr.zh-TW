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
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 系統管理員可以瞭解如何在桌面和 Web 用戶端Microsoft Teams新來賓加入組織，Azure Active Directory B2B 共同管理入口網站。
ms.openlocfilehash: e70b32face0948446ba084f0150dc4da7c9a69b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611772"
---
# <a name="add-a-guest-to-a-team"></a>將來賓新增至團隊

任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分加入 Teams。

做為系統管理員，您可以用多種方式將新來賓新加入組織：

- 全域系統管理員或 Teams 系統管理員與團隊擁有者可在 Teams 用戶端或 Teams 系統管理中心中，將來賓新增至團隊。 若要深入瞭解，請參閱[將來賓新增至團隊](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。 如果您尚未設定來賓存取，請透過[在小組中與來賓共同作業](/microsoft-365/solutions/collaborate-as-team)步驟設定。

- 透過 Azure Active Directory (Azure AD) B2B 共同作業，將來賓新增到您的組織。 若要瞭解詳細資料，請參閱 [快速入門：在 Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)入口網站中新增來賓至您的目錄。

系統管理員還可以透過指派 [來賓邀請者] 角色，將新增來賓到組織的權限委派給其他人。 如需詳細資訊，請參閱[啟用 B2B 外部共同作業和管理可以邀請來賓的使用者](/azure/active-directory/external-identities/delegate-invitations) (部分機器翻譯)。

透過 Azure AD B2B 共同作業功能，組織可為 B2B 使用者強制執行條件式存取和多重要素驗證 (MFA) 原則。 這些原則可以在租用戶層級、應用程式或個別使用者層級強制執行，與為組織全職員工和成員啟用原則的方式相同。 這類原則會在資源組織強制執行。 如需詳細資訊，請參閱[適用於 B2B 共同作業使用者的條件式存取](/azure/active-directory/external-identities/conditional-access)。 無法封鎖個別來賓。

已透過 Azure AD B2B、Microsoft 365群組或 SharePoint新增的來賓已準備就緒。 管理員Microsoft 365團隊擁有者可以將這些來賓新加入各自的團隊。 如果您直接將來賓新增到與團隊相關聯的 Microsoft 365 群組，來賓會取得團隊的存取權，但 Microsoft 365 群組不會產生邀請電子郵件給來賓，因此團隊的某個人應該通知來賓。

> [!NOTE]
> 來賓須遵守 [Microsoft 365 或 Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) 和 [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) 的服務限制。

您可以在 Azure AD 或 Microsoft 365 安全性中心追蹤來賓的新增狀態。 在 Microsoft Teams 中新增來賓將經過稽核並記錄為「已新增成員至群組」的 Azure AD 群組管理活動。 有關詳細資料，請參閱稽核及報告 [B2B 共同合作使用者](/azure/active-directory/external-identities/auditing-and-reporting) ，以及搜尋合規性中心的 [稽核記錄](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。


## <a name="related-topics"></a>相關主題

[在 Microsoft Teams 中授權來賓存取](teams-dependencies.md)

[在 Microsoft Teams 中開啟或關閉來賓存取](set-up-guests.md)