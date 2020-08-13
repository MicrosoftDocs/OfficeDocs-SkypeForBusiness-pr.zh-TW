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
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: 系統管理員可以了解如何將新的來賓使用者新增至 Microsoft Teams 桌面版和網頁用戶端中的組織，以及 Azure Active Directory B2B 共同作業入口網站。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 099e7a0a1fd7368385d564f46e2df12d5aced4b2
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656124"
---
<a name="add-a-guest-to-a-team"></a>將來賓新增至團隊
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分加入 Teams。

身為系統管理員，您可以透過幾種方式將新來賓使用者新增至組織：
- 全域系統管理員或 Teams 系統管理員與團隊擁有者可在 Teams 用戶端或 Teams 系統管理中心中，將來賓新增至團隊。 若要深入瞭解，請參閱[將來賓新增至團隊](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。 如果您尚未設定來賓存取，請進行[來賓存取檢查清單](guest-access-checklist.md)中的步驟。

> [!NOTE] 
> 啟用 **[系統管理員和來賓邀請者角色中的使用者可邀請]** 時，則不適用。 這是因為 Teams 不支援來賓邀請者角色。

- 透過 Azure Active Directory (Azure AD) B2B 共同作業，將來賓新增到您的組織。 全域系統管理員可以利用 Azure AD B2B 共同作業功能邀請並授權多個外部使用者，方法是將逗號分隔值 (CSV) 檔 (列數上限為 2000 列) 上傳到 B2B 共同作業入口網站。 如需詳細資訊，請參閱 [Azure Active Directory B2B 共同作業](https://go.microsoft.com/fwlink/p/?linkid=826383)。

透過 Azure AD B2B 共同作業功能，組織可為 B2B 使用者強制執行條件式存取和多重要素驗證 (MFA) 原則。 這些原則可以在租用戶層級、應用程式或個別使用者層級強制執行，與為組織全職員工和成員啟用原則的方式相同。 這類原則會在資源組織強制執行。 如需詳細資訊，請參閱[適用於 B2B 共同作業使用者的條件式存取](https://go.microsoft.com/fwlink/?linkid=857454)。 無法封鎖個別來賓使用者。

您透過 Azure AD B2B、Microsoft 365 群組或 SharePoint Online 新增的來賓使用者已準備就緒。 Microsoft 365 或 Office 365 系統管理員或團隊擁有者可將這些來賓新增至個別團隊中。 如果團隊已使用 Microsoft 365 群組，且已將來賓新增至群組，來賓將可存取團隊。 透過 Microsoft 365 群組新增來賓並不會為來賓產生邀請電子郵件，因此團隊中的人員應通知來賓。

> [!NOTE]
> 來賓須遵守 [Microsoft 365 或 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 的服務限制。

您可以在 Azure AD 或 Microsoft 365 安全性中心追蹤來賓的新增狀態。 在 Microsoft Teams 中新增來賓將經過稽核並記錄為「已新增成員至群組」的 Azure AD 群組管理活動。 如需詳細資訊，請參閱[稽核及報告 B2B 共同作業使用者](https://go.microsoft.com/fwlink/p/?linkid=858884)，以及[在 Microsoft 365 安全性中心搜尋稽核記錄](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。


## <a name="more-information"></a>詳細資訊

[在 Microsoft Teams 中授權來賓存取](teams-dependencies.md)</br>
[在 Microsoft Teams 中開啟或關閉來賓存取](set-up-guests.md)</br>
[使用 PowerShell 控制來賓對團隊的存取](guest-access-powershell.md)
