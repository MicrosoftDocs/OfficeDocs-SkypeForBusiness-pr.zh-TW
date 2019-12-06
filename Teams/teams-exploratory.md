---
title: 管理 Microsoft Teams Exploratory 體驗
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 未取得 Microsoft Teams 授權的 Office 365 使用者可以起始 Exploratory Teams 授權。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6777dfbafac89c798955245b93f1e4537093b0cf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871781"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>管理 Microsoft Teams Exploratory 授權
=======================================================

Microsoft Teams Exploratory 體驗可讓貴組織中擁有 Azure Active Directory (AAD) 和未取得 Teams 授權的使用者起始 Teams 探勘體驗。 系統管理員可以為其組織中的使用者開啟或關閉這項功能。 舊版 [Microsoft 商務雲端試用版](iw-trial-teams.md)現在稱為 Teams Exploratory 體驗。

[!INCLUDE [preview-feature](includes/preview-feature.md)]此體驗將於 2020 年 1 月中推出。

## <a name="whats-in-the-teams-exploratory-experience"></a>Microsoft Teams Exploratory 體驗有什麼內容？

Teams Exploratory 體驗中的服務方案包含：
 - Exchange Online (方案 1)
 - 適用於 Office 365 的 Flow
 - MyAnalytics 的深入解析
 - Microsoft Forms (方案 E1)
 - Microsoft Planner
 - Microsoft 搜尋
 - Microsoft StaffHub
 - 適用於 O365 E1 SKU 的 Microsoft Stream
 - Microsoft Teams
 - 適用於 Office 365 的行動裝置管理
 - 適用於 Office 365 的 Office 行動裝置應用程式 
 - Office Online
 - 適用於 Office 365 的 PowerApps
 - SharePoint Online (方案 1)
 - Sway
 - To-Do (方案 1)
 - Whiteboard (方案 1)
 - Yammer Enterprise


## <a name="whos-eligible"></a>符合使用資格的對象

必須啟用使用者才能註冊應用程式和試用版 (於 Microsoft 365 系統管理中心)。 如需詳細資訊，請參閱本文稍後的[管理 Teams Exploratory 體驗](#manage-the-teams-exploratory-experience)。 

沒有包含 Teams 的 Office 365 授權之使用者可以起始 Teams Exploratory 體驗。 例如，如果使用者擁有 Office 365 商務版 (其中不包含 Teams)，使用者就符合 Teams Exploratory 體驗使用資格。

## <a name="who-isnt-eligible"></a>不符合使用資格的對象

如果您是整合合作夥伴客戶，或是 GCC、GCC High、DoD 或 EDU 客戶，則貴組織不符合使用資格。


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>使用者註冊 Teams Exploratory 體驗的方式

合格的使用者可以透過登入 Teams ([teams.microsoft.com](https://teams.microsoft.com)) 來註冊取得 Teams Exploratory 體驗。 系統會自動指派此授權，且租用戶系統管理員在第一次貴組織中的人員啟動 Teams Exploratory 體驗時，將會收到電子郵件通知。

## <a name="manage-the-teams-exploratory-experience"></a>管理 Teams Exploratory 體驗

Teams Exploratory 體驗應由個別使用者起始，而您可能無法代表使用者員工起始此服務。

Teams Exploratory 體驗隨附 Exchange Online 授權，但在系統管理員指派之前，不會指派給使用者。 如果使用者沒有 Exchange 授權，且系統管理員尚未指派 Exchange Online 授權，則使用者將無法在 Teams 中排程會議，且可能會遺失其他 Teams 功能。

系統管理員可以使用**試用版應用程式和服務**切換功能來停用使用者在其組織內執行 Teams Exploratory 體驗。


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>防止使用者安裝試用版應用程式和服務

您可以關閉使用者安裝試用版應用程式和服務的功能，即可防止使用者執行 Teams Exploratory 體驗。

1. 從 [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home)，移至 [設定]****  >  [服務與增益集]****  >  [使用者所擁有的應用程式與服務]****。

    ![系統管理中心的 [服務與增益集] 頁面的螢幕擷取畫面](media/iw-trial-enable-1.png)

2. 關閉 [讓使用者安裝試用版的應用程式與服務]****。

    ![系統管理中心的 [使用者所擁有的應用程式與服務] 頁面的螢幕擷取畫面](media/iw-trial-enable-2.png)
> [!NOTE]
> 如果貴組織不符合 Teams Exploratory 使用資格，您將不會看到 [讓使用者安裝試用版應用程式與服務]**** 切換功能。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>管理具有 Teams 授權的使用者可用性

已獲含 Teams 授權的使用者不符合 Teams Exploratory 體驗的使用資格。 開啟 Teams 服務方案後，使用者就可以登入並使用 Teams。 如果服務方案已停用，則使用者無法登入，也無法使用 Teams Exploratory 體驗。

若要關閉對 Teams 的存取：

1. 在 Microsoft 365 系統管理中心，選取 [使用者]****  >  [作用中的使用者]****。

2. 選取使用者名稱旁的方塊。

3. 在右側的 [產品授權]**** 列中，選擇 [編輯]****。

4. 在 [產品授權]**** 窗格中，將開關切換至 [關閉]****。

    ![系統管理中心的 [產品授權] 頁面的螢幕擷取畫面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>管理已在使用 Teams Exploratory 體驗之使用者的 Teams 可用性

如果使用者正在執行 Teams Exploratory 體驗，您可以移除授權或服務方案將它關閉。

若要關閉 Teams Exploratory 體驗授權：

1. 在 Microsoft 365 系統管理中心，選取 [使用者]****  >  [作用中的使用者]****。

2. 選取使用者名稱旁的方塊。

3. 在右側的 [產品授權]**** 列中，選擇 [編輯]****。

4. 在 [產品授權]**** 窗格中，將此探勘授權的開關切換至 [關閉]****。

    
>[!Note]
>組織中的第一個使用者啟動 Teams Exploratory 體驗之後，將會出現 [Teams Exploratory] 切換開關。

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>管理適用於擁有 Teams Exploratory 授權之使用者的 Teams

您可以管理擁有 Teams Exploratory 授權的使用者，就像您管理擁有一般付費授權的使用者一般。 如需詳細資訊，請參閱[管理貴組織的 Teams 設定](enable-features-office-365.md)。

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>從 Teams Exploratory 授權升級使用者

若要從 Teams Exploratory 授權升級使用者，請執行下列動作：

1. 購買包括 Teams 的訂閱。

2. 從使用者移除 Teams Exploratory 訂閱。

3. 指派新購買的授權。

如需詳細資訊，請參閱 [Microsoft Teams 的 Office 365 授權](Office-365-licensing.md)。

> [!NOTE]
> 如果 Teams Exploratory 授權結束，且使用者未立即升級為包含 Teams 的訂閱，則不會移除使用者資料。 使用者仍然存在於 Azure Active Directory 中，且 Teams 內的所有資料仍會保留。 一旦將新授權指派給使用者以再次啟用 Teams 功能，所有內容仍會存在。 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>舊版 Microsoft Teams 商業雲端試用版授權會發生什麼情況？

自 2020 年 1 月中起，符合資格的使用者就可以開始使用最新的 Microsoft Teams Exploratory 體驗。 所有 Teams 商務雲端試用版授權將在試用到期之前，自動轉換為新服務。

### <a name="remove-a-teams-exploratory-license"></a>移除 Teams Exploratory 授權

- 如果您想要透過 PowerShell 移除此授權，請參閱：[使用 Office 365 PowerShell 從使用者帳戶移除授權](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- 如果您想要透過系統管理入口網站移除此授權，請參閱：[在商務用 Office 365 中移除使用者的授權](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)
