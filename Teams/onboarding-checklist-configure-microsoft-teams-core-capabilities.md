---
title: 上機檢查清單 - 設定核心功能 - Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您為組織設定專案時，請遵循此檢查清單Teams工作與活動。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7bce0a3d1b55e0cb0f8c8130c89f390a309967d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865642"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>設定Microsoft Teams核心功能

| 否 | 活動或工作 | 描述 | 完成？ | 其他資訊 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 驗證您的環境是否包含Teams先決條件 | Teams依賴其他平臺來建構端對端共同解決方案。 與 IT 小組合作，確保您已部署並正確Exchange、SharePoint線上商務用 OneDrive。 | | [線上SharePoint與商務用 OneDrive互動的方式Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md) |
| 2  | 驗證Teams租使用者已啟用 | Teams所有組織預設都開啟該按鈕。 檢查 **&中的** 服務載入Microsoft 365 系統管理中心頁面，確認Teams已啟用貴組織，並在必要時啟用。 | | [在 Microsoft Teams 或 Microsoft 365 中Office 365](office-365-set-up.md) |
| 3  | 設定角色和許可權 | Teams支援兩種類型的角色：成員和擁有者。 <br/><br/>將成員新增到團隊後，擁有者也可以將成員升級為擁有者角色。 最佳做法是，建議您將至少兩個擁有者指派給每個團隊。 <br/><br/>根據預設，組織中每一位在 Exchange Online上託管信箱的人Exchange Online建立團隊。 建立新團隊的使用者會自動獲授予該團隊的擁有者角色。 <br/><br/>如果需要，您可以設定群組Microsoft 365只讓特定使用者建立新團隊。 | | [指派角色和許可權Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365群組Microsoft Teams](office-365-groups.md) <br/><br/>[管理誰可以建立Microsoft 365群組](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 設定租使用者Teams設定 | 您可以在租使用者層級Teams一些設定。 啟用訂閱的使用者Teams從租使用者設定繼承這些設定：<ul><li>一般</li><li>電子郵件整合</li><li>應用程式</li><li>自訂雲端儲存空間</li><li>通話和會議</li><li>訊息傳送</li></ul>| | [管理組織的 Microsoft Teams 設定](enable-features-office-365.md) |
| 5  | 選擇性：設定來賓存取權 | 您可以使用來賓存取Teams組織外部人員，以授予他們團隊和頻道的存取權來共同合作。 來賓存取是在 Teams。 預設為關閉。 <br/>如果貴組織打算使用此功能，請啟用來賓存取並設定全租使用者來賓設定。 | | [Microsoft Teams 中的來賓存取](guest-access.md) |
| 6  | 選擇性：設定Teams命名策略 | Teams使用者建立或編輯小組名稱時，Microsoft 365群組的命名策略。 <br/><br/>根據預設，當使用者建立團隊時，不會採用任何命名限制。 <br/><br/>如果您需要強制執行團隊名稱的規則，請Microsoft 365適用于貴組織的群組命名原則。 您可以設定強制性的首碼和尾碼，並指定封鎖的字詞。 | | [在 Microsoft 365中建立團隊時，規劃Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Microsoft 365群組命名策略](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 設定Exchange SMTP 網域Teams網域 | Teams新增Exchange Online使用 SMTP 網域來傳送通知給小組成員，email.teams.microsoft.com 或移除時傳送通知。 <br/><br/>請務必將此 SMTP 網域新增到您基礎結構中公認的網域Exchange清單中。 | | [在郵件中建立安全的寄件者Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | 設定及管理使用者對 Teams | 雖然強烈建議您為 Teams Teams 啟用所有使用者，但您可以指派或移除 Teams 產品授權，以允許或禁止存取 Teams。 | | [管理使用者對 Microsoft Teams](user-access.md) |
| 9  | 指派授權給使用者 | 指派授權給使用者，以使用音訊會議、電話系統和通話方案等功能 | | [指派Microsoft Teams附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 選擇性：使用 PowerShell 管理Teams | 您可以使用 PowerShell Cmdlet，而非 Microsoft 365 系統管理中心管理和管理Teams設定。 | | [Microsoft TeamsPowerShell](/powershell/module/teams/?view=teams-ps) |