---
title: Microsoft Teams 中的資源特定同意
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/26/2022
search.appverid: MET150
description: 了解您需要設定的設定，以控制貴組織中的小組擁有者是否可以同意應用程式。
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd47f8e46147e3b4d30052ff4a1b9fcde6c128e1
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377151"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teams 中的資源特定同意

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams 中的資源特定同意可讓小組擁有者同意應用程式存取團隊資料。 這類存取權的範例包括讀取頻道訊息、建立和刪除頻道，以及建立和移除頻道索引標籤的功能。

身為系統管理員，您可以控制貴組織中的小組擁有者是否可以透過您使用 Azure Active Directory (Azure AD) PowerShell 模組或 Azure 入口網站及 Microsoft Teams 系統管理中心設置的設定來授予同意。  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>設定小組擁有者是否可以同意應用程式

以下是您必須設置的設定，以控制小組擁有者是否可以同意應用程式。 請務必檢視下列所有設定。

### <a name="settings-in-azure-active-directory-portal"></a>Azure Active Directory 入口網站中的設定

下列兩個設定決定小組擁有者是否可以同意應用程式。

> [!IMPORTANT]
> 變更這些設定並不會影響已獲得同意之應用程式的資料存取。 例如，如果您將這些設定設置為禁止小組擁有者授予同意，這些變更不會移除已獲同意的資料存取權。

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>使用者可以同意應用程式代表其設定存取公司資料

此設定會控制貴組織中的使用者是否可以代表自己同意應用程式。 若要讓小組擁有者授予同意，此設定必須設為 **[是]**。 若要管理此設定，請執行下列動作：

1. 在 [Azure 入口網站] 中，移至 **企業應用程式** > **[使用者設定]**。
2. 在 **[企業應用程式**] 底下，將 **[使用者可以同意應用程式代表他們自己存取公司資料**] 設為 **[否]** 或 **[是]**。

您也可以使用 PowerShell 管理此設定。 若要深入了解，請參閱將 [將使用者內容設定為應用程式](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。

#### <a name="the-enablegroupspecificconsent-setting"></a>「EnableGroupSpecificConsent」 設定

此設定會控制貴組織中的使用者是否可以同意他們擁有之群組的應用程式存取公司資料。 必須啟用此設定，小組擁有者才能授予同意。 如需如何使用 PowerShell 管理此設定的步驟，請參閱 [設定群組擁有者同意存取群組資料的應用程式](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 系統管理中心的設定

除了 Azure AD 中的設定、[[管理應用程式]](manage-apps.md) 頁面上的 [全組織應用程式設定](manage-apps.md#manage-org-wide-app-settings)、在 [[管理應用程式]](manage-apps.md#allow-and-block-apps) 頁面上是否封鎖或允許應用程式，以及指派給小組擁有者的 [應用程式權限原則](teams-app-permission-policies.md) 決定小組擁有者是否可以授予同意。

> [!IMPORTANT]
> 變更這些設定並不會影響已獲得同意之應用程式的資料存取。 例如，如果您停用整個組織的第三方應用程式，或如果您封鎖特定應用程式以防止小組擁有者授予同意，這些變更並不會移除已獲得同意的資料存取權。  

#### <a name="the-allow-third-party-apps-option-in-org-wide-app-settings"></a>全組織應用程式設定中的 [允許協力廠商應用程式] 選項

這個全組織應用程式設定會控制貴組織中的使用者是否可以使用第三方應用程式。 此設定必須開啟，才能讓小組擁有者授予同意。 若要管理此設定，請執行下列動作：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 選取 **[全組織應用程式設定** ]，然後在 [ **協力廠商應用程式**] 底下，關閉或開啟 [ **允許協力廠商應用程式]**。

   :::image type="content" source="media/resource-specific-consent-org-wide-setting.png" alt-text="顯示在 Teams 設定中允許協力廠商應用程式的螢幕擷取畫面。":::

您的變更可能需要長達 24 小時才會生效。

#### <a name="allow-or-block-the-app-at-the-org-level"></a>在組織層級允許或封鎖應用程式

當您在 [[管理應用程式]](manage-apps.md#allow-and-block-apps) 頁面上封鎖或允許應用程式時，將對貴組織中的所有使用者封鎖或允許該應用程式。 如果允許該應用程式，小組擁有者只能同意應用程式。 若要允許或封鎖組織層級的應用程式，請執行下列動作：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 在 [管理應用程式] 頁面上，選取應用程式，然後選取 [ **封鎖** ] 來封鎖它，或選取 [ **允許** ] 來允許它。

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>指派給小組擁有者的應用程式權限原則

小組擁有者只能對其應用程式權限原則允許它們執行的應用程式授予同意。 若要檢視和管理指派給小組擁有者的應用程式權限原則，請執行下列動作：

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[使用者]**。
1. 按兩下團隊擁有者的顯示名稱，然後選取 [ **原則]**。
1. 指派給小組擁有者的原則會列在 **[應用程式權限原則**] 下方。

    * 若要指派不同的原則，請選取 **[編輯**]，然後選取您要指派的原則。
    * 若要編輯指派給團隊擁有者的原則設定，請選取原則名稱，然後進行所要的變更。  

## <a name="upload-custom-apps"></a>上傳自訂應用程式

上傳使用資源特定同意的自訂應用程式 (也稱為側載) 時，此應用程式必須來自安裝該應用程式的租用戶。 換句話說，Azure AD 應用程式註冊必須來自此租用戶。 全域系統管理員不受此限制，而且可以直接將自訂應用程式從任何租用戶上傳至小組 (側載) 或租用戶應用程式目錄。

## <a name="related-articles"></a>相關文章

* [可用的 RSC 權限](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Microsoft Graph](https://developer.microsoft.com/graph)
* [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
* [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
