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
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2d31474233057d930ccdbc0bdfea27262cc5dc04
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046002"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams 的限制和規格

本文說明一些套用到 Teams 的限制、規格和其他需求。

## <a name="teams-and-channels"></a>小組和頻道

|功能    | 最大限制 |
|-----------|---------------|
|一位使用者可以建立的小組數目 | 受限於 250 的物件限制&sup1;         |
|一位使用者可以加入成為成員的團隊數目|1,000&sup2;|
|一個小組中的成員數目 | 25,000<sup>6</sup>     |
|每個小組擁有者人數 | 100   |
|一個租用戶中允許的全組織小組數目 | 5&sup2;     |
|一個[全組織小組](create-an-org-wide-team.md)中的成員數目 | 10,000       |
|一位全域系統管理員可以建立的小組數目        |  500,000   |
|一個 Microsoft 365 或 Office 365 組織可以擁有的小組數目    | 500,000&sup3;     |
|每個小組的頻道數目    | 200 (包含已刪除的頻道)<sup>4</sup>        |
|每個小組的私人頻道數量    |30 (包含已刪除的頻道)<sup>4</sup>        |
|私人頻道中的成員數目    |250|
|可匯入小組中的通訊群組清單、安全性群組或 Microsoft 365 群組的大小上限    |3,500|
|Microsoft 365 群組中可轉換成小組的成員數目上限    |10,000<sup>6</sup>     |
|頻道交談貼文大小 | 每篇貼文約 28 KB<sup>5</sup> |

<sup>1</sup> Azure Active Directory 中的任何目錄物件都會計入此限制。全域系統管理員會從此限制豁免，使用[應用程式權限](/graph/permissions-reference)呼叫 Microsoft Graph 的應用程式亦然。

<sup>2</sup> 此限制包含已封存的小組。 

<sup>3</sup> 若要進一步增加小組數目，您必須與 Microsoft 支援服務連絡，並要求進一步增加您的租用戶中 Azure Active Directory 物件的數量。增加只能針對實際生產案例執行。

<sup>4</sup> 已刪除的頻道可以在 30 天內還原。在這 30 天內，已刪除的頻道會持續計入每個小組 200 個頻道或 30 個私人頻道的限制。30 天後，已刪除的頻道及其內容會永久刪除，且該頻道不再會計入每個小組頻道的限制。

<sup>5</sup> 28 KB 是大約限制，因為其包含訊息本身 (文字、影像連結等等)、@ 提及、連接器數目和回應。

<sup>6</sup> 來自團隊外部的共用頻道成員會計入此限制。 進一步請注意，團隊/頻道提及在超過 10,000 個成員的小組中會封鎖。

> [!NOTE]
> 如需共用頻道的限制，請參閱[共用頻道的限制](/MicrosoftTeams/shared-channels#limits-for-shared-channels)。

## <a name="messaging"></a>訊息傳送

### <a name="chat"></a>聊天

參與屬於 Teams 中聊天清單之交談的使用者必須擁有 Exchange Online (雲端式) 信箱，系統管理員才能搜尋聊天交談。這是因為屬於聊天清單之交談會儲存在聊天參與者的雲端式信箱中。如果聊天參與者沒有 Exchange Online 信箱，系統管理員將無法搜尋或保留聊天交談。例如，在 Exchange 混合式部署中，具有內部部署信箱的使用者可能可以參與屬於 Teams 中聊天清單之交談。然而，在此情況下，因為使用者沒有雲端式信箱，這些交談中的內容將無法搜尋也無法保留。(如需詳細資訊，請參閱 [Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)。)


|功能  | 最大限制  |
|---------|---------|
|一個私人聊天中的人員數目<sup>1</sup>  | 250<sup>2</sup> |
|交談視訊或音訊通話中的人員數目 | 20 |
|檔案附件的數目<sup>3</sup>  |10     |
|聊天大小 | 每篇貼文約 28 KB<sup>4</sup> |

<sup>1</sup> 如果一個聊天超過 20 個人，以下的聊天功能會關閉：Outlook 自動回覆和 Teams 狀態訊息；輸入指示器；視訊和音訊通話；共用；讀取回條。當私人群組聊天包含超過 20 個成員時，也會移除 [設定傳遞選項] 按鈕 (!)。

<sup>2</sup> 每次只能將 200 名成員新增至群組聊天。[如需詳細資訊，請參閱此文章。](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat)

<sup>3</sup> 如果附件數量超過此限制，您會看見錯誤訊息。

<sup>4</sup> 28 KB 是大約限制，因為它包含訊息本身 (文字、影像連結等等)、@-提及和回應。

### <a name="emailing-a-channel"></a>傳送電子郵件到頻道

 如果使用者想要將電子郵件傳送到 Teams 中的頻道，使用者可以使用頻道的電子郵件地址。當電子郵件屬於頻道時，任何人都可以回覆電子郵件以開始交談。以下是一些傳送電子郵件到頻道時適用的限制。

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
> 所有 Microsoft 365 和 Office 365 授權的郵件大小、檔案附件和內嵌影像的限制都相同。在 Teams 中寄送電子郵件給頻道的功能不適用 Office GCC/GCCH/DOD 組織。

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
> 分組會議室只能在少於 300 名出席者的會議中建立。 此外，在會議中建立分組會議室會自動將會議出席者人數限制為 300 人。 建議使用者不要在預期超過 300 名參與者的會議中初始化分組會議室。 如需大型小組會議的資訊，請與使用者分享指南 [適用於大型 Teams 會議的最佳做法](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)。

### <a name="meeting-expiration"></a>會議到期

> [!NOTE]
> 會議 URL 絕不會停止運作。到期只會與任何 PSTN 撥入號碼、CVI 座標和/或基礎會議原則及設定相關。

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

<sup>1</sup> 您可根據自己的需求排定許多即時活動，但一次只能執行 15 個。製作人一加入即時活動，就表示該活動執行中。嘗試加入第 16 個即時活動的製作人會收到錯誤。

如需更多有關即時活動以及 Teams 即時活動與 Skype 會議廣播的比較詳細資訊，請移至 [Teams 即時活動和 Skype 會議廣播](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)。另請參閱[排程 Teams 即時活動](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。

> [!IMPORTANT]
> **Microsoft 365 的即時活動限制增加**
>
> **為了繼續支援客戶的需求，我們將延長即時活動的暫時限制增加，直到 2022年 12 月 31 日，包括**:
>
>- 活動支援最多達 20000 個出席者
>- 不同租用戶可以同時進行 50 個活動
>- 每個廣播的活動持續時間 (16 小時)
>
> 此外，可透過 Microsoft 365 輔助計畫來規劃最多 100,000 位出席者參與的即時活動。小組會評估每個要求，並與您一起判斷可用的選項。[深入了解](https://aka.ms/Stream/Blog/LiveEventOptions)。

## <a name="presence-in-outlook"></a>在 Outlook 中的顯示狀態

Outlook 2013 傳統型應用程式和更新版本中支援 Outlook 中的 Teams 顯示狀態。若要深入了解 Teams 中的顯示狀態，請參閱 [Teams 中的使用者顯示狀態](presence-admins.md)。

## <a name="storage"></a>儲存空間

Microsoft Teams 中的每個小組在 SharePoint Online 中都有一個小組網站，小組中的每個頻道在預設小組網站的文件庫中都有一個資料夾。在交談中共用的檔案會自動新增到文件庫，在 SharePoint 中設定的權限和檔案安全性選項會自動在 Teams 中反映。

> [!NOTE]
> 每個[私人頻道](./private-channels.md)都有自己的 SharePoint 網站 (先前稱之為 “網站集合)。

如果您的租用戶中未啟用 SharePoint Online，Microsoft Teams 使用者就無法一律在小組中共用的檔案。私人聊天中的使用者也無法共用檔案，因為該功能需要商務用 OneDrive (其綁定至 SharePoint 授權)。

透過將檔案儲存在 SharePoint Online 文件庫和商務用 OneDrive，您將遵守所有在租用戶層級設定的合規性規則。(如需詳細資訊，請參閱 [SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md)。)

由於 Teams 是在 SharePoint Online 後端執行以進行檔案共用，因此 SharePoint 的限制會適用小組內的 [檔案] 區段。以下是 SharePoint Online 適用的儲存空間限制。

|功能                 |Microsoft 365 商務基本版  |Microsoft 365 商務標準版   |Office 365 企業版 E1  |Office 365 企業版 E3  |Office 365 企業版 E5  |Office 365 企業版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|儲存空間                 |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB，加上每個購買授權 10 GB   |每個組織 1 TB，加上每個購買授權 10 GB |每個組織 1 TB，加上每個購買授權 10 GB  |每個組織 1 TB            |
|Teams 檔案的儲存空間 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |每個網站或群組最多 25 TB。 |
|檔案上傳限制 (每個檔案)    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |

頻道可由針對小組建立的 SharePoint Online 網站 (先前稱之為 "網站集合”) 內的資料夾進行備份，因此 [頻道] 內的檔案索引標籤會共用所屬小組的儲存空間限制。

如需詳細資訊，請參閱 [SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

## <a name="class-teams"></a>課程小組

Microsoft Teams 教育版提供專為獨特教育案例 (例如教室教學) 所設計的範本。如需有關小組類型 (包括課程小組) 的詳細資訊，請參閱[在 Microsoft Teams 中選擇要共同作業的小組類型](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)。

課程小組是一個範本類型，其中包含其他應用程式，且具有的限制與小組成員數目不同。

> [!NOTE]
> 使用課程小組需要 [Office 365 教育版授權](https://www.microsoft.com/education/products/office)。

下表列出課程小組的限制：

|功能  |最大限制  |
|---------|---------|
|一個小組中的成員數目    | 請參閱本文的 [Teams 和頻道](#teams-and-channels)一節        |
|課程小組中要使用作業的成員數目    | 300        |
|課程小組中要使用 OneNote 課程筆記本的成員數目     |300         |

課程小組可支援超過 300 個成員。不過，如果您計劃在您的小組內使用「作業」應用程式或「課程筆記本」應用程式，則您必須將成員數目保持在以上的上限之下。

## <a name="tags"></a>標籤

|功能  |最大限制  |
|---------|---------|
|每個小組的標記數量    | 100        |
|每個小組的建議預設標記數量    | 25        |
|指派給標記的小組成員人數    |100         |
|每個小組指派給使用者的標記數量    |25         |

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
