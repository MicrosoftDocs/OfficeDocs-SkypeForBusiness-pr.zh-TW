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
description: 未取得 Microsoft Teams 授權的 Microsoft 365 或 Office 365 使用者可以起始 Exploratory Teams 授權。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99017e63ae784c7c4271454829198c7c06ecfe8e
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868460"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>管理 Microsoft Teams Exploratory 授權
=======================================================

Microsoft Teams Exploratory 體驗可讓貴組織中擁有 Azure Active Directory (AAD) 和未取得 Teams 授權的使用者起始 Teams 探勘體驗。 系統管理員可以為其組織中的使用者開啟或關閉這項功能。 舊版 [Microsoft 商務雲端試用版](iw-trial-teams.md)現在已由 Teams Exploratory 體驗取代。

## <a name="whats-in-the-teams-exploratory-experience"></a>Microsoft Teams Exploratory 體驗有什麼內容？

系統管理員將在 Teams Exploratory 體驗中看到的服務方案如下：
 - Exchange Online (方案 1)
 - Microsoft 365 或 Office 365 的流程
 - MyAnalytics 的深入解析
 - Microsoft Forms (方案 E1)
 - Microsoft Planner
 - Microsoft 搜尋
 - Microsoft StaffHub
 - 適用於 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream
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


## <a name="whos-eligible"></a>符合使用資格的對象

只要使用者有受管理的 AAD 網域電子郵件地址，且目前還沒有受指派 Teams 授權，就符合這種使用體驗。 例如，如果使用者擁有 Microsoft 365 Apps 商務版 (其中不包含 Teams)，使用者就符合 Teams Exploratory 體驗使用資格。

必須啟用使用者才能註冊應用程式和試用版 (於 Microsoft 365 系統管理中心)。 如需詳細資訊，請參閱本文稍後的[管理 Teams Exploratory 體驗](#manage-the-teams-exploratory-experience)。 


## <a name="who-isnt-eligible"></a>不符合使用資格的對象

如果您是整合合作夥伴客戶，或是 GCC、GCC High、DoD 或 EDU 客戶，則貴組織不符合使用資格。


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>使用者註冊 Teams Exploratory 體驗的方式

合格的使用者可以透過登入 Teams ([teams.microsoft.com](https://teams.microsoft.com)) 來註冊取得 Teams Exploratory 體驗。 系統會自動指派此授權，且租用戶系統管理員在第一次貴組織中的人員啟動 Teams Exploratory 體驗時，將會收到電子郵件通知。

## <a name="manage-the-teams-exploratory-experience"></a>管理 Teams Exploratory 體驗

Teams Exploratory 體驗應由個別使用者起始，而您可能無法代表使用者員工起始此服務。

Teams Exploratory 體驗隨附 Exchange Online 授權，但在系統管理員指派之前，不會指派給使用者。 如果使用者沒有 Exchange 授權，且系統管理員尚未指派 Exchange Online 授權，則使用者將無法在 Teams 中排程會議，且可能會遺失其他 Teams 功能。

系統管理員可以使用**試用版應用程式和服務**切換功能來停用使用者在其組織內執行 Teams Exploratory 體驗。


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>防止使用者安裝試用版應用程式和服務

您可以關閉使用者安裝試用版應用程式和服務的功能，即可防止使用者執行 Teams Exploratory 體驗。 您必須具備系統管理員權限。 若要深入了解系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色來管理 Teams](teams-exploratory.md)

1. 從 [Microsoft 365 系統管理中心][](https://portal.office.com/adminportal/home)，移至 [設定]****  >  [設定]****、選取 [服務]****，然後選取 [使用者所擁有的應用程式與服務]****。

    ![系統管理中心的 [服務] 頁面的螢幕擷取畫面](media/iw-trial-services.png)

2. 取消選取 [讓使用者安裝試用版的應用程式與服務]**** 核取方塊。

    ![系統管理中心的 [使用者所擁有的應用程式與服務] 頁面的螢幕擷取畫面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 如果貴組織不符合 Teams Exploratory 使用資格，您將不會看到 [讓使用者安裝試用版的應用程式與服務]**** 選項。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>管理具有 Teams 授權的使用者可用性

已獲含 Teams 授權的使用者不符合 Teams Exploratory 體驗的使用資格。 開啟 Teams 服務方案後，使用者就可以登入並使用 Teams。 如果服務方案已停用，則使用者無法登入，也無法使用 Teams Exploratory 體驗。 您必須具備系統管理員權限。 

若要關閉對 Teams 的存取：

1. 在 [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home)中，選取 [使用者] **** >  [作用中的使用者]****。

2. 選取使用者名稱旁的方塊。

3. 在右側的 [產品授權]**** 列中，選擇 [編輯]****。

4. 在 [產品授權]**** 窗格中，將開關切換至 [關閉]****。

    ![系統管理中心的 [產品授權] 頁面的螢幕擷取畫面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>管理已在使用 Teams Exploratory 體驗之使用者的 Teams 可用性

如果使用者正在執行 Teams Exploratory 體驗，您可以移除授權或服務方案將它關閉。 您必須具備系統管理員權限。 

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

若要從 Teams Exploratory 授權升級使用者 (您必須擁有系統管理員權限)，請執行下列動作：

1. 購買包括 Teams 的訂閱。

2. 從使用者移除 Teams Exploratory 訂閱。

3. 指派新購買的授權。

如需詳細資訊，請參閱 [Microsoft Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

> [!NOTE]
> 如果 Teams Exploratory 授權結束，且使用者未立即升級為包含 Teams 的訂閱，並不會移除使用者資料。 使用者仍然存在於 Azure Active Directory 中，且 Teams 內的所有資料仍會保留。 一旦將新授權指派給使用者以再次啟用 Teams 功能，所有內容仍會存在。 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>舊版 Microsoft Teams 商業雲端試用版授權會發生什麼情況？

自 2020 年 2 月起，符合資格的使用者就可以開始使用最新的 Microsoft Teams Exploratory 體驗。 所有 Teams 商務雲端試用版授權將在試用到期之前，自動轉換為新服務。

當使用者第一次登入過期的 Teams Commercial Cloud 試用版時，系統會自動將 Teams Exploratory 體驗授權指派給該使用者。 使用者在登入之前不會進行轉換。

### <a name="remove-a-teams-exploratory-license"></a>移除 Teams Exploratory 授權

- 如果您想要透過 PowerShell 移除此授權，請參閱：[使用 Office 365 PowerShell 從使用者帳戶移除授權](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- 如果您想要透過系統管理入口網站移除此授權，請參閱：[刪除組織的使用者](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Teams Exploratory 體驗持續時間？

您在下一個**合約週年日**或 2021 年 1 月或之後**續約**之前，無需任何額外費用即可獲得 Microsoft Teams Exploratory 體驗。 屆時 Microsoft Exploratory 體驗授權的使用者將需要移至包括 Teams 的付費授權。 在該時間之後起始的任何 Microsoft Exploratory 體驗授權，在您的下一**週年日**或**續約**週期前都將維持免費提供。 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a>如果使用者在週年日或續約日到期前起始 Microsoft Teams Exploratory 體驗，會發生什麼情況？

在您的**合約週年日**或**續約**日 90 天內起始的 Microsoft Teams Exploratory 體驗授權，直到下一個週年日或續約週期為止前，都不需移到付費授權。 

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a>如果我的合約沒有周年紀念日或每年續約日期 (例如月對月合約)，該怎麼辦？

對於沒有周年紀念日或每年續約日期的合約，在第一位使用者啟用 Microsoft Teams Exploratory 體驗授權後的第二年將被視為周年紀念日或續約日期。 根據上述原則，必須在每年的該日期之前將擁有 Microsoft Teams Explorator 授權的使用者轉換為付費授權。

例如，如果第一位使用者在 2020 年 6 月 19 日啟用了 Microsoft Teams Exploratory，則他們和客戶租用戶中的所有其他合格使用者必須在 2021 年 6 月 19 日之前轉換為 Teams 的付費授權。 

