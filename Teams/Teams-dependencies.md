---
title: 在 Microsoft Teams 中授權來賓存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: 透過四種不同的授權等級管理 Microsoft Teams 的來賓存取功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6bf763caf0b44490ee578f0bf130a1d4db56a3b
ms.sourcegitcommit: 294b32fb06c56a6eefd1cc44cc5bc93555b6503b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845565"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中授權來賓存取
===========================================

為滿足貴組織的需求，您可以透過四種不同的授權等級管理 Microsoft Teams 的來賓存取功能。 所有授權等級都適用於您的 Microsoft 365 或 Office 365 組織。 每個授權等級控制的來賓體驗如下所示：

- **Azure Active Directory**：Microsoft Teams 的來賓存取需要 Azure AD 企業對企業 (B2B) 平台。 此授權等級控制目錄、租用戶和應用程式層級的來賓體驗。
- **Microsoft Teams**：僅控制 Microsoft Teams 中的來賓體驗。
- **Microsoft 365 群組**：控制 Microsoft 365 群組和 Microsoft Teams 中的來賓體驗。
- **SharePoint Online 和商務用 OneDrive**：控制 SharePoint Online、商務用 OneDrive、Microsoft 365 群組和 Microsoft Teams 中的來賓體驗。

這些不同的授權等級能夠讓您彈性設定貴組織的來賓存取。 例如，如果您不想在 Microsoft Teams 中允許來賓使用者，但是想要在貴組織中全面允許來賓使用者，只要在 Microsoft Teams 中關閉來賓存取即可。 另一個範例：您可以啟用 Azure AD、Microsoft Teams 和群組等級的來賓存取，但是接著在符合一或多個準則 (例如資料分類等於機密) 的小組中，停用所選小組的新增來賓使用者功能。 SharePoint Online 和商務用 OneDrive 擁有自己的來賓存取設定，不需要依賴 Microsoft 365 群組。

> [!NOTE]
> 來賓會受 [Microsoft 365 和 Office 365 服務描述](https://go.microsoft.com/fwlink/p/?linkid=282347)和 [Azure AD B2B 共同作業限制](https://go.microsoft.com/fwlink/p/?linkid=853019)中所描述的服務限制。 

以下圖表顯示在 Azure Active Directory、Microsoft Teams 和 Microsoft 365 或 Office 365 之間，來賓存取之授權相依性的授權方式和整合。

![來賓存取的授權相依性圖表。](media/teams_dependencies_image1.png)

以下圖表以高等級的角度，顯示透過一般來賓存取的邀請與兌換流程，使用者體驗搭配權限模型的運作方式。

![邀請與兌換流程圖表](media/authorize-guest-image1.png)

此處請特別注意，應用程式、Bot 和連接器可能需要各自的權限集和/或使用者帳戶專屬的同意。 這些情況可能需要個別授權。 同樣地，SharePoint 可能會針對特定使用者、使用者群組或甚至是在網站層級，強制規定額外的外部共用界限。

以上兩張圖表也可以在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中使用。

## <a name="control-guest-access-in-azure-active-directory"></a>控制 Azure Active Directory 的來賓存取

使用 Azure AD 來判斷外部共同作業者是否能以來賓身分受邀進入您的租用戶，以及採取何種方式。 如需 Azure B2B 來賓存取的詳細資訊，請參閱[什麼是 Azure Active Directory B2B 中的來賓使用者存取權](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)。 如需 Azure AD 角色的詳細資訊，請參閱[從 Azure Active Directory 租用戶中的合作夥伴組織授與權限給使用者](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)。

邀請的設定會套用到租用戶層級，然後在目錄、租用戶和應用程式層級控制來賓體驗。 若要在 Azure 入口網站設定這些設定，前往 **[Azure Active Directory]** > **[使用者]** > **[使用者設定]**，在 **[外部使用者]** 之下，選取 **[管理外部共同作業設定]**。

Azure AD 包含有下列設定可設定外部使用者：

- **來賓使用者存取權限制**：此原則會決定來賓在目錄中的權限。 有三個原則選項。

    - **[來賓使用者的存取權和成員相同 (最包容)]** 設定表示來賓擁有的目錄資料存取權，與目錄中的一般使用者相同。
    - **[來賓使用者對目錄物件的屬性和成員資格擁有有限的存取權]** 設定表示來賓沒有特定目錄工作的權限，例如列舉使用者、群組，或使用 Microsoft Graph 的其他目錄資源。
    - **[來賓使用者存取權受限於其自身目錄物件的屬性和成員資格 (最受限制)]** 設定表示來賓只能存取自己的目錄物件。
    
  若要深入了解，請參閱 [Azure Active Directory 中的預設使用者權限為何？](https://go.microsoft.com/fwlink/?linkid=2135493)
- **[系統管理員與來賓邀請者角色中的使用者可以邀請]**：**[是]** 表示系統管理員和來賓邀請者角色中的使用者將可以邀請來賓加入租用戶。 **[否]** 表示系統管理員和使用者無法邀請來賓加入租用戶。
- **成員可邀請**：若要允許您目錄中的非系統管理員成員邀請來賓，請將此原則設定為 **[是]** (建議使用)。 如果您希望只讓系統管理員新增來賓，可以將此原則設定為 **[否]**。 請記住，設定為 **[否]** 將會限制非系統管理員小組擁有者的來賓體驗；他們只能在已由系統管理員在 AAD 中新增的 Teams 中新增來賓。
- **[來賓可邀請]**：**[是]** 表示目錄中的來賓可以邀請其他來賓，在受 Azure AD 保護的資源 (例如 SharePoint 網站或 Azure 資源) 上共同作業。 **[否]** 表示來賓無法邀請其他來賓與貴組織共同作業。
    > [!IMPORTANT]
    > Teams 目前不支援來賓邀請者角色，因此，即使您將 **[來賓可邀請]** 設定為 **[是]**，來賓仍無法在 Teams 中邀請其他來賓。
 
如需有關控制誰可以邀請來賓的詳細資訊，請參閱[委派 Azure Active Directory B2B 共同作業邀請](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。

> [!NOTE]
> 您也可以管理哪些網域可以做為來賓受邀加入您的租用戶。 請參閱[允許/封鎖來賓獲得 Microsoft 365 群組的存取權限](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)。

您不需要將使用者來賓帳戶手動新增到 Azure AD B2B，因為當您將來賓新增到 Teams 時，帳戶會自動新增到目錄。

### <a name="licensing-for-guest-access"></a>來賓存取的授權
來賓存取的授權是 Azure AD 授權的一部分。 來賓存取隨附於所有 Microsoft 365 商務標準版和 Office 365 企業版訂閱。 如需有關授權的詳細資訊，請參閱 [Azure Active Directory B2B 共同作業授權指引](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。

> [!NOTE]
> 僅擁有獨立版 Office 365 訂閱方案 (例如 Exchange Online Plan 2) 的組織使用者將無法受邀為貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。 若要讓這些使用者使用 Teams，這些使用者必須獲派 Microsoft 365 商務標準版、Office 365 企業版或 Office 365 教育版訂閱。 

## <a name="control-guest-access-in-teams"></a>控制 Teams 的來賓存取

Teams 的來賓存取依預設會關閉。 若要開啟來賓存取，請參閱[開啟或關閉 Microsoft Teams 的來賓存取](set-up-guests.md)。 


## <a name="control-guest-access-in-microsoft-365-groups"></a>控制 Microsoft 365 群組的來賓存取

在 Microsoft 365 群組中，您可以控制貴組織中所有 Microsoft 365 群組和 Microsoft Teams 小組的新增來賓使用者和來賓存取。

1. 使用您的全域系統管理員帳戶登入 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。

2. 在左側，選擇 **[設定]**，然後選取 **[服務]&amp; [增益集]**。

3. 選取 **Microsoft 365 群組**。

     ![[設定] 中的 [Microsoft 365 群組] 螢幕擷取畫面](media/authorize-guest-image2.png)
  
4. 在 [Microsoft 365 群組] 頁面上，根據您是否想讓貴組織外部的小組和群組擁有者存取 Microsoft 365 群組而定，將開關切換為 **[開啟]** 或 **[關閉]**。 按一下或點選 **[讓群組擁有者將貴組織外部的人員新增到群組]** 旁的 **[開啟]**。 如果您將開關切換為 **[開啟]**，您會看到另一個用來控制是否要讓群組和小組擁有者將組織外部人員新增至 Microsoft 365 群組和 Microsoft Teams 的選項。 如果您想讓群組和小組擁有者新增來賓使用者，請將此開關設定為 **[開啟]**。 
 
   ![[Microsoft 365 群組] 面板及選項已開啟的螢幕擷取畫面](media/authorize-guest-image3.png)

這些設定會套用到租用戶層級，控制 Microsoft 365 群組和 Teams 中的來賓體驗。

如需有關群組中的來賓存取，包括來賓存取的運作方式、來賓存取的管理方法以及常見問題的解答等詳細資訊，請參閱 [管理 Microsoft 365 群組中的來賓存取權](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#manage-groups-guest-access)以及[Microsoft 365 群組的來賓存取權](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>控制 SharePoint Online 和商務用 OneDrive 的來賓存取

Teams 需要 SharePoint Online 和商務用 OneDrive 來儲存頻道和聊天交談的檔案和文件。  

如需完整的 Teams 來賓存取體驗，Microsoft 365 及 Office 365 系統管理員必須設定下列設定：

- 在 SharePoint Online：選取 **[現有的來賓]**、**[新的及現有來賓]** 或 **[任何人]**。

    如需詳細資訊，請參閱[開啟或關閉外部共用](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)。

- 在 Microsoft 365 群組：開啟 **[讓群組擁有者將貴組織外部的人員新增到群組]**

    如需詳細資訊，請參閱上述的[控制 Microsoft 365 群組的來賓存取](#control-guest-access-in-microsoft-365-groups)。
  
這些設定會套用到租用戶層級，控制 SharePoint Online、商務用 OneDrive、Microsoft 365 群組和 Teams 中的來賓體驗。

針對連接至 Teams 的小組網站，您可以管理 SharePoint Online 外部使用者設定。 若要深入了解，請參閱[管理 SharePoint 小組網站設定](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。

## <a name="external-access-federation-vs-guest-access"></a>外部存取 (同盟) 與來賓存取

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>相關主題

- [Microsoft 365 來賓共用設定參考](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
