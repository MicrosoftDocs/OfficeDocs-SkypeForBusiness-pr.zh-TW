---
title: 在 Microsoft 團隊中管理您的裝置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 瞭解如何管理與組織中的小組搭配使用的裝置。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b85012adbf0967889e74fb5765b02c9b2ea18f
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2019
ms.locfileid: "39211934"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>在 Microsoft 團隊中管理您的裝置

::: zone target="docs"
做為管理員，您可以從 Microsoft 團隊系統管理中心管理與組織中的小組搭配使用的所有裝置。 您可以查看及管理貴組織的裝置庫存，以及執行更新、重新開機及監視裝置診斷的工作。 您也可以建立設定檔並將其指派給裝置或裝置群組。 

## <a name="what-devices-can-you-manage"></a>您可以管理哪些裝置？
裝置必須經過認證，才能供小組使用，並已在小組中註冊。 在使用者第一次登入裝置上的小組時，裝置會自動註冊。 如需可管理的認證裝置清單，請參閱[電話會議](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)與[手機](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)。

> [!NOTE]
> 如果您有 Microsoft Intune，裝置會自動在 Intune 中註冊。 裝置註冊之後，系統會確認裝置合規性，並將條件式存取原則套用到裝置上。 

## <a name="manage-devices-in-teams"></a>管理團隊中的裝置

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中，移至 [**裝置** > **管理裝置**]。
2. 選取 [**所有裝置**]。  

::: zone-end

 您可以從這裡，查看及管理您組織中所有已註冊團隊的裝置。 您會在每個裝置上看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次查看，以及歷程記錄。 您可以自訂 [視圖]，以顯示符合您需求的資訊。

 以下是如何管理組織中的小組裝置的一些範例。  
    
|若要執行此動作 .。。  |執行此動作 |
|---------|---------|
|變更裝置資訊   | 選取 >**編輯**的裝置。 您可以編輯 [裝置名稱]、[使用者資訊]、[資產標記]，以及 [新增記事] 等詳細資料。     |
|管理軟體更新   |選取 >**更新**的裝置。 您可以查看裝置可用的軟體和固件更新清單，並選擇要安裝的更新。    |
|重新開機裝置   |選取 >**重新開機**的裝置。          |
|查看裝置歷程記錄  | 選取裝置 > 歷程**記錄**]。 您可以查看裝置的更新歷程記錄。     |
|[查看] 診斷  | 選取 >**診斷**的裝置。        |

## <a name="use-configuration-profiles-in-teams"></a>在團隊中使用設定檔

使用設定檔來管理貴組織中的小組裝置設定和功能。 您可以建立或上傳設定檔，以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或裝置群組。 

### <a name="create-a-configuration-profile"></a>建立設定檔

::: zone target="docs"

![顯示 Microsoft [小組標誌] 的圖示](media/teams-logo-30x30.png) 使用 Microsoft 團隊 & 商務用 Skype 系統管理中心

1. 在左側導覽中，移至 [**裝置** > **管理裝置**]。

::: zone-end

2. 選取 [**設定檔**]，然後選取 [**新增設定檔**]。
3. 輸入設定檔的名稱，並視需要新增易記的描述。
4. 為設定檔指定您想要的設定，然後按一下 [**儲存**]。

### <a name="assign-a-configuration-profile"></a>指派設定檔

::: zone target="docs"

![顯示 Microsoft [小組標誌] 的圖示](media/teams-logo-30x30.png) 使用 Microsoft 團隊 & 商務用 Skype 系統管理中心

1. 在左側導覽中，移至 [**裝置** > **管理裝置**]。

::: zone-end

2. 選取 [**設定檔**]，然後在 [**指派給**您要指派的設定檔] 底下，按一下連結。  
3. 在 [**將裝置指派給**設定設定檔] 窗格中，搜尋並選取您要指派的裝置。
4. 按一下 [**儲存**]。
