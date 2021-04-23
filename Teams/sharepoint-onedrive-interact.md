---
title: SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online &商務用 OneDrive 與 Teams 互動;私人聊天檔案儲存&小組、標準頻道、&文件庫之間的互動。
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948621"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動

> [!Tip]
> 觀看以下工作階段以了解 Teams 如何與 Azure Active Directory (AAD)、Microsoft 365 群組、Exchange、SharePoint 和商務用 OneDrive 進行互動：[Microsoft Teams 的基礎](https://aka.ms/teams-foundations)

Microsoft Teams 中的每個團隊在 SharePoint Online 中都有一個小組網站，團隊中的每個標準頻道會獲得預設小組網站文件庫中的資料夾。 在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。 若要在 SharePoint 中查看變更網站位址的影響，請閱讀 [變更網站位址](/sharepoint/change-site-address)。

> [!NOTE]
> 本文僅適用于標準頻道。 私人頻道的架構與標準通道不同。 每個私人頻道都有自己的 SharePoint 網站集合，與父小組網站分開。 若要深入瞭解，請參閱 [Microsoft Teams 中的私人頻道](private-channels.md)。

私人聊天檔案會儲存在寄件者的商務用 OneDrive 資料夾中，並會在檔案共用過程中自動授予所有參與者許可權。

若使用者並非以 SharePoint Online 進行指派及授權，他們將無法使用 Microsoft 365 或 Office 365 中的 [商務用 OneDrive] 儲存空間。 檔案共用會繼續在標準頻道中使用，但若沒有 Microsoft 365 或 Office 365 中的商務用 OneDrive 儲存空間，使用者將無法在聊天中共用檔案。

透過將檔案儲存在 SharePoint Online 文件庫和 OneDrive for Business，您將遵守所有在租用戶層級設定的合規性規則  

> [!NOTE]
> Microsoft Teams 目前不支援與 SharePoint 內部部署整合。

以下是小組、標準頻道和文件庫之間關係範例。

針對每個小組，會建立 SharePoint 網站，而 **共用檔** 資料夾是團隊建立的預設資料夾。 每個標準頻道 ，包括一般 (每個團隊的預設頻道) 共用 **檔中的資料夾**。

![SharePoint Online 中共用文件資料夾的圖表。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> 目前無法將預設的 SharePoint 網站和文件庫取代為另一個網站和文件庫。 我們聽到您要求，我們正在考慮。 查看 [Teams 藍圖](https://aka.ms/teamsroadmap) 或 [Teams UserVoice，](https://aka.ms/TeamsUserVoice) 以隨時瞭解即將推出的功能。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> 若要新增連結至現有 SharePoint 網站頁面或現有 SharePoint 文件庫的小組的 Tab：
> 1. 選取定位停駐點旁的加號。
> 2. 選取 **現有 SharePoint** 網站頁面的 SharePoint或現有文件庫的文件庫。
> 3. 選取適當的頁面或文件庫。

針對每個使用者，Microsoft **Teams** 聊天檔案的 OneDrive 資料夾會用來儲存在私人聊天中與其他使用者共用的所有檔案 (1：1 或 1：) ，並自動將許可權配置為僅限制預定使用者的存取權。

![名為 Microsoft Teams 聊天檔案的 OneDrive 資料夾圖表](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

請注意，對於公用團隊，SharePoint 小組網站會布備「外部使用者以外的所有人」存取權。 對於不是該團隊成員的人，公用團隊不會顯示在 Teams 中。 不過，他們可以使用 SharePoint 小組網站的 URL 存取 SharePoint 小組網站上的內容。 

## <a name="channel-files-tab"></a>頻道檔案選項卡

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

Teams **中的** 檔案選項卡與 SharePoint 檔視圖非常類似。 在檔案 **選項卡** 上，使用者可以：

- 請參閱新增檔案功能表中 **的其他** 選項。
- 將檔案同步處理至其本地磁碟機。
- 在所有 **檔功能表** 上，從清單視圖切換到 **壓縮清單** 至 **磚** 視圖。
- 識別需要注意或具有惡意攻擊的檔案。
- 立即查看檔案是唯讀還是已簽出。
- 簽出並簽入檔案。
- 釘選、取消釘選及變更檔案的排序次序。
- 識別哪些檔案需要中繼資料
- 選擇更多篩選選項。
- 根據欄標題將檔案分組。
- 修改欄設定 (向左或向右移動、隱藏) 欄寬。

## <a name="default-link-type-setting"></a>預設連結類型設定

SharePoint 和 OneDrive 具有系統管理員設定，可指定為檔案建立的連結的預設連結類型。 Teams 會採用相同的方法，方法是重新使用系統管理員為 SharePoint 和 OneDrive 所設定。 有關此方法的詳細資訊，請參閱當使用者取得共用連結時變更[預設連結類型。](/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>詳細資訊

有關 SharePoint 如何與 Teams 合作之詳細資訊，請參閱 [SharePoint 和 Teams：更好在一起](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。

若要深入瞭解 Teams 中的來賓體驗，請閱讀來賓 [體驗是什麼](guest-experience.md)。