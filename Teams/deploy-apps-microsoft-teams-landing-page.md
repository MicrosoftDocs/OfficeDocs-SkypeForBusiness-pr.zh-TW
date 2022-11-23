---
title: 了解 Microsoft Teams 中的應用程式
ms.reviewer: ''
description: 了解應用程式，並根據您的組織設定檔和商務需求，決定 Teams 中允許哪些應用程式。
ms.topic: conceptual
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 7713f1f2bf1f3a4866751d02ba702cb2d3d244f0
ms.sourcegitcommit: d95a3408e31d3dec37c534c110b09a8847bec724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2022
ms.locfileid: "69156839"
---
# <a name="understand-microsoft-teams-apps-and-their-capabilities"></a>瞭解 Microsoft Teams 應用程式及其功能

Teams 中的應用程式可協助使用者整合工作場所的工具和服務，並與其他人共同作業。 例如，使用者在 Teams 中使用釘選行事曆應用程式快速與其他人共同作業、應用程式具有機器人功能，可通知使用者 Teams 頻道中 Web 服務的品質，以及共用和指派工作給頻道中各種使用者的應用程式。 Microsoft Teams 應用程式是 Web 架構的 SaaS 應用程式，不需要在本機部署。

身為系統管理員，您可以設定應用程式控管程式，在使用者的眾多需求與貴組織的 IT 原則、標準和風險設定檔之間取得平衡。

我們豐富的已驗證且安全的 Teams 應用程式 [目錄](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) ，可讓使用者存取貴組織每天需要的工具和服務。 Teams 系統管理中心提供系統管理員企業級的控制項和組態來管理應用程式。 您可以控制每個使用者在會議、聊天和頻道等各種內容中的應用程式可用性。

此文章可協助您了解應用程式類型，以及使用者可從何處存取這些應用程式。 若要深入了解應用程式的使用，請參閱[適用於終端使用者的應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

您的使用者在 Teams 中可使用的不同類型應用程式包括：

* [屬於 Teams 一部分的核心應用程式](#core-apps)。
* [Microsoft 創建的其他應用程式](#apps-created-by-microsoft)。
* 由合作夥伴建立[的協力廠商應用程式](#third-party-apps-created-by-independent-app-developers) (經Microsoft) 驗證。
* 由您自己的組織創建的[自訂應用程式](#custom-apps-created-within-an-organization-for-internal-use)。

## <a name="core-apps"></a>核心應用程式

某些 Teams 功能，例如：活動摘要、小組、聊天、行事曆、通話、檔案和作業 (教育界租用戶) 會預設為可用，並且預設為釘選以供終端使用者輕鬆存取。 對於前線員工而言，僅有活動、班次、聊天和通話可供使用和釘選。 身為系統管理員，您可以使用此[設定原則](/microsoftteams/teams-app-setup-policies)來修改預設行為。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="核心應用程式是預設釘選在 Teams 中的應用程式。" lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>由 Microsoft 建立的應用程式

Microsoft 提供許多應用程式來提升生產力和共同作業。 您和使用者可以尋找在 Teams 系統管理中心列為 Publisher 或在 Teams 市集中列為提供者Microsoft來尋找這些應用程式。

Teams 隨附一組內建的應用程式，包括清單、工作、稱讚、核准等。 建議您在初始推出 Teams 時包括精選的應用程式，例如 Microsoft Planner。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="顯示 Teams 系統管理中心中Microsoft應用程式清單的螢幕擷取畫面。" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>由獨立應用程式開發人員建立的協力廠商應用程式

除了Microsoft提供的應用程式，您還可以使用協力廠商應用程式。 Microsoft嚴格驗證所有這些應用程式的功能和安全性。 在 Teams 市集中提供這些應用程式之前，會先執行詳盡的手動和自動化測試，而且即使在即時發佈應用程式之後，許多測試仍會以一般頻率繼續。 若要瞭解應用程式驗證的優點，請參閱 [驗證協力廠商應用程式](overview-of-app-validation.md)。 部分應用程式訂閱[Microsoft合規性計畫](overview-of-app-certification.md)，以在驗證之外接受多層進一步檢查。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams 市集中協力廠商應用程式範例的螢幕擷取畫面。":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>在組織內建立供內部使用的自訂應用程式

由貴組織中的開發人員建立的應用程式稱為自訂應用程式 (或企業營運應用程式)。 貴組織可能會針對組織特定的需求委託建立自訂應用程式。 您有權為整個組織或特定使用者允許或封鎖此類應用程式。 貴組織的開發人員可以使用與 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 整合的 Teams 來建立自訂低程式碼解決方案。

當系統管理員允許使用自訂應用程式後，使用者可以在 Teams 市集的左側流覽中選取 **[為您的組織打造** ] 來尋找這類應用程式。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 傳統型應用程式中 Teams 市集中自訂應用程式的螢幕擷取畫面。" lightbox="media/built-for-your-org2.png":::

如需詳細資訊，請參 [閱瞭解及管理自訂及側載的應用程式](custom-app-overview.md)。

## <a name="about-app-templates"></a>關於應用程式範本

使用應用程式開發方法，Microsoft建立並提供功能性和生產就緒的範例應用程式。 這些應用程式統稱為 Teams 的應用程式範本，並提供給：

* 說明 Teams 中的一些共同作業使用案例。
* 展示應用程式開發的最佳做法和方法。
* 提供開放原始碼應用程式，讓開發人員可以擴充以建立自己的應用程式。

您的組織開發人員會透過簡易變更提供的原始程式碼來自訂應用程式範本。 您為使用者提供這些應用程式做為自訂應用程式，以符合任何組織的需求。

若要深入了解，請參閱 [Microsoft Teams 應用程式範本](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="discover-and-use-apps-in-teams"></a>在 Teams 中探索和使用應用程式

使用者可以從 Teams 應用程式儲存在 Teams 桌面或 Web 用戶端中檢視 Teams 中所有可用的應用程式。 使用者可以依名稱搜尋、依類別流覽，以及流覽為您的組織所建置且使用 Power Platform 建置的應用程式，以在 Teams 中探索和安裝應用程式。

應用程式可以釘選到 Teams 以便輕鬆存取。 如果設定原則允許，以及 Teams 系統管理員允許該應用程式，使用者就可以 [自行釘](https://support.microsoft.com/office/pin-an-app-for-easy-access-3045fd44-6604-4ba7-8ecc-1c0d525e89ec) 選應用程式。系統管理員可以釘選應用程式並控制釘選應用程式的行為。如需詳細資訊，請參閱 [應用程式設定原則](/teams-app-setup-policies)。

:::image type="content" source="media/user-app-experience-find-apps.png" alt-text="螢幕擷取畫面顯示使用者可在 Microsoft Teams 中流覽應用程式的所有位置。" lightbox="media/user-app-experience-find-apps-full.png":::

使用者可以從 Teams App Store 尋找並新增應用程式至 Teams。 他們也可以直接從其工作內容新增應用程式，例如聊天或頻道索引標籤、Teams 會議或訊息區。 如需詳細資訊，請參閱[將應用程式新增至 teams Microsoft](https://support.microsoft.com/office/add-an-app-to-microsoft-teams-b2217706-f7ed-4e64-8e96-c413afd02f77)。

使用者只能在系統管理員允許應用程式時新增及使用應用程式，且該應用程式會透過 [許可權原則](teams-app-permission-policies.md)提供給使用者。 組織的 IT 系統管理員完全控制誰可以安裝哪些應用程式內容。 使用者無法新增已封鎖的應用程式，任何在 Teams 市集中具有鎖定圖示的應用程式都會針對該使用者封鎖。 不過， [使用者可以向組織 IT 系統管理員要求核准](https://support.microsoft.com/office/request-apps-that-require-approval-by-your-org-924e3a9e-33f0-44c2-9e81-e875214c05ae)。 應用程式核准之後，使用者就可以從 Teams 市集新增應用程式。

> [!NOTE]
> 只有個人可以要求核准，才能在 Teams 中新增應用程式。

## <a name="understand-app-capabilities"></a>瞭解應用程式功能

Teams 應用程式功能是開發人員在應用程式中建置以完成各種 Teams 應用程式使用案例的核心功能。 應用程式包含下列一或多項功能。 這些是 Teams 應用程式和系統管理員使用常見的 [應用程式控管方法](manage-apps.md)來管理這些應用程式的不同功能。

<!---
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="Graphic that shows the app capabilities of a Microsoft Teams app." border="false":::
--->

* **Bot**：Bot 也稱為聊天機器人或交談機器人。 它是執行簡單且重複的工作的應用程式。 聊天機器人互動可以是快速的問題與解答，也可以是提供存取服務或協助的複雜交談。 使用者可以在個人聊天、頻道或群組聊天中與 Bot 交談。 如需詳細資訊，請參閱[Microsoft Teams 中的 Bot](/microsoftteams/platform/bots/what-are-bots)。

* **索引標籤**：索引標籤是釘選在頻道或聊天頂端的 Teams 感知網頁。 索引標籤可讓您以類似網頁的體驗與內容和服務互動。 這些是簡單的 HTML `iframe` 標記，可新增為個別使用者團隊、群組聊天或個人應用程式內頻道的一部分。 如需詳細資訊，[請參閱Microsoft Teams 索引標籤](/microsoftteams/platform/tabs/what-are-tabs)。

* **網路功能和連接器**：Web 端子和連接器可協助您將各種 Web 服務連線至Microsoft Teams 中的頻道和團隊。 Web 端子是使用者定義的 HTTP 回撥，會通知使用者 Teams 頻道中已執行的任何動作。 這是應用程式取得即時資料的一種方式。 連接器可讓使用者訂閱，以接收來自 Web 服務的通知和訊息。 如需詳細資訊，請參閱 [網路任務和連接器](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。

  若要允許使用者在 Teams 中使用自訂連接器，請參閱 [在 Teams 中使用自訂連接器](office-365-custom-connectors.md)。

* **訊息中心延伸** 模組：訊息擴充功能是插入應用程式內容或在訊息上採取行動的快速鍵，使用者不必離開交談。 使用者可以從撰寫郵件區域、命令方塊或直接從郵件中搜尋或啟動外部系統中的動作。 如需詳細資訊，請參閱 [訊息延伸模組](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet)。

* **會議擴充** 功能：使用者可以整合會議中的郵件延伸功能，提高會議生產力，藉此強化會議體驗。 您可以識別各種參與者角色和使用者類型、取得會議事件，以及產生會議內對話方塊。 如需詳細資訊，請參閱 [Teams 會議相關應用程式](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings)。

<!---
* **Cards and task modules**: Cards provide users with various visual, audio, and selectable messages and help in conversation flow. Task modules help you create modal pop-up experiences in Microsoft Teams. They're useful for starting and completing the tasks, or displaying rich information like videos or Power business intelligence (BI) dashboards. For more information, see [Cards and task modules](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules).
--->

* **活動摘要**：Teams 中的活動摘要包含頻道和聊天等各種範圍中所有活動的通知。 應用程式可以廣播訊息給團隊或頻道的所有成員，以通知任何更新。 使用者可以自訂他們檢視的通知。

若要檢視對應至 Teams 功能的常見使用案例，請參閱將 [您的使用案例對應至 Teams 應用程式功能](/microsoftteams/platform/concepts/design/map-use-cases)。

## <a name="related-articles"></a>相關文章

* [深入瞭解 Teams 的應用程式範本](/microsoftteams/platform/samples/app-templates)。
* [Teams 應用程式更新與系統管理員角色](apps-update-experience.md)
* [Teams 系統管理中心的應用程式管理和控管概觀](manage-apps.md)
