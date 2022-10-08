---
title: 在 Microsoft Teams 中管理應用程式權限原則
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 了解 Microsoft Teams 中的應用程式權限原則，以及如何控制使用者的應用程式可用性。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 24c4b85bb1c4b97597bad6a38e6a67c35dc1abb0
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377041"
---
# <a name="manage-access-to-teams-apps-using-app-permission-policies"></a>使用應用程式許可權原則管理 Teams 應用程式的存取權

身為系統管理員，您可以使用應用程式許可權原則來控制貴組織中每個使用者皆可使用的應用程式。 您設定允許或封鎖所有應用程式或特定應用程式的許可權適用于 [Teams 中的所有應用程式類型](deploy-apps-microsoft-teams-landing-page.md)。 您必須是全域管理員或 Teams 服務系統管理員，才能管理這些原則。

若要允許應用程式，您必須在 [整個組織的應用程式設定](manage-apps.md#manage-org-wide-app-settings)、 [個別應用程式的設定](manage-apps.md#allow-and-block-apps)和應用程式許可權原則中允許它。 雖然其他兩種方法只是允許應用程式在貴組織中使用，但許可權原則可讓您控制哪些使用者可以使用特定應用程式。 您可以建立原則並套用至特定使用者，藉此控制每個使用者和每個 App 的存取權。

Teams 系統管理中心可讓您建立兩種類型的許可權原則：

* `Global (Org-wide default)` 原則預設為存在，並適用于所有使用者。 此原則所做的任何變更都會影響所有使用者，因為此原則預設會套用至所有使用者。
* 系統管理員建立的原則僅適用于套用該原則的使用者。 建立新原則以允許特定使用者或使用者群組使用應用程式。

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="螢幕擷取畫面顯示正在建立新的應用程式許可權原則。" lightbox="media/app-permission-policy.png":::

如果您的組織已經在 Teams 上，您在 [Microsoft 365 系統管理中心的租 **使用者全租使用者設定** 中設定的應用程式設定，會反映在 Teams 系統管理中心的 [[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)] 頁面上的整個組織應用程式設定中。 如果您剛開始使用 Teams，根據預設，所有應用程式都可以在全組織全域設定中使用。 它包括由 Microsoft、協力廠商軟體提供者和您的組織所發佈的應用程式。

> [!NOTE]
> 若要瞭解 Microsoft 365 政府社群雲端高 (GCCH) 和美國商務部 (DoD) 環境中的協力廠商應用程式設定，請參閱 [管理 Microsoft 365 政府版的整個組織應用程式設定](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government)。

## <a name="create-an-app-permission-policy"></a>建立應用程式許可權原則

如果您想要控制可供不同使用者群組使用的應用程式，請使用一或多個自訂應用程式權限原則。 您可以根據應用程式是否由 Microsoft、第三方或您的組織發佈，來建立並指派個別的自訂原則。 如果已在全組織應用程式設定中停用第三方應用程式，您在建立自訂原則之後就無法再變更。

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[許可權原則](https://admin.teams.microsoft.com/policies/app-permission)**。
1. 選取 [新增 **]**。
1. 提供原則的名稱和描述。
1. 在 **[Microsoft 應用程式**]、 **[協力廠商應用程式**] 和 [ **自訂應用程式**] 底下，選取下列其中一個選項：

    * `Allow all apps`
    * `Allow specific apps and block all others`
    * `Block specific apps and allow all others`
    * `Block all apps`

1. 如果您選取了 **[允許特定的應用程式並封鎖所有其他的]**，請新增您要允許的應用程式：

    1. 選取 [允許應用程式 **]**。
    1. 搜尋您要允許的應用程式，然後選取 **[新增]**。 搜尋結果會篩選至應用程式開發人員 (**Microsoft 應用程式**、**第三方應用程式** 或 **自訂應用程式**)。
    1. 選擇一或多個應用程式之後，選 **取 [允許]**。

1. 如果您選取 **[封鎖特定應用程式並允許所有其他** 應用程式]，同樣地搜尋並選擇您要封鎖的應用程式，然後選取 [ **封鎖]**。

1. 選取 [儲存 **]**。

## <a name="edit-an-app-permission-policy"></a>編輯應用程式權限原則

您可以使用 Teams 系統管理中心來編輯全域原則或您所建立的任何自訂原則。

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[許可權原則](https://admin.teams.microsoft.com/policies/app-permission)**。
1. 按一下原則名稱左側來選取原則，然後選取 [編輯 **]**。
1. 進行變更以允許或封鎖三個類別中的特定應用程式。
1. 選取 [儲存 **]**。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>將自訂應用程式權限原則指派給使用者

只有在您將原則套用至使用者或使用者群組時，應用程式許可權原則才會生效。 查看 [將原則指派給使用者的](policy-assignment-overview.md#ways-to-assign-policies)不同方式。

## <a name="considerations-when-using-app-permission-policies"></a>使用應用程式許可權原則時的考慮

下列是使用應用程式許可權原則授與存取權或不允許存取應用程式時的一些考慮事項：

* 只有在您將原則套用至使用者或使用者群組時，應用程式許可權原則才會生效。

* 編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。

* 使用者無法與不允許使用者使用之應用程式的任何功能互動。

* 使用者可以搜尋封鎖的應用程式，並要求系統管理員核准。 系統管理員保留完整的控制權以 [核准或忽略使用者要求](user-requests-approve-apps.md)。

* 應用程式設定原則可與應用程式許可權原則搭配運作。 您從一組允許的應用程式中選取要釘選設定原則的應用程式。 不過，如果使用者的應用程式許可權原則禁止使用已釘選的應用程式，使用者便無法使用該應用程式。

* 應用程式原則適用于使用任何 Teams 網頁版、行動裝置版或桌上出版的使用者。

## <a name="related-articles"></a>相關文章

* [在 Teams 中管理應用程式的設定](admin-settings.md)
* [在 Teams 中將原則指派給使用者](policy-assignment-overview.md)
* [Teams 功能可用性比較](/office365/servicedescriptions/teams-service-description#feature-availability)
