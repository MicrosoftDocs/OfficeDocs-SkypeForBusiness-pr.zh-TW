---
title: 規劃將您的 StaffHub 團隊移至 Microsoft 團隊中的倒班
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 取得如何規劃以將您的 StaffHub 小組移至 Microsoft 團隊中的指導方針。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5a6079924803f7dbdde0c49bb5bd5d1f1aa2c4b
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825701"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>規劃將您的 StaffHub 團隊移至 Microsoft 團隊中的倒班

> [!IMPORTANT]
> 2019年12月31日生效，Microsoft StaffHub 將停用。 我們正在將 StaffHub 功能組建至 Microsoft 團隊。 今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。 StaffHub 將會停止針對2019年12月31日的所有使用者使用。 任何試圖開啟 StaffHub 的人，都會顯示一則訊息，讓他們下載小組。 若要深入瞭解，請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。 

當您開始規劃變更時，就會開始從 StaffHub 轉至團隊。 為了確保您移至團隊的成功，我們已建立範例時程表來示範典型的轉場方案。 [範例] 時程表簡要說明準備進行移動的規劃活動，並引導您逐步將貴組織的 StaffHub 小組移至團隊。

使用時間表做為指示從 StaffHub 移至團隊，並根據貴組織的需求加以自訂的指導方針。 請務必查看連結至時程表中步驟的資源。

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>準備將您的 StaffHub 團隊移至團隊

|循序漸進 |指導方針  |資源 |
|---------|---------|---------|
|1    |準備及識別干係人         |         |
|2     |查看從 StaffHub 轉至團隊和團隊加入的檔         |[StaffHub 停用](microsoft-staffhub-to-be-retired.md)<br><br>[將您的 StaffHub 團隊移至團隊中的倒班](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[開始使用 Teams](../../get-started-with-teams-quick-start.md)         |
|3    |為您的組織啟用 Office 365 群組        |[Office 365 群組與團隊](../../Office-365-groups.md)      |
|4    |確認已滿足先決條件         |[檢查是否符合先決條件](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|500   |指派團隊授權給貴組織中的 StaffHub 使用者|[指派 Teams 授權](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[管理 Teams 的使用者存取](../../user-access.md)      |
|6    |安裝 StaffHub PowerShell 模組        |[安裝 StaffHub PowerShell 模組](install-the-staffhub-powershell-module.md)        |
|utf-7     |判斷時程表並找出移至團隊的 StaffHub 使用者       |[執行報告以顯示作用中 StaffHub 的使用情況](run-report-to-show-staffhub-usage.md) |
|型     |找出沒有 Azure AD 帳戶的 StaffHub 使用者（在 StaffHub 中顯示為「非使用中」），並連結帳戶給他們     |[連結 Azure AD 帳戶給沒有 StaffHub 小組成員的人員](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|9    |為您的組織量身定制的使用者建立訓練內容         |[為小組準備使用者準備方案](../../upgrade-user-readiness.md)     |
|第    |與 StaffHub 使用者進行溝通，以在小組中轉移轉變         |[StaffHub 至團隊向使用者進行電子郵件通訊的範例](staffhub-to-teams-email-template.md)         |
|11     |安裝團隊用戶端         |[取得 Teams 用戶端](../../get-clients.md) |
|之間    |將 FirstLineWorker 應用程式設定原則指派給使用者（或建立並指派自訂應用程式設定原則），以將倒班 app 釘選到團隊用戶端  |[將 FirstlineWorker 應用程式設定原則指派給使用者](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|合     |訓練使用者如何使用倒班與團隊         |[在團隊中的使用者](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[班次協助檔](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Teams 說明文件](https://support.office.com/teams)<br><br>[Teams 訓練影片](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|4     |複習您的 StaffHub 小組清單，以確保那些小組中的所有使用者都應該移至團隊。 移除不應在排程上的使用者。 |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>將貴組織的 StaffHub 團隊移至團隊

|循序漸進 |指導方針 |資源  |
|---------|---------|---------|
|1  |找出試驗小組並移動一個團隊          |[移動 StaffHub 小組](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|2    |驗證試驗小組並找出任何搬遷問題。 視需要更新訓練檔。         |         |
|3     |找出其他試驗小組，並將五個小組移至十個團隊         |[移動您的 StaffHub 團隊](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |找出剩餘的 StaffHub 團隊，並以分段的方式進行移動         |[移動您的 StaffHub 團隊](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|500     |繼續提供對倒班與團隊的支援         |         |
|6     |如果已啟用自助密碼重設，請在團隊中執行支援登入問題報告       |[針對自助密碼重設設定執行報告](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
