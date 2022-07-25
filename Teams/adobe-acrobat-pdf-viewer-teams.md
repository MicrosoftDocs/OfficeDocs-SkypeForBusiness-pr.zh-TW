---
title: Adobe Acrobat 做為 Teams 中的預設 PDF 檢視器
author: guptaashish
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
description: 瞭解如何將 Adobe Acrobat 設定為預設的 PDF 檢視器，以便在 Microsoft Teams 中檢視和編輯 PDF 檔案。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002334"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Adobe Acrobat 做為 Teams 中的預設 PDF 檢視器

> [!NOTE]
> Teams 中的 Adobe Acrobat 預設 PDF 體驗目前僅在公開預覽中提供。 使用此功能之前，請先為您的租使用者[啟用公開預覽](public-preview-doc-updates.md#enable-public-preview)。 確保使用者將 Teams 用戶端版本變更為公開預覽，以在 Teams 中體驗 Adobe Acrobat 做為 PDF 檢視器。

身為系統管理員，您可以將 Adobe Acrobat 設為預設應用程式，以便在 Microsoft Teams 中檢視及編輯 PDF 檔案。 您的使用者不需要 Adobe Acrobat 訂閱或 Adobe ID 來檢視、搜尋、批註及標注 PDF 檔案。

## <a name="set-up-adobe-acrobat-app"></a>設定 Adobe Acrobat 應用程式

若要將 Adobe Acrobat 設定為預設應用程式來檢視 PDF 檔案，請依照下列步驟進行：

1. 登入 Teams 系統管理中心，然後移至 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 搜尋 Adobe Acrobat 應用程式，然後選取 **Adobe Acrobat** 應用程式。

   > [!NOTE]
   >
   > * 確定 Adobe Acrobat 應用程式狀態已設為 **[允許]**。 否則，請啟 **用 [允許]** 切換開關。
   > * 如果應用程式許可權原則或整個組織應用程式設定中有任何已封鎖應用程式的現有系統管理設定，請確定您允許應用程式在 [應用程式許可權原則](teams-app-permission-policies.md) 或 [整個組織應用程式設定](teams-app-permission-policies.md)中使用。

1. 在 [ **許可權] 索引標籤中** ，選 **取 [檢閱許可權]**。

1. 選取 **[接受]**。

   :::image type="content" source="media/permission-policy.png" alt-text="Teams 系統管理中心中應用程式許可權的螢幕擷取畫面。" lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>為所有使用者安裝 Adobe Acrobat 應用程式

您可以使用全域 (組織的預設) 原則來指派並讓所有使用者都能使用 Adobe Acrobat 應用程式。 此步驟會在 Teams 中觸發訊號，將應用程式設定為 PDF 檔案的預設檔案處理常式。 若要為所有使用者指派 Adobe Acrobat 應用程式，請遵循下列步驟：

1. 在 Teams 系統管理中心，移至 **Teams 應用程式**  >  [**設定原則**](https://admin.teams.microsoft.com/policies/app-setup)。

1. 在 **[管理原則]** 索引標籤下，選 **取 [全域 (預設)**]，然後選取 [ **編輯]**。

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 系統管理中心中 Adobe Acrobat 應用程式設定原則的螢幕擷取畫面。":::

1. 在 [已安裝的應用程式] 底下，選取 **[新增應用程式]**。

1. 搜尋 **Adobe Acrobat**，選取應用程式名稱旁的 **[新增** ]，然後選取 [ **新增]**。

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="顯示如何為所有使用者新增 Adobe Acrobat 應用程式的螢幕擷取畫面。" lightbox="media/add-adobe-acrobat-app.png":::

1. 選取 [儲存 **]**。

選取 [儲存] 後，系統會將 Adobe Acrobat 應用程式設定為透過 Teams，從聊天、頻道或檔案應用程式開啟 Adobe Acrobat 應用程式中的任何 PDF 檔案。

如果您想要為少數特定人員或群組選擇性地允許 Adobe Acrobat 應用程式，您可以指派 [自訂應用程式許可權原則](teams-app-permission-policies.md)。

瞭解下列有關此功能的資訊：

* 設定原則之後，通常需要 [幾個小時](teams-app-setup-policies.md) ，應用程式才能供使用者使用。
設定原則之後，安裝的應用程式會在幾個小時後提供給使用者使用。
* 檢視釘選在頻道中的 PDF 檔案做為索引標籤，並在作業應用程式中檢視 PDF 檔案時，仍可繼續由原生 Teams 體驗提供。
* 在 Teams 中做為預設 PDF 檢視器的 Adobe Acrobat 僅適用于桌面和 Web 用戶端。 行動用戶端不支援此功能。
* 使用者需要 Adobe Acrobat 方案來使用進階工具，例如匯出 PDF、組織頁面、合併檔案、壓縮 PDF 及保護 PDF。

> [!NOTE]
> 從 Teams 桌面用戶端，如果您在登入 Adobe Acrobat 應用程式時遇到任何問題，您可以在瀏覽器中開啟 Teams 並登入。 這是已知的問題，將于 2022 年 9 月解決。

## <a name="faqs"></a>常見問題 解答

* 如何從 Teams 用戶端移除 Adobe Acrobat 應用程式？
  
  使用者可以從 Teams 用戶端卸載應用程式，而系統管理員可以從設定原則中移除 Adobe Acrobat 應用程式。

* 系統管理員可以在 Adobe Acrobat 應用程式設為預設處理常式後封鎖它嗎？
  
  是的，但是在系統管理員封鎖應用程式之前，請先移除設定原則，以確保使用者能安全地回到 Teams 預設體驗。
