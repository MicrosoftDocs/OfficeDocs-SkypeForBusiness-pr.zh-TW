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
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 9b8d4ca3140b6bd8907938b5c2ac86aeabb39e37
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912622"
---
# <a name="understand-microsoft-teams-apps-and-their-capabilities"></a>瞭解 Microsoft Teams 應用程式及其功能

Teams 中的應用程式可協助使用者整合工作場所的工具和服務，並與其他人共同作業。 例如，使用者在 Teams 中使用釘選行事曆應用程式快速與其他人共同作業、應用程式具有機器人功能，可通知使用者 Teams 頻道中 Web 服務的品質，以及共用和指派工作給頻道中各種使用者的應用程式。 Microsoft Teams 應用程式是 Web 架構的 SaaS 應用程式，不需要在本機部署。

身為系統管理員，您可以設定應用程式控管程式，在使用者的眾多需求與貴組織的 IT 原則、標準和風險設定檔之間取得平衡。

我們豐富的已驗證且安全的 Teams 應用程式 [目錄](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) ，可讓使用者存取貴組織每天需要的工具和服務。 Teams 系統管理中心提供系統管理員企業級的控制項和組態來管理應用程式。 您可以控制每個使用者在會議、聊天和頻道等各種內容中的應用程式可用性。

此文章可協助您了解應用程式類型，以及使用者可從何處存取這些應用程式。 若要深入了解應用程式的使用，請參閱[適用於終端使用者的應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

您的使用者在 Teams 中可使用的不同類型應用程式包括：

* [屬於 Teams 一部分的核心應用程式](#core-apps)。
* [Microsoft 創建的其他應用程式](#apps-created-by-microsoft)。
* 由合作夥伴建立[的協力廠商應用程式](#third-party-apps-created-by-independent-app-developers) (經過 Microsoft) 驗證。
* 由您自己的組織創建的[自訂應用程式](#custom-apps-created-within-an-organization-for-internal-use)。

## <a name="core-apps"></a>核心應用程式

某些 Teams 功能，例如：活動摘要、小組、聊天、行事曆、通話、檔案和作業 (教育界租用戶) 會預設為可用，並且預設為釘選以供終端使用者輕鬆存取。 對於前線員工而言，僅有活動、班次、聊天和通話可供使用和釘選。 身為系統管理員，您可以使用此[設定原則](/microsoftteams/teams-app-setup-policies)來修改預設行為。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="核心應用程式是預設釘選在 Teams 中的應用程式。" lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>Microsoft 建立的應用程式

Microsoft 提供許多應用程式來提升生產力和共同作業。 您和使用者可以在 Teams 系統管理中心尋找列為 Publisher 的 Microsoft，或在 Teams 市集中列為「提供者」，藉此找到這些應用程式。

Teams 隨附一組內建的應用程式，包括清單、工作、稱讚、核准等。 建議您在初始推出 Teams 時包括精選的應用程式，例如 Microsoft Planner。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="顯示 Teams 系統管理中心中 Microsoft 應用程式清單的螢幕擷取畫面。" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>由獨立應用程式開發人員建立的協力廠商應用程式

除了 Microsoft 提供的應用程式之外，您還可以使用協力廠商應用程式。 Microsoft 會嚴格驗證所有這些應用程式的功能和安全性。 在 Teams 市集中提供這些應用程式之前，會先執行詳盡的手動和自動化測試，而且即使在即時發佈應用程式之後，許多測試仍會以一般頻率繼續。 若要瞭解應用程式驗證的優點，請參閱 [驗證協力廠商應用程式](overview-of-app-validation.md)。 部分訂閱 [Microsoft 合規性計畫的](overview-of-app-certification.md) 應用程式會經歷驗證以外的多層進一步檢查。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams 市集中協力廠商應用程式範例的螢幕擷取畫面。":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>在組織內建立供內部使用的自訂應用程式

由貴組織中的開發人員建立的應用程式稱為自訂應用程式 (或企業營運應用程式)。 貴組織可能會針對組織特定的需求委託建立自訂應用程式。 您有權為整個組織或特定使用者允許或封鎖此類應用程式。 貴組織的開發人員可以使用與 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 整合的 Teams 來建立自訂低程式碼解決方案。

當系統管理員允許使用自訂應用程式後，使用者可以在 Teams 市集的左側流覽中選取 **[為您的組織打造** ] 來尋找這類應用程式。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 傳統型應用程式中 Teams 市集中自訂應用程式的螢幕擷取畫面。" lightbox="media/built-for-your-org2.png":::

如需詳細資訊，請參 [閱瞭解及管理自訂及側載的應用程式](custom-app-overview.md)。

## <a name="about-app-templates"></a>關於應用程式範本

使用應用程式開發方法，Microsoft 會建立並提供功能與生產就緒的範例應用程式。 這些應用程式統稱為 Teams 的應用程式範本，並提供給：

* 說明 Teams 中的一些共同作業使用案例。
* 展示應用程式開發的最佳做法和方法。
* 提供開放原始碼應用程式，讓開發人員可以擴充以建立自己的應用程式。

您的組織開發人員會透過簡易變更提供的原始程式碼來自訂應用程式範本。 您為使用者提供這些應用程式做為自訂應用程式，以符合任何組織的需求。

若要深入了解，請參閱 [Microsoft Teams 應用程式範本](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="understand-app-capabilities"></a>瞭解應用程式功能

Teams 應用程式功能是可以在應用程式中內建的核心功能，以啟用整合和互動。

:::row:::
    :::column span="":::
    :::column-end:::
    :::column span="3":::
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="顯示 Microsoft Teams 應用程式應用程式功能的圖形。" border="false":::
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::

為了提供讓使用者在 Teams 中工作的豐富體驗，應用程式開發人員可使用下列功能建立應用程式：

* **Bot**：Bot 也稱為聊天機器人或交談機器人。 它是執行簡單且重複的工作的應用程式。 聊天機器人互動可以是快速的問題與解答，也可以是提供存取服務或協助的複雜交談。 使用者可以在個人聊天、頻道或群組聊天中與 Bot 交談。 如需詳細資訊，請參閱 [Microsoft Teams 中的 Bot](/microsoftteams/platform/bots/what-are-bots)。

  Teams 支援在私人聊天和頻道中使用 Bot。 系統管理員可以控制是否允許在 Microsoft 365 或 Office 365 組織中使用 Bot。 如需開啟或關閉自訂 Bot 的相關資訊，請參 [閱 Teams 系統管理中心的應用程式管理和控管概觀](manage-apps.md)。

* **索引標籤**：索引標籤是釘選在頻道或聊天頂端的 Teams 感知網頁。 索引標籤可讓您以類似網頁的體驗與內容和服務互動。 它們是簡單的 HTML <iframe \> 標籤，指向應用程式資訊清單中宣告的網域，而且可以新增為個別使用者團隊、群組聊天或個人應用程式內頻道的一部分。 如需詳細資訊，請參閱 [Microsoft Teams 索引標籤](/microsoftteams/platform/tabs/what-are-tabs)。

  在每個私人聊天中，預設會建立 [交談]、[檔案]、[組織] 和 [活動] 索引標籤。 除了這些內建索引標籤之外，開發人員還可以設計和新增自訂索引標籤。 如需詳細資訊，請參閱 [在 Teams 中使用內建和自訂索引標籤](/microsoftteams/platform/tabs/what-are-tabs)。

* **Web 端子和連接器**：Web 端子和連接器可協助將 Web 服務連線到 Microsoft Teams 中的頻道和團隊。 Web 端子是使用者定義的 HTTP 回撥，會通知使用者 Teams 頻道中已執行的任何動作。 這是應用程式取得即時資料的一種方式。 連接器可讓使用者訂閱，以接收來自您 Web 服務的通知和訊息。 如需詳細資訊，請參閱 [網路任務和連接器](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。

  若要允許使用者在 Teams 中使用自訂連接器，請參閱 [在 Teams 中使用自訂連接器](office-365-custom-connectors.md)。

* **訊息中心延伸** 模組：訊息擴充功能是插入應用程式內容或在訊息上採取行動的快速鍵，使用者不必離開交談。 使用者可以從撰寫郵件區域、命令方塊或直接從郵件中搜尋或啟動外部系統中的動作。 如需詳細資訊，請參閱 [訊息延伸模組](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet)。

* **會議擴充** 功能：使用者可以整合會議中的索引標籤、Bot 和訊息擴充功能，增強會議體驗，提高會議生產力。 您可以識別各種參與者角色和使用者類型、取得會議事件，以及產生會議內對話方塊。 如需詳細資訊，請參閱 [Teams 會議相關應用程式](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings)。

* **卡片和工作模組：卡** 片可為使用者提供各種視覺、音訊和可選取的訊息，以及交談流程中的說明。 工作模組可協助您在 Microsoft Teams 中建立模式快顯體驗。 它們對於開始和完成工作，或是顯示如影片或 Power business intelligence (BI) 儀表板等豐富資訊很有用。 如需詳細資訊，請參閱 [卡片和工作模組](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules)。

若要檢視對應至 Teams 功能的常見使用案例，請參閱將 [您的使用案例對應至 Teams 應用程式功能](/microsoftteams/platform/concepts/design/map-use-cases)。

## <a name="related-articles"></a>相關文章

* [深入瞭解 Teams 的應用程式範本](/microsoftteams/platform/samples/app-templates)
* [Teams 系統管理中心的應用程式管理和控管概觀](manage-apps.md)
