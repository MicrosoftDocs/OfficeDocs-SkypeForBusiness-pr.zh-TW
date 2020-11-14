---
title: Microsoft Teams 中的來賓存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Microsoft Teams 中的來賓存取可將團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。
ms.openlocfilehash: cab51fd9cf0a81c849a0baf379150ccb2e08d818
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030279"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的來賓存取

有了來賓存取權，您就可以為組織外部人員提供對團隊、頻道、資源、聊天和應用程式的存取權，同時維持對公司資料的控制權。

來賓是不屬於員工、學生或組織成員的人員。 他們沒有貴組織的學校或公司帳戶。 例如，來賓可能包括有合作夥伴、廠商、供應商或顧問。 只要是不屬於貴組織成員的任何人都可以在 Teams 中新增為來賓。 這表示任何擁有商務帳戶的人 (也就是， (有 Outlook.com、Gmail.com 或其他) 人的 Azure Active Directory 帳戶) 或消費者電子郵件帳戶時，都可以使用團隊和頻道體驗，在小組中參與來賓。

就像團隊管理員一樣，您可以 [控制來賓可以 (且無法) 在團隊中使用的功能](manage-guests.md)。 團隊中的來賓與其他 Microsoft 365 的相容性和審核保護功能所涵蓋，且可在 Azure AD 中進行管理。 來賓存取受到 Azure AD 和 Microsoft 365 或 Office 365 服務的限制。

來賓體驗有刻意設計的限制。 如需訪客在小組中能及不能執行之動作的完整清單，請參閱 [比較小組成員和來賓的功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)。

> [!IMPORTANT]
> 對於共存的升級模式，來賓存取遵循 Teams 的全組織設定。 這項設定無法變更。

若要比較外部存取 (同盟) 和來賓存取 (並決定您應使用的方式)，請閱讀[在 Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。

## <a name="set-up-guest-access"></a>設定來賓存取權

團隊中的來賓存取需要在 Microsoft 365 中設定其他設定，包括 Azure AD、Microsoft 365 群組和 SharePoint 中的設定。 如果您準備好要開始邀請客人給小組，請閱讀下列其中一項：

- 若要設定供團隊使用的來賓存取權，請參閱 [與團隊中的來賓共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業。
- 若要與使用 Azure Active Directory 的合作夥伴組織共同作業，並允許來賓自行註冊小組存取，請參閱 [使用受管理的來賓建立 B2B extranet](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。

團隊中的來賓存取權是全組織的設定，預設為關閉狀態。 您可以使用 [敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制對個別團隊的來賓存取權。

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>來賓成為小組成員的方式

1. 小組擁有者或 Microsoft 365 系統管理員會 [將來賓新增至小組](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。
2. 來賓會收到來自小組擁有者的歡迎電子郵件，其中具有小組相關資訊，以及現在成為成員預期有什麼優點。
3. 來賓接受邀請。
  在 Azure Active Directory 中擁有公司或學校帳戶的來賓使用者，可以接受邀請並直接進行驗證。 其他使用者傳送一次性傳遞程式碼，以驗證其身分識別 (需要) 的一次性 [密碼驗證](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) 。
4. 接受邀請之後，來賓可以[參與小組和頻道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、接收及回應頻道訊息、[存取頻道中的檔案](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、參與交談、加入會議、在文件上共同作業等等。 

在 Teams 中，系統會清楚地識別來賓。 來賓使用者的名稱包括標籤 **(來賓)** ，頻道包含一個圖示指出小組中有來賓。 如需詳細資訊，請參閱[來賓體驗像什麼](guest-experience.md)。
  
來賓隨時可以離開 Teams 內的小組。 如需詳細資訊，請參閱[如何離開小組？](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> 離開團隊後，不會從組織的目錄中移除來賓帳戶。 這必須由 Microsoft 365 全域管理員或 Azure AD 系統管理員來完成。

## <a name="licensing-for-guest-access"></a>來賓存取的授權

來賓存取包含在所有 Microsoft 365 商務標準版、Microsoft 365 企業版及 Microsoft 365 教育版訂閱中。 不需要額外的 Microsoft 365 授權。 Teams 未限制您可以新增的來賓數量。 不過，可新增至您租用戶的來賓總數可能受到 Azure AD 的付費功能限制。 如需詳細資訊，請參閱 [AZURE AD 外部身分識別的計費模型](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。

> [!NOTE]
> 貴組織中擁有獨立 Microsoft 365 訂閱者案（例如 Exchange Online 方案2）的使用者，不能受到受邀者對您組織的訪客，因為小組會認為這些使用者屬於同一個組織。 若要讓這些使用者使用 Teams，這些使用者必須獲派 Microsoft 365 商務標準版、Office 365 企業版或 Office 365 教育版訂閱。 

## <a name="guest-access-reviews"></a>來賓存取審查

您可以使用 Azure AD 來建立群組成員或指派給應用程式的使用者的存取權審查。 建立週期性存取檢查可節省您的時間。 如果您需要例行查看有權存取應用程式、團隊或群組成員的使用者，您可以定義這些評論的頻率。 

您可以自行執行來賓存取權審查、要求客人審查自己的成員資格，或是要求應用程式擁有者或商業決策人來執行存取審查。 使用 Azure 入口網站執行來賓存取審查。 如需詳細資訊，請參閱 [使用 AZURE AD access 評論管理來賓存取](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

## <a name="related-topics"></a>相關主題

[與組織外部人員共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[封鎖特定 Microsoft 365 群組或 Microsoft 團隊小組的來賓使用者](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[建立安全的來賓共用環境](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[連絡商務產品的客戶支援 - 系統管理說明](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[使用三層保護層級來設定團隊](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
