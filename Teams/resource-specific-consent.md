---
title: Microsoft Teams中的特定資源同意
author: guptaashish
ms.author: guptaashish
ms.reviewer: nkramer
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解您需要設定的設定，以控制貴組織中的團隊擁有者是否可以同意應用程式。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5ef3f94c511dfe86ab7b153bfa8dd3ea1a04fa
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190494"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teams中的特定資源同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams中的資源特定同意可讓團隊擁有者同意應用程式存取小組資料。 這類存取的範例包括讀取頻道訊息、建立和刪除頻道，以及建立和移除頻道索引標籤的功能。

身為系統管理員，您可以控制貴組織中的團隊擁有者是否可以使用 Azure Active Directory (Azure AD) PowerShell 模組或Azure 入口網站和 Microsoft Teams 系統管理中心，透過您設定的設定來提供同意。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>設定團隊擁有者是否可以同意應用程式

以下是您必須設定的設定，以控制團隊擁有者是否可以同意應用程式。 請務必檢閱下列所有設定。

### <a name="settings-in-azure-ad"></a>Azure AD 中的 設定

下列兩個設定決定團隊擁有者是否可以同意應用程式。

> [!IMPORTANT]
> 變更任何這些設定並不會影響已獲得同意之應用程式的資料存取。 例如，如果您將這些設定設定為防止團隊擁有者同意，這些變更並不會移除已授與的資料存取權。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>[使用者可以同意應用程式代表他們存取公司資料] 設定

此設定會控制貴組織中的使用者是否可以代表其同意應用程式。 若要讓團隊擁有者提供同意，此設定必須設為 **[是]**。 若要管理此設定，請執行下列動作：

1. 在Azure 入口網站中，移至 **Enterprise應用程式**  >  **使用者設定**。
2. 在 **[Enterprise 應用程式**] 底下，將 **[使用者可以代表他們同意存取公司資料的應用程式**] 設為 [**否**] 或 [**是]**。

您也可以使用 PowerShell 管理此設定。 若要深入瞭解，請參閱將 [使用者內容設定為應用程式](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。

#### <a name="the-enablegroupspecificconsent-setting"></a>[EnableGroupSpecificConsent] 設定

此設定會控制貴組織中的使用者是否可以同意他們擁有之群組的應用程式存取公司資料。 必須啟用此設定，團隊擁有者才能提供同意。 如需如何使用 PowerShell 管理此設定的步驟，請參閱設定 [群組擁有者同意存取群組資料的應用程式](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams系統管理中心的設定

除了 Azure AD 中的設定、[[管理應用程式](manage-apps.md)] 頁面上的[整個組織應用程式設定](manage-apps.md#manage-org-wide-app-settings)、在 [[管理應用程式](manage-apps.md#allow-and-block-apps)] 頁面上是否封鎖或允許應用程式，以及指派給團隊擁有者的[應用程式許可權原則](teams-app-permission-policies.md)決定小組擁有者是否可以提供同意。

> [!IMPORTANT]
> 變更任何這些設定並不會影響已獲得同意之應用程式的資料存取。 例如，如果您停用整個組織的協力廠商應用程式，或是您封鎖特定應用程式以防止團隊擁有者同意，這些變更並不會移除已授與的資料存取權。  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>全組織應用程式設定中的 [允許協力廠商應用程式] 設定

這個全組織應用程式設定會控制貴組織中的使用者是否可以使用協力廠商應用程式。 此設定必須開啟，才能讓團隊擁有者提供同意。 若要管理此設定，請執行下列動作：

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **[Teams應用程式**  >  **管理應用程式**]，然後按一下 [全組織 **應用程式設定]**。
2. 在 [ **協力廠商應用程式**] 底下，關閉或開啟 **[允許協力廠商應用程式]**。

    ![[在 Teams 中允許協力廠商應用程式] 設定的螢幕擷取畫面](media/resource-specific-consent-org-wide-setting.png)

您可能需要等候 24 小時，變更才會生效。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>在組織層級允許或封鎖應用程式

當您在 [ [管理應用程式](manage-apps.md#allow-and-block-apps) ] 頁面上封鎖或允許應用程式時，該應用程式會遭到封鎖或允許給貴組織中的所有使用者。 如果允許該應用程式，團隊擁有者只能同意應用程式。 若要允許或封鎖組織層級的應用程式，請執行下列動作：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 在 [管理應用程式] 頁面上，選取應用程式，然後按一下 [ **封鎖** ] 加以封鎖，或按一下 [ **允許** ]。

    ![全組織設定中已封鎖應用程式的螢幕擷取畫面。](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>指派給團隊擁有者的應用程式許可權原則

團隊擁有者只能同意其應用程式許可權原則允許他們執行的應用程式。 若要檢視和管理指派給團隊擁有者的應用程式許可權原則，請執行下列動作：

1. 在 Microsoft Teams系統管理中心的左側導覽中，移至 [**使用者]**。
2. 按兩下團隊擁有者的顯示名稱，然後按一下 [ **原則]**。
3. 指派給團隊擁有者的原則會列在 **[應用程式許可權原則**] 下方。
    - 若要指派不同的原則，請按一下 **[編輯**]，然後選取您要指派的原則。
    - 若要編輯指派給團隊擁有者的原則設定，請按一下原則名稱，然後進行所要的變更。  

## <a name="uploading-custom-apps"></a>上傳自訂應用程式

上傳自訂應用程式 (使用資源特定同意的已知側載) 時，應用程式必須來自其安裝的租使用者。 換句話說，Azure AD 應用程式註冊必須來自此租使用者。 全域系統管理員不受此限制，而且可以直接將自訂應用程式從任何租使用者上傳至小組 (側載) 或租使用者應用程式目錄。

## <a name="related-topics"></a>相關主題

- [可用的 RSC 許可權](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
