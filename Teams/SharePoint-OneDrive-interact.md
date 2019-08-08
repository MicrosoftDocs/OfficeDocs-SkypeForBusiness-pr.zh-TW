---
title: SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: 瞭解 SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式, 例如私人聊天檔案的儲存方式, 以及團隊、頻道與文件庫之間的關聯性。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28a4a968fc9e478c3a13fb38acd1019221b5dcb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233021"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式

> [!Tip]
> 請觀看下列會話, 瞭解團隊與 Azure Active Directory (AAD)、Office 365 群組、Exchange、SharePoint 和商務用 OneDrive 的互動方式: [Microsoft 團隊的基礎](https://aka.ms/teams-foundations)

Microsoft 團隊中的每個小組在 SharePoint Online 中都有小組網站, 小組中的每個頻道都在預設的小組網站文件庫中取得一個資料夾。 在交談中共用的檔案會自動新增至文件庫, SharePoint 中設定的許可權和檔案安全性選項會自動反映在小組中。

私人聊天檔案會儲存在寄件者的商務用 OneDrive 資料夾中, 而許可權會自動授與所有參與者, 做為檔案共用程式的一部分。

如果使用者未使用 SharePoint Online 授權指派及啟用, 他們在 Office 365 中就沒有商務用 OneDrive 儲存空間。 檔案共用功能會繼續在頻道中運作, 但是使用者無法在 Office 365 中的商務用 OneDrive 儲存空間中共用檔案。

透過將檔案儲存在 SharePoint Online 文件庫和商務用 OneDrive 中, 就會遵循在租使用者層級設定的所有合規性規則。 

> [!NOTE]
> 目前 Microsoft 團隊不支援與 SharePoint 內部部署的整合。

下列是團隊、頻道與文件庫之間的關聯性範例。

針對每個小組, 都會建立一個 SharePoint 網站, 而 [**共用文件**] 資料夾則是為該小組建立的預設資料夾。 每個頻道, 包括**一般**頻道 (每個小組的預設頻道) 在 [**共用檔**] 中都有一個資料夾。

![SharePoint Online 中的 [共用文件] 資料夾圖表。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 目前無法將預設的 SharePoint 網站與文件庫取代為其他人。 我們已聽取您想要的內容, 我們正在考慮。 檢查 [[團隊藍圖](https://aka.ms/teamsroadmap)] 或 [[團隊 UserVoice](https://aka.ms/TeamsUserVoice) ], 掌握即將推出的功能。

> [!TIP]
> 若要將索引標籤新增至您的小組, 以連結至現有的 SharePoint 網站頁面或現有的 SharePoint 文件庫:
> 1. 選取索引標籤旁的加號。
> 2. 針對現有的文件庫, 選取任一**sharepoint**的現有 sharepoint 網站頁面或**文件庫**。
> 3. 選取適當的頁面或文件庫。

針對每位使用者, **Microsoft 團隊聊天**檔案是用來儲存在私人聊天中與其他使用者共用的所有檔案 (1:1 或 1: 許多), 並自動設定許可權, 以限制只有預定使用者才能存取。

![名為 Microsoft 團隊聊天檔案的 OneDrive 資料夾圖表](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>[頻道檔案] 索引標籤

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

團隊中的 [檔案] 索引標籤會與 [SharePoint**檔**] 視圖密切類似。 在 [ **** 檔案] 索引標籤上, 使用者可以:

- 請參閱 [**新增**檔案] 功能表中的其他選項。
- 將檔案同步處理到其本機磁片磁碟機。
- 在 [**所有檔**] 功能表上, 從 [**清單**] 視圖切換至 [將**清單壓縮**至 [**磚**] 視圖。
- 找出需要注意或有惡意程式碼的檔案。
- 立即查看檔案是唯讀或取出。
- 取出和存回檔案。
- 釘選、解除固定及變更檔的排序次序。
- 找出需要中繼資料的檔案
- 從許多其他篩選選項中進行選擇。
- 根據欄標題來分組檔案。
- 修改欄設定 (向左或向右移動、隱藏) 和欄寬。

## <a name="default-link-type-setting"></a>預設連結類型設定

SharePoint 和 OneDrive 擁有管理員設定, 可指定為檔案建立之連結的預設連結類型。 團隊會重複使用系統管理員針對 SharePoint 和 OneDrive 設定的設定, 採用相同的方法。 如需有關此方法的詳細資訊,[請參閱變更使用者取得共用連結時的預設連結類型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。 

## <a name="more-information"></a>其他資訊

如需 SharePoint 與團隊搭配運作方式的詳細資訊, 請參閱[sharepoint 與團隊: 更好搭配](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)使用。

若要深入瞭解團隊中的來賓體驗, 請閱讀[來賓體驗](guest-experience.md)。

