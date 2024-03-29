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
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.guestaccess.overview
- chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Microsoft Teams 中的來賓存取可將團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。
ms.openlocfilehash: 399cd1c0aecb7377292810b26cd123873405f547
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198465"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams 中的來賓存取

透過來賓存取，您可以向組織外部的人員提供團隊、頻道中的文件、資源、聊天和應用程式的存取權，同時又能保有自身公司資料的完整控制權。 請參閱[使用 Microsoft 365 和 Microsoft Teams 設定安全的共同作業](/microsoft-365/solutions/setup-secure-collaboration-with-teams)。 Teams 的來賓存取是一項全組織設定，預設為開啟。 您可以透過使用 [敏感性標籤](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)，控制來賓對個別 Teams 的存取。

> [!NOTE]
> 如果您只想尋找、通話、聊天及設定與其他組織人員的會議，請使用[外部存取](manage-external-access.md)。

來賓是在您組織中沒有學校或公司帳戶的人。 例如，來賓可能包括有合作夥伴、廠商、供應商或顧問。 只要是不屬於貴組織成員的任何人都可以在 Teams 中新增為來賓。 這表示任何擁有商務帳戶（也就是 Azure Active Directory 帳戶）或消費者電子郵件帳戶（使用 Outlook.com、Gmail.com 或其他）的人員都能以來賓身分參與 Teams，擁有對團隊和頻道體驗的存取權。

When you invite a guest to Teams, a guest account is created for them in Azure Active Directory and they are covered by the same compliance and auditing protection as other Microsoft 365 users. Guest access is subject to Azure AD and Microsoft 365 service limits.

The guest experience has limitations by design. For a full list of what a guest can and can't do in Teams, see [Guest access in Microsoft Teams](guest-experience.md).

> [!IMPORTANT]
> Guests follow Teams Org-wide settings for the coexistence Upgrade mode. This can't be changed.

若要比較外部存取 (同盟) 和來賓存取 (並決定您應使用的方式)，請閱讀[在 Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。

Shared channels offer an alternative to guest access, allowing you to invite people outside your organization without requiring a guest account in Azure AD. To compare guest access with shared channels, see [Plan external collaboration](/microsoft-365/solutions/plan-external-collaboration).

若要設定來賓存取，請參閱 [在小組中與來賓共同作業](/microsoft-365/solutions/collaborate-as-team)。 

## <a name="set-up-guest-access"></a>設定來賓存取

Teams 中的來賓存取需要設定 Microsoft 365 中的其他設定，包括在 Azure AD、Microsoft 365 群組和 SharePoint 中的設定。 如果您準備好要開始邀請來賓使用 Teams，請閱讀下列其中一項：

- 若要為 Teams 設定一般使用的來賓存取，請參閱 [在小組中與來賓共同作業](/microsoft-365/solutions/collaborate-as-team)。
- 若要與合作夥伴組織共同作業，使用 Azure Active Directory 並允許來賓自行註冊以取得小組存取，請參閱 [使用受管理來賓建立 B2B 外部網路](/microsoft-365/solutions/b2b-extranet)。

> [!NOTE]
> 如果您是系統管理員，且在 Microsoft Teams 來賓存取方面遭遇問題，請選取下方的 [執行測試 **]**，系統會在 Microsoft 365 系統管理中心填入來賓存取的診斷。 這些測試會檢查您的設定，並快速建議為租用戶啟用來賓存取的下一個步驟。
>> [!div class="nextstepaction"]
>> [執行測試: 來賓存取](https://aka.ms/TeamsGuestAccessDiagDMC)

## <a name="how-a-guest-gets-added-to-a-team"></a>如何將來賓新增至團隊

1. 小組擁有者或 Microsoft 365 系統管理 [將來賓新增至小組](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。
2. 來賓會收到團隊擁有者的歡迎電子郵件，其中包含團隊相關資訊，以及新加入團隊後能期待什麼。
3. 來賓接受邀請。
  在 Azure Active Directory 中擁有公司或學校帳戶的來賓可以接受邀請並直接驗證。 其他使用者會收到一次性密碼以驗證其身分識別 ([一次性密碼驗證](/azure/active-directory/external-identities/one-time-passcode) 必要)。
4. 接受邀請之後，來賓可以[參與小組和頻道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、接收及回應頻道訊息、[存取頻道中的檔案](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、參與交談、加入會議、在文件上共同作業等等。 

在 Teams 中，系統會清楚地識別來賓。 來賓的名稱包括標籤 **(來賓)**，頻道包含一個圖示指出小組中有來賓。 如需詳細資訊，請參閱[來賓體驗像什麼](guest-experience.md)。
  
來賓隨時可以離開 Teams 內的小組。 如需詳細資訊，請參閱[如何離開小組？](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> 離開小組並不會將來賓帳戶直接從貴組織中移除。 必須由 Microsoft 365 全域系統管理員或 Azure AD 系統管理員來完成。

## <a name="licensing-for-guest-access"></a>來賓存取的授權

來賓存取可以搭配所有 Microsoft 365 商務標準版、Microsoft 365 企業版和 Microsoft 365 教育版訂閱使用。 您不需要額外的 Microsoft 365 授權。 [適用於 Azure AD 外部身分的計費模型](/azure/active-directory/b2b/licensing-guidance)適用於 Microsoft 365 中的來賓。 只有組織外部人員可以受邀為來賓。

> [!NOTE]
> Teams 不支援將來賓帳戶轉換成 Azure AD 成員帳戶或將 Azure AD 成員帳戶轉換成來賓。

## <a name="guest-access-reviews"></a>來賓存取權檢閱

您可以使用 Azure AD，為群組中或已指派給應用程式的使用者建立存取權檢閱。 建立週期性的存取權檢閱可以節省您的時間。 如果您需要定期檢閱擁有應用程式、團隊或群組存取權的使用者，您可以定義執行檢閱的頻率。 

您可以自行執行來賓存取權檢閱、要求來賓檢閱自己的存取權，或要求應用程式擁有者或商務決策者執行存取權檢閱。 使用 Azure 入口網站以執行來賓存取權檢閱。 如需其他資訊，請參閱 [使用 Azure AD 存取權檢閱管理來賓存取](/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

## <a name="related-topics"></a>相關主題

[與組織外部的人員共同作業](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[在特定的 Microsoft 365 群組或 Microsoft Teams 小組封鎖來賓](/microsoft-365/solutions/per-group-guest-access)

[建立安全的來賓共用環境](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[連絡商務產品的客戶支援 - 系統管理說明](/microsoft-365/admin/contact-support-for-business-products)

[為 Teams 設定三層保護](/microsoft-365/solutions/configure-teams-three-tiers-protection)
