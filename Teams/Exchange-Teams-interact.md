---
title: Exchange 與 Microsoft 團隊如何互動
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 瞭解 Microsoft 團隊與各種 Exchange 設置（例如建立及加入團隊、建立頻道等）之間存在哪些功能。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae03611a684f7f596c185873585c844e30d4330b
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650876"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 與 Microsoft 團隊如何互動

> [!Tip]
> 請觀看下列會話，瞭解團隊如何與 Azure Active Directory 進行互動 (AAD) 、Microsoft 365 群組、Exchange、SharePoint 和商務用 OneDrive： [Microsoft 團隊基礎](https://aka.ms/teams-foundations)

針對完整的團隊體驗，每位使用者都應該啟用 Exchange Online、SharePoint Online 和 Microsoft 365 群組建立。

使用者的 Exchange 信箱可以在線上託管或內部部署。

以 Exchange Online 或 Exchange 專用 vNext 為宿主的使用者可以使用團隊的所有功能。 他們可以建立及加入團隊和頻道、建立及聊天會議、呼叫及聊天、修改使用者設定檔圖片 (如果 Outlook 網頁版信箱原則允許他們這麼做，請) ，然後新增及設定連接器、索引標籤和 bot。 如需可用功能的更完整清單，請參閱下表。

以 Exchange Online 專用 (舊版) 託管的使用者必須同步處理到 Microsoft 365 或 Office 365 上的 Azure Active Directory。 他們可以建立及加入團隊與頻道、新增及設定索引標籤和機器人，以及利用聊天與通話功能。 不過，他們無法修改個人檔案圖片、管理會議、存取 outlook 連絡人或管理連接器。

> [!IMPORTANT]
> 為了與內部部署整合，強烈建議您使用 Exchange Server 2016 或更新版本進行 Exchange 完整傳統混合式部署。 新式混合式支援僅限於空閒/忙碌，不會提供從小組到內部部署的行事曆整合。 如需有關設定混合式部署的詳細資訊，請參閱 [Exchange 伺服器混合式部署](https://docs.microsoft.com/exchange/exchange-hybrid)。

擁有內部部署之信箱的使用者必須同步處理到 Azure Active Directory。 它們可以利用上述案例中的所有功能，但如果符合在已 [託管內部部署的信箱需求](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) 所列的需求，他們就能管理會議。

下表提供根據 Exchange 環境的功能可用性的實用快速參考。

**支援的動作：**

| 使用者的信箱託管于：                                        | eDiscovery       | 法律 &nbsp; 封存    | 留成  | 團隊和頻道管理 | 在團隊中建立及查看會議 | 修改使用者個人資料圖片 | 通話記錄 | 管理連絡人 | 存取 Outlook 連絡人 | 語音信箱  | 新增及設定連接器 | 新增及設定索引標籤 | 新增及設定 bot |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | 是 <sup>1</sup> | 是 <sup>1</sup>   | 是        | 是                   | 是                               | 是<sup>7</sup>             | 是          | 是             | 是 <sup>6</sup>        | 是        | 是                          | 是                    | 是                    |
| **Exchange Online 專用 vNext**                                 | 是 <sup>1</sup> | 是 <sup>1</sup>   | 是        | 是                   | 是                               | 是<sup>7</sup>             | 是          | 是             | 是 <sup>6</sup>        | 是        | 是                          | 是                    | 是                    |
| **Exchange Online 專用-舊版** (同步處理到 Azure AD 所需)   | 是 <sup>1</sup> | 是 <sup>1、2</sup> | 是 <sup>3</sup> | 是                   | 否                                | 否                          | 是          | 是             | 否                      | 是 <sup>4</sup> | 是 <sup>5</sup>                   | 是                    | 是                    |
| **Exchange 內部部署** (同步處理到 Azure AD)  | 是 <sup>1</sup> | 是 <sup>1</sup>   | 是 <sup>3</sup> | 是                   | 是 <sup>8</sup>         | 否                          | 是          | 是             | 否                      | 是 <sup>4</sup> | 是 <sup>5</sup>                   | 是                    | 是                    |

所有主機版選項支援<sup>1</sup>個 eDiscovery 與針對通道訊息規範的法定保留。

<sup>2</sup> 團隊私人聊天訊息尚不支援針對此託管選項進行法律封存。

<sup>3</sup> 保留會針對線上使用者使用陰影信箱來儲存訊息。

<sup>4</sup> 個小組擁有內部部署 Exchange 信箱的使用者可能會在 Outlook 中使用語音信箱及接收語音信箱訊息，但無法在團隊用戶端中查看或播放語音信箱訊息。

<sup>5</sup> 如果小組的其中一個擁有者可以新增連接器，該小組中的其他人都能這樣做，即使他們的信箱是內部部署的。

只有<sup>6</sup>個 [預設連絡人] 資料夾中的連絡人。 不支援存取其他連絡人資料夾或子資料夾。

<sup>7</sup> 個小組都是由租使用者管理員設定的 [Outlook 網頁信箱原則](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) 設定，以控制使用者是否可以變更其個人檔案圖片。 如果在原則中關閉了 **-SetPhotoEnabled** 設定，使用者就無法新增、變更或移除其個人檔案圖片。 例如，如果使用者上傳由貴組織 IT 或人力資源部門核准的個人資料圖片，就不需要採取任何動作。 不過，如果使用者上傳不適當的圖片，請根據貴組織的內部原則進行變更。

<sup>8</sup> 您必須符合在 [建立及查看信箱內部部署區段會議的需求](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) 中所列的需求。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>充分利用 Microsoft 團隊的需求

Microsoft 團隊與數個 Microsoft 365 和 Office 365 服務搭配使用，可為使用者提供豐富的體驗。 若要支援此體驗，您必須啟用某些功能或服務並指派授權。

- 必須為使用者指派 Exchange Online 授權。

- 若要在小組交談中共用和儲存檔案，必須具備 SharePoint Online。 Microsoft 團隊不支援 SharePoint 內部部署。

- 如果使用者想要在聊天中共用檔案，則必須指派 SharePoint Online 授權。 如果使用者未使用 SharePoint Online 授權指派及啟用，他們在 Microsoft 365 或 Office 365 中不會有商務用 OneDrive 儲存空間。 檔案共用功能會繼續在頻道中運作，但是使用者無法在 Microsoft 365 或 Office 365 中的商務用 OneDrive 儲存空間中共用檔案。

- 若要在 Microsoft 團隊中建立小組，必須為使用者啟用 Microsoft 365 群組建立功能。

  > [!IMPORTANT]
  > 如果您在將使用者移至 [ **僅限團隊** ] 模式之後卸載商務用 Skype 用戶端，目前狀態可能會在 Outlook 和其他 Office app 中停止運作。 目前狀態在 Teams 中可正常運作。 若要解決此問題，請在 Microsoft 團隊右上角選取您的個人檔案圖片，然後選取 [ **設定**]。 在 [**一般**] 索引標籤的 [**應用程式**] 底下，選取 [**註冊團隊] 做為 office (的聊天 app 需要重新開機 office 應用程式) ** 選取此選項之後，請關閉並重新開啟所有 Office app （包括 Outlook）。 開啟 Outlook 之後，便可使用目前狀態資訊。

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>針對內部部署的信箱建立及查看會議的需求

如果信箱是內部部署的主機，若要建立及查看會議，必須符合下列需求：

- 需要將所需的小組授權指派給 Azure Active Directory 同步處理的使用者。

- 使用者必須同步處理到 Azure Active Directory。 如需如何使用 Azure AD Connect 與 Azure Active Directory 同步處理的相關資訊，請參閱混合式身分 [識別檔](https://docs.microsoft.com/azure/active-directory/hybrid/)。

- 信箱託管于 Exchange Server 2016 累計更新3或更新版本中。

- 自動探索和 Exchange Web 服務是在外部發佈。

- OAuth 驗證是透過 Exchange 混合式設定向導（執行完整的混合式設定）來設定， (傳統或現代) 。 如果您無法使用混合式設定向導，請按照 [設定 exchange 與 Exchange Online 組織之間的 OAuth 驗證](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述的方式來設定 OAuth。

  > [!NOTE]
  > Exchange 信任來自團隊服務的 OAuth 權杖，稱為 EvoSTS。 步驟1應該足夠，但只需要 EvoSTS;ACS 用於 [行事曆] 中的 [空閒/忙碌] 查閱。

- [Azure AD Connect] 中的 [Exchange 混合式部署] 功能核取方塊已設定。

- 針對 Mac 版的行事曆 app 支援與團隊 Outlook Add-In，Exchange Web 服務 Url 必須在 Exchange 服務主體的租使用者 Azure AD 中設定為 Spn。 此步驟是使用混合式設定向導或遵循 [混合式新式驗證的手動步驟](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)完成。

若要為這些使用者啟用行事曆委派：

- 您也必須完成步驟2-3，如在 [商務用 Skype Online 與 Exchange Server 之間設定整合與 OAuth](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)中所述。這些步驟會提供小組排程應用程式，以確認委派許可權所需的許可權。
 
  > [!NOTE]
  > 步驟2包括 ArchiveApplication 的角色分派，這不是委派所必需的作業。

- 當您代表某人排程會議時需要 Exchange 2013 CU19 或更新版本時，小組排程 Outlook 的增益集。 這是為了支援由我們的服務對信箱進行未驗證的搜尋，以檢查 delegator 信箱的委派許可權。 代理人和 delegator 位置可以是 Exchange 2013 或更新版本，或是 Exchange online，但自動探索必須解析為 Exchange 2013 CU19 或更新版本。

## <a name="additional-considerations"></a>其他考慮

以下是您在組織中實施 Microsoft 團隊時要考慮的一些額外事項。

- 在 Microsoft 團隊中，安全性與合規性功能（例如 eDiscovery、內容搜尋、封存和法律封存）在 Exchange Online 和 SharePoint Online 環境中的運作效果最佳。 在頻道交談中，郵件會在 Exchange Online 中的群組信箱中日記，在這裡可供 eDiscovery 使用。 如果 SharePoint Online 和商務用 OneDrive (使用公司或學校帳戶) 在整個組織和使用者中都是啟用，則團隊內的所有檔案也都能使用這些相容性功能。

- 使用條件式存取控制並保護團隊和 Exchange 中的合規性原則設定。 如需詳細資訊，請參閱 [如何針對團隊使用條件式存取原則？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- 如果您的組織具備合規性需求，以確保所有會議討論都能被發現，您應該在召集人擁有 Exchange 內部部署信箱時，停用 [私人會議]。 如需詳細資訊，請參閱 [允許排程私人會議](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings)。

- 在 Exchange 混合式部署中，無論聊天參與者是否有雲端型信箱或內部部署信箱，都可以搜尋聊天訊息中的內容。 若要深入瞭解，請參閱 [搜尋以雲端為基礎的信箱給內部部署使用者](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)。 若要瞭解如何在團隊中搜尋內容，請參閱 [Microsoft 365 規範中心中的內容搜尋](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)。

## <a name="troubleshooting"></a>疑難排解

如需本主題的完整疑難排解指南，請務必查看 [Microsoft 團隊與 Exchange Server 互動問題的疑難排解](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)。
