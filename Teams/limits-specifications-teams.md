---
title: Microsoft 團隊的限制與規格
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: 瞭解適用于 Microsoft 團隊的限制、規格及其他需求。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecd31a243da999704b7d466b3dc93dd66fb7ac25
ms.sourcegitcommit: 9053c0d5ddb6be3ce3da85dffcde3f45dbc0ab7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407993"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft 團隊的限制與規格

本文將說明適用于團隊的一些限制、規格及其他需求。

## <a name="teams-and-channels"></a>團隊和頻道 

|功能    | 最大限制 |
|-----------|---------------|
|使用者可以建立的團隊人數 | 受限於250物件限制&sup1;         |
|團隊中的成員數目 | 5000       |
|租使用者允許的組織內團隊人數 | 500     |
|[組織內小組](create-an-org-wide-team.md)中的成員數目 | 5000       |
|全域管理員可建立的團隊人數        |  500000   |
|Office 365 租使用者可擁有的團隊人數    | 500000&sup2;     |
|每個團隊的頻道數目    | 200 (包括刪除的通道) &sup3;         |

&sup1;Azure Active Directory 中的任何目錄物件都會計入此限制。 全域管理員會免除這個限制, 就像是使用[應用程式許可權](https://docs.microsoft.com/graph/permissions-reference)呼叫 Microsoft Graph 的 app 一樣。

&sup2;此限制包括已歸檔的團隊。

&sup3; 刪除的頻道可以在30天內還原。 在30天內, 已刪除的頻道會繼續依每個團隊的200頻道數量計算。 在30天之後, 已刪除的頻道及其內容會永久刪除, 且頻道不會在每個團隊的200頻道限制範圍內。

## <a name="channel-names"></a>頻道名稱

頻道名稱不能包含下列字元或單字。

|||
|---------|---------|
|標點符號     | ~ #% & * {} +/\:  < > ？ &#124; "" .。。        |
|這些範圍中的字元    | 0到1F<br>80到9F        |
|關鍵字     | forms、CON、CONIN $、CONOUT $、PRN、AUX、NUL、COM1 至 COM9、LPT1 到 LPT9、desktop &#95;vti&#95;|

頻道名稱也無法以底線 (_) 或句號 (.) 開頭, 或以句點 (.) 結尾。

## <a name="meetings-and-calls"></a>會議和通話

|功能     | 最大限制 |
|------------|---------------|
|會議中的人員人數  | 250    |

## <a name="teams-live-events"></a>團隊即時事件

|功能     | 最大限制 |
|------------|---------------|
|物件大小 | 10000出席者 |
|事件的持續時間 | 4小時 |
|欄1  |欄2等  |
|---------|---------|
|Row1     |         |
|Row2     |         |

|Office 365 租使用者 | 中的併發即時事件 |15 |

如需即時事件的詳細資訊, 以及團隊即時事件與 Skype 會議廣播的比較, 請移至 [[小組即時事件] 和 [Skype 會議](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)廣播]。

## <a name="storage"></a>容量

Microsoft 團隊中的每個小組在 SharePoint Online 中都有小組網站, 小組中的每個頻道都在預設的小組網站文件庫中取得一個資料夾。 在交談中共用的檔案會自動新增至文件庫, SharePoint 中設定的許可權和檔案安全性選項會自動反映在小組中。

如果您未在租使用者中啟用 SharePoint Online, Microsoft 團隊使用者就無法在小組中共用檔案。 私人聊天中的使用者也無法共用檔案, 因為該功能需要商務用 OneDrive (與 SharePoint 授權相關聯)。

透過將檔案儲存在 SharePoint Online 文件庫和商務用 OneDrive 中, 就會遵循在租使用者層級設定的所有合規性規則。 (如需詳細資訊, 請參閱[SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。)

由於團隊是在 SharePoint Online 後端執行檔案共用, 因此 SharePoint 限制適用于小組中的 [檔案] 區段。 以下是 SharePoint Online 適用的儲存空間限制。

|功能                 |Office 365 商務基本版  |Office 365 商務版   |Office 365 企業版 E1  |Office 365 企業版 E3  |Office 365 企業版 E5  |Office 365 企業版 F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|容量                 |每個組織 1 TB 加上購買的每個授權 10 GB  |每個組織 1 TB 加上購買的每個授權 10 GB  |每個組織 1 TB 加上購買的每個授權 10 GB   |每個組織 1 TB 加上購買的每個授權 10 GB |每個組織 1 TB 加上購買的每個授權 10 GB  |每個組織 1 TB           |
|小組檔案的儲存空間 |每個網站集合或群組最多 25 TB |每個網站集合或群組最多 25 TB |每個網站集合或群組最多 25 TB |每個網站集合或群組最多 25 TB |每個網站集合或群組最多 25 TB |每個網站集合或群組最多 25 TB |
|檔案上傳限制 (每個檔案)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

頻道是由針對小組建立的 SharePoint Online 網站集合中的資料夾所支援, 因此頻道內的檔案索引標籤會共用其所屬團隊的儲存空間限制。

如需詳細資訊, 請參閱[SharePoint Online 限制](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)。

## <a name="messaging"></a>傳送

參與 Microsoft 團隊中聊天清單一部分交談的使用者, 必須擁有 Exchange Online (雲端) 信箱, 以供系統管理員搜尋交談交談。 這是因為聊天清單中的交談是儲存在聊天參與者的雲端型信箱中。 如果聊天參與者沒有 Exchange Online 信箱, 系統管理員將無法在聊天交談中搜尋或進行封存。 例如, 在 Exchange 混合式部署中, 擁有內部部署信箱的使用者可能可以參與 Microsoft 團隊中的聊天清單中的交談。 不過, 在這種情況下, 來自這些交談的內容無法進行搜尋, 而且無法保留, 因為使用者沒有雲端信箱。 (如需詳細資訊, 請參閱[Exchange 與 Microsoft 團隊互動的方式](exchange-teams-interact.md))。

Microsoft 團隊聊天功能可在 Microsoft Exchange 後端使用, 因此您可以將 Exchange 郵件限制套用至 Microsoft 團隊中的聊天功能。 如果使用者想要傳送電子郵件至小組中的頻道, 他們會使用頻道電子郵件地址。 一旦電子郵件是頻道的一部分, 任何人都可以回復以開始交談。 以下是一些適用于傳送電子郵件到頻道的限制。 

|功能  | 最大限制  |
|---------|---------|
|私人聊天中的人員人數  | 100    |
|郵件大小&dagger;  |25 KB   |
|檔附件的數目&Dagger;  |第     |
|內嵌圖像的數目&Dagger; |50   |

&dagger;如果郵件超過這個限制, 就會產生預覽訊息, 並要求使用者從提供的連結中查看或下載原始電子郵件。

&Dagger;如果附件或影像數量超過這個限制, 就不會處理郵件, 而且 NDR 電子郵件會傳回給寄件者, 通知他們發生錯誤。

> [!NOTE]
> 在所有 Office 365 授權中, 郵件大小、檔案附件及內嵌圖像限制都是相同的。

如需詳細資訊, 請參閱[Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。

## <a name="browsers"></a>流覽

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>作業系統

如需作業系統需求的相關資訊, 請參閱[取得 Microsoft 團隊的用戶端](get-clients.md)。
