---
title: 在 Microsoft 團隊中管理貴組織的任務應用程式
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: 瞭解如何管理組織中使用者的 [工作] app。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 18af74a2a62f8282ee9b39c998db803235cc4ff0
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130494"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft 團隊中管理貴組織的任務應用程式

## <a name="overview-of-tasks"></a>任務概覽

[工作] app 為 Microsoft 團隊帶來了一種內聚性的工作管理體驗，整合了由 [microsoft](https://todo.microsoft.com/tasks/) 提供的個別工作，以及由 Planner 提供的小組工作，集中在一個位置。 使用者可以將工作作為小組左邊的 app 存取，以及在個別團隊的頻道中作為索引標籤。 [工作] 中的 [**我** 的工作] 和 [**共用方案**] 可讓使用者查看及管理其個別及小組工作，並設定其工作優先順序。 在團隊桌面、web 和行動用戶端中都有可用的工作。 

> [!NOTE]
> 當我們在團隊桌面用戶端上推出工作體驗時，應用程式名稱最初會以 **Planner** 顯示給使用者。 然後，該名稱會暫時變更為工作（ **依 Planner 及待辦事項**），稍後再將其重新命名為 [ **任務**]。 在團隊行動用戶端上，使用者將永遠會看到應用程式名稱做為 [ **任務**]。 在桌面體驗推出後，行動體驗的可用性可能會有短暫的延遲。

   ![[團隊] 清單上工作清單視圖的螢幕擷取畫面](media/manage-tasks-app-tasks.png)

針對想要簡化第一線員工工人工作管理的組織而言，工作也包含可讓您以不同的第一線員工員工的規模進行設定、發佈及追蹤任務的功能。 例如，公司和地區性領導可以建立併發布針對相關位置（例如特定零售商店）的工作清單，以及透過即時報告追蹤進度。 管理員可以將工作指派給其員工，並直接在其位置內進行活動，而第一線員工工作者在行動或桌面上會有其已指派任務的優先順序清單。 若要啟用 [ [任務發佈](#task-publishing)]，您必須先設定組織的小組目標階層，以定義階層中所有團隊之間相互關聯的方式。

## <a name="what-you-need-to-know-about-tasks"></a>任務所需注意的事項

[工作] 可做為應用程式和頻道中的索引標籤。 請記住，應用程式是由 Planner 中的任務和小組任務組成，而 tab 只會顯示小組工作。

在工作中，使用者可以取得桌面、網站和行動裝置體驗。 如果工作是在小組桌面用戶端上安裝，使用者也會在他們的小組網頁和行動用戶端上看到它。 例外狀況為來賓使用者。 請務必知道，來賓只能從小組行動用戶端存取任務作為 app。 來賓會在兩個小組的桌面和 web 用戶端上看到 [任務] 索引標籤。

[**我** 的工作] 會顯示使用者的個別工作。 [**共用方案**] 會顯示整個小組正在處理的工作，並包含任何以 [任務] 索引標籤新增為頻道的工作清單。 請注意下列事項：

- 使用者在 [工作] 應用程式中建立的工作清單也會顯示在 [為該使用者執行用戶端]。 同樣地，使用者在工作中建立的工作清單會顯示在該使用者的 [工作]**工作中。** 個別工作也是如此。

- 新增至頻道的任何 [任務] 索引標籤也會出現在 Planner 用戶端中。 當使用者在 Planner 中建立計畫時，除非將 [工作] 或 [Planner] 應用程式新增為頻道的索引標籤，否則方案將不會顯示。 當使用者新增 [任務] 索引標籤時，他們可以建立新的清單或方案，或選擇現有的清單或方案。

## <a name="set-up-tasks"></a>設定任務

> [!IMPORTANT]
> 您針對 Planner 所設定的設定與原則也會套用至 [任務]。

### <a name="enable-or-disable-tasks-in-your-organization"></a>啟用或停用組織中的任務

預設會針對貴組織中的所有團隊使用者啟用 [任務]。 您可以在 Microsoft 團隊系統管理中心的 [ [管理應用程式](manage-apps.md) ] 頁面上關閉或開啟組織階層的 app。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。
2. 在應用程式清單中，執行下列其中一項操作：

    - 若要關閉貴組織的工作，請搜尋 [任務] app，選取該應用程式，然後按一下 [ **封鎖**]。
    - 若要開啟貴組織的工作，請搜尋 [任務] app，選取該應用程式，然後按一下 [ **允許**]。

> [!NOTE]
> 如果您找不到 [任務] app，請在本文的第一張筆記中搜尋名稱。 App 可能仍在重新命名的程式中。

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>針對貴組織中的特定使用者啟用或停用工作

若要允許或封鎖貴組織中的特定使用者使用工作，請確定您的組織已開啟 [ [管理應用程式](manage-apps.md) ] 頁面上的工作，然後建立自訂應用程式許可權原則，並將其指派給那些使用者。 若要深入瞭解，請參閱 [在團隊中管理 app 許可權原則](teams-app-permission-policies.md)。

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>使用應用程式設定原則將任務釘選到團隊

App 設定原則可讓您自訂小組，以醒目提示貴組織中的使用者最重要的 app。 您在原則中設定的應用程式會釘選在小組桌面用戶端的 [應用程式行] &mdash; 側邊，以及小組行動用戶端的最下方， &mdash; 使用者可以快速且輕鬆地存取。

若要為使用者釘選 [工作] 應用程式，您可以編輯全域 (組織範圍的預設) 原則，或建立並指派自訂應用程式設定原則。 若要深入瞭解，請參閱 [管理團隊中的 app 設定原則](teams-app-setup-policies.md)。

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>如果使用者已獲得 Exchange Online 授權，就會看到使用者的 [我的工作]

如果您不希望使用者看到 **我** 的工作，您可以將其隱藏。 若要這樣做，請 [移除使用者的 Exchange Online 授權](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。 請務必注意，在移除 Exchange Online 授權之後，該使用者就無法再存取其信箱了。  信箱資料會保留30天，之後將會移除資料，且無法復原，除非信箱放 [在適當位置或訴訟封存中](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)。

我們建議您不要對資訊工作者進行此操作，但在某些情況下可能會套用這種情況，例如針對不依賴電子郵件的第一線員工工作人員。

## <a name="task-publishing"></a>任務發佈

透過 [任務發佈]，您的組織可以發佈針對特定位置的工作清單， (團隊在您的組織中) ，以定義並共用工作方案，以便在這些位置完成。

- 發佈小組中的人員（例如公司或地區性領導）可以建立工作清單，並將其發佈至特定團隊。<br>
    ![[任務發佈] 的螢幕擷取畫面](media/manage-tasks-app-publish.png)
- 收件者小組的管理員可以查看已發佈的工作清單，並將個別任務指派給小組成員。<br>
    ![指派任務的螢幕擷取畫面](media/manage-tasks-app-assign.png)
- 第一線員工工人有簡單的行動體驗，可查看指派給他們的工作。 他們可以附加相片，在適當時顯示其工作，並將其任務標示為已完成。
- [發行者與管理員] 可以查看報表，以查看每個階層的工作作業及完成狀態，包括依位置 (的小組) 、工作清單及個別任務。<br>
    ![行動裝置上指派任務的螢幕擷取畫面](media/manage-tasks-app-reporting.png)

使用者在 [工作] app 的 [ **已發佈的清單** ] 索引標籤上建立、管理及發佈工作清單。 只有在您的組織 [設定團隊目標](#set-up-your-team-targeting-hierarchy) 階層，且使用者位於包含在階層中的小組時，此索引標籤才會向使用者顯示。 階層決定使用者是否可以發佈或接收工作清單，以及查看已接收清單的報表。

### <a name="example-scenario"></a>範例案例

以下是如何進行工作發佈的範例。

Contoso 正在推出新的食物 takeout 和遞送促銷。 若要維持一致的品牌體驗，他們必須在超過300的存放位置，協調推出一致的方式執行。

行銷小組與零售通訊管理員共用促銷明細及對應的工作清單。 零售通訊管理員（可充當商店的閘道管理員）會審閱資訊、建立促銷的工作清單，然後針對每個需要由每個受影響的儲存區執行的工作單元建立任務。 完成工作清單後，她必須選取必須完成工作的商店。 在這種情況下，促銷只適用于美國擁有店內餐館的商店。 在 [工作] 中，她會根據 [儲存在店內餐館] 屬性來篩選商店清單，選取階層中的 [符合美國] 位置，然後將工作清單發佈至這些商店。

每個位置的商店管理員都會收到已發佈任務的複本，並將這些工作指派給他們的小組成員。 管理員可以使用 [任務經驗] 來瞭解其商店所需的所有工作。 他們也可以使用可用的篩選器，將焦點放在特定的工作集合上，例如 [今天到期的工作] 或特定區域中的工作。

在每個市集中位置的第一線員工工作者現在會在行動裝置上的工作中有一個優先順序清單。 完成工作後，他們會將它標示為完成。 有些人甚至可能會選擇將相片上傳並附加至工作，以顯示他們的工作。

Contoso 總部和中級經理可以查看報告，以查看每個商店及跨商店的工作作業與完成狀態。 他們也可以向下切入特定任務，以查看不同商店中的狀態。 隨著啟動日期更接近，他們可以隨時找出任何 abnormalities，並視需要查看其小組。 此可見度可讓 Contoso 改善推出的效率，並在其商店中提供更一致的體驗。

### <a name="set-up-your-team-targeting-hierarchy"></a>設定您的團隊目標階層

若要在貴組織中啟用任務發佈，您必須先設定您的團隊目標架構。CSV 檔案。 架構定義階層中的所有團隊如何彼此關聯，以及用來篩選和選取團隊的屬性。 建立架構之後，請將其上傳至團隊，將其套用到您的組織。 發佈小組的成員（例如範例案例中的零售通訊管理員），可以根據階層、屬性或兩者的組合來篩選小組，以選取應收到工作清單的相關小組，然後將工作清單發佈至這些小組。

如需如何設定您的團隊目標階層的步驟，請參閱 [設定您的團隊目標](set-up-your-team-hierarchy.md)階層。

## <a name="power-automate-and-graph-api"></a>電源自動化及圖形 API

[工作] 可支援 Planner 的電源自動作業及圖形 Api。 若要深入瞭解，請參閱：

- [Planner 工作與計畫 API 概覽](https://docs.microsoft.com/graph/planner-concept-overview)
- [使用 Microsoft 與電源自動進行](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
