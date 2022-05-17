---
title: 管理 Microsoft Teams 中的標籤
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在Microsoft Teams中管理貴組織中的標籤使用方式。
ms.openlocfilehash: 0fa615f2bbcdd7965777925b2413717779ad4a7a
ms.sourcegitcommit: 54cb804e6e8338f2d09499e53416e6d55ef1cc40
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/17/2022
ms.locfileid: "65442009"
---
# <a name="manage-tags-in-microsoft-teams"></a>管理 Microsoft Teams 中的標籤

## <a name="overview"></a>概觀

Microsoft Teams中的標籤可讓使用者快速且輕鬆地與團隊中的一部分人員聯繫。 您可以建立及指派自訂標籤，根據屬性將人員分類，例如角色、專案、技能或位置。 或者，標籤可以根據人員的排程和班次資訊，自動指派給 [ [班次] 應用程式](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts)中的人員。 將標籤新增至一或多個小組成員之後，團隊中的任何人都可以在頻道貼文中@mentions使用標籤，或只與指派該標記的人員開始交談。

如先前所述，Teams中有兩種標籤。

- **自訂標籤**：團隊擁有者和團隊成員 (啟用此功能時，) 可以手動建立並指派標籤給人員。 例如，「設計工具」或「Radio 因特式」標籤會觸及團隊中的這些人員，而不需要輸入他們的名稱。
- **按班標記**：使用此功能，系統會自動指派符合排程的標籤，並在Teams的 [Shifts 應用程式](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)中指派組名。 例如，「EngineerOnCall」標籤會在聊天或頻道貼文中使用標籤時，觸及排定在 Shifts 中工作的所有工程師。 透過按班標記，當使用者需要快速轉送資訊時，Teams會猜出對輪班員工名稱的猜測。 JDA、Kronos 和 AMiON 等主要員工管理系統也可以透過將它們與 Teams 中的 Shifts 整合，藉此支援按班次標記。 若要深入瞭解如何設定此功能，請參閱 [按班設定標記](#set-up-tagging-by-shift)。

> [!NOTE]
> 私人或共用頻道不支援標籤。  

## <a name="how-tags-work"></a>標籤的運作方式

標籤可以手動新增或自動指派給特定團隊的人員。 然後，您可以在聊天中的 [收件者 **] 行或** 團隊任何標準頻道的貼文中使用@mentions。 以下是一些範例，說明如何在 Teams 中使用標籤：

- 商店經理會張貼公告至頻道以通知所有收納者。
- 醫院系統管理員會傳送訊息給頻道中的所有無線電員。
- 行銷經理會開始與所有設計者進行群組聊天。
- 托兒會傳送訊息給所有隨選寄件者。  (即將推出) 
- 系統工程師在頻道張貼公告，以通知所有在班上的欄位工程師。  (即將推出) 

當頻道交談中@mentioned標籤時，與標籤相關聯的小組成員將會收到通知，就像任何其他@mention一樣。

## <a name="manage-custom-tags-for-your-organization"></a>管理貴組織的自訂標籤

身為系統管理員，您可以在Microsoft Teams系統管理中心控制整個組織使用標籤的方式。 目前您無法使用 PowerShell 來管理標籤。

![在系統管理中心Microsoft Teams標記設定的螢幕擷取畫面。](media/manage-tags-admin-settings.png)

團隊最多可以有 100 個標籤，最多可以指派 200 個小組成員給一個標籤，而同一個團隊中最多可以將 25 個標籤指派給單一使用者。 

### <a name="set-who-can-add-custom-tags"></a>設定誰可以新增自訂標籤

根據預設，團隊擁有者可以新增自訂標籤。 您可以變更此設定，允許團隊擁有者和小組成員建立、編輯、刪除及管理標籤，或者您可以關閉組織的標籤。

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，按一下 **[Teams**  >  **Teams設定]**。
2. 在 [ **標記**] 下方的 [ **標籤受管理者**] 旁邊，選取下列其中一個選項：

    - **團隊擁有者和成員**：允許團隊擁有者和成員管理標籤。
    - **團隊擁有者**：允許團隊擁有者管理標籤。
    - **已停** 用：關閉標籤。

### <a name="configure-custom-tags-settings"></a>設定自訂標籤設定

您可以設定下列標籤設定，以控制在整個組織中使用自訂標籤的方式。

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，按一下 **[Teams**  >  **Teams設定]**。
2. 在 [ **標記**] 下，根據貴組織的需求設定下列專案。

    - **讓團隊擁有者覆寫誰可以管理標籤**：當您開啟此設定時，團隊擁有者可以設定團隊成員是否可以在團隊內建立及管理標籤，而 「標籤」的值是由設定為每個團隊的預設值 **來管理** 。 如果您關閉此設定，則無法變更每個團隊的 [卷 **標** ] 設定。
    - **建議的預設標籤**：使用此標記來新增一組預設標籤。 您最多可以新增 25 個標籤，每個標籤最多可以包含 25 個字元。 團隊擁有者和成員 (啟用此功能) 可以使用這些建議、新增至他們，或建立一組新的標籤。
    - **建立自訂標籤**：開啟此設定可讓使用者新增您所設定之預設標籤以外的標籤。 如果關閉此設定，則人員只能使用建議的預設標籤。 如果您關閉此功能，請確定您新增一或多個預設標籤。

## <a name="manage-custom-tags-settings-for-a-team"></a>管理團隊的自訂標籤設定

如果您開啟 [**讓團隊擁有者覆寫誰可以在** Microsoft Teams 系統管理中心管理標籤] 設定，團隊擁有者可以設定成員是否可以在團隊層級新增標籤。 若要這麼做，請在小組 **設定** 索引標籤上，**移至 [** 標籤]，然後選擇誰可以新增標籤。

![團隊層級之標籤設定的螢幕擷取畫面。](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>使用標籤

以下說明如何新增自訂標籤，以及如果您在 Teams) 中使用 Shifts 應用程式，如何透過班 (設定標記。 若要深入瞭解，請參閱[在 Teams 中使用標籤](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

### <a name="create-and-assign-custom-tags"></a>建立及指派自訂標籤

若要建立及指派自訂標籤，請選 **取** 應用程式左側Teams，然後在清單中尋找您的小組。 選 **取 [̇ ̇ ̇ 更多選項]**，然後選擇 **[管理標籤]**。 您可以在這裡建立標籤，並將標記指派給小組中的人員。

![螢幕擷取畫面顯示如何在Teams用戶端中套用標籤。](media/manage-tags-teams.png)

若要刪除標籤，請選取標籤旁的 **[̇ ̇ ̇ 更多選項** ]，然後選取 **[刪除標籤]**。

### <a name="set-up-tagging-by-shift"></a>依班次設定標記

按班標記可讓您的使用者即時聯繫上班的人員。 Teams會自動指派符合排程標籤的使用者，並從 Shifts 應用程式移轉組名，以啟用動態角色型訊息。 通知只會傳送給輪班時使用標籤開始聊天或頻道文章的人員。 

1. 在 Teams 中，移至[Shifts 應用程式](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. 建立 [班次群組，](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 並以角色等屬性為其命名。 例如，EngineerOnCall。 班組名會是標籤的名稱。
3. 將班次指派給團隊成員以[填寫排程](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea)。 完成後，請選取 [班次] 應用程式右上角的 [ **與小組共用]**。
4. 等候 15 分鐘，讓排定的班次填入標記服務。
5. 在Teams中使用標籤的任何位置使用標籤。

## <a name="related-topics"></a>相關主題

[在 Teams 中使用標籤](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[在 Teams 中管理貴組織的 Shifts 應用程式](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts 說明文件](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
