---
title: Exchange 和 Microsoft Teams 如何互動
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 了解 Microsoft Teams 與各種 Exchange 設定 (如建立和加入小組、建立頻道等) 之間存在哪些功能。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 31f468e6e3fea0915322e632ad27f2213d5d63c7
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598362"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 和 Microsoft Teams 如何互動

> [!Tip]
> 觀看以下工作階段以了解 Teams 如何與 Azure Active Directory (AAD)、Microsoft 365 群組、Exchange、SharePoint 和商務用 OneDrive 進行互動：[Microsoft Teams 的基礎](https://aka.ms/teams-foundations)

為了獲得完整的 Teams 體驗，每個使用者都應能夠使用 Exchange Online、SharePoint Online 和 Microsoft 365 群組。

使用者的 Exchange 郵箱可以線上裝載，或內部部署裝載。

裝載於: Exchange Online 或 Exchange 專用 vNext 的使用者可以使用 Teams 的所有功能。 他們可以建立和加入小組和頻道、建立和查看會議、呼叫和聊天、修改使用者設定檔圖片 (如果 Outlook 網頁版郵箱原則允許他們這樣做)，以及新增和設定連接器、索引標籤和機器人。 有關可用功能的更全面清單，請參閱下方表格。

必須將裝載於: Exchange Online 專用 (舊版) 的使用者同步到 Microsoft 365 或 Office 365 上的 Azure Active Directory。 他們可以建立和加入小組和頻道，新增和設定索引標籤和機器人，並使用聊天和通話功能。 但是，他們不能修改使用者設定檔圖片、管理會議、存取 Outlook 連絡人或管理連接器。

> [!IMPORTANT]
> 為了與內部部署整合，強烈建議您使用 Exchange Server 2016 或更高版本進行 Exchange 完全經典混合式部署。 例如，新式混合支援僅限於空閒/忙碌，不會提供從 Teams 到內部部署郵箱的行事曆整合。 有關設定混合式部署的詳細資訊，請參閱 [Exchange Server 混合式部署](/exchange/exchange-hybrid)。

具有內部部署主控的郵箱的使用者必須同步到 Azure Active Directory。 他們可以利用上述案例中的所有功能，但另外，如果滿足[內部部署主控的郵箱要求部分列出的需求](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)，他們可以管理會議。

下表提供了有關基於 Exchange 環境的功能可用性的快速參考。

**支援動作：**

| 使用者的郵箱代管在：                                        | 電子文件探索       | 法務&nbsp;保存措施    | 保留  | 團隊和頻道管理 | 建立和檢視 Teams 中的會議 | 修改使用者設定檔圖片 | 通訊記錄 | 管理連絡人 | 存取 Outlook 連絡人 | 語音信箱  | 新增和設定連接器 | 新增和設定索引標籤 | 新增和設定機器人 |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | 是 <sup>1</sup> | 是 <sup>1</sup>   | 是        | 是                   | 是                               | 是<sup>7</sup>             | 是          | 是             | 是 <sup>6</sup>        | 是        | 是                          | 是                    | 是                    |
| **Exchange Online 專用 vNext**                                 | 是 <sup>1</sup> | 是 <sup>1</sup>   | 是        | 是                   | 是                               | 是<sup>7</sup>             | 是          | 是             | 是 <sup>6</sup>        | 是        | 是                          | 是                    | 是                    |
| **Exchange Online 專用 – 舊版** (需要同步到 Azure AD)  | 是 <sup>1</sup> | 是 <sup>1，2</sup> | 是 <sup>3</sup> | 是                   | 否                                | 否                          | 是          | 是             | 否                      | 是 <sup>4</sup> | 是 <sup>5</sup>                   | 是                    | 是                    |
| **Exchange 內部部署** (同步到 Azure AD) | 是 <sup>1，9</sup> | 是 <sup>1</sup>   | 是 <sup>3</sup> | 是                   | 是 <sup>8</sup>         | 否                          | 是          | 是             | 否                      | 是 <sup>4</sup> | 是 <sup>5</sup>                   | 是                    | 是                    |

<sup>1</sup> 所有代管選項都支援 eDiscovery 和針對管道訊息的合規性保留。

<sup>2</sup> 此主控選項的合法保留尚不支援 Teams 私人聊天訊息。

<sup>3</sup> 保留將為線上使用者使用陰影郵箱來存儲郵件。

<sup>4</sup> 具有內部部署 Exchange 郵箱的 Teams 使用者可以與 Teams 搭配使用語音信箱，並在 Outlook 中接收語音訊息，但無法在 Teams 用戶端中查看或播放語音信箱將。

<sup>5</sup> 如果小組的擁有者之一可以新增連接器，則該團隊中的其他所有人都可以新增連接器，即使他們的郵箱為內部部署主控。

<sup>6</sup> 僅限預設連絡人資料夾中的連絡人。 不支援存取其他連絡人資料夾或子資料夾。

<sup>7</sup> Teams 接受由租用戶管理員設定的 [[Outlook 網頁版信箱原則]](/powershell/module/exchange/client-access/set-owamailboxpolicy) 設定，來控制使用者是否可以變更個人資料相片。 如果在策略中關閉 **-SetPhotoEnabled** 設定，使用者就無法新增、變更或移除其個人檔案圖片，因此如果系統管理員變更相片，就不會將 porfile 圖片同步至團隊。
<sup>8</sup> 您需要滿足[為內部部署主控的的郵箱建立和檢視會議的需求](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)列出的要求。

<sup>9</sup> 也至少需要 Exchange Online 方案 1 授權。 詳細資訊，請參閱 [搜尋內部部署使用者的 Teams 聊天資料](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users)。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>充分利用 Microsoft Teams 的需求

Microsoft Teams 與多個 Microsoft 365 和 Office 365 服務合作，為使用者提供豐富的體驗。 要支援這種體驗，您需要啟用某些功能或服務並指派授權。

- 必須為使用者指派 Exchange Online 權限。

- 需要 SharePoint Online 才能在團隊交談中共用和儲存檔案。 Microsoft Teams 不支援 SharePoint 的內部部署。

- 如果使用者要在聊天中共用檔案，則必須為其指派 SharePoint Online 授權。 若使用者並非以 SharePoint Online 進行指派及授權，他們將無法使用 Microsoft 365 或 Office 365 中的 [商務用 OneDrive] 儲存空間。 在通道中仍可繼續使用檔案共用，但若沒有 Microsoft 365 或 Office 365 中的 商務用 OneDrive 儲存空間，使用者便無法在 [聊天] 中分享檔案。

- 使用者必須啟用 Microsoft 365 群組建立才能在 Microsoft Teams 中建立團隊。

  > [!IMPORTANT]
  > 如果您在將使用者移至 **[僅 Teams]** 模式之後解除安裝商務用 Skype 用戶端，則 Outlook 和其他 Office 應用程式中的目前狀態可能會停止運作。 目前狀態在 Teams 中可正常運作。 若要解决此問題，請選取 Microsoft Teams 右上角的個人資料圖片，然後選取 **[設定]**。 在 **[應用程式]** 下的 **[一般]** 索引標籤上，選取 **[將 Teams 登記為 Office 的聊天應用程式] (需要重新啟動 Office 應用程式)**。 選取此選項後，請關閉並重新開啟所有 Office 應用程式 (包括 Outlook)。 開啟 Outlook 後，目前狀態將可用。

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>為內部部署主控的的郵箱建立和檢視會議的需求

如果為內部部署主控的郵箱，則要建立和檢視會議，必須滿足以下要求：

- 需要為 Azure Active Directory 同步使用者指派所需的 Teams 授權。

- 使用者必須同步到 Azure Active Directory。 有關如何使用 Azure AD Connect 與 Azure Active Directory 同步的資訊，請參閱[混合式身分識別檔案](/azure/active-directory/hybrid/)。

- 郵箱託管在 Exchange Server 2016 累積更新 3 或更高版本中。

- 自動探索和 Exchange Web 服務是在外部發佈的。

- OAuth 驗證最好透過執行完全混合式設定 (傳統或新式) 的 Exchange 混合式設定精靈進行設定。 如果無法使用混合式設定精靈，請按照[設定 Exchange 和 Exchange Online 組織之間的 OAuth 驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中的說明設定 OAuth。

  > [!NOTE]
  > Exchange信 任來自 Teams 服務 (稱為 EvoSTS) 的 OAuth 權杖。 第 1 步應該足够了，但是只有 EvoSTS；ACS 用於行事曆中的空閒/忙碌查閲。

- 已設定 Azure AD Connect 中 Exchange 混合式部署功能的核取方塊。

- 對於行事曆應用程式支援和 Mac 版 Teams Outlook 增益集，Exchange Web 服務 URL 必須設定為 Exchange 服務主體的租用戶 Azure AD 中的 SPN。 這一步是透過混合組態精靈完成的，或者遵循[混合式新式驗證的手動步驟](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)來完成的。

要為這些使用者啟用行事曆委派，請執行以下操作：

- 您也必須完成步驟，如在商務用 Skype Online 和 Exchange Server 之間設定整合和 [OAuth 中所述](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises);這些步驟會為 Teams 排程應用程式提供確認代理人許可權所需的許可權。
 
  > [!NOTE]
  > 步驟 2 包括 ArchiveApplication 的角色指派，這不是委派所必需的。

- 當代表其他人排程會議時，Outlook 的 Teams 排程附加元件需要 Exchange 2013 CU19 或更新更新。 這是為了支援我們服務對郵箱進行未驗證的的探索，以檢查委派者郵箱的委派權限。 代理人和委派者位置可以是 Exchange 2013 或更高版本，或 Exchange online，但自動探索必須解析為 Exchange 2013 CU19 或更高版本。

## <a name="additional-considerations"></a>其他考量因素

在貴組織中實行 Microsoft Teams 時，需要考慮一些額外内容。

- 在 Microsoft Teams 中，eDiscovery、內容搜尋、封存和訴訟資料暫留等安全性和合規性功能在 Exchange Online 和 SharePoint Online 環境中效果最佳。 對於頻道交談，訊息會記錄到 Exchange Online 中的群組郵箱，在那裡可以使用 eDiscovery。 如果在整個組織和使用者中啟用了 SharePoint Online 和商務用 OneDrive (使用工作或學校帳戶)，則 Teams 中的所有檔案也可以使用這些符合性功能。

- 使用條件式存取控制和保護 Teams 和 Exchange 中合規性原則的設定。 有關更多資訊，請參閱[條件式存取原則如何為 Teams 工作？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- 如果貴組織有合規性需求以確保所有會議討論都可探索，則如果召集人有 Exchange 內部部署郵箱，則應停用私人會議。 有關詳細資訊，請參閱[允許排程私人會議](./meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)。

- 在 Exchange 混合式部署中，聊天訊息中的內容都是可搜尋的，而不管聊天參與者是使用雲端式郵箱還是內部部署信箱。 若要了解更多資訊，請參閲[搜尋內部部署的雲端式郵箱](/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)。 要瞭解如何在 Teams 中搜尋內容，請閱讀[Microsoft 365 合規性中心中的內容搜尋](/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)。

- 對於目前狀態，Microsoft Teams 必須檢查郵箱是裝載於 Exchange Online 還是内部部署。 然後服務决定存取郵箱的位置。 若要使 Teams 服務能够透過對 Exchange Online 服務的 REST API 呼叫檢查郵箱位置，您必須透過執行 Exchange 混合組態精靈來部署 Exchange 混合環境，如[使用混合組態精靈建立混合部署](/exchange/hybrid-deployment/deploy-hybrid)中所述。

## <a name="troubleshooting"></a>疑難排解

有關此主題的完整疑難排解指南，請確保查看[Microsoft Teams 和 Exchange Server 互動問題疑難排解](/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)。