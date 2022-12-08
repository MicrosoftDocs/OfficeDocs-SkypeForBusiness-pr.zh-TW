---
title: Microsoft Teams 的限制和規格
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: 本文說明套用到 Microsoft Teams 的限制、規格和其他需求。
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ae4adf9d803ea0b3482451a9ece5d3ceb0df598
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307528"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams 的限制和規格

本文說明一些套用到 Teams 的限制、規格和其他需求。

## <a name="teams-and-channels"></a>團隊和頻道

|功能    | 最大限制 |
|-----------|---------------|
|一位使用者可以建立的團隊數目 | 受限於 250 的物件限制&sup1;         |
|一位使用者可以加入成為成員的團隊數目|1,000&sup2;|
|一個團隊中的成員數目 | 25,000<sup>6</sup>     |
|每個團隊擁有者人數 | 100   |
|一個租用戶中允許的全組織團隊數目 | 5&sup2;     |
|一個[全組織團隊](create-an-org-wide-team.md)中的成員數目 | 10,000       |
|一位全域系統管理員可以建立的團隊數目        |  500,000   |
|一個 Microsoft 365 或 Office 365 組織可以擁有的團隊數目    | 500,000&sup3;     |
|每個團隊的頻道數目    | 200 (包含已刪除的頻道)<sup>4</sup>        |
|每個團隊的私人頻道數量    |30 (包含已刪除的頻道)<sup>4</sup>        |
|私人頻道中的成員數目    |250|
|可匯入團隊中的通訊群組清單、安全性群組或 Microsoft 365 群組的大小上限    |3,500|
|Microsoft 365 群組中可轉換成團隊的成員數目上限    |10,000<sup>6</sup>     |
|頻道交談貼文大小 | 每篇貼文約 28 KB<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> 此限制包含已封存的團隊。 

<sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.

<sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>5</sup> 28 KB 是大約限制，因為其包含訊息本身 (文字、影像連結等等)、@ 提及、連接器數目和回應。

<sup>6</sup> 來自團隊外部的共用頻道成員會計入此限制。 進一步請注意，團隊/頻道提及在超過 10,000 個成員的團隊中會封鎖。

> [!NOTE]
> 如需共用頻道的限制，請參閱[共用頻道的限制](/MicrosoftTeams/shared-channels#limits-for-shared-channels)。

## <a name="messaging"></a>訊息傳送

### <a name="chat"></a>聊天

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|功能  | 最大限制  |
|---------|---------|
|一個私人聊天中的人員數目<sup>1</sup>  | 250<sup>2</sup> |
|交談視訊或音訊通話中的人員數目 | 20 |
|檔案附件的數目<sup>3</sup>  |10     |
|聊天大小 | 每篇貼文約 28 KB<sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> 如果附件數量超過此限制，您會看見錯誤訊息。

<sup>4</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@-提及和回應。

### <a name="emailing-a-channel"></a>傳送電子郵件到頻道

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|功能  | 最大限制  |
|---------|---------|
|郵件大小<sup>1<sup> | 24 KB |
|檔案附件的數目<sup>2</sup>  |20     |
|每個檔案附件的大小 | 小於 10 MB |
|內嵌影像的數目<sup>2</sup> |50   |

> [!NOTE]
> 您可以傳送至頻道的電子郵件數量有節流限制。 限制是每個使用者、每頻道、每十秒六封電子郵件，每個使用者、每租用戶、每十秒八封電子郵件。
<sup>1</sup> 如果郵件超過此限制，系統會產生預覽郵件，然後要求使用者從提供的連結下載並檢視原始電子郵件。

<sup>2</sup> 如果附件或影像的數目超過此限制，您會看見錯誤訊息。

如需詳細資訊，請參閱 [Exchange Online 限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>頻道名稱

頻道名稱不能包含下列字元或字詞：

|類型|範例|
|---------|---------|
|字元     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|這些範圍內的字元    | 0 至 1F<br>80 至 9F        |
|字詞     | forms、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 至 COM9、LPT1 至 LPT9、desktop.ini、&#95;vti&#95;|

頻道名稱也不能以底線 (_) 或句號 (.) 為開頭，或是以句號 (.) 為結尾。

## <a name="meetings-and-calls"></a>會議和通話

|功能     | 最大限制 |
|------------|---------------|
|一場會議中的人數 (可以交談和通話)  | 1000 位，包含 GCC、GCCH 和 DoD，但不包含 A1 (300)。 **僅檢視** 會允許高達 20,000 名僅限聆聽參與者加入會議，其中的召集人擁有 E3/E5/A3/A5 SKU 以及政府用 (GCC、GCC High、DoD) 的授權。 網路研討會也即將推出僅檢視體驗。 深入了解[僅供檢視體驗](view-only-meeting-experience.md)。<sup>1，2</sup>|
|交談視訊或音訊通話中的人員數目 | 20 |
|PowerPoint 檔案大小的最大值 | 2 GB|
|Teams 會保留[會議記錄](cloud-recording.md)，該記錄不會上傳至 Microsoft Stream，但可供本機下載 | 20 天 |
| 會議錄製長度上限 | 4 小時或 1.5 GB。 達到此限制時，錄製作業將會結束並自動重新啟動。
  
<sup>1</sup> 為了在大型會議、網路研討會和即時活動中獲得最佳體驗，Microsoft 建議使用最新版的 Teams 桌面用戶端或 Teams 行動裝置用戶端。

<sup>2</sup> 大型會議、網路研討會和即時活動中的簡報者應該使用 Teams 桌面用戶端。 如需主持大型會議的更多秘訣，請參閱 [大型 Teams 會議的最佳做法](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)。

> [!NOTE]
> 分組會議室只能在少於 300 名出席者的會議中建立。 此外，在會議中建立分組會議室會自動將會議出席者人數限制為 300 人。 建議使用者不要在預期超過 300 名參與者的會議中初始化分組會議室。 如需大型團隊會議的資訊，請與使用者分享指南 [適用於大型 Teams 會議的最佳做法](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)。

### <a name="meeting-expiration"></a>會議到期

> [!NOTE]
> A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers, CVI coordinates, and/or underlying meeting policies and settings.

|會議類型  |會議將在這些時間後到期  |每次您開始或更新會議，到期時間會延長這麼多時間  |
|---------|---------|---------|
|立即開會     |開始時間 + 8 小時         |不適用         |
|一般 (沒有結束時間)     |開始時間 + 60 天         | 60 天        |
|一般 (有結束時間)     |結束時間 + 60 天         |60 天         |
|週期性 (沒有結束時間)     |開始時間 + 60 天         |60 天         |
|週期性 (有結束時間)     |最後發生的結束時間 + 60 天         |60 天         |

> [!NOTE]
> Microsoft Teams 會議的時間限制為 30 小時。

## <a name="teams-live-events"></a>Teams 即時活動

|功能     | 最大限制 |
|------------|---------------|
|對象數目 | 10,000 位出席者 |
|活動持續時間 | 4 小時 |
|在 Microsoft 365 或 Office 365 組織中並行執行即時活動 <sup>1</sup> | 15 |

<sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.

如需即時活動的詳細資訊，請移至 [Teams 即時活動](teams-live-events/plan-for-teams-live-events.md#teams-live-events)。 請參閱[排程 Teams 即時活動](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。

> [!IMPORTANT]
> **Microsoft 365 即時活動限制增加**
>
> **為了繼續支援客戶的需求，我們會將即時活動的暫時限制延長至 2023 年 6 月 30 日，包括：**
>
>- 活動支援最多達 20000 個出席者
>- 不同租用戶可以同時進行 50 個活動
>- 每個廣播的活動持續時間 (16 小時)
>
> Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>在 Outlook 中的顯示狀態

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).

## <a name="storage"></a>儲存空間

Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

> [!NOTE]
> 每個[私人頻道](./private-channels.md)都有自己的 SharePoint 網站 (先前稱之為 “網站集合)。

If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)

Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.

|功能                 |Microsoft 365 商務基本版  |Microsoft 365 商務標準版   |Office 365 企業版 E1  |Office 365 企業版 E3  |Office 365 企業版 E5  |Office 365 企業版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|儲存空間                 |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB，加上每個購買授權 10 GB   |每個組織 1 TB，加上每個購買授權 10 GB |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB            |
|Teams 檔案的儲存空間 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |
|檔案上傳限制 (每個檔案)    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |

頻道可由針對團隊建立的 SharePoint Online 網站 (先前稱之為 "網站集合”) 內的資料夾進行備份，因此 [頻道] 內的檔案索引標籤會共用所屬團隊的儲存空間限制。

如需詳細資訊，請參閱 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

## <a name="class-teams"></a>班級團隊

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

班級團隊是一個範本類型，其中包含其他應用程式，且具有的限制與團隊成員數目不同。

> [!NOTE]
> 使用班級團隊需要 [Office 365 教育版授權](https://www.microsoft.com/education/products/office)。

下表列出班級團隊的限制：

|功能  |最大限制  |
|---------|---------|
|一個團隊中的成員數目    | 請參閱本文的 [Teams 和頻道](#teams-and-channels)一節        |
|班級團隊中要使用作業的成員數目    | 300        |
|班級團隊中要使用 OneNote 課程筆記本的成員數目     |300         |

A class team can support more than 300 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.

## <a name="tags"></a>標籤

|功能  |最大限制  |
|---------|---------|
|每個團隊的標記數量    | 100        |
|每個團隊的建議預設標記數量    | 25        |
|指派給標記的團隊成員人數    |200         |
|每個團隊指派給使用者的標記數量    |25         |

## <a name="contacts"></a>連絡人

Teams 使用下列連絡人：

- 您組織 Active Directory 中的連絡人
- 新增至使用者 Outlook 預設資料夾的連絡人

Teams 使用者可以與您組織 Active Directory 中的任何人通訊，可以將您組織 Active Directory 中的任何人新增為連絡人以及新增至連絡人清單，方法是前往 [聊天] > [連絡人] 或是 [通話] > [連絡人]。

Teams 使用者也可以將不在您組織 Active Directory 中的人員新增為連絡人，方法是前往 [通話] > [連絡人]。

## <a name="browsers"></a>瀏覽器

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>作業系統

如需作業系統需求的相關資訊，請參閱[取得 Microsoft Teams 用戶端](get-clients.md)。
