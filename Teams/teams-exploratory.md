---
title: 管理 Microsoft Teams Exploratory 體驗
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: 沒有 Microsoft Teams 授權的 Microsoft 365 或Office 365使用者可以起始探索 Teams 授權。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e5535be61aab03158aa11c68ebd3b753b3ca972
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851773"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>管理 Microsoft Teams Exploratory 授權

The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.

## <a name="whats-in-the-teams-exploratory-experience"></a>Microsoft Teams Exploratory 體驗有什麼內容

系統管理員將在 Teams Exploratory 體驗中看到的服務方案如下：

- Exchange Online (方案 1)
- Microsoft 365 或 Office 365 的流程
- MyAnalytics 的深入解析
- Microsoft Forms (方案 E1)
- Microsoft Planner
- Microsoft 搜尋
- Microsoft StaffHub
- 適用於 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream <sup>1</1>
- Microsoft Teams
- Microsoft 365 或 Office 365 的行動裝置管理
- 適用於 Office 365 的 Office 行動裝置應用程式
- Office Online
- 適用於 Microsoft 365 或 Office 365 的 PowerApps
- SharePoint Online (方案 1)
- Sway
- To-Do (方案 1)
- Whiteboard (方案 1)
- Yammer Enterprise

  <sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch, you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.

## <a name="whos-eligible"></a>符合使用資格的對象

用戶符合 Teams Exploratory 體驗的標準，如果他們滿足以下條件：

- 有受管理的 Azure AD 網域電子郵件地址。
- 屬於具有付費訂閱的租用戶。
- 沒有有效的 Teams 授權。
- 不在已建立授權指派原則的租使用者中。

Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.

## <a name="who-isnt-eligible"></a>不符合使用資格的對象

使用者在以下情況不符合條件：

- 目前有來自付費授權或試用版授權或先前具有試用版授權
- 位於至少使用過/收到過一個特殊 COVID 特殊優惠的租使用者中。

如果您是整合合作夥伴客戶，或是 GCC、GCC High、DoD 或 EDU 客戶，則貴組織不符合使用資格。

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>使用者註冊 Teams Exploratory 體驗的方式

合格的使用者可以透過登入 Teams 電腦版或網頁版 ([teams.microsoft.com](https://teams.microsoft.com)) 來註冊取得 Teams Exploratory 體驗。 目前不支援透過行動裝置啟用 Exploratory。 當他們註冊時，系統會自動指派此授權給他們，而租使用者系統管理員會在第一次您的組織中有人啟動 Teams Exploratory 體驗時收到電子郵件通知。

## <a name="manage-the-teams-exploratory-experience"></a>管理 Teams Exploratory 體驗

Teams Exploratory 體驗應由個別使用者起始，而您可能無法代表使用者員工起始此服務。

The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.

系統管理員可以使用 **試用版應用程式和服務** 切換功能來停用使用者在其組織內執行 Teams Exploratory 體驗。

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>防止使用者安裝試用版應用程式和服務

您可以關閉使用者安裝試用版應用程式和服務的功能，即可防止使用者執行 Teams Exploratory 體驗。

1. 從 [Microsoft 365 系統管理中心]，移至 **[設定]** > **[組織設定]**、選取 **[服務]**，然後選取 **[使用者所擁有的應用程式與服務]**。

    ![系統管理中心的 [服務] 頁面。](media/iw-trial-services.png)

2. 取消選取 **[讓使用者安裝試用版的應用程式與服務]** 核取方塊。

    ![系統管理中心的 [使用者所擁有的應用程式與服務] 頁面。](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 如果貴組織不符合 Teams Exploratory 使用資格，您將不會看到 **[讓使用者安裝試用版的應用程式與服務]** 選項。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>管理具有包含 Teams 授權使用者的可用性

已獲含 Teams 授權的使用者不符合 Teams Exploratory 體驗的使用資格。 開啟 Teams 服務方案後，使用者就可以登入並使用 Teams。 如果服務方案已停用，使用者就無法登入，而且無法使用 Teams Exploratory 體驗。 您必須具備系統管理員權限。

若要關閉對 Teams 的存取：

1. 在 Microsoft 365 系統管理中心，選取 **[使用者]**  >  **[作用中的使用者]**。

2. 選取使用者名稱旁的方塊。

3. 在 **[產品授權]** 列中，選擇 **[編輯]**。

4. 在 **[產品授權]** 窗格中，將開關切換至 **[關閉]**。

    ![系統管理中心的 [產品授權] 頁面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>管理已在使用 Teams Exploratory 體驗之使用者的 Teams 可用性

If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.

若要關閉 Teams Exploratory 體驗授權：

1. 在 Microsoft 365 系統管理中心，選取 **[使用者]**  >  **[作用中的使用者]**。

2. 選取使用者名稱旁的方塊。

3. 在 **[產品授權]** 列中，選擇 **[編輯]**。

4. 在 **[產品授權]** 窗格中，將此探勘授權的開關切換至 **[關閉]**。

    > [!NOTE]
    > 組織中的第一個使用者啟動 Teams Exploratory 體驗之後，將會出現 [Teams Exploratory] 切換開關。

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>管理適用於擁有 Teams Exploratory 授權之使用者的 Teams

You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).

### <a name="upgrade-users-from-teams-exploratory"></a>從 Teams Exploratory 升級使用者

您必須擁有系統管理員權限以從 Teams Exploratory 升級使用者。 如需詳細資訊，請參閱 [從 Teams Exploratory 試用版升級使用者](upgrade-from-teams-exploratory.md)。

> [!NOTE]
> 如果 Teams Exploratory 授權終止，且使用者未立即升級至包含 Teams 的訂閱，他們在 30 天寬限期後便無法存取 Teams、OneDrive 和 Sharepoint。 30 天后，關聯的 Teams、OneDrive 和 SharePoint 資料就會刪除。 使用者仍然存在於 Azure Active Directory 中。
> 
> 一旦將新授權指派給使用者以再次啟用 Teams 功能，則如果在寬限期時間範圍內新增使用者，則所有內容仍將存在。

### <a name="remove-a-teams-exploratory-license"></a>移除 Teams Exploratory 授權

- 如果您想要透過 PowerShell 移除此授權，請參閱：[使用 Office 365 PowerShell 從使用者帳戶移除授權](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- 如果您想要透過系統管理入口網站移除此授權，請參閱：[從貴組織刪除使用者](/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>什麼是資料保留原則

請參閲 [Microsoft 365 訂閱資訊](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires)。

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Teams Exploratory 體驗持續時間

Teams Exploratory 將以 12 個月訂閱形式 (從使用者初始註冊起) 提供所有新客戶使用。 新的 Teams Exploratory 訂閱會在組織中的第一個使用者註冊 Teams Exploratory 時開始，並且會在 12 個月之後到期。 由於 12 個月是從第一位使用者註冊日期開始，到期日將對相同租用戶中的所有使用者套用。

> [!NOTE]
> 體驗的結束日期在組織層級設定，表示它會套用至相同組織中的所有使用者。 例如，使用者 1 在 2021 年 1 月 1 日註冊取得訂閱。 這會起始 2021 年 12 月 31 日的訂閱結束日期。 另一位使用者，使用者 2 在 2021 年 10 月 1 日註冊取得訂閱。 使用者 2 可以使用 Teams Exploratory 兩個月，因為其結束日期將為 2021 年 12 月 31 日，因為他們與使用者 1 屬於相同組織的訂閱。

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>在 12 個月的 Teams Exploratory 體驗結束時，系統管理員應該執行什麼動作

在 12 個月訂閱結束時，系統管理員應將所有 Teams Exploratory 使用者轉換成包括 Teams 在內的付費授權。 確保在 Teams Exploratory 訂閱到期之前完成此動作至關重要，以避免任何干擾使用者的體驗。


> [!NOTE]
> 在前一個 Exploratory 體驗授權到期後的 3 個月內客戶將被停用並封鎖開始新 Explaratory 授權。

如需詳細資訊，請參閱本文上方的 [從 Teams Exploratory 升級使用者](#upgrade-users-from-teams-exploratory)。
