---
title: 在 Microsoft Teams 中管理您的裝置
author: dstrome
ms.author: dstrome
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
description: 瞭解如何管理組織中 Teams 使用的裝置。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41213955c9e57829208ce0ec98448195dc266044
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50350593"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft Teams 中管理您的裝置

您可以從 Microsoft Teams 系統管理中心管理組織中與 Microsoft Teams 一起使用的裝置。 您可以查看及管理貴組織的裝置庫存，以及執行更新、重新開機及監控裝置診斷等工作。 您也可以建立設定檔並將設定檔指派給裝置或裝置群組。

若要管理裝置 ，例如變更裝置組配置、重新開機裝置、管理更新，或查看裝置和周邊健康情況，您必須指派下列其中一個 Microsoft 365 系統管理員角色：

- Microsoft 365 全域系統管理員
- Teams 服務系統管理員
- Teams 裝置系統管理員

有關 Teams 中的系統管理員角色詳細資訊，請參閱使用[Teams 系統管理員角色來管理 Teams。](../using-admin-roles.md)

## <a name="what-devices-can-you-manage"></a>您可以管理哪些裝置？

您可以管理已認證並註冊 Teams 的任何裝置。 使用者第一次在裝置上註冊 Teams 時，會自動註冊裝置。 有關可管理的認證裝置清單，請參閱：

- [共同合作橫條圖](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [會議電話](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [電話機](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Microsoft Teams 會議室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teams 顯示](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams 面板](teams-panels.md)

若要管理裝置，請在[Microsoft Teams](https://admin.teams.microsoft.com)系統管理中心的左側流覽中，前往裝置，然後選取裝置類型。 每種裝置類型都有自己的區段，可讓您個別管理它們。

## <a name="manage-teams-rooms-devices"></a>管理 Teams 會議室裝置

您可以使用 Teams 系統管理中心來查看及遠端系統管理整個組織的 Teams 會議室裝置。 Teams 系統管理中心可讓您一目了然地查看哪些裝置健康情況良好，哪些裝置需要注意，並讓您專注于特定裝置，以查看裝置健康情況、會議績效、通話品質及周邊設備的詳細資訊。 

以下是您可以執行一些操作來管理 Teams 會議室裝置。 您可以在裝置 Teams 會議室下的 [Microsoft Teams 系統](https://admin.teams.microsoft.com)管理中心 **找到**  >  **Teams 會議室裝置**。

若要瞭解如何管理 Teams 會議室裝置的詳細資訊，請參閱管理 [Microsoft Teams 會議室](../rooms/rooms-manage.md)。

| 若要這麼做...                          | 請這麼做                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 變更一或多個裝置上的設定 | 選取一或多個裝置> **編輯設定**。 如果您選取多個裝置，您變更的值將會取代所有所選裝置上的值。                                                                                                                                                                                                                       |
| 重新開機裝置                        | 選取一或多個裝置> **重新開機**。 當您重新開機裝置時，您可以選擇是否要立即重新開機裝置，或選取排程重新開機以在特定的日期和時間重新開機裝置。 您選取的日期和時間是重新開機之裝置的本地時間。                                                                                            |
| 查看會議活動                  | 選取裝置名稱以開啟裝置詳細資料> **活動**。 當您開啟活動 **選項卡** 時，可以看到裝置參與的所有會議。 此摘要視圖會顯示會議開始時間、參與者人數、持續時間，以及整體通話品質。                                                                                        |
| 查看會議詳細資料                   | 選取裝置名稱以開啟裝置詳細資料> **活動>** 選取會議。 當您開啟會議詳細資料時，可以看到會議的所有參與者、他們在通話中的時間、Teams 會話類型及其個別通話品質。 如果您想要查看參與者通話的技術資訊，請選取參與者的通話開始時間。 |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>管理電話、共同合作長條、Teams 顯示器和 Teams 面板 

在 Teams 系統管理中心，您可以在貴組織的 Teams 中查看及管理電話、共同合作長條、Teams 顯示和 Teams 面板。 您在每個裝置上看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次查看和歷程記錄。 您可以自訂該視圖以顯示符合您需求的資訊。

如果您已經註冊，系統會自動在 Microsoft Intune 中註冊電話、共同合作橫條圖、Teams 顯示和 Teams 面板。 註冊裝置之後，會確認裝置合規性，並且將條件式存取原則適用于裝置。

以下是一些範例，說明如何在貴組織中管理電話、共同合作長條、Teams 顯示和 Teams 面板。  

| 若要這麼做...                           | 請這麼做                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 變更裝置資訊               | 選取編輯> **裝置**。 您可以編輯詳細資料，例如裝置名稱、資產標記，以及新增記事。                                                                                                                                                                                                              |
| 管理軟體更新                 | 選取更新> **裝置**。 您可以查看裝置可用的軟體與硬體更新清單，並選擇要安裝的更新。 有關更新裝置的資訊，請參閱遠端 [更新 Teams 裝置](remote-update.md)                                                          |
| 將 Teams 手機升級至 Teams 顯示  | 在 **IP 電話頁面上** ，選取一或多個 Teams 電話> **升級**。 只有支援升級到 Teams 的電話才能使用此選項。 若要深入瞭解，請參閱將 [Teams 手機升級至 Teams 顯示](upgrade-phones-to-displays.md)。                                                      |
| 指派或變更群組原則 | 選取一或多個裝置> **指派群組原則**。                                                                                                                                                                                                                                                       |
| 新增或移除裝置標記               | 選取一或多個裝置> **標記**。 有關裝置標記的資訊，請參閱管理 [Teams 裝置標記](manage-device-tags.md)。                                                                                                                                                                 |
| 重新開機裝置                         | 選取一或多個裝置> **重新開機**。                                                                                                                                                                                                                                                                    |
| 使用裝置標記篩選裝置        | 選取篩選圖示、 **選取標記欄位** 、指定要篩選的裝置標記， **然後選取應用程式**。 有關使用裝置標記篩選裝置的資訊，請參閱使用篩選來退回 [具有特定標記的裝置](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。 |
| 查看裝置歷程記錄與診斷     | 在 [**歷程記錄**》欄下，按一下裝置 [查看連結以查看其更新歷程記錄及診斷詳細資料。                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>在 Teams 中使用組設定檔

使用組設定檔管理貴組織中不同 Teams 裝置之設定和功能，包括共同合作長條、Teams 顯示器、Teams 電話和 Teams 面板。 您可以建立或上傳設定設定檔，以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或一組裝置。 

#### <a name="create-a-configuration-profile"></a>建立組設定檔

若要建立 Teams 裝置類型的組設定檔：

1. 在左側流覽中，前往裝置>選取 Teams 裝置類型>**設定檔**。 例如，選取 **裝置**  >  **Teams 面板**  >  **的設定檔，** 以建立 Teams 面板的新組設定檔。
2. 按一下 [新增 **]**。
3. 輸入設定檔的名稱，並選擇性地新增好用的描述。
4. 指定您想要的設定檔設定，然後按一下 **[儲存**。
   新建立的配置設定檔會顯示在配置檔案清單中。

#### <a name="assign-a-configuration-profile"></a>指派組設定檔
為 Teams 裝置類型建立組設定檔之後，請將其指派給一或多個裝置。

1. 在左側流覽中，前往裝置 **>選取** Teams 裝置類型。 例如，若要將組設定檔指派給 Teams 面板裝置，請選取 **裝置**  >  **Teams 面板**。
2. 選取一或多個裝置，然後按一下 [**指派組式。**  
3. 在指派 **組式窗格中** ，搜尋設定檔以指派給選取的裝置。
4. 按一下 **[Apply.**
   針對您適用群組原則的裝置，動作欄會顯示 **Config Update，** 而組 **設定檔欄會顯示** 組設定檔名稱。 
