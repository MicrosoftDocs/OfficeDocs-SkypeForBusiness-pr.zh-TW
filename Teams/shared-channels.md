---
title: Microsoft Teams 中的共用頻道 (預覽)
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何使用和管理 Microsoft Teams 中的共用頻道 (預覽)。
ms.openlocfilehash: 3a5b7f1005af95580f56b87188bc8a67325d440d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712114"
---
# <a name="shared-channels-in-microsoft-teams-preview"></a>Microsoft Teams 中的共用頻道 (預覽)

在 Microsoft Teams 中的共用頻道建立共同作業空間，您可以在這裡邀請不在小組中的人員。 只有身為共用頻道擁有者或成員的使用者可以存取該頻道。 雖然來賓 (組織中具有 Azure Active Directory 來賓帳戶的人員) 無法新增到共用頻道，但您可以使用 Azure AD B2B 直接連線來邀請組織外部人員參與共用頻道。

如果您想要與一群不同小組成員的人員共同作業，您可能會想要使用共用頻道。 例如，在同一個專案或產品不同層面工作的工程、銷售和支援人員，可以使用共用頻道來共同作業。

只有共用頻道的成員才能查看以及參與他們所加入的共用頻道。 已連接共用頻道的小組其他成員不會看到該頻道。

共用頻道建立之後，會連結到父系小組，且不能移至其他小組。 此外，共用頻道不能轉換成標準頻道，反之亦然。

## <a name="best-practices-for-the-shared-channels-preview"></a>共用頻道預覽的最佳做法

共用頻道為預覽階段，您必須已設定[Microsoft Teams 公開預覽](/MicrosoftTeams/public-preview-doc-updates)。 如果您想要與其他組織共用頻道，也必須已設定 Teams 公開預覽。

我們建議您為所有使用者啟用預覽。 未啟用預覽的使用者無法建立共用頻道，但仍可以新增到共用頻道。 為所有使用者啟用預覽有助於確保一致的體驗。

## <a name="getting-started-with-shared-channels"></a>開始使用共用頻道

預設會在 Teams 中啟用共用頻道。 您可以選擇人員是否可建立共用頻道、是否可以與組織外部人員共用，以及是否可[建立頻道原則](/MicrosoftTeams/teams-policies)來參與外部共用頻道。

如果您打算與組織外部人員共用頻道，請閱讀[規劃外部共同作業](/microsoft-365/solutions/plan-external-collaboration)，以了解重要的規劃考量。

與組織外部人員共用頻道時，您也需要設定 Azure AD 中的跨租用戶存取設定。 您想要共用頻道的每個組織也必須完成此設定。 請參閱[與頻道中的外部參與者共同作業](/microsoft-365/solutions/collaborate-teams-direct-connect)了解詳細資料。

## <a name="shared-channel-creation"></a>共用頻道建立

只有小組擁有者可以建立共用頻道。 小組成員和來賓無法建立共用頻道。 您可以在組織層級管理建立共用頻道的能力。 使用 [原則](teams-policies.md) 來控制組織中的哪些使用者能夠建立共用頻道。

建立共用頻道的人會成為共用頻道擁有者，只有共用頻道擁有者可以直接新增或移除頻道中的人員。 (您可以新增多個擁有者。) 共用頻道擁有者可以將組織中的任何人新增到他們建立的共同頻道。 共用頻道的成員有安全的交談空間，而且新成員加入之後，他們可以在該共用頻道中查看所有交談 (甚至是舊的交談)。

小組擁有者可以查看其小組中所有共用頻道的名稱，也可以刪除小組中的任何共用頻道。 小組擁有者無法查看共用頻道中的檔案或共用頻道的交談和成員清單，除非他們是該共用頻道的成員。

小組成員只能查看其已加入的共用頻道。

複製小組不會複製相關聯的共用頻道。

## <a name="shared-channel-deletion"></a>共用頻道刪除

已刪除的共用頻道可在刪除後的 30 天內還原。 還原已刪除的共用頻道後，將會還原所有先前 (個人與小組共用) 成員資格。

已刪除的小組可在刪除後的 30 天內還原。 刪除小組時，也會刪除所有共用頻道。 當已刪除的小組還原時，所有共用頻道以及所有共用關聯性都會還原。

當小組封存後，個別共用會維持不變，但與父系小組外的小組共用將會移除。 當已封存的小組未封存時，所有共用頻道只會使用個別共用來還原。

## <a name="adding-and-removing-owners-and-members"></a>新增和移除擁有者和成員

如果共用頻道擁有者是一或多個共用頻道的最後一位擁有者，則無法透過 Teams 用戶端將其移除。

如果最後一個共用頻道擁有者離開貴組織，或是從與小組相關聯的 Microsoft 365 群組中被移除，則會自動將共用頻道的一位成員升級為共用頻道擁有者。 請考慮新增多個擁有者，以避免這種情況。

## <a name="channel-owner-settings"></a>頻道擁有者設定

每個共用頻道都有自己的設定，而頻道擁有者可加以管理，包括新增和移除成員、新增索引標籤、以及監視整個頻道的功能。 這些設定與父系小組設定彼此無關。 共用頻道建立時會繼承父系小組的設定，之後，就可以變更其設定，與父系小組設定互不相干。

共用頻道擁有者可以按一下 [管理頻道 **]**，然後使用 [成員 **]** 和 [設定 **]** 索引標籤來新增或移除成員及編輯設定。

## <a name="shared-channel-owner-and-member-actions"></a>共用頻道擁有者和成員動作

下表概述擁有者、成員、來賓可在共用頻道中執行哪些動作。

|動作  |小組擁有者|小組成員|小組來賓|共用頻道擁有者|共用頻道成員|共用頻道外部參與者|
|---------|---------|---------|---------|---------|---------|---------|
|建立共用頻道|系統管理員控制|系統管理員和小組擁有者控制|否|不適用|否|否|
|刪除共用頻道|是|否|否|是|否|否|
|離開共用頻道|不適用|不適用|不適用|是，除非他們是最後一個擁有者|是|是|
|編輯共用頻道|否|不適用|不適用|是|否|否|
|還原已刪除的共用頻道|是|否|否|是|否|否|
|新增成員|否|不適用|不適用|是|否|否|
|編輯設定|否|不適用|不適用|是|否|否|
|管理索引標籤和應用程式|否|不適用|不適用|是，必須為小組安裝應用程式|頻道擁有者控制|否|

## <a name="shared-channel-sharepoint-sites"></a>共用頻道 SharePoint 網站

每個共用頻道都有[自己的 SharePoint 網站](/SharePoint/teams-connected-sites)。 分隔的網站是為了確保僅限共用頻道的成員才可存取共用頻道檔案。 依預設，這些網站會以文件庫建立，且可以透過[網站管理介面](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04)輕鬆地增強為功能完整的網站。 每個網站都在與父系小組的網站相同的地理區域中建立。 這些輕量型網站擁有自訂範本識別碼 TEAMCHANNEL#0，可讓您透過 PowerShell 和圖形 API 更輕鬆地進行管理。 

> [!NOTE]
> 只有頻道中擁有擁有者或成員許可權的人才能存取共用頻道網站中的內容。 父團隊和系統管理員中的人員無法存取，除非他們也是頻道成員。

共用頻道網站會同步處理來自父系小組網站的資料分類。 網站擁有者和成員群組的成員資格，會與共用頻道的成員資格保持同步。 無法透過 SharePoint 獨立管理共用頻道網站的網站權限。 

Teams 會管理共用頻道網站的生命週期。 如果在 Teams 以外刪除網站，只要共用頻道仍在使用中，就會在 4 小時內自動還原網站。 如果網站已永久刪除，將會為共用頻道佈建新網站。

如果還原共用頻道或含有共用頻道的小組，則會一併還原網站。 如果共用頻道網站已還原，且超過共用頻道的 30 天虛刪除時機，則網站會以獨立網站的方式運作。

## <a name="shared-channel-messages"></a>共用頻道訊息

共用頻道訊息會儲存在與共用頻道相關聯的專用系統信箱中，而不是群組信箱中。

有關執行電子文件探索搜尋共用頻道訊息之詳細資訊，請參閱[在 Microsoft Teams 中舉辦內容的電子文件探索調查](ediscovery-investigation.md)。

## <a name="considerations-around-file-access-in-shared-channels"></a>共用頻道檔案存取權的考量

共用頻道 中的檔案、資料夾和 OneNote 筆記本，可以使用[共用 SharePoint 檔案共用](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c)與頻道外的人員共用。

如果透過 SharePoint 將共用頻道中檔案、資料夾或筆記本的存取權授與使用者，則從小組或共用頻道中移除該使用者並不會移除該使用者對檔案、資料夾或筆記本的存取權。

如果現有的筆記本是以索引標籤的形式新增到共用頻道，則對共用頻道的存取權不會變更，且筆記本會保留其現有的權限。

## <a name="limits-for-shared-channels-preview"></a>共用頻道的限制 (預覽)

下表說明頻道和成員數目上限。

|上限...|值|注釋|
|:---------|:----|:----|
|小組中的成員|25,000|包含小組中的所有使用者，以及共用頻道中的直接成員。|
|每個小組的共用頻道|50|託管並與小組共用。 (在 30 天的修復期間包含已刪除的頻道。)|
|可以與之共用頻道的小組|50|排除父系小組|
|共用頻道中的成員|1,000 名直接成員，包括最多 50 個小組。 (此限制的目的，頻道會以一個成員的計數與每個小組共用)|即時更新一次只能供 25,000 個使用者使用，頻道清單中只會顯示 25,000 個使用者。|

也會有下列限制：

- 除了 Stream、Planner 和 Forms 之外，共用頻道支援其他索引標籤。

- 公開預覽不支援 LOB 應用程式、Bot、連接器和訊息擴充功能。

- 當您從現有小組建立小組時，不會複製現有小組中任何的共用頻道。

- 未接的活動電子郵件中不會包含來自共用頻道的通知。

## <a name="related-topics"></a>相關主題

[B2B 直接連線概述](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[設定 B2B 直接連線的跨租用戶存取設定](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Teams 的小組和頻道概觀](teams-channels-overview.md)

[Microsoft Teams 中的私人頻道](/microsoftteams/private-channels)