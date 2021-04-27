---
title: 在 Microsoft Teams 中管理標記
author: cichur
ms.author: v-cichur
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
description: 瞭解如何在 Microsoft Teams 中管理貴組織如何使用標記。
ms.openlocfilehash: c63817f5b3ee9c736311982b54dbc9a220564229
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030103"
---
# <a name="manage-tags-in-microsoft-teams"></a>在 Microsoft Teams 中管理標記

## <a name="overview"></a>概觀

Microsoft Teams 中的標記可讓使用者快速且輕鬆地與團隊中的一部分人員聯繫。 您可以建立並指派自訂標記，根據角色、專案、技能或位置等屬性來將人員分類。 或者，標記也可以根據人員排程和班次資訊自動指派給人員， (即將) 。 [](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 將標記新加入一或多個小組成員之後，頻道文章中的小組@mentions就可以在 @mentions 中使用標記，或只與指派該標記的人開始交談。

如先前所述，Teams 有兩種標記。

- **自訂標記**：團隊擁有者和小組成員 (啟用此功能時，) 手動建立並指派標記給人員。 例如，「設計工具」或「放射科醫生」標記會抵達團隊中的這些人員，而不需要輸入他們的名稱。
- **以班次標記**：使用這項功能，在 Teams 中的 [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 應用程式中，系統會自動指派符合其排程和班次組名的標記。 例如，在聊天或頻道貼文使用標記時，「EngineerOnCall」標記會到達所有排程在 Shifts 中工作的工程師。 有了輪班標記，當使用者需要快速轉遞資訊時，Teams 會因為知道輪班員工的名稱而不需要猜測。 以班次標記也可以由 JDA、Kronos 和 AMiON 等主要員工管理系統做為後盾，將它們與 Teams 中的 Shift 整合。 若要深入瞭解如何設定此功能，請參閱設定班次 [標記](#set-up-tagging-by-shift)。

> [!NOTE]
> 私人頻道尚不支援標記。 標記不適用於 GCC High 或美國國防部 (DoD) 組織。 

## <a name="how-tags-work"></a>標記如何工作

您可以手動新增或自動將標記指派給特定團隊中的人員。 然後可用於聊天@mentions的至行或小組任何標準頻道的貼文。 以下是在 Teams 中如何使用標記的一些範例：

- 商店管理員會張貼公告至頻道，以通知所有出納。
- 醫院系統管理員會傳送訊息給頻道中所有的放射科醫師。
- 行銷經理會開始與所有設計師進行群組聊天。
- 一名護士會傳送訊息給所有的通話中卡片專家。  (即將推出) 
- 系統工程師會張貼公告至頻道，以通知所有輪班的現場工程師。  (即將推出) 

當頻道交談@mentioned標記時，與標記相關聯的小組成員會收到通知，就像任何其他@mention。

## <a name="manage-custom-tags-for-your-organization"></a>管理貴組織的自訂標記

做為系統管理員，您可以在 Microsoft Teams 系統管理中心控制整個組織的標記使用方式。 目前，您無法使用 PowerShell 來管理標記。

![Microsoft Teams 系統管理中心標記設定螢幕擷取畫面](media/manage-tags-admin-settings.png)

團隊最多可以有 100 個標記，最多 100 個小組成員可以指派給標記，最多 25 個標記可以指派給單一使用者。 

### <a name="set-who-can-add-custom-tags"></a>設定誰可以新增自訂標記

根據預設，團隊擁有者可以新增自訂標記。 您可以變更此設定，讓團隊擁有者和小組成員建立、編輯、刪除及管理標記，也可以關閉貴組織的標記。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，按一下 **[全組織設定** Teams  >  **設定**> 。
2. 在 **標記下****，選取下列** 其中一個選項，以管理標記旁的標記：

    - **團隊擁有者和成員**：允許團隊擁有者和成員管理標記。
    - **團隊擁有者**：允許團隊擁有者管理標記。
    - **已停用**：關閉標記。

### <a name="configure-custom-tags-settings"></a>設定自訂標記設定

您可以設定下列標記設定，以控制自訂標記在整個組織的使用方式。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，按一下 **[全組織設定** Teams  >  **設定**> 。
2. 在 **標記下**，根據貴組織的需求設定下列專案。

    - 讓團隊擁有者取代誰可以管理標記：當您開啟此設定時，團隊擁有者可以設定小組成員是否可以在團隊中建立和管理標記，而標記值是由設定來管理，是每個團隊的預設值。 如果您關閉此設定，則無法變更每個團隊的標記管理方式設定。
    - **建議的預設標記**：使用此標記可新增一組預設標記。 您可以新增最多 25 個標記，每個標記最多可以包含 25 個字元。 如果已啟用 (團隊擁有者和成員) 可以使用這些建議、新增到他們，或建立一組新的標記。
    - **建立自訂標記：** 開啟此設定，讓其他人新增您設定之建議的預設標記外的其他標記。 如果關閉此選項，則使用者只能使用建議的預設標記。 如果您關閉此功能，請確定您新增一或多個預設標記。

## <a name="manage-custom-tags-settings-for-a-team"></a>管理小組的自訂標記設定

如果您在 Microsoft Teams系統管理中心開啟了讓團隊擁有者取代誰可以管理標記設定，團隊擁有者可以設定成員是否可以在小組層級新增標記。 若要這麼做，請前往團隊的設定選項卡上，前往 **標記，然後選擇** 誰可以新增標記。

![小組層級的標記設定螢幕擷取畫面](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>使用標記

以下是如何新增自訂標記，以及如果您使用的是 Teams (中的 Shifts 應用程式，如何以 shift 或 shift 設定) 。 若要深入瞭解，請查看在 [Teams 中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。

### <a name="create-and-assign-custom-tags"></a>建立及指派自訂標記

若要建立及指派自訂標記，請選取應用程式左側的 **Teams，** 然後在清單中尋找您的小組。 選取 **11 個其他選項**，然後選擇管理 **標記**。 您可以在這裡建立標記，並將標記指派給小組中的人員。

![如何在 Teams 用戶端中申請標記的螢幕擷取畫面 ](media/manage-tags-teams.png)

若要刪除標記，請選取 **標記旁的 10** 個其他選項，然後選取 **刪除標記**。

### <a name="set-up-tagging-by-shift"></a>設定班次標記

1. 在 Teams 中，前往 [Shifts 應用程式](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。
2. 建立 [班次群組，](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 以角色等屬性命名。 例如，EngineerOnCall。 班次組名是標記的名稱。
3. [將班指派](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 給小組成員，以填寫排程。 完成後，請在 Shifts 應用程式的右上角，選取 與 **小組共用**。
4. 等候 15 分鐘，讓排定的班次填入標記服務。
5. 在 Teams 中使用標記的任何位置使用標記。

以班次標記可讓您的使用者即時與輪班人員聯繫。 通知只會在使用標記開始聊天或頻道貼文時，只發給輪班人員。

## <a name="related-topics"></a>相關主題

[在 Teams 中使用標記](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[在 Teams 中管理貴組織的 Shifts 應用程式](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts 說明文件](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
