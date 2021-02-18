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
description: 使用 Microsoft Teams Learning 應用程式建立中央中樞，讓員工可以共用、指派及學習整個組織的內容庫。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6dd82c786c30fb4f2ac2ae70f2df6810cfe5d6ad
ms.sourcegitcommit: 75d710e3858f79ef601cd92e435a4a29dae0aba0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50285617"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>安裝、管理及指派 Teams 學習應用程式的許可權， (預覽) 

*本文包含 Teams Learning 應用程式的初步內容，此為私人預覽版。*

Microsoft Teams Learning 應用程式 (預覽) 讓貴組織的團隊和個人能夠自然地學習。 應用程式在 Teams 中建立一個中央中樞，讓員工可以共用、指派及學習整個組織的內容庫。 系統管理員設定許可權，並允許應用程式的學習內容來源。 學習內容可以包含 LinkedIn學習、Microsoft Learn、Microsoft 365 訓練、貴組織儲存在 SharePoint Online 中的內容，以及應用程式支援的協力廠商提供者。

若要將 Teams 學習應用程式設定 (預覽) ，您必須參與：

-   Teams 系統管理中心系統管理員
-   Microsoft 365 系統管理中心系統管理員 (，即全域系統管理員) 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>在 Teams 系統管理 (管理) Teams 學習應用程式

Teams 系統管理員會從 App store (私人預覽) Teams 學習應用程式，並透過 Teams 系統管理中心來申請應用程式設定、管理和許可權原則。

### <a name="manage-the-teams-learning-app-private-preview"></a>管理 Teams 學習應用程式 (預覽) 

若要管理應用程式的設定，請遵循下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **Teams 應用程式**  >  **管理應用程式**。

   ![Teams 系統管理中心的左側流覽顯示 Teams 應用程式與管理應用程式區段](media/learning-app-teams-manage-apps-nav.png)

2. 在管理 **應用程式頁面** 的搜尋方塊中，輸入學習以搜尋 Teams Learning 應用程式， (預覽) 。

   ![Teams 系統管理中心的管理應用程式頁面，顯示搜尋方塊](media/learning-app-teams-manage-apps-page.png)

3. 在學習 **頁面上** ：
   1. 在 **狀態****下，選取** 允許開啟應用程式。
   2. 在設定 **Tab** 的 **App** 設定區段，前往 Microsoft 365 系統管理中心以設定學習內容來源。

   ![Teams 系統管理中心的學習頁面，顯示狀態與應用程式設定區段](media/learning-app-teams-learning-page.png)

4. 管理 **應用程式設定** 之後，請前往許可權和設定政策，將許可權授予應有權存取應用程式的員工，做為貴組織參與私人預覽的一部分。

> [!NOTE]
>  如果貴組織是 Teams TAP100 計畫的一部分，而貴組織在 Ring 4.0 中，您可能需要執行下列操作，才能在 Ring 3.0 中啟用核准的使用者，才能存取 Teams Learning 應用程式 (私人預覽版) 。

在私人預覽中，Teams 學習應用程式 (3.0) 發行。 如果貴組織使用鈴聲 4.0，您就不會在 App Store 看到該應用程式。 若要測試應用程式，您需要建立自訂應用程式權限原則，將其設定為允許 **所有應用程式**，並將它指派給已核准響鈴 3.0 的使用者。

   ![TAP-AppsPermission-Plcy 頁面，顯示已選取允許所有應用程式](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心設定學習內容來源

Microsoft 365 系統管理中心的系統管理員可以管理 Teams 學習應用程式的相關設定 (私人預覽) 並設定學習內容來源。

系統管理員可以選取哪些額外的學習內容來源 (例如 SharePoint 或支援的協力廠商內容提供者來源) 應用程式的使用者可以使用。 系統管理員接著會設定這些來源，以確保內容可供搜尋和探索，且可供使用 App 的員工流覽。

> [!NOTE]
>  使用者以瀏覽器或內嵌檢視器LinkedIn非 Microsoft 和學習專業版學習。 此已配置的學習受貴組織和協力廠商之間的個別授權、隱私權和服務條款所限制，而非學習 (預覽版) 條款。 在學習版預覽 (中選取) ，請確認貴組織與使用者之間已簽訂合約。

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>設定應用程式學習內容來源的設定

這些步驟是由 Microsoft 365 系統管理員執行。

1.  在 Microsoft 365 系統管理中心的左側流覽中，前往 **設定**  >  **組織設定**。

2.  在設定 **頁面上** 的 & **載入載入&，** 選取學習 **應用程式**。

   ![Microsoft 365 系統管理中心的設定頁面，其中列出學習應用程式](media/learning-app-365-settings-page.png)

3.  在學習 **應用程式面板** 上，選取您想要為組織設定的學習內容來源， **然後選取儲存**。

   ![Microsoft 365 系統管理中心的學習應用程式面板，其中顯示內容來源選項](media/learning-app-365-settings-learning-app-panel.png)

在存在的所有學習來源中，有些預設會啟用。 包括：

- LinkedIn學習 (免費內容) 
- Microsoft Learn
- Microsoft 365 訓練

> [!NOTE]
> 如果貴組織有 LinkedIn學習標準版或專業版訂閱，則貴組織員工的內容存放庫會解除鎖定。 只有擁有許可權的員工才能使用整個內容存放庫。

其他來源可能需要手動啟用或進行配置。 非 Microsoft 的學習來源會于貴組織和協力廠商之間個別授權。 您必須確認已註冊他們學習的您和使用者。

若要啟用或停用學習內容來源，請選取來源旁邊的核取方塊。 如果已啟用來源，將會顯示一個核取方塊。

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a>將 SharePoint 設定為學習內容來源， (即將推出) 

您將 SharePoint 設定為 Microsoft 365 系統管理中心內 (預覽) Teams 學習應用程式學習內容來源。

### <a name="overview"></a>概觀

系統管理員會提供網站 URL，讓學習服務可以在其中以結構化 SharePoint 清單的形式建立空白的集中式學習內容存放庫。 組織可以使用此清單來提供包含學習內容的跨公司 SharePoint 資料夾連結。 系統管理員負責收集和策展資料夾的 URL 清單。 這些資料夾應僅包含可在 Teams 學習 App 中提供的內容， (預覽) 。

### <a name="permissions"></a>權限

資料夾 URL 可以從組織的任何 SharePoint 網站收集。 這些資料夾中的任何內容都可以搜尋，但只能使用個別員工有權使用的內容。
 
### <a name="learning-service"></a>學習服務

學習服務會使用所提供的資料夾 URL，從儲存在這些資料夾中的所有內容取得中繼資料。 在集中式存放庫中提供資料夾 URL 的 24 小時內，員工可以在 App 中搜尋及使用公司的內容。 目前不支援從存放庫刪除內容。 只有在 Microsoft 365 系統管理中心提供新的 SharePoint 網站 URL，才能移除非故意顯示的內容。

### <a name="configure-sharepoint-as-a-source"></a>將 SharePoint 設定為來源

這些步驟是由 Microsoft 365 系統管理員執行。

1.  在 Microsoft 365 系統管理中心的左側流覽中，**前往設定。**
 
2.  在設定 **頁面上** 的 & **載入載入&，** 選取學習 **應用程式**。

   ![Microsoft 365 系統管理中心的設定頁面，其中列出學習應用程式](media/learning-app-365-settings-page.png)

3.  在學習 **應用程式面板** 中，提供您想要 App 建立集中式存放庫之 SharePoint 網站的網站 URL。

   ![Microsoft 365 系統管理中心的學習應用程式面板顯示已選取 SharePoint](media/learning-app-365-panel-sharepoint-selected.png)

4.  SharePoint 清單會自動在提供的組織的 SharePoint 網站內建立。 在 SharePoint 網站的左側流覽中，選取 **學習應用程式內容存放庫**。 

   ![SharePoint 中的左側流覽顯示學習應用程式內容存放庫區段](media/learning-app-content-repository-nav.png)

 
5. 在學習 **應用程式內容存放庫頁面上** ，使用學習內容資料夾的 URL 填入 SharePoint 清單。

   1.   選取 **新增** 以查看 **新的專案** 面板。 

   ![SharePoint 中顯示新選項的學習應用程式內容存放庫頁面](media/learning-app-content-repository-new.png)
 
   2.   在新增 **專案面板** 的 **標題欄位中，** 新增您所選擇的目錄名稱。 在資料夾 **URL 欄位中** ，將 URL 新增到學習內容資料夾。 選取 **儲存**。

   ![SharePoint 中顯示標題和資料夾 URL 欄位的新增專案面板](media/learning-app-new-item-panel.png)

   3. 學習應用程式內容存放庫頁面會更新為新的學習內容。

   ![SharePoint 中的學習應用程式內容存放庫頁面，顯示更新的資訊](media/learning-app-content-repository-populated.png)


 


