---
title: 在 Microsoft Teams 中管理標籤
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
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
description: 瞭解如何在 Microsoft Teams 中管理貴組織中的標籤使用方式。
ms.openlocfilehash: 9c2da438d3f88a172759ec13672aec663ae6add9
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647427"
---
# <a name="manage-tags-in-microsoft-teams"></a>在 Microsoft Teams 中管理標籤

Microsoft Teams 中的標籤可讓使用者快速且輕鬆地與團隊中的一部分人員聯繫。 您可以建立及指派自訂標籤，根據屬性將人員分類，例如角色、專案、技能或位置。 或者，標籤可以根據人員的排程和班次資訊，自動指派給 [ [班次] 應用程式](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6)中的人員。 將標籤新增至一或多個小組成員之後，頻道貼文中的團隊中任何人都可以在@mentions中使用標籤，僅通知被指派該交談標籤的人員。

如前所述，Teams 中有兩種標籤。

- **自訂標籤**：團隊擁有者和團隊成員 (，如果他們擁有許可權，) 可以手動建立並指派標籤給人員。 例如，「設計工具」或「Radio 因特式」標籤會觸及團隊中的這些人員，而不需要輸入他們的名稱。
- **按班標記**：透過這項功能，使用者會在 Teams 的 [Shifts 應用程式](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_usetags) 中自動指派符合其排程和班組名稱的標籤。 例如，「EngineerOnCall」標籤會在聊天或頻道貼文中使用標籤時，觸及排定在 Shifts 中工作的所有工程師。 透過按班標記，當使用者需要快速轉送資訊時，Teams 會利用對輪班員工名稱的猜測。

> [!NOTE]
> 私人或共用頻道不支援標籤。

## <a name="how-tags-work"></a>標籤的運作方式

您可以手動新增標籤 (自訂標籤) ，或在 [班次] 應用程式) 中設定 [班次]，自動指派給特定小組 (上的人員。 標籤可在聊天中的 [收件者 **] 行或** 團隊任何標準頻道的貼文中使用@mentions。 以下是一些在 Teams 中如何使用標籤的範例：

- 商店經理會張貼公告至頻道以通知所有收納者。
- 醫院系統管理員會傳送訊息給頻道中的所有無線電員。
- 行銷經理會開始與所有設計者進行群組聊天。
- 托兒會傳送訊息給所有隨選寄件者。
- 系統工程師在頻道張貼公告，以通知所有在班上的欄位工程師。

當頻道交談中@mentioned標籤時，與標籤相關聯的小組成員將會收到通知，就像任何其他@mention一樣。

## <a name="manage-tags-for-your-organization"></a>管理貴組織的標籤

身為系統管理員，您可以在 Microsoft Teams 系統管理中心控制整個組織使用標籤的方式。 請注意，您無法使用 PowerShell 來管理標籤。

:::image type="content" source="media/manage-tags-admin-settings-shifts.png" alt-text="Microsoft Teams 系統管理中心的標記設定螢幕擷取畫面。":::

團隊最多可以有 100 個標籤，最多可為 200 個小組成員指派一個標籤，而同一個團隊中最多可將 25 個標籤指派給單一使用者。

### <a name="set-who-can-manage-tags"></a>設定誰可以管理標籤

根據預設，團隊擁有者可以建立、編輯及刪除標籤。 您可以變更 [ **誰可以管理標籤** ] 設定，允許團隊擁有者和小組成員管理標籤，或者您也可以關閉組織的標籤。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[Teams** \> **Teams 設定]**。

2. 在 [ **標記**] 底下的 [ **誰可以管理標籤] 旁邊**，選取下列其中一個選項：

    - **團隊擁有者和成員**：允許團隊擁有者和成員管理標籤。
    - **團隊擁有者**：允許團隊擁有者管理標籤。
    - **未啟用**：關閉標籤。

### <a name="configure-tagging-settings"></a>設定標記設定

您可以設定下列標籤設定，以控制在整個組織中使用標籤的方式。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[Teams** \> **Teams 設定]**。

2. 在 [ **標記**] 下，根據貴組織的需求設定下列專案。

    - **團隊擁有者可以變更誰可以管理標籤**：當您開啟此設定時，團隊擁有者可以設定團隊成員是否可以在團隊內建立和管理標籤，而 [ **誰可以管理標籤** ] 設定的值是每個團隊的預設值。 如果您關閉此設定，則無法針對每個團隊變更 [ **誰可以管理標籤** ] 設定。
    - **建議的標籤**：使用此專案來新增一組預設標籤。 您最多可以新增 25 個標籤，每個標籤最多可以包含 25 個字元。 團隊擁有者和成員 (啟用此功能) 可以使用這些建議、新增至他們，或建立一組新的標籤。
    - **自訂標籤**：開啟此設定可讓使用者新增您設定之建議之預設標籤以外的標籤。 如果關閉此設定，則人員只能使用建議的預設標籤。 如果您關閉此功能，請確定您新增一或多個預設標籤。
    - **Shifts 應用程式可以套用標籤**：開啟此設定可讓 Shifts 應用程式自動指派標籤給即時上班的人員。 這些標籤會符合使用者在 Shifts 中的排程和組名。 只有在聊天或頻道文章中使用標籤時，通知才會傳送給輪班的人員。

## <a name="related-topics"></a>相關主題

[在 Teams 中使用標籤](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[管理 Shifts 應用程式](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts 說明文件](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
