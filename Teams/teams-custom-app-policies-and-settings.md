---
title: 管理自訂應用程式原則和設定
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
description: 了解如何管理自訂應用程式原則和設定，控制貴組織中可在 Microsoft Teams 中上傳自訂應用程式的人員。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 7ff0a37d815b3118aea0eb63abc8a414c4a99bd5
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397244"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理自訂應用程式原則和設定

做為系統管理員，您可以使用自訂應用程式原則和設定，控制貴組織中可將自訂應用程式上傳至 Microsoft Teams 的人員。 系統管理員決定可上傳自訂應用程式的使用者，而系統管理員與小組擁有者可判斷貴組織中的特定小組是否可將自訂應用程式新增至其小組。  編輯自訂應用程式原則之後，變更可能需要幾個小時的時間才會生效。 您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。

貴組織內的開發人員可透過將應用程式套件 (.zip 檔案中) 直接上傳至小組或個人內容中，將自訂應用程式新增至 Teams。 這與透過 Teams 應用程式市集新增應用程式的方式不同。 透過上傳應用程式套件新增自訂應用程式 (也稱為側載)，讓貴組織的特定使用者在應用程式就緒廣泛散佈前先測試該應用程式。

## <a name="custom-app-policy-and-settings"></a>自訂應用程式原則和設定

三個元件可決定使用者是否可以將自訂應用程式上傳至團隊，讓您能夠精細地控制誰可以將自訂應用程式新增至團隊，以及可以將自訂應用程式新增至哪些團隊：

- [使用者自訂應用程式原則](#user-custom-app-policy)
- [小組自訂應用程式設定](#team-custom-app-setting)
- [全組織的自訂應用程式設定](#org-wide-custom-app-setting)

這些設定不會影響封鎖第三方應用程式的功能。  

### <a name="user-custom-app-policy"></a>使用者自訂應用程式原則

做為 **應用程式設定原則** 的一部分，系統管理員可以使用此 [[上傳自訂應用程式]](teams-app-setup-policies.md) 原則設定，來控制使用者是否可以將自訂應用程式上傳至 Teams。

若已關閉此設定：

- 使用者無法將自訂應用程式上傳至貴組織的任何小組或個人內容中。
- 使用者可根據全組織自訂應用程式設定，與自訂應用程式互動。

若已開啟此設定:

- 使用者可根據全組織自訂應用程式設定，將自訂應用程式上傳至允許的小組，以及使用者為該小組擁有者的小組。
- 使用者可將自訂應用程式上傳至個人內容。
- 使用者可根據全組織自訂應用程式設定，與自訂應用程式互動。

您可以在全域應用程式設定原則中編輯設定，以包括您需要的應用程式。 如果要針對貴組織中的不同使用者群組自訂 Teams，請建立並指派一或多個自訂應用程式設定原則。

#### <a name="set-a-user-custom-app-policy"></a>設定使用者自訂應用程式原則

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[設定原則](https://admin.teams.microsoft.com/policies/app-setup)**。
1. 選取 [新增 **]**。
1. 開啟或關閉 [上傳自訂應用程式 **]**。
1. 選擇您想要用於原則的任何其他設定。
1. 選取 [儲存 **]**。

### <a name="team-custom-app-setting"></a>小組自訂應用程式設定

系統管理員和小組擁有者可控制小組是否允許將自訂應用程式新增至該小組。 此設定，[允許成員上傳自訂應用程式]**** 同時搭配使用者的自訂應用程式原則，決定了可將自訂應用程式新增至特定小組的人員。

若已關閉此設定：

- 若小組擁有者的自訂應用程式原則允許，他們即可新增自訂應用程式。
- 非小組擁有者的小組成員則無法將自訂應用程式新增至小組。

若已開啟此設定:

- 若小組擁有者的自訂應用程式原則允許，他們即可新增自訂應用程式。
- 若小組擁有者的自訂應用程式原則允許，非小組擁有者的小組成員即可新增自訂應用程式。

#### <a name="configure-the-team-custom-app-setting"></a>設定小組自訂應用程式設定

1. 在 Teams 中，移至團隊，然後選取 **[更多選項...**  > **管理團隊**。
2. 選 **取 [設定]** 並展開 **[成員許可權]**。
3. 選取或清除 [允許成員上傳自訂應用程式]**** 核取方塊。

    ![顯示小組自訂應用程式設定的螢幕擷取畫面。](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>全組織的自訂應用程式設定

在 [[管理應用程式]](manage-apps.md) 頁面上的 **[允許與自訂應用程式互動]** 全組織自訂應用程式設定會套用至貴組織中的所有人，並控管人員是否可上傳或與自訂應用程式互動。 此設定會做為使用者和小組自訂應用程式原則設定的主控開/關切換。 其目的是在安全性事件期間做為主控的開/關切換。 因此，除非啟用整個組織的自訂應用程式設定，否則使用者和小組自訂應用程式原則設定將不會生效，即使已啟用使用者和小組自訂應用程式原則設定也不會生效。

#### <a name="configure-the-org-wide-custom-app-setting"></a>設定全組織自訂應用程式設定

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 選取 **[全組織應用程式設定]**。
1. 在 **自訂應用程式** 底下，開啟或關閉 **[允許與自訂應用程式互動]**。

    ![顯示全組織自訂應用程式設定的螢幕擷取畫面。](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>自訂應用程式原則和設定如何共同運作

此表格摘要說明自訂應用程式原則及設定，它們如何共同運作，以及它們對控制貴組織中誰可將自訂應用程式上傳至 Teams 的合併影響。

假設，舉例來說，您想要允許僅限小組擁有者將自訂應用程式上傳至特定小組。 您可以設定下列項目：

- 在 Microsoft Teams 系統管理中心中開啟 [允許與自訂應用程式互動 **]** 設定。
- 為您想要限制存取權的每個小組關閉 [允許成員上傳自訂應用程式 **]**。
- 在 Microsoft Teams 系統管理中心建立並指派自訂應用程式設定原則，同時開啟 [上傳自訂應用程式 **]** 設定，並將其指派給小組擁有者。

|全組織的自訂應用程式設定 |小組自訂應用程式設定 |使用者自訂應用程式原則 |效果  |
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

- [管理員 Teams 中應用程式的設定](admin-settings.md)。
- [在 Teams 中指派原則給使用者](assign-policies-users-and-groups.md)。
