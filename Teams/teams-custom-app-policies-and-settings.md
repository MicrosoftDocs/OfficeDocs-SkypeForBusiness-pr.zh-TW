---
title: 管理自訂應用程式原則和設定
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何管理自訂應用程式原則和設定，以控制組織中的誰可以在 Microsoft Teams 中上傳自訂應用程式。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 120f19472a0438c6bb76e98e0c8ef473c012c7b7
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681384"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理自訂應用程式原則和設定

> [!NOTE]
> 若要使用 App Studio，請參[閱 開始Microsoft Teams平臺上的 C#/.NET 和 App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio)上的最後一個步驟尚未運作，因此您必須下載 zip 並以舊方式安裝，[Upload要Microsoft Teams的應用程式套](/microsoftteams/platform/concepts/apps/apps-upload)件。

身為系統管理員，您可以使用自訂應用程式原則和設定來控制組織中誰可以上傳自訂應用程式來Microsoft Teams。 系統管理員決定哪些使用者可以上傳自訂應用程式，而系統管理員和團隊擁有者可以判斷貴組織中的特定團隊是否允許將自訂應用程式新增至其中。  編輯自訂應用程式原則之後，可能需要幾個小時，變更才會生效。 您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。

## <a name="overview-of-custom-apps"></a>自訂應用程式概觀

使用者可以將.zip檔案中的應用程式套件 (上傳至小組或個人) ，藉此將自訂應用程式新增至Teams。 這和透過 Teams App Store 新增應用程式的方式不同。 藉由上傳應用程式套件來新增自訂應用程式，也稱為側載，可讓您在應用程式準備好廣泛散佈之前，于開發時進行測試。 它也可以讓您建立僅供內部使用的應用程式，並與您的小組共用，而不需要提交到Teams應用程式市集中Teams應用程式目錄。

![顯示 App Store 中上傳自訂應用程式選項的螢幕擷取畫面。](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>自訂應用程式原則和設定

三個元件可決定使用者是否可以將自訂應用程式上傳至團隊，讓您能夠精細地控制誰可以將自訂應用程式新增至團隊，以及可以將哪些團隊自訂應用程式新增至：

- [使用者自訂應用程式原則](#user-custom-app-policy)
- [團隊自訂應用程式設定](#team-custom-app-setting)
- [整個組織自訂應用程式設定](#org-wide-custom-app-setting)

這些設定不會影響封鎖協力廠商應用程式的功能。  

### <a name="user-custom-app-policy"></a>使用者自訂應用程式原則

在 [應用程式設定原則](teams-app-setup-policies.md)中，系統管理員可以使用原則設定 **Upload自訂應用程式**，控制使用者是否可以將自訂應用程式上傳至Teams。

如果關閉此設定：

- 使用者無法將自訂應用程式上傳至組織中的任何小組或個人內容。
- 使用者可以根據整個組織的自訂應用程式設定與自訂應用程式互動。

如果已開啟此設定：

- 使用者可以根據整個組織的自訂應用程式設定，將自訂應用程式上傳到允許該應用程式的團隊，以及傳送給擁有者的團隊。
- 使用者可以將自訂應用程式上傳到個人內容。
- 使用者可以根據整個組織的自訂應用程式設定與自訂應用程式互動。

您可以編輯全域應用程式設定原則中的設定，以包含您想要的應用程式。 如果您想要自訂群組織中不同使用者群組的Teams，請建立並指派一或多個自訂應用程式設定原則。

#### <a name="set-a-user-custom-app-policy"></a>設定使用者自訂應用程式原則

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **Teams應用程式**  >  **設定原則**。
2. 按一下 [新增 **]**。
3. 開啟或關閉 **Upload自訂應用程式**。
4. 選擇您要用於原則的任何其他設定。
5. 按一下 [儲存]。

### <a name="team-custom-app-setting"></a>團隊自訂應用程式設定

系統管理員和團隊擁有者可以控制團隊是否允許將自訂應用程式新增至其中。 此設定 **：[允許成員上傳自訂應用程式**]，連同使用者的自訂應用程式原則，決定誰可以將自訂應用程式新增至特定小組。

如果關閉此設定：

- 團隊擁有者可以新增自訂應用程式，如果他們的自訂應用程式原則允許的話。
- 非團隊擁有者的團隊成員無法將自訂應用程式新增至團隊。

如果已開啟此設定：

- 團隊擁有者可以新增自訂應用程式，如果他們的自訂應用程式原則允許的話。
- 如果不是團隊擁有者的團隊成員可以新增自訂應用程式，如果他們的自訂應用程式原則允許的話。

#### <a name="configure-the-team-custom-app-setting"></a>設定團隊自訂應用程式設定

1. 在 Teams 中，移至團隊，按一下 [**更多選項...]**  > **管理團隊**。
2. 按一下 **[設定**]，然後展開 **[成員許可權]**。
3. 選取或清除 [ **允許成員上傳自訂應用程式]** 核取方塊。

    ![顯示團隊自訂應用程式設定的螢幕擷取畫面。](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>整個組織自訂應用程式設定

[[管理](manage-apps.md)應用程式] 頁面上的 [**允許與整個自訂應用程式** 互動] 自訂應用程式設定會套用至貴組織中的每個人，並管理他們是否可以上傳自訂應用程式或與自訂應用程式互動。 此設定會做為使用者和團隊自訂應用程式原則設定的主開/關開關。 它旨在在安全性事件期間做為開啟/關閉主開關。 因此，除非啟用整個組織的自訂應用程式設定，否則使用者和小組自訂應用程式原則設定將不會生效，即使已啟用使用者和小組自訂應用程式原則設定。

#### <a name="configure-the-org-wide-custom-app-setting"></a>設定整個組織的自訂應用程式設定

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 按一下 **[全組織應用程式設定]**。
3. 在 [ **自訂應用程式]** 底下，開啟或關閉 **[允許與自訂應用程式互動]**。

    ![顯示整個組織自訂應用程式設定的螢幕擷取畫面。](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>自訂應用程式原則和設定如何搭配運作

本表格摘要列出自訂應用程式原則和設定、它們的搭配運作方式，以及它們對於控制組織中誰可以上傳自訂應用程式至Teams的組合效果。

例如，假設您只允許團隊擁有者將自訂應用程式上傳到特定團隊。 您會設定下列專案：

- 在系統管理中心開啟 [**允許與自訂應用程式互動**] 設定Microsoft Teams。
- 針對您要限制存取的每個團隊，關閉 [ **允許成員上傳自訂應用程式** ]。
- 在已開啟Upload自訂應用程式設定的Microsoft Teams系統管理中心中建立及指派 **自訂應用程式** 設定原則，並將它指派給團隊擁有者。

|整個組織自訂應用程式設定 |團隊自訂應用程式設定 |使用者自訂應用程式原則 |影響  |
|---------|---------|---------|---------|
| 關閉    | 關閉    | 關閉     |貴組織會封鎖與所有自訂應用程式的互動。 除了 Teams Service 管理員或全域系統管理員之外，任何人都無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。   |
| 關閉     | 關閉     | 開啟        |貴組織會封鎖與所有自訂應用程式的互動。 除了 Teams Service 管理員或全域系統管理員之外，任何人都無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。         |
| 關閉    | 開啟        | 關閉        |貴組織會封鎖與所有自訂應用程式的互動。 除了 Teams Service 管理員或全域系統管理員之外，任何人都無法上傳自訂應用程式。您可以使用Windows PowerShell刪除自訂應用程式。         |
| 關閉    | 開啟      | 開啟       |貴組織會封鎖與所有自訂應用程式的互動。 除了 Teams Service 管理員或全域系統管理員之外，任何人都無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。         |
| 開啟    | 關閉       | 關閉         |  使用者無法上傳自訂應用程式。      |
| 開啟     | 關閉       | 開啟         | 如果使用者是團隊擁有者，他們可以將自訂應用程式上傳到團隊。 如果使用者不是團隊擁有者，他們就無法將自訂應用程式上傳至團隊。 使用者可以在個人內容中上傳自訂應用程式。     |
| 開啟     | 開啟     | 關閉         | 使用者無法上傳自訂應用程式。       |
| 開啟    | 開啟        | 開啟        | 無論使用者是否為團隊擁有者，使用者都可以將自訂應用程式上傳到團隊。 使用者可以在個人內容中上傳自訂應用程式。       |

## <a name="related-topics"></a>相關主題

[在 Teams 中管理應用程式的設定](admin-settings.md)

[在 Teams 中將原則指派給使用者](assign-policies-users-and-groups.md)
