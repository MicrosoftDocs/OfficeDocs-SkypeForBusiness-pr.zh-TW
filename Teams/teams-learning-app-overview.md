---
title: '在 (私人預覽版] 中安裝、管理及指派小組學習 app 的許可權) '
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
description: 使用 Microsoft 團隊學習 app 來建立中央中樞，以便在員工可以在組織內共用、分派及學習內容庫。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703409"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>在 (私人預覽版] 中安裝、管理及指派小組學習 app 的許可權) 

*本文包含適用于 [私人預覽] 中的 [團隊學習] app 的基本內容。*

Microsoft 團隊學習 app (私人預覽版) 可讓貴組織中的小組和個人學會自己的日常參與。 應用程式會在團隊中建立一個中央中樞，員工可以在其中在整個組織中共用、分派及學習內容庫。 系統管理員設定許可權，並允許學習應用程式的內容來源。 學習內容可以包括 LinkedIn Learning、Microsoft 學會、Microsoft 365 訓練、貴組織本身的內容儲存在 SharePoint online 中，以及應用程式支援的協力廠商提供者。

若要將 [團隊學習] app 設定 (私人預覽]) ，您必須參與下列作業：

-   團隊系統管理中心管理員
-   Microsoft 365 系統管理中心管理員 (，也就是全域系統管理員) 
-   知識管理員 (Microsoft 365 系統管理中心的新角色，全域系統管理員 (也稱為 IT 管理員或 Microsoft 365 管理員) 可以指派給組織中的任何人。 這個角色透過 Microsoft 365 系統管理中心管理組織的學習內容來源。 )  

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>在團隊系統管理中心中管理團隊學習 app (私人預覽) 

[團隊管理員] 會將團隊學習 app 從應用程式商店 (私人預覽) ，並透過團隊系統管理中心套用 app 設定、管理及許可權原則。

### <a name="manage-the-teams-learning-app-private-preview"></a>在私人預覽版中管理團隊學習 app () 

若要管理 app 的設定，請依照下列步驟執行：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。

   ![小組系統管理中心的左側導覽，顯示 [小組 app] 和 [管理 app] 區段](media/learning-app-teams-manage-apps-nav.png)

2. 在 [ **管理應用程式** ] 頁面上的 [搜尋] 方塊中，輸入「 *學習* 」以搜尋小組學習 app (私人預覽]) 。

   ![[團隊管理中心] 中顯示 [搜尋] 方塊的 [管理應用程式] 頁面](media/learning-app-teams-manage-apps-page.png)

3. 在 [ **學習** ] 頁面上：
   1. 在 [ **狀態**] 底下，選取 [ **允許** ] 以開啟 app。
   2. 在 [ **設定** ] 索引標籤的 [ **應用程式設定** ] 區段中，移至 Microsoft 365 系統管理中心來設定學習內容來源。

   ![[團隊管理中心] 中的 [學習] 頁面，顯示 [狀態及應用程式設定] 區段](media/learning-app-teams-learning-page.png)

4. **管理應用程式** 設定之後，請移至 [**許可權] 和 [設定策略**]，授權給應該有權存取應用程式的員工，該許可權必須是貴組織參與私人預覽版的一部分。

> [!NOTE]
>  如果您的組織是作為 [團隊 TAP100] 計畫的一部分來撥打4.0，則您可能需要執行下列動作，才能在撥打3.0 中的核准使用者， (私人預覽版) 存取團隊學習 app。

在私人預覽版中，小組學習 app (私人預覽) 是在 Ring 3.0 中發行。 如果您的組織是 Ring 4.0，就不會在 app store 中看到該應用程式。 若要測試應用程式，您需要建立自訂應用程式許可權原則，將它設定為 **允許所有** 的 app，並將它指派給響鈴3.0 核准的使用者。

   ![AppsPermission-Plcy 頁面，顯示 [允許所有 app 已選取]](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心設定學習內容來源

Microsoft 365 系統管理中心的管理員（無論是自行或指派知識管理員角色給貴組織中的選取的人員），都可以管理與團隊學習 app 相關的設定 (私人預覽) ，而且可以設定學習內容來源。

> [!TIP]
> 知識系統管理員應該是適度的技術，且擁有現有的 SharePoint 系統管理員認證，最好是在組織的教育、學習、訓練或員工經驗中 versed 的人員。
 
系統管理員會選取將在 app 中提供哪些學習內容來源 (例如 LinkedIn Learning 或 SharePoint) 。 系統管理員接著會設定這些來源，以確保內容可供搜尋和探索使用，且可供使用 app 的員工流覽。

### <a name="assign-the-knowledge-admin-role-optional"></a>指派知識管理員角色 [選用]

這些步驟將由 Microsoft 365 系統管理中心的管理員執行。

1.  在 Microsoft 365 系統管理中心的左導覽中，前往 [ **角色**]。

2.  在 [ **角色** ] 頁面上的 [ **Azure AD** ] 索引標籤上，選取 [ **知識庫系統管理**]。
 
3.  在 [ **知識庫系統管理** ] 頁面上的 [ **指派的管理員** ] 區段中，選取 [ **新增**]，然後新增您針對角色所選擇的人員。

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>設定應用程式學習內容來源的設定

這些步驟將由 Microsoft 365 管理員或知識系統管理員執行。

1.  在 Microsoft 365 系統管理中心的左導覽中，移至 [**設定**  >  **組織設定**]。

2.  在 [ **設定** ] 頁面的 [ **服務 & [增益集** ] 索引標籤上，選取 [ **學習應用程式**]。

   ![Microsoft 365 系統管理中心的 [設定] 頁面，顯示已列出的學習應用程式](media/learning-app-365-settings-page.png)

3.  在 [ **學習 app** ] 面板上，選取您想要為組織設定的學習內容來源，然後選取 [ **儲存**]。

   ![Microsoft 365 系統管理中心的學習應用程式面板，其中顯示 [內容來源] 選項](media/learning-app-365-settings-learning-app-panel.png)

在現有的所有學習來源中，一些預設會啟用。 這些包括：

- LinkedIn Learning (免費內容) 
- Microsoft 學習
- Microsoft 365 訓練

> [!NOTE]
> 如果您的組織有 LinkedIn 學習標準版或 Pro 訂閱，將會針對貴組織中的員工解除鎖定內容儲存庫。 只有擁有許可權的員工才能使用整個內容儲存庫。

其他來源可能需要手動啟用或設定。 不是來自 Microsoft 的學習來源，會在您的組織和協力廠商之間另行提供授權。 您必須確認您已為自己和您的使用者註冊自己的學習。

若要啟用或停用學習內容來源，請選取來源旁邊的核取方塊。 如果已啟用來源，則會顯示核取記號。

## <a name="configure-sharepoint-as-a-learning-content-source"></a>將 SharePoint 設定為學習內容來源

您可以在 Microsoft 365 系統管理中心的 [私人預覽]) ，將 SharePoint 設定為 [團隊學習] (app 的學習內容來源。

### <a name="overview"></a>概觀

知識管理員提供網站 URL，讓教學服務能在結構化 SharePoint 清單的表單中建立空白的集中式學習內容儲存庫。 貴組織可以使用此清單來容納包含學習內容的跨公司 SharePoint 資料夾的連結。 系統管理員負責收集及策劃資料夾的 Url 清單。 這些資料夾應該只包含可在團隊學習 app 中提供的內容 (私人預覽版) 。

### <a name="permissions"></a>權限

您可以從組織中的任何 SharePoint 網站收集資料夾 Url。 這些資料夾中的任何內容都可供搜尋，但只有個別員工擁有許可權的內容才可以使用。
 
### <a name="learning-service"></a>學習服務

學習服務會使用所提供的資料夾 Url，從儲存在這些資料夾中的所有內容取得中繼資料。 在24小時內提供集中式知識庫中的資料夾 URL 之後，員工就可以在 app 中搜尋並使用公司的內容。 此時不支援從知識庫刪除內容。 無意中出現的內容，只能透過在 Microsoft 365 系統管理中心提供新的 SharePoint 網站 URL 來移除。

### <a name="configure-sharepoint-as-a-source"></a>將 SharePoint 設定為來源

這些步驟將由 Microsoft 365 管理員或知識系統管理員執行。

1.  在 Microsoft 365 系統管理中心的左導覽中，移至 [ **設定**]。
 
2.  在 [ **設定** ] 頁面的 [ **服務 & [增益集** ] 索引標籤上，選取 [ **學習應用程式**]。

   ![Microsoft 365 系統管理中心的 [設定] 頁面，顯示已列出的學習應用程式](media/learning-app-365-settings-page.png)

3.  在 [ **學習 app** ] 面板上，提供您想要 app 建立集中式知識庫之 SharePoint 網站的網站 URL。

   ![顯示已選取 SharePoint 的 Microsoft 365 系統管理中心中的 [學習應用程式] 面板](media/learning-app-365-panel-sharepoint-selected.png)

4.  SharePoint 清單是在所提供組織的 SharePoint 網站中自動建立。 在 SharePoint 網站的左側導覽中，選取 [ **學習 App 內容儲存庫**]。 

   ![SharePoint 中的左側導覽，顯示學習應用程式內容庫區段](media/learning-app-content-repository-nav.png)

 
5. 在 [ **學習 App 內容儲存庫** ] 頁面上，使用「學習內容」資料夾的 Url 填入 SharePoint 清單。

   1.   選取 [ **新增** ]，查看 [ **新增專案** ] 面板。 

   ![SharePoint 中的 [學習應用程式內容庫] 頁面，其中顯示 [新增] 選項](media/learning-app-content-repository-new.png)
 
   2.   在 [ **新增專案** ] 面板的 [ **標題** ] 欄位中，新增您選擇的目錄名稱。 在 [ **資料夾 URL** ] 欄位中，將 URL 新增至 [學習內容] 資料夾。 選取 [ **儲存**]。

   ![SharePoint 中的 [新增專案] 面板，顯示 [標題] 和 [資料夾 URL] 欄位](media/learning-app-new-item-panel.png)

   3. 學習 App 內容儲存庫頁面會以新的學習內容更新。

   ![SharePoint 中的 [學習應用程式內容庫] 頁面，其中顯示更新的資訊](media/learning-app-content-repository-populated.png)


 


