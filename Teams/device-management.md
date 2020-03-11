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
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587312"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft 團隊中管理您的裝置

做為管理員，您可以從 Microsoft 團隊系統管理中心管理與組織中的小組搭配使用的裝置。 您可以查看及管理貴組織的裝置庫存，以及執行更新、重新開機及監視裝置診斷的工作。 您也可以建立設定檔並將其指派給裝置或裝置群組。 

## <a name="what-devices-can-you-manage"></a>您可以管理哪些裝置？
您可以管理任何已認證的裝置，以及已註冊的小組。 在使用者第一次登入裝置上的小組時，裝置會自動註冊。 如需可管理的認證裝置清單，請參閱：

- [電話會議](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [手機](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- 共同作業條

裝置會在左側導覽中的 [**裝置**] 底下的 [ [Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com)] 進行管理。

> [!NOTE]
> 如果您有 Microsoft Intune，裝置會自動在 Intune 中註冊。 裝置註冊之後，系統會確認裝置合規性，並將條件式存取原則套用到裝置上。

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>管理團隊中的手機與共同作業橫條圖

即使手機和共同作業橫條圖在 Microsoft [團隊管理中心] 中的管理方式相同，他們在左側導覽中的 [**裝置**] 底下都有各自的區段。 這可讓您分別管理每個類型的裝置。

您可以從這裡，查看及管理您組織中的小組登記的電話和共同作業列。 您會在每個裝置上看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次查看，以及歷程記錄。 您可以自訂 [視圖]，以顯示符合您需求的資訊。

以下是如何管理組織中的小組裝置的一些範例。  
    
|若要執行此動作 .。。  |執行此動作 |
|---------|---------|
|變更裝置資訊   | 選取 >**編輯**的裝置。 您可以編輯裝置名稱、資產標記及新增筆記等詳細資料。     |
|管理軟體更新   |選取 >**更新**的裝置。 您可以查看裝置可用的軟體和固件更新清單，並選擇要安裝的更新。    |
|重新開機裝置   |選取 >**重新開機**的裝置。          |
|查看裝置歷程記錄  | 選取裝置 > 歷程**記錄**]。 您可以查看裝置的更新歷程記錄。     |
|[查看] 診斷  | 選取 >**診斷**的裝置。        |

## <a name="use-configuration-profiles-in-teams"></a>在團隊中使用設定檔

使用設定檔來管理貴組織中的小組裝置設定和功能。 您可以建立或上傳設定檔，以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或裝置群組。 

### <a name="create-a-configuration-profile"></a>建立設定檔

1. 在左側導覽中，移至 [**裝置** > **設定檔**]。
2. 按一下 [**新增**]。
3. 輸入設定檔的名稱，並視需要新增易記的描述。
4. 為設定檔指定您想要的設定，然後按一下 [**儲存**]。

### <a name="assign-a-configuration-profile"></a>指派設定檔

1. 在左側導覽中，移至 [**裝置** > **設定檔**]。
2. 選取您要指派的**設定檔**，然後按一下 [**指派給裝置**]。  
3. 在 [**將裝置指派給**設定設定檔] 窗格中，搜尋並選取您要指派的裝置。
4. 按一下 [**儲存**]。
