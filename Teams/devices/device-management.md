---
title: 在 Microsoft 團隊中管理您的裝置
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 瞭解如何管理與組織中的小組搭配使用的裝置。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40ddf36c27a8fbc3aadfddaddee886d1906bab82
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48793539"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft 團隊中管理您的裝置

您可以從 Microsoft 團隊系統管理中心管理組織中 Microsoft 團隊使用的裝置。 您可以查看及管理貴組織的裝置庫存，以及執行更新、重新開機及監視裝置診斷的工作。 您也可以建立設定檔並將其指派給裝置或裝置群組。

若要管理裝置，例如變更裝置設定、重新開機裝置、管理更新，或查看裝置和週邊電腦健康情況，您必須指派下列 Microsoft 365 系統管理員角色中的其中一項：

- Microsoft 365 全域系統管理員
- 團隊服務管理員
- 團隊裝置管理員

如需有關團隊中系統管理員角色的詳細資訊，請參閱 [使用團隊管理員角色管理團隊](../using-admin-roles.md)。

## <a name="what-devices-can-you-manage"></a>您可以管理哪些裝置？

您可以管理任何已認證的裝置，以及已註冊的小組。 在使用者第一次登入裝置上的小組時，裝置會自動註冊。 如需可管理的認證裝置清單，請參閱：

- [Microsoft Teams 會議室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [電話會議](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [手機](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [團隊顯示](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [共同作業條](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

若要管理裝置，請在 [Microsoft [團隊管理中心](https://admin.teams.microsoft.com)] 的左導覽中，移至 [ **裝置** ]，然後選取裝置類型。 每個類型的裝置都有各自的區段，可讓您分別管理它們。

## <a name="manage-teams-rooms-devices"></a>管理團隊聊天室裝置

您可以使用 [團隊系統管理中心]，在整個組織中查看和遠端系統管理團隊間的裝置。 [團隊系統管理中心] 可讓您輕鬆查看哪些裝置正常運作且需要注意，並讓您專注于特定裝置上，以查看裝置健康情況、會議效能、通話品質以及週邊設備的詳細資訊。 

以下是您可以用來管理團隊聊天室裝置的一些事項。 您可以在 [  。

如需有關如何管理團隊聊天室裝置的詳細資訊，請參閱 [管理 Microsoft 團隊聊天室](../rooms/rooms-manage.md)。

| 若要執行此動作 .。。 | 請這麼做|
|---------------|--------|
| 變更一或多個裝置上的設定 | 選取一或多個裝置 > **編輯設定** ]。 如果您選取多個裝置，您所變更的值將會取代所有選取的裝置上的值。 |
| 重新開機裝置 | 選取一或多個裝置，> **重新開機** ]。 當您重新開機裝置時，您可以選擇是否要立即重新開機裝置，或選取 [ **排程重新開機** ]，在特定的日期和時間重新開機裝置。 您選取的日期和時間是您在裝置重新開機的地方。|
| 查看會議活動 | 選取裝置名稱，以開啟 [裝置詳細資料] > **活動** 。 當您開啟 [ **活動** ] 索引標籤時，您可以看到該裝置參與的所有會議。 這個摘要視圖會顯示會議的開始時間、參與者的人數、其持續時間和整體通話品質。|
| 查看會議詳細資料 |  選取裝置名稱，以開啟 [裝置詳細資料] > **活動** > 選取會議。 當您開啟會議的詳細資料時，您可以看到會議中的所有參與者、通話時長、團隊會議類型，以及個人通話品質。 如果您想要查看參與者通話的相關技術資訊，請選取參與者的通話開始時間。|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>管理手機、共同作業橫條圖和團隊顯示 

在團隊系統管理中心中，您可以在組織中查看和管理手機、共同作業橫條圖，以及團隊顯示已註冊的團隊。 您會在每個裝置上看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次查看，以及歷程記錄。 您可以自訂 [視圖]，以顯示符合您需求的資訊。

如果您已註冊手機、共同作業列和團隊顯示，就會自動在 Microsoft Intune 中註冊。 裝置註冊之後，系統會確認裝置合規性，並將條件式存取原則套用到裝置上。

以下是一些如何管理手機、共同作業列以及團隊在組織中顯示的範例。  

|若要執行此動作 .。。  |請這麼做 |
|---------|---------|
| 變更裝置資訊               | 選取 > **編輯** 的裝置。 您可以編輯裝置名稱、資產標記及新增筆記等詳細資料。     |
| 管理軟體更新                 | 選取 > **更新** 的裝置。 您可以查看裝置可用的軟體和固件更新清單，並選擇要安裝的更新。 如需更新裝置的詳細資訊，請參閱 [遠端更新團隊裝置](remote-update.md)   |
| 將小組電話升級至團隊顯示                | 在 [ **IP 電話** ] 頁面上，選取一或多個小組手機 > **升級** ]。 只有支援升級至團隊的手機才能使用此選項。 若要深入瞭解，請參閱 [將小組電話升級至團隊](upgrade-phones-to-displays.md)。   |
| 指派或變更配置原則 | 選取一或多個裝置 > **指派** 設定]。                                                                                                                                                                                                                   |
| 新增或移除裝置標記               | 選取一或多個 > **管理標記** 的裝置。 如需裝置標籤的詳細資訊，請參閱 [管理團隊裝置標記](manage-device-tags.md)。                                                                                                      |
| 重新開機裝置                         | 選取一或多個裝置，> **重新開機** ]。                                                                                                                                                                                                                                |
| 使用裝置標記篩選裝置        | 選取 [篩選] 圖示、選取 [標籤 **] 欄位、** 指定要篩選的裝置標記，然後選取 [套用 **]。** 如需使用裝置標籤篩選裝置的詳細資訊，請參閱 [使用篩選來傳回具有特定](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)標籤的裝置。|
| 查看裝置歷程記錄                     | 選取裝置 > 歷程 **記錄** ]。 您可以查看裝置的更新歷程記錄。                                                                                                                                                                                |
| [查看] 診斷                        | 選取 > **診斷** 的裝置。                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>在團隊中使用設定檔

使用設定檔來管理貴組織中的小組電話與共同作業橫條圖的設定和功能。 您可以建立或上傳設定檔，以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或裝置群組。 

#### <a name="create-a-configuration-profile"></a>建立設定檔

1. 在左側導覽中，移至 [ **裝置**  >  **設定檔** ]。
2. 按一下 [ **新增** ]。
3. 輸入設定檔的名稱，並視需要新增易記的描述。
4. 為設定檔指定您想要的設定，然後按一下 [ **儲存** ]。

#### <a name="assign-a-configuration-profile"></a>指派設定檔

1. 在左側導覽中，移至 [ **裝置**  >  **設定檔** ]。
2. 選取您要指派的 **設定檔** ，然後按一下 [ **指派給裝置** ]。  
3. 在 [ **將裝置指派給** 設定設定檔] 窗格中，搜尋並選取您要指派的裝置。
4. 按一下 [儲存]  。

