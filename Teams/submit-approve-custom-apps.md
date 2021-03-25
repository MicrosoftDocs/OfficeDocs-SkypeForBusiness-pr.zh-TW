---
title: 使用 Teams App 提交 API 來提交和核准您的自訂應用程式
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何核准使用 Microsoft Teams 中的 Teams App 提交 API 提交的自訂應用程式。
ms.openlocfilehash: 8c12d93a0b4420fd248064c69308e8049dc6326f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116971"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>發佈透過 Teams App 提交 API 提交的自訂應用程式

## <a name="overview"></a>概觀

> [!NOTE]
> 當您發佈自訂 Teams App 時，組織 App Store 中的使用者可以使用它。 發佈自訂應用程式的方法有兩種，而使用方式取決於您取得應用程式的方式。 **本文著重于如何核准** 及發佈開發人員透過 Teams App 提交 API 提交的自訂應用程式。 當開發人員以 .zip 格式傳送應用程式套件時，會使用另一種方法 ，即上傳自訂應用程式。 若要深入瞭解這個方法，請參閱上傳應用程式套件 <a href="/microsoftteams/upload-custom-apps" target="_blank">來發佈自訂應用程式</a>。 GCC 租使用者無法使用核准應用程式小工具。 

> [!IMPORTANT]
> 這個方法目前不適用於 GCC 環境。 您必須使用上傳 *自訂應用程式的方法* 。

本文提供如何將 Teams 應用程式從開發到部署到探索的端對端指南。 您將概觀瞭解 Teams 在應用程式生命週期內提供的連接體驗，以簡化如何開發、部署及管理貴組織 App Store 中的自訂應用程式。

我們將涵蓋生命週期的每一個步驟，包括開發人員如何使用 Teams App 提交 API 將自訂應用程式直接提交至 Microsoft Teams 系統管理中心，以便您進行審閱和核准、如何設定管理貴組織使用者相關應用程式的政策，以及使用者如何在 Teams 中探索這些 App。

![從開發到部署的應用程式概觀](media/custom-app-lifecycle.png)

本指南著重于應用程式的 Teams 層面，適用于系統管理員和 IT 專業人員。 有關開發 Teams 應用程式的資訊，請參閱 <a href="/microsoftteams/platform" target="_blank">Teams 開發人員檔</a>。

## <a name="develop"></a>開發

### <a name="create-the-app"></a>建立應用程式

Microsoft Teams 開發人員平臺讓開發人員能輕鬆整合您自己的應用程式和服務，以提高生產力、更快速地做出決策，並圍繞現有內容和工作流程建立共同作業。 Teams 平臺內建的應用程式是 Teams 用戶端與服務與工作流程之間的橋樑，直接將它們納入您的共同合作平臺中。 若要詳細資訊，請前往 <a href="/microsoftteams/platform" target="_blank">Teams 開發人員檔</a>。

### <a name="submit-the-app"></a>提交應用程式

當應用程式可供生產使用時，開發人員可以使用 Teams App 提交 API 提交應用程式，此 API 可稱為 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API、</a>整合式開發環境 (IDE) 例如 Visual Studio 程式碼，或 Power Apps 和 Power Virtual Agents 等平臺。 這麼做之後，App 就可以在<a href="/microsoftteams/manage-apps" target="_blank"></a>Microsoft Teams 系統管理中心的管理應用程式頁面上使用，而您的系統管理員可以在這裡進行審核和核准。

Microsoft Graph 內建的 <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Teams</a>App 提交 API 可讓您的組織在所選擇的平臺上開發，並自動化 Teams 上自訂應用程式的提交至核准程式。

以下範例說明此 App 提交步驟在 Visual Studio Code 中的外觀：

![在 Visual Studio 程式碼中提交應用程式](media/custom-app-lifecycle-submit-app.png)

請記住，這尚未將應用程式發佈至組織的 App Store。 此步驟將應用程式提交至 Microsoft Teams 系統管理中心，您可以在此核准 App 發佈到貴組織的 App Store。

有關使用 Graph API 提交應用程式之詳細資訊，請參閱 <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">這裡</a>。

## <a name="validate"></a>驗證

Microsoft Teams <a href="/microsoftteams/manage-apps" target="_blank">系統</a>管理中心中的 (頁面位於左側流覽中，請前往 **Teams 應用程式** 管理應用程式) ，讓您查看貴組織的所有 Teams  >  應用程式。 頁面 **頂端的** 擱置核准小工具可讓您知道何時提交自訂應用程式供核准。

在表格中，新提交的應用程式會自動顯示已提交和封鎖狀態的 **發佈狀態**。   您可以 **以遞減** 順序排序發佈狀態列，以快速找到應用程式。

![發佈狀態 ](media/custom-app-lifecycle-validate-app.png)

按一下應用程式名稱以前往應用程式詳細資料頁面。 在關於 **的** 選項卡上，您可以查看應用程式的詳細資訊，包括描述、狀態、提交者及應用程式識別碼。

![提交應用程式的應用程式詳細資料頁面](media/custom-app-lifecycle-app-details.png)

有關使用 Graph API 檢查發佈狀態之詳細資訊，請參閱<a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">這裡</a>。

## <a name="publish"></a>發佈

當您準備好要讓使用者使用 App 時，請發佈應用程式。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 按一下應用程式名稱以前往應用程式詳細資料頁面，然後在 [發佈 **狀態** > 方塊中，選取 [ **發佈**> 。

    發佈應用程式之後，發佈 **狀態會變更****為已發佈**，而狀態 **會自動** 變更為 **允許**。

## <a name="set-up-and-manage"></a>設定和管理

### <a name="control-access-to-the-app"></a>控制應用程式的存取權

根據預設，貴組織的所有使用者都可以存取貴組織 App Store 中的應用程式。 若要限制及控制誰有權使用應用程式，您可以建立並指派應用程式權限原則。 如需深入了解，請參閱<a href="/microsoftteams/teams-app-permission-policies" target="_blank">管理 Teams 中的應用程式權限原則</a>。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>釘上並安裝應用程式供使用者探索

根據預設，使用者若要尋找應用程式，必須前往貴組織的 App Store 並流覽或搜尋。 若要讓使用者輕鬆取得應用程式，您可以將應用程式釘到 Teams 中的應用程式欄。 若要這麼做，請建立應用程式設定策略並指派給使用者。 若要深入了解，請參閱<a href="/microsoftteams/teams-app-setup-policies" target="_blank">管理 Teams 中的應用程式設定原則</a>。

### <a name="search-the-audit-log-for-teams-app-events"></a>搜尋 Teams App 事件的稽核記錄

您可以搜尋稽核記錄來查看貴組織的 Teams 應用程式活動。 若要深入瞭解如何搜尋稽核記錄，以及查看記錄在稽核記錄中的 Teams 活動清單，請參閱在 Teams 中搜尋稽核 <a href="/microsoftteams/audit-log-events" target="_blank">記錄中的事件</a>。

在您可以搜尋稽核記錄檔之前，您必須先在<a href="https://protection.office.com" target="_blank">安全性與合規性中心</a>中開啟稽核。 如需深入了解，請參閱<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">開啟或關閉稽核記錄</a>。 請記住，只有當您開啟稽核時，才能使用稽核資料。

## <a name="discover-and-adopt"></a>探索及採用

擁有應用程式許可權的使用者可以在貴組織的 App Store 中找到它。 前往 **應用程式頁面上 *的*** 專為您的組織名稱建立，以尋找貴組織的自訂應用程式。

![顯示已發佈 App 的 App 頁面 ](media/custom-app-lifecycle-discovery.png)

如果您建立並指派了應用程式設定策略，應用程式會釘到 Teams 中的應用程式欄，以便指派該策略的使用者輕鬆存取。

## <a name="update"></a>更新

若要更新應用程式，開發人員應該繼續遵循開發區段 [的步驟](#develop) 。

當開發人員將更新提交到已發佈的自訂 App 時，系統就會在管理應用程式頁面的擱置 **核准** 小工具 <a href="/microsoftteams/manage-apps" target="_blank">中收到通知</a> 。 在表格中， **應用程式的** 發佈狀態會設定為已 **提交更新**。

![顯示擱置要求和應用程式狀態的管理應用程式頁面 ](media/custom-app-lifecycle-update-submitted.png)

若要審查併發布應用程式更新：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 按一下應用程式名稱以前往應用程式詳細資料頁面，然後選取 [可用的更新來查看更新詳細資料。

    ![應用程式詳細資料頁面](media/custom-app-lifecycle-update-app.png)
3. 當您準備好時，請選取 **發佈** 以發佈更新。 這麼做會取代現有的應用程式、更新版本號碼，以及將 **發佈狀態變更** 為 **已發佈**。 對於更新的應用程式，所有應用程式權限原則與應用程式設定策略仍然會強制執行。

    如果您拒絕更新，應用程式的較舊版本會維持發佈狀態。

請記住下列事項：

- 應用程式核准後，任何一個人都可以將更新提交至應用程式。 這表示其他開發人員 ，包括原本提交應用程式的開發人員，可以提交更新至應用程式。
- 當開發人員提交 App 且要求擱置中時，只有相同的開發人員可以提交更新至應用程式。 其他開發人員只能在應用程式核准後提交更新。

有關使用 Graph API 更新應用程式之詳細資訊，請參閱 <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">這裡</a>。

### <a name="update-experience-for-users"></a>使用者的更新體驗

在大多數的情況下，發佈 App 更新之後，新版本會自動顯示給使用者。 不過，Microsoft <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Teams</a> 清單有一些更新需要使用者接受才能完成：

* 已新增或移除 Bot
* 現有 Bot 的「botId」屬性已變更
* 已變更現有 Bot 的 "isNotificationOnly" 屬性
* Bot 的「支援檔」屬性已變更
* 已新增或移除訊息擴充功能
* 已新增連接器
* 已新增靜態定位停駐點
* 已新增可配置的選項卡
* 「webApplicationInfo」中的屬性已變更

![提供新版本](media/manage-your-custom-apps-update1.png)

![應用程式的升級選項](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>相關主題

- [上傳應用程式套件來發佈自訂應用程式](upload-custom-apps.md)
- [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
- [在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
- [在 Teams 中管理應用程式設定原則](teams-app-setup-policies.md)
- <a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Teams 應用程式的 Microsoft Graph API</a>