---
title: Microsoft Teams 中的私人頻道
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft Teams 中的私人頻道。
ms.openlocfilehash: 51768d35f70f0008d5d8a2ad7cccb213de9dcc3c
ms.sourcegitcommit: e55d1623e686db2b183e02052bfe10a0269abb5d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2021
ms.locfileid: "51397566"
---
# <a name="private-channels-in-microsoft-teams"></a>Microsoft Teams 中的私人頻道

Microsoft Teams 中的私人頻道為小組內的共同作業建立了焦點空間。 只有小組中身為私人頻道的擁有者或成員的使用者，才可以存取頻道。 任何人 (包括來賓) 都可以新增為私人頻道的成員，只要他們已經是小組的成員即可。

如果要將共同作業限制為需要知道的人員，或是在不另外建立小組來管理已指派特定專案小組的情況下，促進小組人員之間的溝通，您可能會想要使用私人頻道。

例如，在下列情況中，私人頻道相當實用：

- 小組中的一群人希望能有個專屬空間能共同作業，而不需建立個別小組。
- 小組中的一小群人希望使用私人頻道來討論機密資訊，例如預算、資源、戰略定位等。

鎖定圖示表示私人頻道。 只有私人頻道的成員才能查看以及參與他們所加入的私人頻道。

私人頻道建立之後，會連結到父系小組，且不能移至其他小組。 此外，私人頻道不能轉換成標準頻道，反之亦然。

![螢幕擷取畫面：小組中的私人頻道](media/private-channels-in-teams.png)

## <a name="private-channel-creation"></a>私人頻道建立

依預設，任何小組擁有者或小組成員都可以建立私人頻道。 來賓則無法建立。 您可以在小組層級和組織層級管理建立私人頻道的能力。 使用 [策略](teams-policies.md) 來控制組織中哪些使用者可以建立私人頻道。 設定好政策後，團隊擁有者可以在團隊的設定選項卡中關閉或開啟成員建立私人頻道的能力。 

建立私人頻道的人即為私人頻道擁有者，只有私人頻道擁有者可以直接新增或移除頻道中的人員。 私人頻道擁有者可以將任何小組成員新增至他們建立的私人頻道，包括來賓。 私人頻道的成員有安全的交談空間，而且新成員加入之後，他們可以在該私人頻道中查看所有交談 (甚至是舊的交談)。

小組擁有者可以查看其小組中所有私人頻道的名稱，也可以刪除小組中的任何私人頻道。 (已刪除的私人頻道可以在刪除後的30 天內還原。) 小組擁有者無法查看私人頻道中的檔案或私人頻道的交談和成員清單，除非他們是該私人頻道的成員。

小組成員只能看到已新增到的私人頻道。

## <a name="adding-and-removing-owners-and-members"></a>新增和移除擁有者和成員

如果私人頻道擁有者是一或多個私人頻道的最後一位擁有者，則無法透過 Teams 用戶端將其移除。

如果私人頻道擁有者離開貴組織，或移除與小組相關聯的 Microsoft 365 群組，則私人頻道的成員會自動升級為私人頻道擁有者。

如果小組成員離開或從小組移除，該使用者也會從小組中的所有私人頻道離開或被移除。 如果將使用者新增回小組，則必須將該使用者新增回小組中的私人頻道。

## <a name="channel-owner-settings"></a>頻道擁有者設定

每個私人頻道都有自己的設定，頻道擁有者可以管理，包括新增和移除成員、新增@mentioning整個頻道的功能。 這些設定與父系小組設定彼此無關。 私人頻道建立時會繼承父系小組的設定，之後，就可以變更其設定，與父系小組設定互不相干。

私人頻道擁有者可以按一下 [管理頻道]，然後使用 [成員] 和 [設定] 索引標籤來新增或移除成員及編輯設定。

![螢幕擷取畫面：私人頻道設定](media/private-channels-in-teams-channel-settings.png)

## <a name="private-channel-owner-and-member-actions"></a>私人頻道擁有者和成員動作

下表概述擁有者、成員、來賓可在私人頻道中執行哪些動作。

|動作  |小組擁有者|小組成員|小組來賓|私人頻道擁有者|私人頻道成員|私人頻道來賓|
|---------|---------|---------|---------|---------|---------|---------|
|建立私人頻道|系統管理控制|系統管理與團隊擁有者控制|否|不適用|不適用|N/A|
|刪除私人頻道|是|否|否|是|否|否|
|離開私人頻道|N/A|不適用|不適用|是，除非他們是最後一個擁有者|是|是|
|編輯私人頻道|否|不適用|不適用|是|否|否|
|還原已刪除的私人頻道|是|否|否|是|否|否|
|新增成員|否|不適用|不適用|是|否|否|
|編輯設定|否|不適用|不適用|是|否|否|
|管理索引標籤和應用程式|否|不適用|不適用|是，團隊必須安裝應用程式|頻道擁有者控制|否|

## <a name="manage-the-lifecycle-of-private-channels"></a>管理私人頻道的生命週期

請參閱 [在 Teams 中](private-channels-life-cycle-management.md) 管理私人頻道的生命週期，以瞭解如何管理貴組織中私人頻道的生命週期。 這包括如何控制貴組織的使用者是否能夠建立私人頻道、如何代表小組擁有者建立私人頻道、如何取得所有私人頻道訊息的清單以進行封存和稽核之用，以及其他管理工作。  

## <a name="private-channel-sharepoint-sites"></a>私人頻道 SharePoint 網站

每個私人頻道都有自己的 SharePoint 網站。 另一個網站是為了確保只能存取私人頻道中的成員，才能存取私人頻道檔案。 這些網站預設是使用文件庫建立，而且能透過網站管理介面輕鬆增強為 [功能完整的網站](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04)。 每個網站都是在同一個地理區域中建立，與父團隊的網站相同。 這些輕量型網站擁有自訂範本識別碼 TEAMCHANNEL#0，可讓您透過 PowerShell 和圖形 API 更輕鬆地進行管理。

私人頻道網站會同步處理資料分類，並繼承父小組網站的來賓存取許可權。 網站擁有者和成員群組的成員資格會與 Teams 中私人頻道的成員資格保持同步。 對 SharePoint 中擁有者或成員群組成員資格的任何變更，都會在 4 小時內自動還原為私人頻道成員資格。 在特定使用者需要存取文件而不需要存取私人頻道訊息的情況下，請將他們新增至網站上的 [訪客] 群組，或新增至與擁有者和成員不同的新群組。

Teams 會管理私人頻道網站的生命週期。 如果網站在 Teams 外部刪除，只要私人頻道仍在使用中，背景工作會于四小時內還原網站。 如果網站已永久刪除，系統將會為私人頻道提供新網站。

如果私人頻道或包含私人頻道的團隊已還原，網站會隨它還原。 如果私人頻道網站已還原，且超出私人頻道的 30 天虛刪除視窗，該網站會以獨立網站方式運作。

## <a name="private-channel-message-compliance-records"></a>私人頻道訊息合規性記錄

在私人頻道中傳送的訊息記錄會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。 記錄的標題會有格式設定，指出寄自哪一個私人頻道。

如需有關以「電子文件探索」搜索私人頻道訊息的詳細資訊，請參閱[私人頻道的電子文件探索](ediscovery-investigation.md#ediscovery-of-private-channels)。

## <a name="considerations-around-file-access-in-private-channels"></a>私人頻道中檔案存取的考慮

當您在私人頻道中建立新的 OneNote 筆記本時，其他使用者仍然可以存取該筆記本，因為「存取」行為與「和使用者共用私人頻道 SharePoint 網站中任何其他項目」的存取權相同。

如果透過 SharePoint 將私人頻道中筆記本的存取權授予使用者，則從小組或私人頻道中移除該使用者並不會移除該使用者對筆記本的存取權。

如果現有筆記本新增為私人頻道的定位停駐點，則私人頻道的存取權不會變更，而且筆記本會保留其現有許可權。

## <a name="private-channel-limitations"></a>私人頻道限制

目前，私人頻道支援連接器和索引標籤 (Stream、Planner、Forms 除外)。 我們正致力讓私人頻道支援所有的應用程式，包括傳訊擴充功能和 Bot。

每個小組最多可以有 30 個私人頻道，每個私人頻道最多可以有 250 個成員。 30 個私人頻道限制不計入每個小組 200 個標準頻道的限制。 

當您從現有團隊建立團隊時，不會複製現有團隊中任何私人頻道。

目前未接活動電子郵件中不會包含來自私人頻道的通知。

## <a name="related-topics"></a>相關主題

[Teams 的小組和頻道概觀](teams-channels-overview.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[使用 Microsoft 圖形 API 搭配 Teams](/graph/api/resources/teams-api-overview)
