---
title: Microsoft Teams 中的聊天、團隊、頻道和應用程式
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: 包含逐步指導，以在 Microsoft Teams 中為聊天、團隊、應用程式和頻道設定 Teams 設定。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
- seo-marvel-apr2020
- seo-marvel-may2020
appliesto: Microsoft Teams
ms.openlocfilehash: dd54d3eb8f7512a9e0f5bc7491decb2b080944b6
ms.sourcegitcommit: 167868ad6fc02676cfdade5d498e7c4e09778bec
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69190334"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Microsoft Teams 中的聊天、團隊、頻道和應用程式

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

若要開始使用，請觀看我們的簡短 Teams 聊天、團隊和頻道影片 (4 分 30 秒)：

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj?autoplay=false]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> 建議您一開始推出 Teams 時能夠包含我們的精選應用程式，例如 Planner。 在您推動 Teams 採用時新增其他 [Teams 應用程式](deploy-apps-microsoft-teams-landing-page.md) 。

 > [!Note]
 > 如需有關不同平台上 Teams 功能的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="chat-deployment-prerequisites"></a>聊天部署必要條件

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|問問自己|動作 |
|------------|-------|
|我的組織是否已準備好要推出 Teams？|若要回答此問題，請參閱： <ul><li>[針對 Teams 準備組織的網路](prepare-network.md)</li><li>[URL 和 IP 位址範圍](office-365-urls-ip-address-ranges.md)</li><li>[在建立團隊時規劃 Microsoft 365 群組](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>核心部署決策

這些是大部分組織想要變更的聊天、團隊和頻道設定 (如果預設設定不符合他們的需求)。

### <a name="teams-administrators"></a>Teams 系統管理員

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| 問問自己 | 動作 |
|--------------|--------|
|誰將獲指派 Teams 通訊系統管理員角色？|若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。|
|誰將獲指派 Teams 通訊支援工程師角色？|若要指派系統管理員角色，[使用 Azure Active Directory 將系統管理員和非系統管理員角色指派給使用者](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。|
|誰將獲指派 Teams 通訊支援專員角色？||

### <a name="teams-owners-and-members"></a>Teams 擁有者和成員

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|問問自己|動作 |
|------------|-------|
|應該對每個角色指派誰？ | 若要比較每個角色的功能，請參閱[在 Microsoft Teams 中指派團隊擁有者、仲裁者和成員](assign-roles-permissions.md)。
|如何指派使用者角色？ | 若要指派或變更角色，請參閱[指派使用者角色](assign-roles-permissions.md)。
|我需要控制誰可以在頻道中貼文及回覆嗎？ | 若要設定仲裁，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。

### <a name="messaging-policies"></a>訊息原則

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.

|問問自己|動作 |
|------------|-------|
|我要自訂全域訊息原則嗎？|如需使用 Microsoft Teams 系統管理中心來變更全域訊息原則或新增原則的相關資訊，請參閱[在 Teams 中管理訊息原則](messaging-policies-in-teams.md)。|
|我需要多個訊息原則嗎？|若要在 PowerShell 中建立並指派訊息原則，請參閱 [PowerShell 指令碼範例 - 建立並指派訊息原則](scripts/powershell-script-teams-messaging-policy-edu.md)。|
|我如何判斷哪些使用者群組可以獲得哪個訊息原則？|若要了解 CsTeamsMessagingPolicy Cmdlet，請參閱 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)。|

### <a name="external-access"></a>外部存取

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|問問自己|動作 |
|------------|-------|
|<ul><li>我要關閉組織的外部會議和聊天嗎？</li><li>如果啟用，我要限制組織可以與其通訊的網域嗎？</li></ul> |<br>若要開啟或關閉外部會議和聊天，請參閱 [管理外部會議和聊天](manage-external-access.md)。|

### <a name="guest-access"></a>來賓存取

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> 若要深入了解外部存取和來賓存取，請參閱這裡 - [在 Microsoft Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)

|問問自己|動作 |
|------------|-------|
|我要將組織的來賓存取關閉嗎？|若要開啟或關閉來賓存取，請參閱[開啟或關閉 Teams 中的來賓存取](set-up-guests.md)。|
|如果啟用，我將會自訂組織中來賓可使用的功能嗎？|若要自訂來賓存取功能的可用性，請參閱[在 Teams 中授權來賓存取](teams-dependencies.md)。|

### <a name="private-channels"></a>私人頻道

私人頻道允許小組成員的子集在其他小組成員無法查看或存取的私人空間中共同作業。 任何人 (包括來賓) 都可以新增為私人頻道的成員，只要他們已經是小組的成員即可。

|問問自己|動作 |
|------------|-------|
|我想要允許小組擁有者和成員建立私人頻道嗎？|若要為組織設定私人頻道原則，請參閱[在 Microsoft Teams 中管理頻道原則](teams-policies.md)|

### <a name="shared-channels"></a>共用頻道

共用頻道允許您將不是小組成員的人員新增至頻道。 這包括組織外部人員。 共用頻道優於來賓存取的方面在於，組織外部人員不需要在您的目錄中具有來賓帳戶。

|問問自己|動作 |
|------------|-------|
|使用共用頻道與來賓存取的時機為何？|請參閱 [Microsoft Teams 中的共用頻道](shared-channels.md)。|
|<ul><li>我是否將允許小組擁有者建立共用頻道？</li><li>我是否將允許小組擁有者與組織外部人員共用頻道？</li><li>我是否將允許使用者參與組織外部的共用頻道？</li></ul> |<br>若要為組織設定共用頻道原則，請參閱[在 Microsoft Teams 中管理頻道原則](teams-policies.md)。|

### <a name="teams-settings"></a>Teams 設定

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|問問自己|動作 |
|------------|-------|
|我要自訂組織的 Teams 設定嗎？ | 若要了解 Teams 設定以及如何加以自訂，請參閱 [Teams 設定](enable-features-office-365.md#teams-settings)。|

### <a name="teams-clients"></a>Teams 用戶端

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|問問自己|動作 |
|------------|-------|
|我要自訂組織的 Teams 用戶端可用性嗎？|請查看 [Teams 應用程式的硬體需求](hardware-requirements-for-the-teams-app.md)。 |
|我要自訂組織的 Teams 用戶端設定嗎？|了解如何[使用 MSI 安裝 Teams](msi-deployment.md)。|

### <a name="teams-usage-reporting"></a>Teams 使用情況報告

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|問問自己|動作 |
|------------|-------|
|<br> 誰需要查看 Teams 使用情況報告，以及他們是否具備檢視報告的正確角色？ |<ul><li>如果使用者不是系統管理員，請[指派報告讀取者角色](teams-activity-reports.md#reports-reader-role)。</li><li>請參閱[角色和使用權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)和[檢視和指派角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)來了解如何在 Azure Active Directory 中指派系統管理員角色。|

### <a name="teams-default-apps"></a>Teams 預設應用程式

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.

若要深入瞭解如何在 Teams 中推出和管理應用程式，請參閱我們深入的 [應用程式管理](deploy-apps-microsoft-teams-landing-page.md) 指導方針。

## <a name="additional-deployment-decisions"></a>其他部署決策

根據組織的需求和組態而定，您可能會想要變更這些設定。

### <a name="teams-licensing"></a>Teams 授權

Teams 會隨著許多 Microsoft 365 授權提供。

|問問自己|動作 |
|------------|-------|
|我的使用者是否擁有使用我要推出的 Teams 所有功能所需的授權？ | 若要深入瞭解授權需求，請參閱 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)。|

### <a name="exchange-and-sharepoint-interoperability"></a>Exchange 和 SharePoint 互通性

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|問問自己|動作 |
|------------|-------|
| 我是否能部署我目前使用 Exchange 和 SharePoint 部署所需的 Teams 功能？ |如需 Teams 中 Exchange 和 SharePoint 的詳細資訊，請參閱：<ul><li> [Exchange 和 Teams 如何互動](exchange-teams-interact.md)</li><li>[SharePoint Online 和 OneDrive 如何與 Teams 互動](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Teams 的限制和規格

規劃 Teams 的企業部署時，應考慮任何相關的限制和規格，例如團隊中成員人數的上限、使用者可建立的團隊人數上限等等。

|問問自己|動作 |
|------------|-------|
| 隨著我的 Teams 推出，我可能會有哪些限制？ | 若要深入了解，請參閱 [Teams 的限制和規格](limits-specifications-teams.md)。 |

### <a name="urls-and-ports"></a>URL 和連接埠

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|問問自己|動作 |
|------------|-------|
| 我是否需要網際網路存取規則，才能讓使用者能使用 Teams，或是開放必要的最基本連接埠即已足夠？ | 若要深入了解，請參閱 [URL 和 IP 位址範圍](office-365-urls-ip-address-ranges.md)。|

### <a name="governance-naming-conventions-who-can-create-teams"></a>控管 (命名慣例，可建立團隊的人員)

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.

| 問問自己 | 動作 |
|--------------|--------|
|我是否需要對可以建立團隊的人員實作控制？| 請閱讀[規劃 Teams 中的控管](plan-teams-governance.md)。|
|我是否需要對團隊的命名方式實作控制？|請閱讀[在 Azure AD 中對 Microsoft 365 群組強制執行命名原則](/azure/active-directory/users-groups-roles/groups-naming-policy)。|

### <a name="teams-application-policy-side-rail-control"></a>Teams 應用程式原則 (側邊欄控制)

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| 問問自己 | 動作 |
|--------------|--------|
|我應該建立預先設定的釘選 Teams 應用程式集嗎？ | 請閱讀[在 Teams 中管理應用程式的設定](admin-settings.md)。|
|我如何決定哪些群組會收到這些應用程式群組？|請閱讀 [Teams 應用程式權限和考量](app-permissions.md)。|

### <a name="archiving-and-compliance"></a>封存與合規性

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| 問問自己 | 動作 |
|--------------|--------|
|我需要設定團隊保留嗎？|若要設定保留原則，請參閱[設定 Teams 保留原則](retention-policies.md)。|
|我需要設定團隊封存嗎？|若要封存或還原團隊，請參閱[封存或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。|
|我需要設定額外的合規性設定嗎？|如需安全性和合規性的詳細資訊，請參閱 [Teams 的安全性與合規性概觀](security-compliance-overview.md)。|

### <a name="conditional-access"></a>條件式存取

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| 問問自己 | 動作 |
|--------------|--------|
|<br>我需要為 Teams 設定條件式存取嗎？|<ul><li>若要了解存取原則的運作方式，請參閱[條件式存取原則如何適合 Teams？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>若要為 Teams 設定多重要素驗證 (MFA)，請參閱：<ul><li>[快速入門：透過 Azure Active Directory 條件式存取來要求特定應用程式需要 MFA](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Azure Active Directory 條件式存取設定參考](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>教育版 (EDU)

在教育單位工作的 IT 專業人員可以利用教育版 Teams，該版本提供許多專為與學生、教職員和更廣泛企業的教育特定案例而量身打造的功能。

| 問問自己 | 動作 |
|--------------|--------|
|我要使用教育版特定的 Teams 範本嗎？ |若要深入了解教育版 Teams，請參閱[系統管理員的 Microsoft 教育控管常見問題集](plan-teams-governance-edu.md)。|
|我將部署限定範圍搜尋嗎？|若要設定 Teams 教育版，請參閱[快速入門 - Teams 教育版系統管理員](teams-quick-start-edu.yml)。|
|我要將 Teams 與學校資料同步處理服務整合，以佈建使用者帳戶嗎？|[Teams 教育版管理員的資源](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>政府版 - GCC 考量

Office 365 政府版 - GCC (政府社群雲端) 適合用來滿足在美國聯邦、州、當地、部落或特區政府實體推動 Office 365 部署或處理受限於政府法規和需求的其他實體 IT 專業人員的需求。

| 問問自己 | 動作 |
|--------------|--------|
| 我會需要在 Office 365 政府版 (政府社群雲端環境) 中部署 Teams 嗎? | 如需部署考量，請參閱[規劃 Office 365 政府版 - GCC 部署](plan-for-government-gcc.md)。|

## <a name="next-steps"></a>後續步驟

- 聊天、團隊、頻道和應用程式的[推動採用](adopt-microsoft-teams-landing-page.md)。
- 在您的 Teams 初始推出中包含精選應用程式，例如 Planner。 在您推動 Teams 採用時新增其他 [Teams 應用程式](deploy-apps-microsoft-teams-landing-page.md) 。
- [推出會議和研討會](deploy-meetings-microsoft-teams-landing-page.md)
- [推出雲端語音](cloud-voice-landing-page.md)
