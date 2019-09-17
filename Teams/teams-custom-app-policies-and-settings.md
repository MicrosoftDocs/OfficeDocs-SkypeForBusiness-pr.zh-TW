---
title: 管理 Microsoft 團隊中的自訂應用程式原則和設定
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何管理自訂應用程式原則和設定，以控制貴組織中的哪些人員可以上傳 Microsoft 團隊中的自訂應用程式。
f1keywords:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
ms.openlocfilehash: 90733b43ddb1d94d8c0f763ac048384816681f46
ms.sourcegitcommit: 472825b0f4db1542a5b855d637aa90b4bcd797bc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2019
ms.locfileid: "36993974"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>管理 Microsoft 團隊中的自訂應用程式原則和設定

> [!NOTE]
> 若要使用應用程式 Studio，請參閱[使用 c #/.NET 和 App Studio 的 Microsoft 團隊平臺快速](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio)入門最後一個步驟尚無法運作，因此您必須先下載該 zip，然後在將[應用程式套件上傳到 Microsoft 團隊](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)時將它安裝。

做為管理員，您可以使用自訂的應用程式原則和設定來控制貴組織中的哪些人可以將自訂應用程式上傳到 Microsoft 團隊。 系統管理員決定可以上傳自訂應用程式的使用者，以及系統管理員和小組擁有者可以判斷您組織中的特定團隊是否允許將自訂應用程式新增到他們。  

## <a name="overview-of-custom-apps"></a>自訂應用程式的概覽

使用者可以將自訂 app 新增至團隊，方法是將應用程式套件（在 .zip 檔案中）直接上傳到小組或個人內容。 這與透過 [團隊 app store] 新增應用程式的方式不同。 透過上傳應用程式套件（又稱為邊載）來新增自訂應用程式，可讓您在開發應用程式之前先測試該 app，然後才能廣泛發佈。 它也可讓您建立僅供內部使用的 app，並與您的小組共用該應用程式，而不需提交至 [小組] app 商店中的 [小組] 應用程式目錄。

![螢幕擷取畫面顯示 app store 中的 [上傳自訂應用程式] 選項](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>自訂 app 原則和設定

三個元件會判斷使用者是否可將自訂應用程式上傳至團隊，讓您精細控制哪些人可以將自訂應用程式新增至團隊，以及可將哪些團隊自訂應用程式新增至：

- [使用者自訂 app 原則](#user-custom-app-policy)
- [團隊自訂應用程式設定](#team-custom-app-setting)
- [全組織的自訂應用程式設定](#org-wide-custom-app-setting)

這些設定不會影響封鎖協力廠商應用程式的能力。  

### <a name="user-custom-app-policy"></a>使用者自訂 app 原則

在[應用程式設定原則](teams-app-setup-policies.md)中，系統管理員可以使用原則設定、**允許上傳自訂應用程式**，控制使用者是否能將自訂應用程式上傳給團隊。
 
如果已關閉此設定：

- 使用者無法將自訂應用程式上傳到貴組織中的任何小組或個人內容。
- 根據組織範圍內的自訂應用程式設定，使用者可以與自訂應用程式互動。

如果已開啟此設定：

- 使用者可以將自訂應用程式上傳給小組，讓他們能根據組織範圍內的自訂應用程式設定，將自訂 app 上傳給擁有者的團隊。
- 使用者可以將自訂應用程式上傳到個人內容。 
- 根據組織範圍內的自訂應用程式設定，使用者可以與自訂應用程式互動。

您可以編輯全域 app 設定原則中的設定，以包含您想要的 app。 如果您想要針對貴組織中不同的使用者群組自訂小組，請建立並指派一或多個自訂應用程式設定原則。

#### <a name="set-a-user-custom-app-policy"></a>設定使用者自訂 app 原則

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **設定原則**]。
2. 按一下 [**新增**]。
3. 開啟或關閉 [**允許上傳自訂應用程式**]。
4. 選擇您想要用於原則的任何其他設定。
5. 按一下 [**儲存**]。

### <a name="team-custom-app-setting"></a>團隊自訂應用程式設定

系統管理員和小組擁有者可以控制團隊是否允許將自訂應用程式新增到其中。 此設定可**讓成員上傳自訂應用程式**，以及使用者的自訂應用程式原則，決定誰可以將自訂應用程式新增至特定團隊。
 
如果已關閉此設定：

- 如果他們的自訂 app 原則允許，小組擁有者可以新增自訂應用程式。
- 不是團隊擁有者的小組成員無法將自訂應用程式新增至團隊。

如果已開啟此設定：

- 小組擁有者可以新增自訂的應用程式（如果他們的自訂應用程式原則允許）。
- 不是團隊擁有者的小組成員可以新增自訂應用程式（如果他們的自訂應用程式原則允許）。

#### <a name="configure-the-team-custom-app-setting"></a>設定小組自訂應用程式設定

1. 在 [團隊] 中，移至團隊，按一下 [**更多選項] ̇̇̇** > [**管理團隊**]。
2. 按一下 [**設定**]，然後展開 [**成員許可權**]。
3. 選取或清除 [**允許成員上傳自訂應用程式**] 核取方塊。

    ![顯示小組自訂應用程式設定的螢幕擷取畫面](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>全組織的自訂應用程式設定

組織範圍的自訂應用程式設定，可**讓您與自訂應用程式進行互動**，並將其套用至組織中的所有人，並控制他們是否可以上傳或與自訂 app 互動。 此設定會覆寫使用者和團隊的自訂應用程式原則與設定。 它是用來在安全性事件期間作為主機開啟/關閉切換。

#### <a name="configure-the-org-wide-custom-app-setting"></a>設定組織範圍的自訂應用程式設定

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > ]**許可權原則**。
2. 按一下 [**全組織式應用程式設定**]。
3. 在 [**自訂應用程式**] 底下，開啟或關閉 [**允許與自訂應用程式互動**]。

    ![顯示組織範圍自訂應用程式設定的螢幕擷取畫面](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>自訂 app 原則與設定如何共同運作

下表摘要列出自訂應用程式原則和設定、它們如何共同運作，以及其結合控制哪些人可以將自訂應用程式上傳至團隊的效果。

例如，您想要只允許團隊擁有者將自訂應用程式上傳到特定團隊。 您可以設定下列專案：
- 在 Microsoft 團隊系統管理中心開啟 [**允許與自訂應用程式互動**] 設定。
- 針對您要限制存取權的每個團隊，關閉 [**允許成員上傳自訂應用程式**]。
- 在 Microsoft 團隊系統管理中心建立並指派自訂的應用程式設定原則，**使用者可以開啟 [自訂應用程式**] 設定，然後將它指派給小組擁有者。

|全組織的自訂應用程式設定 |團隊自訂應用程式設定 |使用者自訂 app 原則 |效果  |
|---------|---------|---------|---------|
| 出    | 出    | 出     |您的組織已封鎖與所有自訂應用程式的互動。 任何人都無法上傳自訂應用程式。 您可以使用 PowerShell 來移除自訂應用程式。   |
| 出     | 出     | 按        |您的組織已封鎖與所有自訂應用程式的互動。 任何人都無法上傳自訂應用程式。 您可以使用 PowerShell 來移除自訂應用程式。         |
| 出    | 按        | 出        |您的組織已封鎖與所有自訂應用程式的互動。 任何人都無法上傳自訂應用程式。 您可以使用 Windows PowerShell 來刪除自訂應用程式。         |
| 出    | 按      | 按       |您的組織已封鎖與所有自訂應用程式的互動。 任何人都無法上傳自訂應用程式。 您可以使用 PowerShell 來移除自訂應用程式。         |
| 按    | 出       | 出         |  使用者無法上傳自訂應用程式。      |
| 按     | 出       | 按         | 如果使用者是團隊擁有者，則可將自訂應用程式上傳至團隊。 如果使用者不是團隊擁有者，則他們無法將自訂應用程式上傳至團隊。 使用者可以在個人內容中上傳自訂應用程式。     |
| 按     | 按     | 出         | 使用者無法上傳自訂應用程式。       |
| 按    | 按        | 按        | 無論使用者是否為小組擁有者，使用者都可以將自訂應用程式上傳至團隊。 使用者可以在個人內容中上傳自訂應用程式。       |

 ## <a name="related-topics"></a>相關主題
- [團隊中應用程式的系統管理設定](admin-settings.md)
