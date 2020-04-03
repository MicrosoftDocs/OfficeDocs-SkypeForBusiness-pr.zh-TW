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
ms.openlocfilehash: 68468455da96fc3b2790a832b6732d7211bd7733
ms.sourcegitcommit: dc6108917392754d950cea47b92f871211bf4212
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131141"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange 與 Microsoft 團隊如何互動

> [!Tip]
> 請觀看下列會話，瞭解團隊與 Azure Active Directory （AAD）、Office 365 群組、Exchange、SharePoint 和商務用 OneDrive 的互動方式： [Microsoft 團隊的基礎](https://aka.ms/teams-foundations)

為了獲得完整的 Teams 體驗，每個使用者都應能夠建立 Exchange Online、SharePoint Online 和 Office 365 群組。

使用者的 Exchange 信箱可以在線上託管或內部部署。 不過，某些功能需要與您的 Office 365 租使用者進行混合式部署。

以 Exchange Online 或 Exchange 專用 vNext 為宿主的使用者可以使用團隊的所有功能。 他們可以建立及加入團隊和頻道、建立及觀看會議、呼叫及聊天、修改使用者設定檔圖片（如果 Outlook 網頁版信箱原則允許他們這麼做），以及新增及設定連接器、索引標籤和 bot。

以 Exchange Online 專用（舊版）託管的使用者必須同步處理到 Office 365 上的 Azure Active Directory。 他們可以建立及加入團隊與頻道、新增及設定索引標籤和機器人，以及利用聊天與通話功能。 不過，他們無法修改個人檔案圖片、管理會議、存取 outlook 連絡人或管理連接器。

擁有內部部署之信箱的使用者必須同步處理到 Azure Active Directory。 他們可以使用上述案例中的所有功能，此外還可以變更使用者設定檔圖片（如果 Outlook 網頁版信箱原則允許他們這麼做），以及管理會議，提供 Exchange Server 2016 （累加更新3）或更新版本，都是在內部部署執行。

下表提供根據 Exchange 環境的功能可用性的實用快速參考。


**支援的動作：**

| 使用者的信箱託管于： | eDiscovery| 法律&nbsp;封存 | 留成| 團隊和頻道管理 |在團隊中建立及查看會議| 修改使用者個人資料圖片 | 通話記錄 | 管理連絡人 | 存取 Outlook 連絡人 | 語音信箱 |新增及設定連接器|新增及設定索引標籤|新增及設定 bot| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|是<sup>2</sup>|是<sup>2</sup>|是|是|是|是<sup>8</sup>|是|是|是<sup>7</sup>|是|是|是|是|
|**Exchange Online 專用 vNext**|是<sup>2</sup>|是<sup>2</sup>|是|是|是|是<sup>8</sup>|是|是|是<sup>7</sup>|是|是|是|是|
|**Exchange Online 專用–傳統**版（需要同步處理到 Azure AD）|是<sup>2</sup>|是<sup>2、3</sup>|是<sup>4|是|否|否|是|是|否|是<sup>5|是<sup>6|是|是|
|**Exchange 內部部署**（需要同步處理到 Azure AD）|是<sup>2</sup>| 是<sup>2、3</sup> |是<sup>4|是|是（Exchange 2016 CU3 +）|是<sup>8</sup> （EXCHANGE 2016 CU3 +）|是|是|否|是<sup>5|是<sup>6|是|是|

支援<sup>1</sup>個 EXCHANGE 2016 CU3 及以上版本。  

在所有託管選項中，都支援針對通道訊息的相容性啟用<sup>2</sup>個 EDiscovery 和法律封存。

<sup>3</sup>團隊私人聊天訊息尚不支援針對此託管選項進行法律封存。

<sup>4</sup>保留會針對線上使用者使用陰影信箱來儲存訊息。 [Microsoft 團隊支援針對 Exchange 混合式環境中的團隊使用者使用 eDiscovery](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)。

具有內部部署 Exchange 信箱的<sup>5 個</sup>小組使用者可能會在 Outlook 中使用語音信箱及接收語音信箱訊息，但無法在團隊用戶端中查看或播放語音信箱訊息。

<sup>6</sup>如果小組的其中一個擁有者可以新增連接器，該小組中的其他人都能這樣做，即使他們的信箱是內部部署的。

只有<sup>7</sup>個 [預設連絡人] 資料夾中的連絡人。 不支援存取其他連絡人資料夾或子資料夾。

<sup>8 個</sup>團隊會將 Outlook 設為租使用者管理員設定的[Outlook 網頁信箱原則](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)設定，以控制使用者是否可以變更其個人檔案圖片。 如果在原則中關閉了 **-SetPhotoEnabled**設定，使用者就無法新增、變更或移除其個人檔案圖片。 例如，如果使用者上傳由貴組織 IT 或人力資源部門核准的個人資料圖片，就不需要採取任何動作。 不過，如果使用者上傳的圖片不適當，請根據貴組織的內部原則變更圖片。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>充分利用 Microsoft 團隊的需求

Microsoft 團隊可搭配數種 Office 365 服務使用，為使用者提供豐富的體驗。 若要支援此體驗，您必須啟用某些功能或服務並指派授權。

- 若要在小組交談中共用和儲存檔案，必須具備 SharePoint Online。 Microsoft 團隊不支援 SharePoint 內部部署。

- 如果使用者想要在聊天中共用檔案，則必須指派 SharePoint Online 授權。 如果使用者未使用 SharePoint Online 授權指派及啟用，他們在 Office 365 中就沒有商務用 OneDrive 儲存空間。 檔案共用功能會繼續在頻道中運作，但是使用者無法在 Office 365 中的商務用 OneDrive 儲存空間中共用檔案。

- 若要在 Microsoft 團隊中建立小組，必須為使用者啟用 Office 365 群組建立功能。

- 若要讓 Microsoft 團隊與 Exchange 內部部署搭配運作，您必須按照[設定 exchange 與 Exchange Online 組織之間的 OAuth 驗證](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述的方式來設定新的 Exchange OAuth 驗證通訊協定。

> [!NOTE]
>針對 Exchange 內部部署與團隊整合，必須針對 AAD 同步處理的使用者指派所需的授權。

> [!IMPORTANT]
> 如果您在將使用者移至 [**僅限團隊**] 模式之後卸載商務用 Skype 用戶端，目前狀態可能會在 Outlook 和其他 Office app 中停止運作。 目前狀態在 Teams 中可正常運作。 若要解決此問題，請在 Microsoft 團隊右上角選取您的個人檔案圖片，然後選取 [**設定**]。 在 [**一般**] 索引標籤的 [**應用程式**] 底下，選取 **[以 Office 聊天應用程式註冊團隊（需要重新開機 office 應用程式）**]。 選取此選項之後，請關閉並重新開啟所有 Office app （包括 Outlook）。 開啟 Outlook 之後，便可使用目前狀態資訊。

## <a name="additional-considerations"></a>其他考慮

以下是您在組織中實施 Microsoft 團隊時要考慮的一些額外事項。

- 在 Microsoft 團隊中，安全性與合規性功能（例如 eDiscovery、內容搜尋、封存和法律封存）在 Exchange Online 和 SharePoint Online 環境中的運作效果最佳。 在頻道交談中，郵件會在 Exchange Online 中的群組信箱中日記，在這裡可供 eDiscovery 使用。 如果是在整個組織和使用者啟用 SharePoint Online 和商務用 OneDrive （使用公司或學校帳戶），則小組中的所有檔案也都提供這些規範功能。

- 使用條件式存取控制並保護團隊和 Exchange 中的合規性原則設定。 如需詳細資訊，請參閱[如何針對團隊使用條件式存取原則？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- 如果您的組織具備合規性需求，以確保所有會議討論都能被發現，您應該在召集人擁有 Exchange 內部部署信箱時，停用 [私人會議]。

- 在 Exchange 混合式部署中，無論聊天參與者是否有雲端型信箱或內部部署信箱，都可以搜尋聊天訊息中的內容。 若要深入瞭解，請閱讀在[Office 365 中搜尋內部部署使用者的雲端信箱](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)。 若要瞭解如何在團隊中搜尋內容，請參閱[Office 365 安全性 & 合規性中心中的內容搜尋](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)。

> [!TIP]
> 如需如何使用 Azure AD Connect 與 Azure Active Directory 同步處理的相關資訊，請參閱[整合內部部署身分識別與 Azure Active directory](https://go.microsoft.com/fwlink/?linkid=854600)。
