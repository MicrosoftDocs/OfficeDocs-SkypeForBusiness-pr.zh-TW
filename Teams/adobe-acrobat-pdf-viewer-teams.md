---
title: 將 Adobe Acrobat 做為 Teams 中的預設 PDF 檢視器
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 09/25/2022
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
ms.openlocfilehash: 67be332ee916f30b0341dc3ac03e047558cead0c
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343278"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>將 Adobe Acrobat 設定為 Microsoft Teams 中的預設 PDF 檢視器

身為系統管理員，您可以將 Adobe Acrobat 設為預設應用程式，以便在 Microsoft Teams 中檢視和編輯 PDF 檔案。 您的使用者可以檢視和搜尋 PDF 檔案。 使用者也可以在登入之後免費批註 PDF 檔案並加上批註。

若要將 Adobe Acrobat 應用程式設定為租用戶中 PDF 檔案的預設處理常式，請在必要條件中完成下列步驟：

* [允許 Adobe Acrobat 應用程式](#allow-adobe-acrobat-app-in-your-tenant)。
* [安裝 Adobe Acrobat Reader](#install-adobe-acrobat-app-for-all-users)。

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>在您的租用戶中允許 Adobe Acrobat 應用程式

若要將應用程式設定為預設 PDF 檢視器，請確定您允許在租使用者中 [使用協力廠商應用程式](manage-apps.md#manage-org-wide-app-settings) 。 然後遵循下列指示，將 Adobe Acrobat 設定為 PDF 檔案的預設應用程式。

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

1. 或者，如果您擁有 Adobe Acrobat 授權，也可以允許 SSO 使用Microsoft Azure Active Directory身分識別。 我們建議您使用設定 [身分識別和單一登入](https://helpx.adobe.com/enterprise/using/set-up-identity.html)中的指示來設定 SSO。

完成設定後，Teams 會使用 Adobe Acrobat 應用程式做為 PDF 檔案的預設檔案處理常式。

如果您想要為少數人或群組選擇性地允許 Adobe Acrobat 應用程式，請使用 [應用程式許可權原則](teams-app-permission-policies.md)。

## <a name="considerations-and-limitations"></a>考量與限制

了解下列有關此功能的資訊：

* 設定原則之後，通常 [需要幾個小時](teams-app-setup-policies.md#considerations-and-limitations) ，應用程式才能供使用者使用。
* Teams 應用程式的原生 PDF 體驗可用來檢視釘選在頻道中的 PDF 檔案做為索引標籤，而且可在 [作業] 應用程式中使用。
* 將 Adobe Acrobat 做為 Teams 中的預設 PDF 檢視器僅適用於桌面和 Web 用戶端。 行動用戶端不支援此功能。
* 使用者需要 Adobe Acrobat 方案才能使用進階工具，例如匯出 PDF、組織頁面、合併檔案、壓縮 PDF 及保護 PDF。
* 若要卸載應用程式，使用者可以從他們的 Teams 用戶端移除應用程式。 管理員可以使用安裝原則移除 Adobe Acrobat 應用程式。
* 如果您封鎖 Adobe Acrobat 應用程式，請從設定原則中移除應用程式。 這可確保使用者體驗還原為使用原生 PDF 檔案檢視器。
* 如果您在 Teams 桌面用戶端中登入 Adobe Acrobat 應用程式時遇到任何問題，請使用 [瀏覽器中的 Teams](https://teams.microsoft.com/) 登入。
* 登入免費 [的 Adobe 帳戶](https://acrobat.adobe.com/us/en/) ，以在 PDF 檔案上加上批註或加上批註。 Teams 中的應用程式可以提供像是注釋、組織、壓縮及保護 PDF 檔案等功能。 如需功能與先決條件的完整清單，請參閱 [在 Teams 中使用 Acrobat 應用程式管理 PDF 檔案](https://www.adobe.com/content/dam/dx-dc/pdf/ue/acrobat-msft-teams-feature-comp-ue.pdf)。
* 當您在 PDF 檔上共同作業時，系統會將檔暫時儲存 (最多 24 小時，) 儲存在您所在地區的 Adobe 伺服器上。 此暫時儲存空間有助於暫時處理。 當您的檔從本機檔案系統傳輸到伺服器，並在伺服器上保持加密時，您的檔會端對端加密。 請參閱 [Acrobat 的安全性](https://aka.ms/Adobe_Acrobat_Security)。
