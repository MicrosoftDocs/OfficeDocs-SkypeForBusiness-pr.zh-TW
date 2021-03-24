---
title: 上機檢查清單 - 設定核心功能 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您為貴組織設定 Teams 時，請遵循此檢查清單的核心、工作與活動。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c28f33cb8d3c3823f74deb8f6540a39482f68b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098029"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>設定 Microsoft Teams 核心功能

| 否 | 活動或工作 | 說明 | 完成？ | 其他資訊 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 驗證您的環境包含所有 Teams 先決條件 | Teams 依賴其他平臺來建構端對端共同解決方案。 與 IT 小組合作，確保您已部署並正確設定 Exchange、SharePoint Online 和商務用 OneDrive。 | | [SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md) <br/><br/>[Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md) |
| 2  | 驗證租使用者已啟用 Teams | 所有組織預設都開啟 Teams。 檢查 **Microsoft** 365 系統管理&中的服務與載入載入元件頁面，確認貴組織已啟用 Teams，並視需要啟用。 | | [在 Microsoft 365 或 Office 365 中設定 Microsoft Teams](office-365-set-up.md) |
| 3  | 設定角色和許可權 | Teams 支援兩種類型的角色：成員和擁有者。 <br/><br/>將成員新增到團隊後，擁有者也可以將成員升級為擁有者角色。 最佳做法是，建議您將至少兩個擁有者指派給每個團隊。 <br/><br/>根據預設，組織中擁有 Exchange Online 上託管信箱的每個人都可以建立團隊。 建立新團隊的使用者會自動獲授予該團隊的擁有者角色。 <br/><br/>視需要，您可以設定 Microsoft 365 群組設定，只讓特定使用者建立新團隊。 | | [在 Microsoft Teams 中指派角色和許可權](assign-roles-permissions.md) <br/><br/>[Microsoft 365 群組和 Microsoft Teams](office-365-groups.md) <br/><br/>[管理誰可以建立 Microsoft 365 群組](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 設定租使用者範圍的 Teams 設定 | 您可以在租使用者層級設定一些 Teams 設定。 已啟用 Teams 的使用者會從租使用者設定繼承這些設定：<ul><li>一般</li><li>電子郵件整合</li><li>應用程式</li><li>自訂雲端儲存空間</li><li>通話和會議</li><li>訊息傳送</li></ul>| | [管理組織的 Microsoft Teams 設定](enable-features-office-365.md) |
| 5  | 選擇性：設定來賓存取權 | 您可以在 Teams 中使用來賓存取權，將團隊和頻道的存取權授予組織外部人員，以共同合作。 來賓存取權是 Teams 中的租使用者層級設定。 預設為關閉。 <br/>如果貴組織打算使用此功能，請啟用來賓存取並設定全租使用者來賓設定。 | | [Microsoft Teams 中的來賓存取](guest-access.md) |
| 6  | 選擇性：設定 Teams 命名策略 | 當使用者建立或編輯團隊名稱時，Teams 會運用 Microsoft 365 群組的命名策略。 <br/><br/>根據預設，當使用者建立團隊時，不會採用任何命名限制。 <br/><br/>如果您需要強制執行團隊名稱的規則，請設定適用于貴組織的 Microsoft 365 群組命名原則。 您可以設定強制性的首碼和尾碼，並指定封鎖的字詞。 | | [在 Microsoft Teams 中建立團隊時，規劃 Microsoft 365 群組](plan-office-365-groups.md) <br/><br/>[Microsoft 365 群組命名政策](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 設定 Teams SMTP 網域的 Exchange | Teams 使用 Exchange Online 在新增或移除小組成員時，使用 SMTP 網域 email.teams.microsoft.com 傳送通知給小組成員。 <br/><br/>請務必將此 SMTP 網域新增到 Exchange 基礎結構中公認的網域清單中。 | | [在 Exchange 中建立安全的寄件者清單](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | 設定及管理 Teams 的使用者存取權 | 雖然我們強烈建議您啟用 Teams 的所有使用者，但您可以指派或移除 Teams 產品授權，允許或不允許以每個使用者為基礎存取 Teams。 | | [管理 Microsoft Teams 的使用者存取權](user-access.md) |
| 9  | 指派授權給使用者 | 針對音訊會議、電話系統及通話方案等功能指派授權給使用者 | | [指派 Microsoft Teams 附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 選擇性：使用 PowerShell 管理 Teams | 您可以使用 PowerShell Cmdlet，而不是 Microsoft 365 系統管理中心來管理 Teams 設定。 | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |