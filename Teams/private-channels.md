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
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
- m365initiative-securecollab
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何使用和管理 Microsoft Teams 中的私人頻道。
ms.openlocfilehash: d1a97d904d61044c693addb364cbafbf4d46b9a3
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198865"
---
# <a name="private-channels-in-microsoft-teams"></a>Microsoft Teams 中的私人頻道

Microsoft Teams 中的私人頻道為小組內的共同作業建立了焦點空間。 只有小組中身為私人頻道的擁有者或成員的使用者，才可以存取頻道。 任何人 (包括來賓) 都可以新增為私人頻道的成員，只要他們已經是小組的成員即可。

如果要將共同作業限制為需要知道的人員，或是在不另外建立小組來管理已指派特定專案小組的情況下，促進小組人員之間的溝通，您可能會想要使用私人頻道。

例如，在下列情況中，私人頻道相當實用：

- 小組中的一群人希望能有個專屬空間能共同作業，而不需建立個別小組。
- 團隊中的一部分人員想要使用私人頻道來討論機密資訊，例如預算、重新採購、策略定位等等。

A lock icon indicates a private channel. Only members of private channels can see and participate in private channels that they are added to.

私人頻道建立之後，會連結到父系小組，且不能移至其他小組。 此外，私人頻道不能轉換成標準頻道，反之亦然。

[比較私人頻道和其他的頻道類型](/microsoftteams/teams-channels-overview#channel-feature-comparison)。

![團隊私人頻道的螢幕擷取畫面。](media/private-channels-in-teams.png)

## <a name="private-channel-creation"></a>私人頻道建立

依預設，任何小組擁有者或小組成員都可以建立私人頻道。 來賓則無法建立。 您可以在小組層級和組織層級管理建立私人頻道的能力。 使用 [原則](teams-policies.md) 來控制組織中的哪些使用者能夠建立私人頻道。 設定好原則之後，小組擁有者就可以在小組的 **[設定]** 索引標籤中，關閉或開啟成員建立私人頻道的能力。

建立私人頻道的人即為私人頻道擁有者，只有私人頻道擁有者可以直接新增或移除頻道中的人員。 私人頻道擁有者可以將任何小組成員新增至他們建立的私人頻道，包括來賓。 私人頻道的成員有安全的交談空間，而且新成員加入之後，他們可以在該私人頻道中查看所有交談 (甚至是舊的交談)。

小組擁有者可以查看其小組中所有私人頻道的名稱，也可以刪除小組中的任何私人頻道。 (已刪除的私人頻道可以在刪除後的30 天內還原。) 小組擁有者無法查看私人頻道中的檔案或私人頻道的交談和成員清單，除非他們是該私人頻道的成員。

小組成員只能查看其已加入的私人頻道。

## <a name="adding-and-removing-owners-and-members"></a>新增和移除擁有者和成員

如果私人頻道擁有者是一或多個私人頻道的最後一位擁有者，則無法透過 Teams 用戶端將其移除。

如果私人頻道擁有者離開貴組織，或是從與小組相關聯的 Microsoft 365 群組中被移除，則會自動將私人頻道的一位成員升級為私人頻道擁有者。

如果小組成員離開或從小組移除，該使用者也會從小組中的所有私人頻道離開或被移除。 如果將使用者新增回小組，則必須將該使用者新增回小組中的私人頻道。

## <a name="channel-owner-settings"></a>頻道擁有者設定

每個私人頻道都有自己的設定，而頻道擁有者可加以管理，包括新增和移除成員、新增索引標籤、以及監視整個頻道的功能。 這些設定與父系小組設定彼此無關。 私人頻道建立時會繼承父系小組的設定，之後，就可以變更其設定，與父系小組設定互不相干。

私人頻道擁有者可以按一下 [管理頻道]，然後使用 [成員] 和 [設定] 索引標籤來新增或移除成員及編輯設定。

![私人頻道設定的螢幕擷取畫面。](media/private-channels-in-teams-channel-settings.png)

## <a name="private-channel-owner-and-member-actions"></a>私人頻道擁有者和成員動作

下表概述擁有者、成員、來賓可在私人頻道中執行哪些動作。

|動作  |小組擁有者|小組成員|小組來賓|私人頻道擁有者|私人頻道成員|私人頻道來賓|
|---------|---------|---------|---------|---------|---------|---------|
|建立私人頻道|系統管理員控制|系統管理員和小組擁有者控制|否|不適用|不適用|不適用|
|刪除私人頻道|是|否|否|是|否|否|
|離開私人頻道|N/A|不適用|不適用|是，除非他們是最後一個擁有者|是|是|
|編輯私人頻道|否|不適用|不適用|是|否|否|
|還原已刪除的私人頻道|是|否|否|是|否|否|
|新增成員|否|不適用|不適用|是|否|否|
|編輯設定|否|不適用|不適用|是|否|否|
|管理索引標籤和應用程式|否|不適用|不適用|是，必須為小組安裝應用程式|頻道擁有者控制|否|

## <a name="private-channel-sharepoint-sites"></a>私人頻道 SharePoint 網站

每個私人頻道都有自己的 SharePoint 網站。 分隔的網站是為了確保僅限私人頻道的成員才可存取私人頻道檔案。 依預設，這些網站會以文件庫建立，且可以透過[網站管理介面](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04)輕鬆地增強為功能完整的網站。 每個網站都在與父系小組的網站相同的地理區域中建立。 這些輕量型網站擁有自訂範本識別碼 "TEAMCHANNEL#0" 或 "TEAMCHANNEL#1"，可讓您透過 PowerShell 和圖形 API 更輕鬆地進行管理。 

> [!NOTE]
> 只有頻道中擁有擁有者或成員許可權的人才能存取共用頻道網站中的內容。 父團隊和系統管理員中的人員無法存取，除非他們也是頻道成員。

私人頻道網站會同步處理資料分類，並繼承父系小組網站中的來賓存取權限。 網站擁有者和成員群組的成員資格，會與 Teams 內私人頻道的成員資格保持同步。 無法透過 SharePoint 獨立管理私人頻道網站的網站權限。 

Teams manages the lifecycle of the private channel site. If the site is deleted outside of Teams, a background job restores the site within four hours as long as the private channel is still active.

如果還原私人頻道或含有私人頻道的小組，則會一併還原網站。 如果私人頻道網站已還原，且超過私人頻道的 30 天虛刪除時機，則網站會以獨立網站的方式運作。

> [!NOTE]
> 在 Microsoft Teams 中建立新小組、私人或共用頻道時，會自動在 SharePoint 中建立小組網站。 若要編輯此小組網站的網站描述或分類，請前往對應頻道的 [Microsoft Teams 中的設定](https://support.microsoft.com/office/change-a-team-s-data-security-classification-in-teams-bf39798f-90d2-44fb-a750-55fa05a56f1d)。
>
> 深入了解如何管理 [Microsoft Teams 連線的小組網站](/SharePoint/teams-connected-sites)。

## <a name="compliance-copies-of-private-channel-messages"></a>私人頻道訊息的合規性複本

在私人頻道中傳送的訊息合規性複本會傳送到所有私人頻道成員的信箱，而不是傳送到群組信箱。 合規性複本的標題會有格式設定，指出寄自哪一個私人頻道。

如需有關以「電子文件探索」搜索私人頻道訊息的詳細資訊，請參閱[私人頻道的電子文件探索](ediscovery-investigation.md#ediscovery-of-private-and-shared-channels)。

## <a name="considerations-around-file-access-in-private-channels"></a>私人頻道檔案存取權的考量

當您在私人頻道中建立新的 OneNote 筆記本時，其他使用者仍然可以存取該筆記本，因為「存取」行為與「和使用者共用私人頻道 SharePoint 網站中任何其他項目」的存取權相同。

如果透過 SharePoint 將私人頻道中筆記本的存取權授予使用者，則從小組或私人頻道中移除該使用者並不會移除該使用者對筆記本的存取權。

如果現有的筆記本是以索引標籤的形式新增到私人頻道，則對私人頻道的存取權不會變更，且筆記本會保留其現有的權限。

## <a name="private-channel-limitations"></a>私人頻道限制

目前，私人頻道支援連接器和索引標籤 (Stream、Planner、Forms 除外)。 我們正致力讓私人頻道支援所有的應用程式，包括傳訊擴充功能和 Bot。

每個小組最多可以有 30 個私人頻道，每個私人頻道最多可以有 250 個成員。 30 個私人頻道限制不計入每個小組 200 個標準頻道的限制。 

當您從現有小組建立小組時，不會複製現有小組中任何的私人頻道。

無法將私人頻道轉換成其他頻道類型。

來自私人頻道的通知不會包含在錯過的活動電子郵件中。

無法排程頻道會議。

## <a name="related-topics"></a>相關主題

[Microsoft Teams 中的共用頻道](/MicrosoftTeams/shared-channels)

[Teams 的小組和頻道概觀](teams-channels-overview.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[使用 Microsoft 圖形 API 搭配 Teams](/graph/api/resources/teams-api-overview)

[頻道資源類型](/graph/api/resources/channel)
