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
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 瞭解如何管理組織中與 Teams 搭配使用的裝置。
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc65025ed255dff1685f7aa30a555facdd3f11c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270838"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams：管理您的裝置 

您可以從 Microsoft Teams 系統管理中心管理組織中與 Microsoft Teams 搭配使用的裝置。 您可以檢視和管理貴組織的裝置庫存，並執行更新、重新開機和監視裝置診斷等工作。 您也可以建立並指派組態設定檔給裝置或裝置群組。

若要管理裝置，例如變更裝置設定、重新開機裝置、管理更新，或檢視裝置和周邊健康情況，您必須獲派下列其中一個 Microsoft 365 系統管理員角色：

- Microsoft 365 全域系統管理員
- Teams 服務系統管理員
- Teams 裝置系統管理員

如需 Teams 中系統管理員角色的詳細資訊，請參閱 [使用 Teams 系統管理員角色管理 Teams](../using-admin-roles.md)。

## <a name="what-devices-can-you-manage"></a>您可以管理哪些裝置？

您可以管理任何經過 Teams 認證且已註冊的裝置。 當使用者第一次登入裝置上的 Teams 時，會自動註冊裝置。 如需可管理的認證裝置清單，請參閱：

- [Microsoft Teams 會議室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [會議電話](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [電話機](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams 顯示器](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams 面板](teams-panels.md)

若要管理裝置，請在 [Microsoft Teams 系統管理中心的](https://admin.teams.microsoft.com)左側導覽中，移至 **[Teams 裝置**]，然後選取裝置類型。 每種類型的裝置都有各自的區段，可讓您個別管理它們。

## <a name="manage-teams-rooms-on-windows-devices"></a>在 Windows 裝置上管理Teams 會議室

您可以使用 Teams 系統管理中心檢視及遠端系統管理貴組織 Windows 裝置上的Teams 會議室。 Teams 系統管理中心可讓您快速查看哪些裝置健康且需要注意，並可讓您專注于特定裝置，以查看裝置健康情況、會議效能、通話品質及周邊裝置的詳細資訊。 

以下是您可以管理Teams 會議室裝置的一些方法。 Teams 會議室裝置可以在 Windows 上的 **[Teams 裝置**  >  ] 底下的 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com)**找到Teams 會議室**。

如需如何管理Teams 會議室裝置的詳細資訊，請參閱[管理Microsoft Teams 會議室](../rooms/rooms-manage.md)。

| 若要這麼做...                          | 執行此動作                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 變更一或多個裝置上的設定 | 選取 [ **編輯設定**] >一或多個裝置。 如果您選取多個裝置，您變更的值將會取代所有選取裝置上的值。                                                                                                                                                                                                                       |
| 重新開機裝置                        | 在 [ **重新開機**] >選取一或多個裝置。 當您重新開機裝置時，您可以選擇是否要立即重新開機裝置，或選取 [ **排程重新開機** ] 以在特定日期和時間重新開機裝置。 您選取的日期和時間是已重新開機之裝置的本機日期和時間。                                                                                            |
| 檢視會議活動                  | 選取裝置名稱以開啟 [活動] >裝置詳細 **資料**。 當您開啟 [ **活動] 索** 引標籤時，您可以看到裝置參與的所有會議。 此摘要檢視會顯示會議開始時間、參與者數目、持續時間，以及整體通話品質。                                                                                        |
| 檢視會議詳細資料                   | 選取裝置名稱以在 [ **活動** ] >開啟裝置詳細資料>選取會議。 當您開啟會議的詳細資料時，您可以看到會議中的所有參與者、他們在通話中的時間長度、Teams 會話類型，以及他們的個別通話品質。 如果您想要查看參與者通話的技術資訊，請選取該參與者的通話開始時間。 |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>在 Android、Teams 顯示器和 Teams 面板上管理手機、Teams 會議室 

在 Teams 系統管理中心，您可以檢視和管理 Android 上的電話、Teams 會議室、Teams 顯示器，以及您組織中 Teams 中註冊的 Teams 面板。 您會針對每個裝置看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次查看和歷程記錄。 您可以自訂檢視以顯示符合您需求的資訊。

如果您已註冊手機、Android Teams 會議室、Teams 顯示器和 Teams 面板，Microsoft Intune會自動註冊。 註冊裝置之後，確認裝置合規性，並套用條件式存取原則至裝置。

以下是一些範例，說明如何管理貴組織中的電話、Teams 會議室、Teams 顯示器和 Teams 面板。  

| 若要這麼做...                           | 執行此動作                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 變更裝置資訊               | 選取 [編輯] >**裝置。** 您可以編輯詳細資料，例如裝置名稱、資產標記和新增記事。                                                                                                                                                                                                              |
| 管理軟體更新                 | 選取 [ **更新**] >裝置。 您可以檢視裝置可用的軟體和韌體更新清單，並選擇要安裝的更新。 如需有關更新裝置的詳細資訊，請參閱 [遠端更新 Teams 裝置](remote-update.md)                                                          |
| 將 Teams 手機升級至 Teams 顯示器  | 在 **IP 手機** 頁面上，選取 [ **升級**] >一或多個 Teams 手機。 此選項僅適用于支援升級至 Teams 顯示器的手機。 若要深入瞭解，請參閱 [將 Teams 手機升級至 Teams 顯示器](upgrade-phones-to-displays.md)。                                                      |
| 指派或變更組態原則 | 選取 [ **指派** 設定] >一或多個裝置。                                                                                                                                                                                                                                                       |
| 新增或移除裝置標籤               | 選取 [ **管理標籤**] >一或多個裝置。 如需裝置標籤的詳細資訊，請參閱 [管理 Teams 裝置標籤](manage-device-tags.md)。                                                                                                                                                                 |
| 重新開機裝置                         | 在 [ **重新開機**] >選取一或多個裝置。                                                                                                                                                                                                                                                                    |
| 使用裝置標籤篩選裝置        | 選取篩選圖示，選取 [ **標籤** ] 欄位，指定要篩選的裝置標籤，然後選取 [ **套用]**。 如需使用裝置標籤篩選裝置的詳細資訊，請參閱 [使用篩選來傳回具有特定標籤的裝置](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。 |
| 檢視裝置歷程記錄與診斷     | 在 [ **歷程記錄]** 欄底下，按一下裝置的 [檢 **視** ] 連結，以檢視其更新記錄和診斷詳細資料。                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>在 Teams 中使用組態設定檔

使用組態設定檔來管理組織中不同 Teams 裝置的設定和功能，包括 Android 上的Teams 會議室、Teams 顯示器、Teams 手機和 Teams 面板。 您可以建立或上傳組態設定檔以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或一組裝置。 

#### <a name="create-a-configuration-profile"></a>建立組態設定檔

若要建立 Teams 裝置類型的組態設定檔：

1. 在左側導覽中，移至 **[Teams 裝置** ] >選取 [設定 **] 設定檔**> Teams 裝置類型。 例如，選取 **[Teams 裝置**  >  **] Teams 面板**  >  **設定設定檔**，為 Teams 面板建立新的組態設定檔。
2. 按一下 [新增 **]**。
3. 輸入設定檔的名稱，並選擇性地新增好記的描述。
4. 指定您想要的設定檔設定，然後按一下 [儲存 **]**。
   新建立的設定檔會顯示在配置檔案清單中。

#### <a name="assign-a-configuration-profile"></a>指派組態設定檔
為 Teams 裝置類型建立組態設定檔之後，請將它指派給一或多個裝置。

1. 在左側導覽畫面中，移至 **[Teams 裝置** ] >選取 Teams 裝置類型。 例如，若要將組態設定檔指派給 Teams 面板裝置，請選 **取 Teams 裝置**  >  **Teams 面板**。
2. 選取一或多個裝置，然後按一下 **[指派設定]**。  
3. 在 [ **指派設定** ] 窗格中，搜尋設定檔以指派給選取的裝置。
4. 按一下 [ **套用]**。
   針對您套用組態原則的裝置， **[動作** ] 欄會顯示 [ **設定更新** ]，而 [ **設定設定檔** ] 欄會顯示組態設定檔名稱。
