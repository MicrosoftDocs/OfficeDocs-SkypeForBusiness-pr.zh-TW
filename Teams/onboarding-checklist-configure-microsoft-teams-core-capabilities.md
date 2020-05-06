---
title: '[加入檢查清單]-設定核心功能-Microsoft 團隊'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您為組織設定小組時，請遵循此檢查清單中的核心、執行任務和活動。
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7d167b8e1e868f550067b08f2f7dbfb22cb0a41
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042100"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>設定 Microsoft 團隊核心功能

| 否 | 活動或任務 | 說明 | 完畢? | 其他資訊 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 確認您的環境包含所有團隊先決條件 | 團隊依賴其他平臺來建立端對端的共同作業方案。 與您的 IT 團隊共同作業，以確保您已部署並正確設定 Exchange、SharePoint Online 和商務用 OneDrive。 | | [SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md) <br/><br/>[Exchange 與 Microsoft 團隊如何互動](exchange-teams-interact.md) |
| 2  | 驗證已針對租使用者啟用團隊 | 預設會為所有組織開啟團隊。 檢查 Microsoft 365 系統管理中心的 [**服務] & [增益集**] 頁面，確認已為您的租使用者啟用小組，並視需要啟用團隊。 | | [在 Microsoft 365 或 Office 365 中設定 Microsoft 團隊](office-365-set-up.md) |
| 3  | 設定角色和許可權 | 團隊支援兩種類型的角色：成員和擁有者。 <br/><br/>將成員新增至團隊之後，擁有者也可以將成員升級為擁有者角色。 最佳做法，我們建議您至少有指派給每個小組的兩個擁有者。 <br/><br/>根據預設，組織中擁有 Exchange Online 之信箱的每個人都可以建立小組。 建立新團隊的使用者會自動獲得該小組的擁有者角色。 <br/><br/>如有需要，您可以設定 Office 365 群組設定，只讓特定使用者建立新的團隊。 | | [在 Microsoft 團隊中指派角色和許可權](assign-roles-permissions.md) <br/><br/>[Microsoft 365 群組和 Microsoft 團隊](office-365-groups.md) <br/><br/>[管理哪些人可以建立 Microsoft 365 群組](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 設定租使用者範圍的團隊設定 | 您可以在租使用者層級設定一些團隊設定。 針對團隊啟用的使用者會從租使用者設定繼承這些設定：<ul><li>一般</li><li>電子郵件整合</li><li>應用程式</li><li>自訂雲端儲存空間</li><li>通話與會議</li><li>訊息傳送</li></ul>| | [管理組織的 Microsoft Teams 設定](enable-features-office-365.md) |
| 500  | 選用：設定來賓存取權 | 您可以在小組中使用來賓存取權，透過授與組織外部人員的許可權來共同作業，讓他們能夠存取團隊和頻道。 來賓存取是團隊中的租使用者層級設定。 預設為關閉。 <br/>如果您的組織打算使用該功能，請啟用來賓存取及設定全租使用者來賓設定。 | | [Microsoft Teams 中的來賓存取](guest-access.md) |
| 6  | 選用：設定團隊命名原則 | 當使用者建立或編輯小組名稱時，小組會利用 Microsoft 365 群組的命名原則。 <br/><br/>根據預設，當使用者建立小組時，不會套用任何命名限制。 <br/><br/>如果您需要強制執行團隊名稱規則，請設定適用于您組織的 Microsoft 365 群組命名原則。 您可以設定強制的首碼和尾碼，並指定封鎖的字。 | | [在 Microsoft 團隊中建立小組時規劃 Microsoft 365 群組](plan-office-365-groups.md) <br/><br/>[Microsoft 365 群組命名原則](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| utf-7  | 針對團隊 SMTP 網域設定 Exchange | 小組使用 Exchange Online，透過 SMTP 網域（email.teams.microsoft.com）傳送通知給小組成員，然後在新增或移除通知。 <br/><br/>請務必將此 SMTP 網域新增至 Exchange 基礎結構中的 [接受的網域] 清單。 | | [在 Exchange Online 中將 Microsoft 團隊 SMTP 網域新增為已接受的網域](smtp-accepted-domain.md) |
| 型  | 設定及管理使用者對團隊的存取權 | 雖然我們強烈建議您為團隊啟用所有使用者，但是您可以指派或移除團隊產品授權，以允許或禁止針對每位使用者存取團隊。 | | [管理使用者對 Microsoft 團隊的存取權](user-access.md) |
| 9  | 指派授權給使用者 | 指派授權給使用者，以取得音訊會議、電話系統和通話方案等功能 | | [指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 第 | [選用]：使用 PowerShell 管理團隊 | 您可以使用 PowerShell Cmdlet （而不是 Microsoft 365 系統管理中心）來管理和管理團隊設定。 | | [Microsoft 團隊 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
