---
title: 管理自訂和側載的應用程式原則和設定
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 瞭解如何管理原則和設定，以控制組織中的誰可以側載應用程式及上傳自訂應用程式。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 818d9b8a64f4a80d8838e368d837a501123976e6
ms.sourcegitcommit: d95a3408e31d3dec37c534c110b09a8847bec724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2022
ms.locfileid: "69156809"
---
# <a name="manage-custom-and-sideloaded-apps-in-teams-admin-center"></a>在 Teams 系統管理中心管理自訂和側載應用程式

Microsoft Teams 可讓組織內部的開發人員為組織內部使用者建置、測試及部署自訂應用程式。 這類應用程式稱為自訂應用程式或商務 (LOB) 應用程式。 貴組織可能會針對組織特定的需求委託建立自訂應用程式。 系統管理員會使用各種設定和原則控制自訂應用程式的推出和許可權。

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="顯示如何在全組織設定面板中允許組織中的自訂應用程式的螢幕擷取畫面。" lightbox="media/custom-app-orgwide-setting.png":::

允許使用自訂應用程式之後，使用者可以在 Teams 市集的左側導覽中選取 **[為您的組織打造** ] 來找到它。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 傳統型應用程式中 Teams 市集中自訂應用程式的螢幕擷取畫面。" lightbox="media/built-for-your-org2.png":::

身為 Teams 系統管理員，您可以使用自訂應用程式原則和設定來控制組織中誰可以上傳自訂應用程式至 Microsoft Teams。 系統管理員決定可上傳自訂應用程式的使用者，而系統管理員與小組擁有者可判斷貴組織中的特定小組是否可將自訂應用程式新增至其小組。 編輯自訂應用程式的設定原則之後，變更需要幾個小時才會生效。 您必須是全域管理員或 Teams 服務系統管理員，才能管理這些原則。

貴組織內的開發人員可透過將應用程式套件 (.zip 檔案中) 直接上傳至小組或個人內容中，將自訂應用程式新增至 Teams。 這個方法與透過 Teams App Store 新增應用程式的方式不同。 透過上傳應用程式套件新增自訂應用程式 (也稱為側載)，讓貴組織的特定使用者在應用程式就緒廣泛散佈前先測試該應用程式。

<!--- During the creation of an app, the developers create and add an app ID to the manifest file. You can view this external app ID on the Manage apps page after you enable the column `External app ID` from the column settings. You can also view it on the app details page of a custom app. The ID is applicable for custom apps only. --->

## <a name="understand-sideloading-of-custom-apps"></a>瞭解自訂應用程式側載

開發自訂應用程式時，以及在發佈這些應用程式給使用者之前，開發人員會透過將應用程式新增至 Teams 市集進行測試來測試應用程式。 開發人員可以自行或使用指定的使用者群組進行測試，但該應用程式無法透過 Microsoft Store 提供給組織中的其他使用者使用。 此方法稱為側載應用程式，僅適用於自訂應用程式。

開發人員可以側載應用程式，將它提供給特定團隊的成員使用，通常是用來測試開發中的應用程式。 以這種方式使用應用程式會限制應用程式開發人員的使用，而且只要系統管理員允許在 Teams 中側載，就不需要系統管理員核准。

開發人員可以與特定團隊共用側載應用程式，而不需要將它提交到 Teams 應用程式目錄。 它讓側載的自訂應用程式可供少數使用者使用，但無法在貴組織的應用程式市集中提供給所有使用者。

身為系統管理員，您可以不允許所有開發人員側載應用程式。 如果您不允許側載，開發人員仍然可以透過[建立個別的測試租用戶](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)來測試其應用程式。 自訂應用程式開發完成後，開發人員會要求系統管理員將自訂應用程式發佈給使用者。 如需詳細資料，請參閱 [如何發佈自訂應用程式](/microsoftteams/upload-custom-apps)。 身為系統管理員，您可以允許 (或封鎖) 所有使用者或特定使用者使用自訂應用程式。

## <a name="app-setup-policy-and-settings-for-custom-apps"></a>自訂應用程式的應用程式設定原則和設定

三個設定決定使用者是否可以將自訂應用程式上傳至小組。 它可讓系統管理員精細地控制誰可以將自訂應用程式新增至團隊，以及可以將哪些團隊自訂應用程式新增至其中。 這些設定不會影響封鎖第三方應用程式的功能。

* [自訂應用程式的使用者應用程式設定原則設定](#user-app-setup-policy-settings-for-custom-apps)
* [小組自訂應用程式設定](#team-custom-app-setting)
* [全組織的自訂應用程式設定](#org-wide-custom-app-setting)

### <a name="user-app-setup-policy-settings-for-custom-apps"></a>自訂應用程式的使用者應用程式設定原則設定

在 [應用程式設定原則](teams-app-setup-policies.md)中，系統管理員可以使用 [ **上傳自訂應用程式**] 設定來控制使用者是否可以將自訂應用程式上傳到 Teams。

若已關閉此設定：

* 使用者無法將自訂應用程式上傳至貴組織的任何小組或個人內容中。
* 使用者可根據全組織自訂應用程式設定，與自訂應用程式互動。

若已開啟此設定:

* 使用者可根據全組織自訂應用程式設定，將自訂應用程式上傳至允許的小組，以及使用者為該小組擁有者的小組。
* 使用者可將自訂應用程式上傳至個人內容。
* 使用者可根據全組織自訂應用程式設定，與自訂應用程式互動。

您可以在全域應用程式設定原則中編輯設定，以包括您需要的應用程式。 如果要針對貴組織中的不同使用者群組自訂 Teams，請建立並指派一或多個自訂應用程式設定原則。

#### <a name="set-an-app-setup-policy-settings-for-custom-apps"></a>設定自訂應用程式的應用程式設定原則設定

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[設定原則](https://admin.teams.microsoft.com/policies/app-setup)**。
1. 選取 [新增 **]**。
1. 提供原則的名稱和描述。
1. 開啟或關閉 **[上傳自訂應用程式]** 設定。
1. 選擇您想要用於原則的任何其他設定。
1. 選取 [儲存 **]**。
1. [將原則套用至](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users) 開發自訂應用程式，並允許上傳這些應用程式的使用者。

> [!NOTE]
> 若要變更此設定，請允許 [全組織應用程式設定](manage-apps.md#manage-org-wide-app-settings)中的自訂應用程式。

### <a name="team-custom-app-setting"></a>小組自訂應用程式設定

系統管理員和小組擁有者可控制小組是否允許將自訂應用程式新增至該小組。 設定 **[允許成員上傳自訂應用程式**]，以及使用者的自訂應用程式設定，決定誰可以將自訂應用程式新增至特定團隊。

若已關閉此設定：

* 如果自訂應用程式的應用程式設定原則設定允許，團隊擁有者可以新增自訂應用程式。
* 非小組擁有者的小組成員則無法將自訂應用程式新增至小組。

若已開啟此設定:

* 團隊擁有者可以新增自訂應用程式，如果他們的自訂應用程式設定允許的話。
* 如果不是團隊擁有者的團隊成員可以新增自訂應用程式，如果他們的自訂應用程式設定允許的話。

#### <a name="configure-the-team-custom-app-setting"></a>設定小組自訂應用程式設定

1. 在 Teams 中，移至團隊，然後選取 **[更多選項...**  > **管理團隊**。
1. 選 **取 [設定]** 並展開 **[成員許可權]**。
1. 選取或清除 [允許成員上傳自訂應用程式]**** 核取方塊。

   :::image type="content" source="media/teams-custom-app-policy-and-settings-team-trim.png" alt-text="顯示小組自訂應用程式設定的螢幕擷取畫面。" lightbox="media/teams-custom-app-policy-and-settings-team.png":::

### <a name="org-wide-custom-app-setting"></a>全組織的自訂應用程式設定

在 [[管理應用程式]](manage-apps.md) 頁面上的 **[允許與自訂應用程式互動]** 全組織自訂應用程式設定會套用至貴組織中的所有人，並控管人員是否可上傳或與自訂應用程式互動。 對於與自訂應用程式相關的設定，此設定會做為使用者和小組開啟或關閉的主開關。 其目的是在安全性事件期間做為主控的開/關切換。 使用者和小組自訂應用程式設定只有在您啟用整個組織的自訂應用程式設定後才會生效。

#### <a name="configure-the-org-wide-custom-app-setting"></a>設定全組織自訂應用程式設定

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 選取 **[全組織應用程式設定]**。
1. 在 **自訂應用程式** 底下，開啟或關閉 **[允許與自訂應用程式互動]**。

    :::image type="content" source="media/teams-custom-app-policy-and-settings-org-wide.png" alt-text="顯示全組織自訂應用程式設定的螢幕擷取畫面。":::

## <a name="how-custom-app-policies-and-settings-work-together"></a>自訂應用程式原則和設定如何共同運作

此表格摘要列出自訂應用程式設定、它們如何搭配使用，以及它們對於控制組織中誰可以將自訂應用程式上傳到 Teams 的組合效果。

假設，舉例來說，您想要允許僅限小組擁有者將自訂應用程式上傳至特定小組。 您可以設定下列項目：

* 在 Microsoft Teams 系統管理中心中開啟 [允許與自訂應用程式互動 **]** 設定。
* 為您想要限制存取權的每個小組關閉 [允許成員上傳自訂應用程式 **]**。
* 在已開啟 [**上傳自訂** 應用程式] 設定設定中心的 Microsoft Teams 系統管理中心中建立及指派自訂原則，並將它指派給團隊擁有者。

|全組織的自訂應用程式設定 |小組自訂應用程式設定 |使用者自訂應用程式設定 | 效果  |
|---------|---------|---------|---------|
| 關閉    | 關閉    | 關閉     |已封鎖貴組織與所有自訂應用程式的互動。 除了 Teams 服務系統管理員或全域系統管理員以外，任何人都無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。   |
| 關閉     | 關閉     | 開啟        |已封鎖貴組織與所有自訂應用程式的互動。 除了 Teams 服務系統管理員或全域系統管理員以外，任何人都無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。         |
| 關閉    | 開啟        | 關閉        |已封鎖貴組織與所有自訂應用程式的互動。 除了 Teams 服務系統管理員或全域系統管理員以外，任何人都無法上傳自訂應用程式。您可以使用Windows PowerShell 來刪除自訂應用程式。         |
| 關閉    | 開啟      | 開啟       |已封鎖貴組織與所有自訂應用程式的互動。 除了 Teams 服務系統管理員或全域系統管理員以外，任何人都無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。         |
| 開啟    | 關閉       | 關閉         |  使用者無法上傳自訂應用程式。      |
| 開啟     | 關閉       | 開啟         | 若使用者為小組擁有者，他們可以將自訂應用程式上傳至小組。 若使用者不是小組擁有者，他們無法將自訂應用程式上傳至小組。 使用者可以在個人內容中上傳自訂應用程式。     |
| 開啟     | 開啟     | 關閉         | 使用者無法上傳自訂應用程式。       |
| 開啟    | 開啟        | 開啟        | 使用者可將自訂應用程式上傳至小組，無論使用者是否為小組擁有者。 使用者可以在個人內容中上傳自訂應用程式。       |

## <a name="related-articles"></a>相關文章

* [管理員 Teams 中應用程式的設定](admin-settings.md)。
* [在 Teams 中指派原則給使用者](assign-policies-users-and-groups.md)。
