---
title: 管理貴組織的設定
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何開啟或關閉 Microsoft Teams 全組織設定，包括應用程式、外部存取、來賓存取、Teams 設定及 Teams 升級喜好設定。
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b9145854008753cf5c0d1f5915096766689c68b
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739241"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>管理組織的 Microsoft Teams 設定

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 系統管理中心的 Teams 應用程式設定

您可以在 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com)的 **Teams App** 中管理貴組織的應用程式。 例如，您可以設定原則，以控制哪些應用程式可供整個組織或特定 Teams 使用者使用，另外還可以自訂 Teams，將對您使用者而言最重要的應用程式加以釘選。

若要深入了解，請參閱[在 Teams 中管理應用程式的設定](admin-settings.md)。  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 系統管理中心的 Teams 全組織設定

您可以在 Microsoft Teams 系統管理中心控制全組織的使用者設定。 若要編輯全組織的設定，請移至 Microsoft Teams 系統管理中心，然後選取 **[全組織設定]**。 您可以設定下列設定。

### <a name="external-access"></a>外部存取

**外部存取**可讓您的 Teams 和商務用 Skype 使用者與組織或網域外的使用者通訊。 若要設定外部存取，請移至[讓您的 Teams 使用者與其他 Teams 組織的使用者交談及通訊](let-your-teams-users-communicate-with-other-people.md)。

若要新增或封鎖網域：

1. 請選取 **[新增網域]**。
2. 在 [新增網域] 窗格中，輸入網域名稱，然後按一下空格鍵儲存名稱。
3. 選取 **[允許]** 或 **[封鎖]**。
4. 選取 **[完成]** 來儲存變更。 

### <a name="guest-access"></a>來賓存取

Microsoft Teams 中的**來賓存取**可將團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。 任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分參與 Teams，擁有小組聊天、會議及檔案的完整存取權。 如需詳細資訊，請參閱 [Microsoft Teams中的來賓存取](guest-access.md)。

### <a name="teams-settings"></a>Teams 設定

在 **Teams 設定**中，您可以設定小組的功能，包括通知和摘要、電子郵件整合、雲端儲存選項和裝置。

#### <a name="notifications-and-feeds"></a>通知和摘要

您可以在這裡控制是否要在 Teams 中的使用者活動摘要中顯示建議的摘要。 若要深入了解活動摘要，請參閱[探索 Teams 中的活動摘要](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)。

#### <a name="tagging"></a>標記

標記可讓使用者與小組中的部分人員進行通訊。 您可以將標記新增至一或多個小組成員。 新增標記之後，可讓小組的任何人在頻道文章中以 @提及來使用該標記，以便只與指派該標記的人員進行通訊。 使用這些設定來控制可以新增標記的人員，以及如何在組織中使用標記。 若要深入了解，請參閱[如何在 Teams 中管理標記](manage-tags.md)。

#### <a name="email-integration"></a>電子郵件整合

開啟此功能能讓使用者使用頻道電子郵件地址將電子郵件傳送到 Teams 中的頻道。 使用者可以針對任何其擁有之小組的頻道執行這項作業。 使用者也可以將電子郵件傳送到小組中已針對小組成員開啟新增連接器的任何頻道。 若要開啟電子郵件整合，請確認**允許使用者傳送電子郵件到頻道電子郵件地址**為**開啟**。

#### <a name="files"></a>檔案

您可以在這裡開啟或關閉檔案分享和雲端檔案儲存選項。

使用者可以從 Teams 頻道和交談的雲端儲存服務上傳及分享檔案。 Teams 中的雲端儲存選項目前包括 Dropbox、Box、ShareFile、Google Drive和 Egnyte (即將推出)。 開啟貴組織要使用的雲端儲存空間提供者的開關。

#### <a name="organization"></a>組織

您可以在這裡開啟 [組織]**** 索引標籤，其中顯示使用者組織的詳細組織結構。 如需詳細資訊，請參閱[使用 Teams 中的組織索引標籤](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)。

#### <a name="devices"></a>裝置

這些設定會控制參與 Microsoft Teams 會議的 Surface Hub 裝置的資源帳戶行為。 使用這些設定來設定驗證需求、要求內容 PIN，以及開啟 Surface Hub 資源帳戶以傳送訊息。

- **需要第二種形式的驗證以存取會議內容** – 選取使用者輸入內容 PIN 時擁有的存取層級。
- **設定內容 PIN** – 要求使用者輸入此 PIN 以防止未經授權的文件存取。 這可防止未授權的使用者加入即將到來的會議及瀏覽附件。
- **資源帳戶可傳送訊息** – 將此設定**開啟**以允許從 Surface Hub 資源帳戶傳送訊息。

#### <a name="search-by-name"></a>依名稱搜尋

Microsoft Teams 範圍目錄搜尋使用 Exchange 通訊錄原則 (APB) 來允許組織建立虛擬邊界，以控制使用者可以如何尋找組織中的其他使用者並與其通訊。 在下列情況下，您可能會想要使用範圍目錄搜尋：

- 貴組織的租用戶中有多家公司，您想要將其分開。 
- 學校需要限制教職員與學生之間的交談。 

將此設定設為 **[開啟]** 以開啟範圍目錄搜尋。

### <a name="skype-for-business"></a>商務用 Skype

使用此頁面來管理組織中商務用 Skype 使用者的商務用 Skype 功能。 若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](skype-for-business-settings.md)。

### <a name="teams-upgrade"></a>Teams 升級

您可以使用這些設定來設定使用者將如何從商務用 Skype 升級為 Microsoft Teams。 

#### <a name="coexistence-mode"></a>共存模式
您可以指定共存模式： 

- **僅 Teams**
- **共存** (Teams 和商務用 Skype 將共存)
- **僅商務用 Skype**
- **商務用 Skype 搭配 Teams** (使用者在商務用 Skype 中接收聊天和通話及排程會議，但使用 Teams 進行群組共同作業)
- **商務用 Skype 搭配 Teams 共同作業和會議** (使用者在商務用 Skype 中接收聊天和通話，但使用 Teams 進行群組共同作業及排程會議)

您選擇的共存模式會決定來電與聊天的路由，以及使用者在發起聊天與通話或排程會議時所使用的應用程式。 如需共存模式的詳細資訊，請參閱[解 Microsoft Teams 和商務用 Skype 的共存和互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

#### <a name="app-preferences"></a>應用程式喜好設定

您可以在這裡選擇使用者將用來加入商務用 Skype 會議的應用程式 (商務用 Skype 或 [Skype 會議 App](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5))。 此設定不依賴共存模式設定。


#### <a name="network-planner"></a>網路規劃中心

網路規劃中心能協助您判斷和整理用於連接組織間 Teams 使用者所需的網路需求。  了解如何[使用 Microsoft Teams 的網路規劃中心](https://docs.microsoft.com/microsoftteams/network-planner)。

您也可以選取 [為商務用 Skype 使用者在背景下載 Teams 應用程式] 選項。  根據預設，此設定會設為 [開啟]。 啟用此設定後，便會為在 Windows 電腦上執行商務用 Skype 應用程式的使用者在背景下載 Teams 應用程式。 若使用者的共存模式為 [僅 Teams] 或在商務用 Skype 中已啟用擱置升級的通知時，便會發生此情況。


## <a name="how-can-i-tell-which-features-are-available"></a>如何判斷哪些功能可供使用？

如需 Teams 新功能的相關資訊，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)。 如需新功能與即將推出的功能的詳細資訊，請參閱 Teams [新增功能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)頁面，以及 Teams 的 [Microsoft Teams 技術社群部落格](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)。 

## <a name="more-information"></a>詳細資訊

如需哪些角色可以執行系統管理功能的相關資訊，請參閱[使用 Microsoft Teams 系統管理員角色來管理 Teams](using-admin-roles.md)。
