---
title: 上線檢查清單 - 設定核心功能 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您為組織設定 Teams 時，請遵循此檢查清單中的核心待辦事項工作和活動。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 170f62afd6cd75d5060243271fb951cf9dd4aa5c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270888"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>設定 Microsoft Teams 核心功能

| 否 | 活動或工作 | 描述 | 完成？ | 其他資訊 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 驗證您的環境包含所有 Teams 先決條件 | Teams 取決於其他平臺來建構端對端共同作業解決方案。 與您的 IT 小組合作，確保您已部署並正確設定 Exchange、SharePoint Online 和 商務用 OneDrive。 | | [SharePoint Online 和 商務用 OneDrive如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md) <br/><br/>[Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md) |
| 2  | 驗證已針對租使用者啟用 Teams | 所有組織預設都會開啟 Teams。 檢查 **Microsoft 365 系統管理中心中的 [服務&載入** 宏] 頁面，確認已為貴組織啟用 Teams，並視需要啟用。 | | [在 Microsoft 365 或 Office 365 中設定 Microsoft Teams](office-365-set-up.md) |
| 3  | 設定角色和許可權 | Teams 支援兩種角色類型：[成員] 和 [擁有者]。 <br/><br/>將成員新增至團隊後，擁有者也可以將成員升級為擁有者角色。 最佳作法是建議您至少指派兩個擁有者給每個團隊。 <br/><br/>根據預設，組織中每個在Exchange Online主控信箱的人都可以建立團隊。 建立新團隊的使用者會自動獲授與該團隊的擁有者角色。 <br/><br/>如有需要，您可以設定 Microsoft 365 群組設定，只讓特定使用者建立新團隊。 | | [在 Microsoft Teams 中指派角色和許可權](assign-roles-permissions.md) <br/><br/>[Microsoft 365 群組和 Microsoft Teams](office-365-groups.md) <br/><br/>[管理誰可以建立Microsoft 365 群組](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 設定全租使用者 Teams 設定 | 您可以在租使用者層級設定一些 Teams 設定。 啟用 Teams 的使用者會繼承租使用者設定中的這些設定：<ul><li>一般</li><li>電子郵件整合</li><li>應用程式</li><li>自訂雲端儲存空間</li><li>通話和會議</li><li>訊息傳送</li></ul>| | [管理組織的 Microsoft Teams 設定](enable-features-office-365.md) |
| 5  | 選用：設定來賓存取權 | 您可以使用 Teams 中的來賓存取權與組織外部人員共同作業，方法是授與他們團隊和頻道的存取權。 來賓存取是 Teams 中的租使用者層級設定。 預設為關閉。 <br/>如果您的組織打算使用該功能，請啟用來賓存取並設定整個租使用者的來賓設定。 | | [Microsoft Teams 中的來賓存取](guest-access.md) |
| 6  | 選用：設定 Teams 命名原則 | 當使用者建立或編輯團隊名稱時，Teams 會運用Microsoft 365 群組的命名原則。 <br/><br/>根據預設，當使用者建立團隊時，不會套用任何命名限制。 <br/><br/>如果您需要針對團隊名稱強制執行規則，請設定Microsoft 365 群組適用于貴組織的命名原則。 您可以設定強制首碼和尾碼，並指定封鎖的單字。 | | [在 Microsoft Teams 中建立團隊時規劃 Microsoft 365 群組](plan-office-365-groups.md) <br/><br/>[Microsoft 365 群組命名原則](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 設定 Teams SMTP 網域的 Exchange | Teams 會使用Exchange Online在新增或移除小組成員時，使用 SMTP 網域（email.teams.microsoft.com」傳送通知給小組成員。 <br/><br/>請務必將此 SMTP 網域新增至 Exchange 基礎結構中公認的網域清單。 | | [在 Exchange 中建立安全的寄件者清單](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | 設定及管理使用者對 Teams 的存取權 | 雖然我們強烈建議您為 Teams 啟用所有使用者，但您可以指派或移除 Teams 產品授權，以允許或不允許個別使用者存取 Teams。 | | [管理使用者對 Microsoft Teams 的存取權](user-access.md) |
| 9  | 指派授權給使用者 | 指派授權給您的使用者，以取得音訊會議、電話系統和通話方案等功能 | | [指派 Microsoft Teams 附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 選用：使用 PowerShell 管理 Teams | 您可以使用 PowerShell Cmdlet 而非Microsoft 365 系統管理中心來管理及管理 Teams 設定。 | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |