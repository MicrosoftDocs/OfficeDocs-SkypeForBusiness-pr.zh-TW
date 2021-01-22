---
title: '安裝、管理及指派 Teams 學習應用程式的許可權， (預覽) '
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: 使用 Microsoft Teams Learning 應用程式建立中央中心，讓員工可以在這裡共用、指派，以及從整個組織的內容庫學習。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6d4cb45334edb9307663eb1ffcab5e7c1085b149
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923835"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>安裝、管理及指派 Teams 學習應用程式的許可權， (預覽) 

*本文包含 Teams Learning 應用程式的初步內容，此為私人預覽。*

Microsoft Teams Learning 應用程式 (預覽) 讓貴組織的團隊和個人能夠自然地學習一天中的內容。 應用程式在 Teams 中建立一個中央中樞，讓員工可以共用、指派及學習整個組織的內容庫。 系統管理員設定許可權並允許應用程式的學習內容來源。 學習內容可能包括 LinkedIn學習、Microsoft Learn、Microsoft 365 訓練、您組織儲存在 SharePoint Online 中的內容，以及應用程式支援的協力廠商提供者。

若要將 Teams Learning 應用程式設定 (預覽) ，您需要包含：

-   Teams 系統管理中心系統管理員
-   Microsoft 365 系統管理中心系統管理員 (，即全域系統管理員) 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>在 Teams 系統管理中心 (Teams) Teams 學習應用程式的私人預覽頁面

Teams 系統管理員會從 App store 安裝 Teams Learning (私人預覽) ，並透過 Teams 系統管理中心來申請應用程式設定、管理及許可權原則。

### <a name="manage-the-teams-learning-app-private-preview"></a>管理 Teams Learning 應用程式 (的私人預覽) 

若要管理應用程式的設定，請遵循下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側流覽區中，前往 **Teams 應用程式**  >  **管理應用程式**。

   ![Teams 系統管理中心的左側流覽，顯示 Teams 應用程式與管理應用程式區段](media/learning-app-teams-manage-apps-nav.png)

2. 在管理應用程式頁面的搜尋方塊中，輸入如何搜尋 Teams Learning 應用程式， (預覽) 。 

   ![Teams 系統管理中心的管理應用程式頁面，顯示搜尋方塊](media/learning-app-teams-manage-apps-page.png)

3. 在學習 **頁面上** ：
   1. 在 **狀態****下，選取** 允許開啟應用程式。
   2. 在應用程式設定的設定設定。

   ![Teams 系統管理中心的學習頁面，顯示狀態與應用程式設定區段](media/learning-app-teams-learning-page.png)

4. 在 **管理應用程式** 設定之後，請前往許可權和設定政策，將許可權授予應擁有應用程式存取權的員工，做為貴組織參與私人預覽的一部分。

> [!NOTE]
>  如果貴組織在 Ring 4.0 中屬於 Teams TAP100 計畫的一部分，您可能需要執行下列操作，才能讓在 Ring 3.0 中核准的使用者存取 Teams Learning 應用程式 (私人預覽) 。

做為私人預覽的一部分，Teams 學習應用程式 (私人預覽) 在 Ring 3.0 中發行。 如果貴組織是在 Ring 4.0，您就不會在 App Store 看到該應用程式。 若要測試應用程式，您需要建立自訂應用程式權限原則，將其設定為允許所有應用程式，並將它指派給 Ring 3.0 核准的使用者。

   ![TAP-AppsPermission-Plcy 頁面顯示已選取的允許所有應用程式](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心設定學習內容來源

Microsoft 365 系統管理中心的系統管理員可以管理 Teams 學習應用程式的相關設定 (私人預覽) 並設定學習內容來源。

系統管理員選取哪些學習內容來源 (App 中LinkedIn學習) SharePoint 頁面。 系統管理員接著會設定這些來源，以確保內容可供搜尋和探索使用，且使用 App 的員工可以流覽。

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>設定應用程式學習內容來源的設定

這些步驟是由 Microsoft 365 系統管理員執行。

1.  在 Microsoft 365 系統管理中心的左側流覽區中，**前往設定**  >  **組織設定**。

2.  在設定頁面上，&載入程式按鈕上的學習 **應用程式。**

   ![Microsoft 365 系統管理中心的設定頁面，顯示列出的學習應用程式](media/learning-app-365-settings-page.png)

3.  在學習 **應用程式面板** 上，選取您想要為組織設定的學習內容來源， **然後選取儲存**。

   ![Microsoft 365 系統管理中心中的學習應用程式面板，其中顯示內容來源選項](media/learning-app-365-settings-learning-app-panel.png)

在所有的學習來源中，有些預設會啟用。 包括：

- LinkedIn學習 (免費內容) 
- Microsoft Learn
- Microsoft 365 訓練

> [!NOTE]
> 如果貴組織有LinkedIn標準版或專業版訂閱，貴組織的員工就會解除鎖定內容存放庫。 只有擁有許可權的員工才能使用整個內容存放庫。

其他來源可能需要啟用或手動進行安裝。 非 Microsoft 的學習來源會由您的組織和協力廠商個別授權。 您必須確認自己已經註冊，為學生和使用者學習。

若要啟用或停用學習內容來源，請選取來源旁的核取方塊。 如果啟用來源，將會顯示勾選記號。

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a>將 SharePoint 設定為學習內容來源 (即將推出) 

您可以在 Microsoft 365 系統管理中心將 SharePoint 設定為 Teams 學習 (的私人) 內容來源。

### <a name="overview"></a>概觀

系統管理員提供網站 URL，讓學習服務可以在其中以結構化 SharePoint 清單的形式，建立空白的集中式學習內容存放庫。 組織可以使用此清單來建立包含學習內容的跨公司 SharePoint 資料夾連結。 系統管理員負責收集和策展資料夾的 URL 清單。 這些資料夾應只包含可在 Teams Learning 應用程式中取得的內容， (預覽) 。

### <a name="permissions"></a>權限

資料夾 URL 可以從組織的任何 SharePoint 網站收集。 這些資料夾中的任何內容都可以搜尋，但只能使用個別員工擁有許可權的內容。
 
### <a name="learning-service"></a>學習服務

學習服務會使用提供的資料夾 URL，取得儲存在這些資料夾中之所有內容的中繼資料。 在提供集中式存放庫中資料夾 URL 的 24 小時內，員工可以在 App 中搜尋及使用公司的內容。 此時不支援從存放庫刪除內容。 只有在 Microsoft 365 系統管理中心提供新的 SharePoint 網站 URL，才能移除不小心顯示的內容。

### <a name="configure-sharepoint-as-a-source"></a>將 SharePoint 設定為來源

這些步驟是由 Microsoft 365 系統管理員執行。

1.  在 Microsoft 365 系統管理中心的左側流覽區中，前往設定 **。**
 
2.  在設定頁面上，&載入程式按鈕上的學習 **應用程式。**

   ![Microsoft 365 系統管理中心的設定頁面，顯示列出的學習應用程式](media/learning-app-365-settings-page.png)

3.  在學習 **應用程式面板** 上，提供您想要應用程式建立集中式存放庫之 SharePoint 網站的網站 URL。

   ![Microsoft 365 系統管理中心中的學習應用程式面板，其中顯示已選取的 SharePoint](media/learning-app-365-panel-sharepoint-selected.png)

4.  SharePoint 清單會在提供的組織的 SharePoint 網站中自動建立。 在 SharePoint 網站的左側流覽中，選取學習 **應用程式內容存放庫**。 

   ![SharePoint 中的左側流覽顯示學習應用程式內容存放庫區段](media/learning-app-content-repository-nav.png)

 
5. 在學習 **應用程式內容存放庫** 頁面上，將 URL 填入 SharePoint 清單至學習內容資料夾。

   1.   選取 **新增** 以查看 **新增專案** 面板。 

   ![SharePoint 中顯示新選項的學習 App 內容存放庫頁面](media/learning-app-content-repository-new.png)
 
   2.   在新增 **專案面板** 的標題欄位中，新增您所選擇的目錄名稱。 在資料夾 **URL 欄位中** ，將 URL 新增到學習內容資料夾。 選取 **儲存**。

   ![SharePoint 中的新增專案面板，其中顯示標題和資料夾 URL 欄位](media/learning-app-new-item-panel.png)

   3. 學習應用程式內容存放庫頁面會以新的學習內容更新。

   ![SharePoint 中的學習應用程式內容存放庫頁面，顯示更新的資訊](media/learning-app-content-repository-populated.png)


 


