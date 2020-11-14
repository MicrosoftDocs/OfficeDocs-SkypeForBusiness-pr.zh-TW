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
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 透過四種不同的授權等級管理 Microsoft Teams 的來賓存取功能。
ms.openlocfilehash: 40bc8c68ac3f1ad3117fa47aa0aad5f14ff3be69
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030989"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>在 Microsoft Teams 中授權來賓存取

為了滿足貴組織的需求，您可以透過四種不同的授權層級管理團隊來賓存取的功能和功能。 所有授權等級都適用于您的 Microsoft 365 組織。 每個授權等級控制的來賓體驗如下所示：

- **Azure Active Directory** ：團隊中的來賓存取權依賴 Azure AD 企業對企業 (B2B) 平臺。 此授權等級控制目錄、租用戶和應用程式層級的來賓體驗。
- **團隊** ：只控制團隊中的來賓體驗。
- **Microsoft 365 群組** ：控制 Microsoft 365 群組和團隊中的來賓體驗。
- **Sharepoint 和 OneDrive** ：控制 Sharepoint、OneDrive、Microsoft 365 群組和團隊中的來賓體驗。

這些不同的授權等級能夠讓您彈性設定貴組織的來賓存取。 例如，如果您不想允許團隊中的來賓使用者，但想要讓您的組織全部擁有，只要關閉小組中的來賓存取。 另一個範例：您可以在 Azure AD、團隊和群組階層啟用來賓存取，但在選取的小組中， [停用與一個或多個準則相符的來賓使用者（例如，資料分類等於 [機密](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)]）。 SharePoint 和 OneDrive 有自己的來賓存取設定，而不依賴 Microsoft 365 群組。

如需端對端來賓存取配置指示，請參閱 [與團隊中的來賓共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業。

> [!NOTE]
> 來賓會受 [Microsoft 365 和 Office 365 服務描述](https://go.microsoft.com/fwlink/p/?linkid=282347)和 [Azure AD B2B 共同作業限制](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)中所描述的服務限制。 

下圖顯示如何授與來賓存取授權相依性，以及如何在 Azure Active Directory、團隊及 Microsoft 365 之間整合。

> [!div class="mx-imgBorder"]
> ![來賓存取的授權相依性圖表。](media/teams_dependencies_image1.png)

以下圖表以高等級的角度，顯示透過一般來賓存取的邀請與兌換流程，使用者體驗搭配權限模型的運作方式。

> [!div class="mx-imgBorder"]
> ![邀請與兌換流程圖表](media/authorize-guest-image1.png)

請務必注意，在這裡，應用程式、bot 和連接器可能需要自己的許可權集和/或同意專用於使用者帳戶。 這些情況可能需要個別授權。 同樣地，SharePoint 可能會針對特定使用者、使用者群組或甚至是在網站層級，強制規定額外的外部共用界限。

以上兩張圖表也可以在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中使用。

## <a name="control-guest-access-in-azure-active-directory"></a>控制 Azure Active Directory 的來賓存取

使用 Azure AD 來判斷外部共同作業者是否能以來賓身分受邀進入您的租用戶，以及採取何種方式。 如需 Azure B2B 來賓存取的詳細資訊，請參閱[什麼是 Azure Active Directory B2B 中的來賓使用者存取權](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)。 如需 Azure AD 角色的詳細資訊，請參閱[從 Azure Active Directory 租用戶中的合作夥伴組織授與權限給使用者](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)。

邀請的設定適用于組織階層，並控制目錄和應用程式層級的來賓體驗。 您可以在 [外部共同作業 [設定](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)] 中設定這些設定。

Azure AD 包含有下列設定可設定外部使用者：

- [來賓使用者存取限制](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **[系統管理員與來賓邀請者角色中的使用者可以邀請]** ： **[是]** 表示系統管理員和來賓邀請者角色中的使用者將可以邀請來賓加入租用戶。 **[否]** 表示系統管理員和使用者無法邀請來賓加入租用戶。
- **成員可邀請** ：若要允許您目錄中的非系統管理員成員邀請來賓，請將此原則設定為 **[是]** (建議使用)。 如果您希望只讓系統管理員新增來賓，可以將此原則設定為 **[否]** 。 請記住，設定為 **[否]** 將會限制非系統管理員小組擁有者的來賓體驗；他們只能在已由系統管理員在 AAD 中新增的 Teams 中新增來賓。
- **[來賓可邀請]** ： **[是]** 表示目錄中的來賓可以邀請其他來賓，在受 Azure AD 保護的資源 (例如 SharePoint 網站或 Azure 資源) 上共同作業。 **[否]** 表示來賓無法邀請其他來賓與貴組織共同作業。 即使設定為 **[是]** ，來賓也無法在團隊中邀請其他來賓。
 
如需控制誰可以邀請客人的詳細資訊，請參閱 [啟用 B2B 外部共同作業及管理可以邀請客人的人員](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。

> [!NOTE]
> 您也可以管理哪些網域可以做為來賓受邀加入您的租用戶。 請參閱 [允許或封鎖來自特定組織的 B2B 使用者邀請](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)。

您不需要將使用者來賓帳戶手動新增到 Azure AD B2B，因為當您將來賓新增到 Teams 時，帳戶會自動新增到目錄。

### <a name="licensing-for-guest-access"></a>來賓存取的授權

來賓存取授權使用 Azure AD 外部身分識別定價，且以每月的活躍訪客為基礎。 如需詳細資訊，請參閱 [AZURE AD 外部](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) 身分識別的計費模型。

> [!NOTE]
> 僅擁有獨立版 Office 365 訂閱方案 (例如 Exchange Online Plan 2) 的組織使用者將無法受邀為貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。 若要讓這些使用者使用 Teams，這些使用者必須獲派 Microsoft 365 商務標準版、Office 365 企業版或 Office 365 教育版訂閱。 

## <a name="external-access-federation-vs-guest-access"></a>外部存取 (同盟) 與來賓存取

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>相關主題

- [Microsoft 365 來賓共用設定參考](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[使用 Microsoft 365 設定安全的共同作業](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
