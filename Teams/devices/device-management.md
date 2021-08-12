---
title: 在 Microsoft Teams 中管理裝置。
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
description: 了解如何管理組織中與 Teams 一同使用的裝置。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e04cc34811190e5948ea2baaec0c368fb4abaf5dced072e56505e73f346d2c2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286332"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft Teams 中管理裝置。

您可以從 Microsoft Teams 系統管理中心管理組織中與 Microsoft Teams 一起使用的裝置。 您可以檢視及管理組織的裝置庫存，以及執行如更新、重新啟動和監視裝置診斷等工作。 您也可以建立組態設定檔，並將其指派給裝置或裝置群組。

若要管理裝置，例如變更裝置設定、重新啟動裝置、管理更新，或檢視裝置和周邊設備健康情況，您必須獲派下列其中一個 Microsoft 365 系統管理員角色：

- Microsoft 365 全域系統管理員
- Teams 服務系統管理員
- Teams 裝置系統管理員

如需 Teams 中系統管理員角色的詳細資訊，請參閱[使用 Microsoft Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)。

## <a name="what-devices-can-you-manage"></a>您可以管理哪些裝置？

您可以管理已經過認證並在 Teams 中註冊的任何裝置。 使用者第一次在裝置上登入 Teams 時，會自動註冊裝置。 如需可管理的認證裝置清單，請參閱：

- [共同作業列](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [會議電話](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [傳統型電話](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Microsoft Teams 會議室](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teams 顯示器](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams 面板](teams-panels.md)

若要管理裝置，請在 [[Microsoft Teams 系統管理中心]](https://admin.teams.microsoft.com) 的左側瀏覽中，移至 **[裝置]**，然後選取裝置類型。 每種裝置類型都有各自的區段，可讓您進行個別管理。

## <a name="manage-teams-rooms-devices"></a>管理 Teams 會議室裝置

您可以使用 [Teams 系統管理中心] 來檢視和遠端管理整個組織的 Teams 會議室裝置。 [Teams 系統管理中心] 可讓您一目了然地查看哪些裝置健康情況良好以及哪些需要注意，並讓您專注於特定裝置，以查看裝置健康情況、會議效能、通話品質及周邊設備的詳細資訊。 

以下是在管理 Teams 會議室裝置時，您可執行的動作。 您可以在 [[Microsoft Teams 系統管理中心]](https://admin.teams.microsoft.com) 的 **[裝置]** > **[Teams 會議室]** 下找到 Teams 會議室裝置。

如需如何管理 Teams 會議室裝置的詳細資訊，請參閱[管理 Microsoft Teams 會議室](../rooms/rooms-manage.md)。

| 若要執行此動作...                          | 執行此動作                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 變更一或多個裝置上的設定 | 選取一或多個裝置 > **[編輯設定]**。 如果您選取多個裝置，您變更的值將會取代所有選取裝置上的值。                                                                                                                                                                                                                       |
| 重新啟動裝置                        | 選取一或多個裝置 > **[重新啟動]**。 當您重新啟動裝置時，您可以選擇是否要立即重新啟動裝置，或選取 **[排程重新啟動]** 以在特定的日期和時間重新啟動裝置。 您選取的日期和時間是正在重新啟動之裝置的本機時間。                                                                                            |
| 檢視會議活動                  | 選取裝置名稱以開啟 [裝置詳細資料] > **[活動]**。 當您開啟 **[活動]** 索引標籤，可以看到裝置已參與的所有會議。 此摘要檢視會顯示會議開始時間、參與者人數、持續時間，以及整體通話品質。                                                                                        |
| 檢視會議詳細資料                   | 選取裝置名稱以開啟 [裝置詳細資料] > **[活動]** > 選取會議。 當您開啟會議詳細資料時，可以看到會議的所有參與者、他們通話多久、Teams 工作階段類型，以及他們的個別通話品質。 如果您想要查看參與者通話的技術資訊，請選取參與者的通話開始時間。 |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>管理電話、共同合作列、Teams 顯示器和 Teams 面板 

您可以在 [Teams 系統管理中心] 檢視及管理在組織的 Teams 中註冊的電話、共同合作列、Teams 顯示器和 Teams 面板。 每個裝置可看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次上線時間和歷程記錄。 您可以自訂該檢視，以顯示符合您需求的資訊。

如果您已註冊，電話、共同作業列、Teams 顯示器和 Teams 面板將自動註冊到 Microsoft Intune 中。 註冊裝置之後，會確認裝置合規性，並且將條件式存取原則套用到裝置。

以下是一些如何在組織中管理電話、共同作業列、Teams 顯示器和 Teams 面板的範例。  

| 若要執行此動作...                           | 執行此動作                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 變更裝置資訊               | 選取裝置 > **[編輯]**。 您可以編輯詳細資料，例如裝置名稱、資產標記，以及新增附註。                                                                                                                                                                                                              |
| 管理軟體更新                 | 選取裝置 > **[更新]**。 您可以檢視裝置可用的軟體和韌體更新清單，並選擇要安裝的更新。 如需更新裝置的詳細資訊，請參閱[遠端更新 Teams 裝置](remote-update.md)                                                          |
| 將 Teams 電話升級為 Teams 顯示器  | 在 **[IP 電話]** 頁面上，選取一或多支 Teams 手機> **[升級]**。 此選項僅適用於支援升級至 Teams 顯示器的手機。 若要深入了解，請參閱[將 Teams 電話升級為 Teams 顯示器](upgrade-phones-to-displays.md)。                                                      |
| 指派或變更設定原則 | 選取一或多個裝置 > **[指派設定]**。                                                                                                                                                                                                                                                       |
| 新增或移除裝置標記               | 選取一或多個裝置 > **[管理標記]**。 如需裝置標記的詳細資訊，請參閱[管理 Teams 裝置標記](manage-device-tags.md)。                                                                                                                                                                 |
| 重新啟動裝置                         | 選取一或多個裝置 > **[重新啟動]**。                                                                                                                                                                                                                                                                    |
| 使用裝置標記篩選裝置        | 選取篩選圖示、選取 **[標記]** 欄位、指定要篩選的裝置標記，然後選取 **[套用]**。 如需使用裝置標記篩選裝置的詳細資訊，請參閱[使用篩選器以傳回具有特定標記的裝置](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。 |
| 檢視裝置歷程記錄與診斷     | 在 **[歷程記錄]** 欄下，按一下裝置的 **[檢視]** 連結，以查看裝置的更新歷程記錄與診斷詳細資料。                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>在 Teams 中使用組態設定檔

使用組態設定檔來管理組織中不同 Teams 裝置 (包括共同合作列、Teams 顯示器、Teams 手機和 Teams 面板) 的設定和功能。 您可以建立或上傳組態設定檔，以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或一組裝置。 

#### <a name="create-a-configuration-profile"></a>建立組態設定檔

若要建立 Teams 裝置類型的組態設定檔：

1. 在左側瀏覽中，前往 **[裝置]** > 選取 Teams 裝置類型 > **[組態設定檔]**。 例如，選取 **[裝置]** > **[Teams 面板]** > **[組態設定檔]**，以建立 Teams 面板的新組態設定檔。
2. 按一下 **[新增]**。
3. 輸入設定檔的名稱，並選擇性地新增易記的描述。
4. 指定設定檔的設定，然後按一下 **[儲存]**。
   新建立的組態設定檔會顯示在設定檔清單中。

#### <a name="assign-a-configuration-profile"></a>指派組態設定檔
建立 Teams 裝置類型的組態設定檔之後，將其指派給一或多個裝置。

1. 在左側瀏覽中，前往 **[裝置]** > 選取 Teams 裝置類型。 例如，若要將組態設定檔指派給 Teams 面板裝置，選取 **[裝置]** > **[Teams 面板]**。
2. 選取一或多個裝置，然後按一下 **[指派設定]**。  
3. 在 **[指派設定]** 窗格中，搜尋要指派給所選裝置的組態設定檔。
4. 按一下 **[套用]**。
   對於您套用組態原則的裝置，**[動作]** 欄會顯示 **[設定更新]**，而 **[組態設定檔]** 欄會顯示組態設定檔名稱。
