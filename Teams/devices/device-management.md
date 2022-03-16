---
title: 在 Microsoft Teams
author: cazawideh
ms.author: czawideh
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 瞭解如何管理組織中與Teams一起使用的裝置。
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69432c2a5fa3657a179e254e4bcdd047dc4c2f66
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63511201"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams：管理您的裝置 

您可以從系統管理中心Microsoft Teams組織中與 Microsoft Teams一起使用的裝置。 您可以查看及管理貴組織的裝置庫存，以及執行更新、重新開機及監控裝置診斷等工作。 您也可以建立組式設定檔並指派給裝置或裝置群組。

若要管理裝置 ，例如變更裝置組組、重新開機裝置、管理更新，或查看裝置和周邊健康情況，您必須指派下列其中一個Microsoft 365系統管理員角色：

- Microsoft 365全域系統管理員
- Teams服務系統管理員
- Teams裝置系統管理員

若要進一Teams系統管理員角色，請參閱Teams[系統管理員角色來管理Teams](../using-admin-roles.md)。

## <a name="what-devices-can-you-manage"></a>您可以管理哪些裝置？

您可以管理任何通過認證並註冊的裝置，Teams。 使用者第一次在裝置上Teams會自動註冊裝置。 有關可管理的認證裝置清單，請參閱：

- [共同合作橫條圖](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [會議電話](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [電話機](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Microsoft Teams 會議室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teams顯示](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams面板](teams-panels.md)

若要管理裝置，請在系統管理中心的左側導Microsoft Teams [](https://admin.teams.microsoft.com)，前往 Teams **裝置**，然後選取裝置類型。 每種類型的裝置都有各自的區段，可讓您個別管理它們。

## <a name="manage-teams-rooms-devices"></a>管理Teams 會議室裝置

您可以使用系統管理Teams，來查看及遠端系統管理Teams 會議室裝置。 Teams系統管理中心可讓您一眼就能輕鬆查看哪些裝置健康，哪些裝置需要注意，並讓您專注于特定裝置，以查看有關裝置健康情況、會議績效、通話品質及周邊設備的詳細資訊。 

以下是您可以執行一些操作，以管理您的Teams 會議室裝置。 Teams 會議室裝置」下的 Microsoft Teams [系統管理中心](https://admin.teams.microsoft.com)Teams **裝置**  >  **Teams 會議室**。

若要瞭解如何管理您的Teams 會議室裝置，請參閱[管理Microsoft Teams 會議室](../rooms/rooms-manage.md)。

| 若要這麼做...                          | 執行此                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 變更一或多個裝置上的設定 | 選取一或多個裝置> **編輯設定**。 如果您選取多個裝置，您變更的值會取代所有所選裝置上的值。                                                                                                                                                                                                                       |
| 重新開機裝置                        | 選取一或多個裝置> **重新開機**。 當您重新開機裝置時，您可以選擇是否要立即重新開機裝置，或選取排程重新開機以在特定的日期和時間重新開機裝置。 您選取的日期和時間是重新開機之裝置的本地日期和時間。                                                                                            |
| 查看會議活動                  | 選取裝置名稱以開啟裝置詳細資料> **活動**。 當您 **開啟活動選項卡** 時，可以看到裝置參與的所有會議。 此摘要視圖會顯示會議開始時間、參與者人數、持續時間，以及整體通話品質。                                                                                        |
| 查看會議詳細資料                   | 選取裝置名稱以開啟裝置詳細資料> **活動** >選取會議。 當您開啟會議詳細資料時，可以看到會議的所有參與者、他們在通話中的時間、Teams會話類型，以及他們的個別通話品質。 如果您想要查看參與者通話的技術資訊，請選取參與者的通話開始時間。 |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>管理電話、共同Teams、Teams面板 

在 Teams系統管理中心中，您可以查看及管理在貴組織Teams中註冊的電話、共同Teams、Teams和Teams面板。 每個裝置的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次顯示和歷程記錄。 您可以自訂該視圖以顯示符合您需求的資訊。

如果您已經註冊Teams，Teams就會自動在 Microsoft Intune中註冊手機、共同合作橫條圖、Teams和麵板。 註冊裝置之後，即會確認裝置合規性，並且將條件式存取原則適用于裝置。

以下是您管理電話、共同合作橫條圖、Teams顯示，以及Teams面板的一些範例。  

| 若要這麼做...                           | 執行此                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 變更裝置資訊               | 選取編輯> **裝置**。 您可以編輯詳細資料，例如裝置名稱、資產標記，以及新增筆記。                                                                                                                                                                                                              |
| 管理軟體更新                 | 選取更新> **裝置**。 您可以查看適用于裝置的軟體和固件更新清單，然後選擇要安裝的更新。 有關更新裝置的資訊，請參閱[遠端更新Teams裝置](remote-update.md)                                                          |
| 將Teams手機升級至Teams顯示  | 在 **IP 電話頁面上**，選取一或多個Teams電話>**升級**。 此選項僅適用于支援升級至Teams顯示。 若要深入瞭解，請參閱將Teams[手機升級Teams顯示](upgrade-phones-to-displays.md)。                                                      |
| 指派或變更組群組原則 | 選取一或多個裝置>**指派組。**                                                                                                                                                                                                                                                       |
| 新增或移除裝置標記               | 選取一或多個管理> **裝置**。 有關裝置標記的資訊，請參閱管理[Teams標記](manage-device-tags.md)。                                                                                                                                                                 |
| 重新開機裝置                         | 選取一或多個裝置> **重新開機**。                                                                                                                                                                                                                                                                    |
| 使用裝置標記篩選裝置        | 選取篩選圖示、 **選取標記欄位** 、指定要篩選的裝置標記， **然後選取應用程式**。 有關使用裝置標記篩選裝置的資訊，請參閱使用篩選來退回具有特定標記 [的裝置](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。 |
| 查看裝置歷程記錄與診斷     | 在 [**歷程記錄>** 欄下，按一下裝置的 [查看連結以查看其更新歷程記錄及診斷詳細資料。                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>在 Teams

使用設定設定檔管理組織中不同裝置Teams的設定和功能，包括共同Teams、Teams手機Teams面板。 您可以建立或上傳設定設定檔，以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或裝置集。 

#### <a name="create-a-configuration-profile"></a>建立設定檔

若要為裝置類型建立Teams設定檔：

1. 在左側流覽中，前往 Teams **裝置**>選取 Teams組>**類型**。 例如，選取 **Teams面板**  >  **Teams**  >  設定檔，為多個面板Teams設定檔。****
2. 按一下 [新增 **]**。
3. 輸入設定檔的名稱，並選擇性地新增一個親切的描述。
4. 指定您想要的設定檔設定，然後按一下 [ **儲存**。
   新建立的配置設定檔會顯示在配置檔案清單中。

#### <a name="assign-a-configuration-profile"></a>指派組組設定檔
為裝置類型建立Teams設定檔之後，請將其指派給一或多個裝置。

1. 在左側流覽中，前往 Teams **裝置**>選取Teams類型。 例如，若要將組Teams設定檔指派給Teams，  >  請選取 Teams裝置 **Teams面板**。
2. 選取一或多個裝置，然後按一下 [ **指派組式**。  
3. 在指派 **組組窗格中** ，搜尋要指派給所選裝置的配置設定檔。
4. 按一下 **[申請**。
   針對您適用組組原則的裝置，動作欄會顯示 **Config Update**，而組組 **設定檔欄會顯示** 組組設定檔名稱。****
