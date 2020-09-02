---
title: 管理 Microsoft 團隊中的標記
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中管理組織中使用標記的方式。
ms.openlocfilehash: 9295d03aecb6c0bc6a4f667214869fe698d4eaab
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324010"
---
# <a name="manage-tags-in-microsoft-teams"></a>管理 Microsoft 團隊中的標記

> [!NOTE]
> 本文中討論的其中一個功能，請 **按 shift 進行標記**，但尚未放開。 我們已宣佈推出，即將推出。如果您是系統管理員，您可以在 [ [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home) ]) 的 [訊息中心] (，找出這項功能的發行時間。 若要維持在即將到來的小組功能上，請參閱 [Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。

## <a name="overview"></a>概觀

Microsoft 團隊中的標記可讓使用者快速且輕鬆地與團隊中的部分人員連線。 您可以建立並指派自訂標籤，以根據屬性（例如角色、專案、技能或位置）來分類人員。 或者，您會在 [ [倒班] 應用程式](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 中根據其排程和倒班資訊，自動將標籤指派給人員 (即將) 。 將標籤新增至一或多個小組成員之後，就可以 @mentions 在您的頻道文章中，由小組中的任何人使用，或只與分派該標記的人員開始交談。

如前文所述，小組中有兩種不同的標記。

- **自訂**標籤：團隊擁有者和小組成員 (如果已為其啟用功能) 可以手動建立並指派標籤給人員。 例如，「設計工具」或「Radiologist」標記會在小組中找到這些人員組，而不需要輸入他們的名稱。
- 使用 (即將推出**的 shift 進行標記**) ：您可以使用此功能，在團隊中的 [[倒班] 應用程式](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)中，系統會自動指派與其排程和班次群組名稱相符的標記。 例如，當您在聊天或頻道文章中使用標籤時，「EngineerOnCall」標記會達到所有排程的專案。 當使用者需要快速轉接資訊時，您可以使用 [依班來標記]，讓團隊不知道隨班的人員名稱。 依倒班進行標記，主要工作力管理系統（例如 JDA、Kronos 和 AMiON）也可以透過團隊中的倒班來整合。 若要深入瞭解如何設定此功能，請參閱 [依倒班設定標記](#set-up-tagging-by-shift-coming-soon)。

> [!NOTE]
> 在私有通道中尚不支援標記。 您尚無法在美國政府社區雲端 (GCC) 、GCC 高或國防 (DoD) 組織中提供標記。

## <a name="how-tags-work"></a>標記的運作方式

您可以手動新增或自動將標記指派給特定小組中的人員。 然後，就可以在聊天中的 [ **至** ] 行或在團隊任何標準頻道的文章中 @mentions 使用。 以下是如何在團隊中使用標記的一些範例：

- 商店主管將公告張貼到頻道，以通知所有出納。
- 醫院管理員會將訊息傳送給頻道中的所有 radiologists。
- 行銷管理員會開始與所有設計人員進行群組聊天。
- 護士會將訊息傳送給所有的通話 cardiologists。 即將推出 () 
- 系統工程師將公告發布至頻道，以通知所有的現場工程人員。 即將推出 () 

當您在頻道交談中 @mentioned 標籤時，與標籤相關聯的小組成員就會收到通知，就像任何其他的 @mention 一樣。

## <a name="manage-custom-tags-for-your-organization"></a>管理貴組織的自訂標籤

身為系統管理員，您可以控制在 Microsoft 團隊系統管理中心的整個組織中使用標記的方式。

![Microsoft 團隊系統管理中心的標記設定的螢幕擷取畫面](media/manage-tags-admin-settings.png)

團隊最多可以有100個標籤，最多可將100個小組成員指派給一個標籤，而且最多25個標籤可以指派給單一使用者。 

### <a name="set-who-can-add-custom-tags"></a>設定誰可以新增自訂標籤

根據預設，小組擁有者可以新增自訂標記。 您可以變更此設定，以允許小組擁有者和小組成員建立、編輯、刪除及管理標籤，或者您可以關閉貴組織的標記。

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定**  >  **團隊設定**]。
2. 在 [ **標記**] 底下 **的 [** 標籤] 旁，選取下列其中一個選項：

    - **小組擁有者和成員**：允許團隊擁有者和成員管理標記。
    - **小組擁有**者：允許團隊擁有者管理標記。
    - [**已停用**]：關閉標記。

### <a name="configure-custom-tags-settings"></a>設定自訂標記設定

您可以設定下列標記設定，以控制如何在整個組織中使用自訂標記。

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**全組織性設定**  >  **團隊設定**]。
2. 根據貴組織的需求，在 [ **標記**] 底下設定下列各項。

    - **讓小組擁有者覆寫誰能管理**標籤：當您開啟此設定時，小組擁有者可以設定小組成員是否可以在小組中建立及管理標籤，而標記的值是 **由 set 管理** ，這是每個團隊的預設值。 如果您關閉此設定，就無法依每個小組的設定來變更 **標記** 。
    - **建議的預設**標籤：使用這個功能來新增一組預設的標籤。 您可以新增最多25個標籤，每個標籤最多可包含25個字元。 小組擁有者和成員 (如果已針對其啟用該功能) 可以使用這些建議、新增到他們，或建立一組新的標記。
    - [**建立自訂**標籤]：開啟此設定可讓其他人新增您所設定的預設標記以外的標記。 如果您關閉此功能，人員只能使用建議的預設標籤。 如果您關閉此功能，請務必新增一個或多個預設標記。

## <a name="manage-custom-tags-settings-for-a-team"></a>管理團隊的自訂標記設定

如果您在 Microsoft 團隊系統管理中心開啟了 [ **讓小組擁有者覆蓋誰可以管理** 標籤] 設定，小組擁有者可以設定成員是否可以在小組層級新增標記。 若要這樣做，請在團隊的 [ **設定** ] 索引標籤上，移至 [標籤 **]，然後**選擇誰可以新增標記。

![小組層次上的 [標籤] 設定的螢幕擷取畫面](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>使用標記

以下說明如何新增自訂標籤，以及如何在您使用 [團隊) 中的 [倒班] 應用程式時，依 shift (設定標記。 若要深入瞭解，請參閱 [在團隊中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

### <a name="create-and-assign-custom-tags"></a>建立及指派自訂標記

若要建立及指派自訂標籤，請選取應用程式左側的 [ **小組** ]，然後在清單中尋找您的小組。 選取 [ **更多選項**]，然後選擇 [ **管理**標籤]。 您可以在這裡建立標籤，並將其指派給小組中的人員。

![如何在團隊用戶端套用標記的螢幕擷取畫面 ](media/manage-tags-teams.png)

若要刪除標記，請移除與標籤相關聯的所有小組成員。

### <a name="set-up-tagging-by-shift-coming-soon"></a>在即將推出的情況中設定標記 () 

1. 在 [團隊] 中，移至 [ [倒班] app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. 建立 [倒班群組](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) ，並將其命名為一個屬性（例如角色）。 例如，EngineerOnCall。 [倒班] 組名就是標記的名稱。
3. 將倒班指派給您的小組成員，即可[填入排程](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea)。 完成時，請在 [倒班] app 的右上角，選取 [ **與團隊共用**]。
4. 請等候15分鐘，讓排程的倒班填入標記服務。
5. 在團隊中您使用標籤的任何位置使用標記。

[依倒班進行標記] 可讓您的使用者即時與其他人取得聯繫。 通知只會傳送給在使用標籤來啟動聊天或頻道文章時，有班次的人員。

## <a name="related-topics"></a>相關主題

[在團隊中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[在 Teams 中管理貴組織的 Shifts 應用程式](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[班次協助檔](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
