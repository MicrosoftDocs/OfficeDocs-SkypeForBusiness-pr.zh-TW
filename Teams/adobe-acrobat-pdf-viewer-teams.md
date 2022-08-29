---
title: 將 Adobe Acrobat 做為 Teams 中的預設 PDF 檢視器
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: 了解如何將 Adobe Acrobat 設定為預設的 PDF 檢視器，以便在 Microsoft Teams 中檢視和編輯 PDF 檔案。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: b1c5654791dde3def8ec622880e26b07f693633f
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396704"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>將 Adobe Acrobat 做為 Microsoft Teams 中的預設 PDF 檢視器

> [!NOTE]
> 將 Adobe Acrobat 做為 Microsoft Teams 中的預設 PDF 體驗目前僅在公開預覽中提供。 若要使用此功能，系統管理員必須為其租用戶 [啟用公開預覽](public-preview-doc-updates.md#enable-public-preview)，並確保使用者將 Teams 用戶端版本變更為公開預覽。

身為系統管理員，您可以將 Adobe Acrobat 設為預設應用程式，以便在 Microsoft Teams 中檢視和編輯 PDF 檔案。 您的使用者可以在不使用 Adobe Acrobat 訂閱或 Adobe ID 的情況下，檢視、搜尋、註解及標註 PDF 檔案。

若要將 Adobe Acrobat 應用程式設定為租用戶中 PDF 檔案的預設處理常式，請在必要條件中完成下列步驟：

* [允許 Adobe Acrobat 應用程式](#allow-adobe-acrobat-app-in-your-tenant)。
* [安裝 Adobe Acrobat Reader](#install-adobe-acrobat-app-for-all-users)。

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>在您的租用戶中允許 Adobe Acrobat 應用程式

在設定應用程式之前，請確定您允許在租用戶中使用應用程式、明確允許 Adobe Acrobat 應用程式，且應用程式權限原則允許 Adobe Acrobat 應用程式。 若要將 Adobe Acrobat 設定為 PDF 檔案的預設應用程式，請遵循下列步驟：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 搜尋 Adobe Acrobat 應用程式，然後選取它。 它會開啟應用程式詳細資料頁面。

1. 選取 [ **許可權] 索引卷** 標，然後選取 [ **檢閱許可權]**。

   :::image type="content" source="media/permission-policy.png" alt-text="Microsoft Teams 系統管理中心的應用程式權限螢幕擷取畫面。" lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. 選取 **[接受]**。

## <a name="install-adobe-acrobat-app-for-all-users"></a>為所有使用者安裝 Adobe Acrobat 應用程式

若要指派並讓所有使用者都能使用 Adobe Acrobat 應用程式，請遵循下列步驟：

1. 在 Teams 系統管理中心，移至 **Teams 應用程式**  >  [**設定原則**](https://admin.teams.microsoft.com/policies/app-setup)。

1. 在 **[管理原則]** 索引標籤下，選取 **[全域 (全組織預設)]**，然後選取 **[編輯]**。

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 系統管理中心中 Adobe Acrobat 應用程式設定原則的螢幕擷取畫面。":::

1. 在已安裝的應用程式下，選取 **[新增應用程式]**。

1. 搜尋 **Adobe Acrobat**，選取應用程式名稱旁的 **[新增]**，然後選取 **[新增]**。

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="顯示如何為所有使用者新增 Adobe Acrobat 應用程式的螢幕擷取畫面。" lightbox="media/add-adobe-acrobat-app.png":::

1. 選取 [儲存 **]**。

選取 [儲存] 之後，Teams 會使用 Adobe Acrobat 應用程式做為 PDF 檔案的預設檔案處理常式。

如果您想要為少數人或群組選擇性地允許 Adobe Acrobat 應用程式，您可以指派 [自訂應用程式權限原則](teams-app-permission-policies.md)。

了解下列有關此功能的資訊：

* 設定原則之後，通常需要[幾個小時](teams-app-setup-policies.md)，應用程式才能供使用者使用。
* 檢視釘選在頻道中的 PDF 檔案做為索引標籤，而在 [作業] 應用程式中檢視 PDF 檔案時，仍可繼續由原生 Teams 體驗提供。
* 將 Adobe Acrobat 做為 Teams 中的預設 PDF 檢視器僅適用於桌面和 Web 用戶端。 行動用戶端不支援此功能。
* 使用者需要 Adobe Acrobat 方案才能使用進階工具，例如匯出 PDF、組織頁面、合併檔案、壓縮 PDF 及保護 PDF。
* 若要解除安裝應用程式，使用者可以從 Teams 用戶端移除應用程式。 系統管理員可以使用安裝原則移除 Adobe Acrobat 應用程式。
* 如果您封鎖 Adobe Acrobat 應用程式，請將它從設定原則中移除。 這可確保使用者體驗還原為使用原生 PDF 檔案檢視器。
* 從 Teams 桌面用戶端，如果您在登入 Adobe Acrobat 應用程式時遇到任何問題，請使用瀏覽器中的 Teams 登入。
