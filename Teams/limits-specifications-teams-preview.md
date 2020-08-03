---
title: Microsoft Teams 的限制和規格
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 本文說明套用到 Microsoft Teams 的限制、規格和其他需求。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 7138495b3f210a7c10b61b7bb8dc1287afefb71c
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522906"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams 的限制和規格

本文說明一些套用到 Teams 的限制、規格和其他需求。

## <a name="teams-and-channels"></a>團隊和頻道

|功能    | 最大限制 |
|-----------|---------------|
|一位使用者可以建立的團隊數目 | 受限於 250 的物件限制&sup1;         |
|一位使用者可以加入成為成員的團隊數目|1,000|
|一個團隊中的成員數目 | 10,000       |
|每個團隊擁有者人數 | 100   |
|一個租用戶中允許的全組織小組數目 | 5     |
|一個[全組織小組](create-an-org-wide-team.md)中的成員數目 | 5,000       |
|一位全域系統管理員可以建立的團隊數目        |  500,000   |
|一個 Microsoft 365 或 Office 365 組織可以擁有的團隊數目    | 500,000&sup2;     |
|每個團隊的頻道數目    | 200 (包含已刪除的頻道)&sup3;         |
|每個團隊的私人頻道數量    |30|
|私人頻道中的成員數目    |250|
|頻道交談貼文大小 | 每篇貼文約 28 KB<sup>4</sup> |

<sup>1</sup>Azure Active Directory 中的任何目錄物件都會計入此限制。 全域系統管理員不受此限制，使用[應用程式權限](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的應用程式也不受此限制。

<sup>2</sup>此限制包含已封存的團隊。

<sup>3</sup>已刪除的頻道可以在 30 天內還原。 在這 30 天內，已刪除的頻道會持續計入每個團隊 200 個頻道的限制。 30 天後，已刪除的頻道及其內容會永久刪除，該頻道不再計入每個團隊 200 個頻道的限制。

<sup>4</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及、連接器數目和回應。

## <a name="messaging"></a>訊息傳送

### <a name="chat"></a>聊天

參與屬於 Teams 中聊天清單之交談的使用者必須擁有 Exchange Online (雲端式) 信箱，系統管理員才能搜尋聊天交談。 這是因為屬於聊天清單之交談會儲存在聊天參與者的雲端式信箱中。 如果聊天參與者沒有 Exchange Online 信箱，系統管理員將無法搜尋或保留聊天交談。 例如，在 Exchange 混合式部署中，具有內部部署信箱的使用者可能可以參與屬於 Teams 中聊天清單之交談。 然而，在此情況下，因為使用者沒有雲端式信箱，這些交談中的內容將無法搜尋也無法保留  (如需詳細資訊，請參閱 [Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md))。

Teams 的聊天是在 Microsoft Exchange 後端執行，因此 Exchange 的傳訊限制會套用到 Teams 中的聊天功能。

|功能  | 最大限制  |
|---------|---------|
|一個私人聊天中的人員數目<sup>1</sup>  | 250<br><br>**附註：** 針對政府用 Teams (GCC、GCC、DoD)，其限制仍為 100。 當政府用雲端限制從 100 增加至 250，我們就會更新本文章。    |
|交談視訊或音訊通話中的人員數目 | 20 |
|檔案附件的數目<sup>2</sup>  |10     |
|聊天大小 | 每篇貼文約 28 KB<sup>3</sup> |

<sup>1</sup> 如果一個聊天超過 20 個人，以下的聊天功能會關閉：Outlook 自動回覆和 Teams 狀態訊息、輸入指示器、視訊和音訊通話、共用、讀取回條。 當私人群組聊天包含超過 20 個成員時，也會移除 [設定傳遞選項] 按鈕 (!)。

<sup>2</sup> 如果附件數目超過此限制，您會看見錯誤訊息。

<sup>3</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@ 提及和回應。

### <a name="emailing-a-channel"></a>傳送電子郵件到頻道

 如果使用者想要將電子郵件傳送到 Teams 中的頻道，使用者可以使用頻道的電子郵件地址。 當電子郵件屬於頻道時，任何人都可以回覆電子郵件以開始交談。 以下是一些傳送電子郵件到頻道時適用的限制。

|功能  | 最大限制  |
|---------|---------|
|郵件大小<sup>1<sup> | 24 KB |
|檔案附件的數目<sup>2</sup>  |20     |
|每個檔案附件的大小 | 小於 10 MB |
|內嵌影像的數目<sup>2</sup> |50   |

<sup>1</sup> 如果郵件超過此限制，系統會產生預覽郵件，然後要求使用者從提供的連結下載並檢視原始電子郵件。

<sup>2</sup> 如果附件或影像的數目超過此限制，您會看見錯誤訊息。

如需詳細資訊，請參閱 [Exchange Online 限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。

> [!NOTE]
> 所有 Microsoft 365 和 Office 365 授權的郵件大小、檔案附件和內嵌影像的限制都相同。

## <a name="channel-names"></a>頻道名稱

頻道名稱不能包含下列字元或字詞。

|||
|---------|---------|
|字元     | ~ # % & * { } + / \ : < > ? &#124; ' " , .        |
|這些範圍內的字元    | 0 至 1F<br>80 至 9F        |
|字詞     | forms、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 至 COM9、LPT1 至 LPT9、desktop.ini、&#95;vti&#95;|

頻道名稱也不能以底線 (_) 或句號 (.) 為開頭，或是以句號 (.) 為結尾。

## <a name="meetings-and-calls"></a>會議和通話

|功能     | 最大限制 |
|------------|---------------|
|一場會議中的人數 (可以交談和通話)  |300. **僅限查看** 允許高達 20,000 名 [僅限傾聽] 參與者加入會議，其中召集人擁有進階通訊附加元件 SKU 的授權。<sup>1</sup> [!INCLUDE [template](includes/preview-feature.md)] <br><br>**附註：** 針對政府用 Teams (GCC、GCC、DoD)，其限制仍為 250。 當政府用雲端限制從 250 增加至 300 並支援會議溢出時，我們就會更新本文章。   |
|一場會議中的人數 (可以交談和通話)  | 300 |
|交談視訊或音訊通話中的人員數目 | 20 |
|PowerPoint 檔案大小的最大值 | 2 GB|
|Teams 會保留[會議記錄](cloud-recording.md)，該記錄不會上傳至 Microsoft Stream，但可供本機下載 | 20 天 |

<sup>1</sup> [預設值] 為開啟。 您可以使用 PowerShell 停用會議溢出。 
```powershell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```
如果會議中不再具有僅限查看功能，或出席者沒有根據設定的 [會議室原則] 或 [選項] 的權限可以略過 [會議室] 的話，則 [僅限查看] 出席者將無法加入會議。 [僅限查看] 參與者將無法查看本機 PPT 共用檔案。

### <a name="meeting-expiration"></a>會議到期

|會議類型  |會議將在這些時間後到期  |每次您開始或更新會議，到期時間會延長這麼多時間  |
|---------|---------|---------|
|立即開會     |開始時間 + 8 小時         |不適用         |
|一般 (沒有結束時間)     |開始時間 + 60 天         | 60 天        |
|一般 (有結束時間)     |結束時間 + 60 天         |60 天         |
|週期性 (沒有結束時間)     |開始時間 + 60 天         |60 天         |
|週期性 (有結束時間)     |最後發生的結束時間 + 60 天         |60 天         |

> [!NOTE]
> Microsoft Teams s會議的時間限制為 24 小時。

## <a name="teams-live-events"></a>Teams 即時活動

|功能     | 最大限制 |
|------------|---------------|
|對象數目 | 10,000 位出席者 |
|活動持續時間 | 4 小時 |
|一個 Microsoft 365 或 Office 365 組織中執行的並行即時活動 <sup>1</sup> | 15 |

<sup>1</sup> 您可根據自己的需求排定許多即時活動，但一次只能執行 15 個。 製作人一加入即時活動，就表示該活動執行中。 嘗試加入第 16 個即時活動的製作人會收到錯誤。

如需更多有關即時活動以及 Teams 即時活動與 Skype 會議廣播的比較詳細資訊，請參閱 [Teams 即時活動和 Skype 會議廣播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast) (英文)。

> [!IMPORTANT]
> **Microsoft 365 的即時活動限制增加**
>
> 為了協助客戶滿足迅速變化的通訊需求，Microsoft 365 即時活動將針對於 Teams 中進行的即時活動暫時提高預設限制，直到 2020 年 10 月 1 日止。 已提高以下限制：
>
> - 出席者限制：活動最多可支援 20,000 位出席者
> - 同時活動：不同租用戶可以同時進行 50 個活動
> - 活動持續時間：每個廣播的活動長度已增加為 16 小時

## <a name="presence-in-outlook"></a>在 Outlook 中的目前狀態

Outlook 2013 傳統型應用程式和更新版本支援在 Outlook 中的 Teams 目前狀態。 若要深入瞭解 Teams 中的目前狀態，請參閱 [Teams 中的使用者目前狀態](presence-admins.md)。

## <a name="storage"></a>儲存空間

Microsoft Teams 中的每個團隊在 SharePoint Online 中都有一個團隊網站，團隊中的每個頻道在預設團隊網站的文件庫中都有一個資料夾。 在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。

> [!NOTE]
> 每個[私人頻道](https://docs.microsoft.com/microsoftteams/private-channels) 都有自己的 SharePoint 網站集合。

如果您未在您的租用戶中啟用 SharePoint Online，Microsoft Teams 使用者一律無法在團隊中共用檔案。 在私人聊天中的使用者也無法共用檔案，因為該功能需要有 OneDrive for Business (綁定至 SharePoint 授權)。

透過將檔案儲存在 SharePoint Online 文件庫和 OneDrive for Business，您將遵守所有在租用戶層級設定的合規性規則  (如需詳細資訊，請參閱 [ Sharepoint 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md))。

由於 Teams 是在 SharePoint Online 後端執行檔案共用，因此 SharePoint 的限制會套用到團隊內的 [檔案] 區段。 以下是 SharePoint Online 適用的儲存空間限制。

|功能                 |Microsoft 365 商務基本版  |Microsoft 365 商務標準版   |Office 365 Enterprise E1  |Office 365 企業版 E3  |Office 365 企業版 E5  |Office 365 企業版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|儲存空間                 |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB，加上每個購買授權 10 GB   |每個組織 1 TB，加上每個購買授權 10 GB |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB            |
|Teams 檔案的儲存空間 |每個網站集合或群組最多 25 TB。 |每個網站集合或群組最多 25 TB。 |每個網站集合或群組最多 25 TB。 |每個網站集合或群組最多 25 TB。 |每個網站集合或群組最多 25 TB。 |每個網站集合或群組最多 25 TB。 |
|檔案上傳限制 (每個檔案)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

頻道受資料夾所支援，而資料夾位於針對團隊建立的 SharePoint Online 網站集合中，因此頻道內的檔案索引標籤會共用所屬團隊的儲存空間限制。

如需詳細資訊，請參閱 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

## <a name="tags"></a>標記

|功能  |最大限制  |
|---------|---------|
|每個小組的標記數量    | 100        |
|每個小組的建議預設標記數量    | 25        |
|指派給標記的小組成員人數    |100         |
|指派給使用者的標記數量    |25         |

## <a name="contacts"></a>連絡人

Teams 使用下列連絡人：

- 您組織 Active Directory 中的連絡人
- 新增至使用者 Outlook 預設資料夾的連絡人

Teams 使用者可以與您組織 Active Directory 中的任何人通訊，可以將您組織 Active Directory 中的任何人新增為連絡人以及新增至連絡人清單，方法是前往 [聊天]**** > [連絡人]**** 或是 [通話]**** > [連絡人]****。

Teams 使用者也可以將不在您組織 Active Directory 中的人員新增為連絡人，方法是前往 [通話]**** > [連絡人]****。

## <a name="browsers"></a>瀏覽器

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>作業系統

如需作業系統需求的相關資訊，請參閱[取得 Microsoft Teams 用戶端](get-clients.md)。
