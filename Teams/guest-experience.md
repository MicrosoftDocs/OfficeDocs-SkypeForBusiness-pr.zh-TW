---
title: 來賓體驗像什麼
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: 瞭解適用于來賓使用者的 Microsoft 團隊功能。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed0ea94910e9b3b5499a1f23a6c1c081590957c7
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160567"
---
<a name="what-the-guest-experience-is-like"></a>來賓體驗像什麼
=================================

當客人邀請您加入小組時，他們會收到歡迎電子郵件訊息。 此訊息包含小組的一些相關資訊，以及該小組所預期的成員。 來賓必須先選取電子郵件訊息中的 [**開啟 Microsoft 團隊**]，然後才能存取團隊和其頻道，以接受邀請。
    
![顯示歡迎電子郵件訊息範例的螢幕擷取畫面](media/guest-experience-image1.png)
    
所有團隊成員都會在頻道執行緒中看到一則訊息，宣佈小組擁有者已新增來賓並提供來賓的名稱。 小組中的每個人都可以輕鬆識別誰是來賓。 如下列範例小組的螢幕擷取畫面所示，橫幅代表「這個小組有客人」，且每個來賓的名稱旁邊都會出現一個 **（來賓）** 標籤。
    
![顯示橫幅通知來賓使用者的螢幕擷取畫面](media/guest-experience-image2.png "螢幕擷取畫面顯示適用于 Northwind 商貿的行銷管道的一部分，並在上方橫幅中發出通知，指出該小組有來賓和來賓的使用者，其名稱旁會出現 [word 來賓]。")

## <a name="comparison-of-team-member-and-guest-capabilities"></a>比較小組成員與來賓的功能

下表比較組織小組成員及其來賓的可用團隊功能。

|**團隊中的功能**|**組織中的小組使用者**|**來賓使用者**|
|:-----|:-----|:-----|
|建立頻道  <br/>  *小組擁有者控制此設定。*  <br/> |&#x2713;|&#x2713;|
|參與私人聊天  <br/> |&#x2713;|&#x2713;|
|參與頻道交談  <br/> |&#x2713;|&#x2713;|
|張貼、刪除及編輯郵件  <br/> |&#x2713;|&#x2713;|
|共用頻道檔案  <br/> |&#x2713;|&#x2713;|
|共用聊天檔案  <br/> |&#x2713;||
|新增應用程式（索引標籤、bot 或連接器）  <br/> |&#x2713;||
|建立會議或存取排程  <br/> |&#x2713;||
|存取商務用 OneDrive 儲存空間  <br/> |&#x2713;||
|建立整個租使用者與團隊/頻道來賓存取原則  <br/> |&#x2713;||
|邀請 Office 365 租使用者網域以外的使用者 <br/>  *小組擁有者控制此設定。*  <br/> <br/> |&#x2713;||
|建立團隊  <br/> |&#x2713;||
|探索並加入公開團隊  <br/> |&#x2713;||
|查看組織結構  <br/> |&#x2713;||
|使用內嵌翻譯  <br/> |&#x2713;||
|成為團隊擁有者  <br/> |&#x2713;||

   
下表顯示與其他使用者類型相比，來賓可用的通話與會議功能。

| 通話功能 | 來賓 | E1 與 E3 使用者 | E5 和企業語音使用者 |
| --------------- | ----- | -------------- | -------------- |
| VOIP 通話 | 是 | 是 | 是 |
| 群組通話 | 是 | 是 | 是 |
| 核心通話控制支援（保留、靜音、影片開啟/關閉、螢幕共用） | 是 | 是 | 是 |
| 轉移目標 | 是 | 是 | 是 |
| 可以轉接來電 | 是 | 是 | 是 |
| 可進行諮詢式轉接 | 是 | 是 | 是 |
| 可透過 VOIP 將其他使用者新增至通話 | 是 | 是 | 是 |
| 可以透過電話號碼將使用者新增到通話中 | 否 | 否 | 是 |
| 轉寄目標 | 否 | 是 | 是 |
| 通話群組目標 | 否 | 是 | 是 |
| 未回復的目標 | 否 | 是 | 是 |
| 可以是聯盟呼叫的目標 | 否 | 是 | 是 |
| 可以進行聯盟通話 | 否 | 是 | 是 |
| 可以立即轉寄其來電 | 否 | 否 | 是 |
| 可以同時撥打來電 | 否 | 否 | 是 |
| 可以傳送未接聽的電話 | 否 | 否 | 是 |
| 未接來電可移至語音信箱 | 否 | 無<sup>1</sup> |是 |
| 擁有可接聽電話的電話號碼 | 否 | 否 | 是 |
| 可以撥打電話號碼 | 否 | 否 | 是 |
| 可以存取通話設定 | 否 | 否 | 是 |
| 可以變更語音信箱問候語 | 否 | 無<sup>1</sup> | 是 |
| 可以變更鈴聲 | 否 | 否  | 是 |
| 支援 TTY | 否 | 否 | 是 |
| 可以擁有代理人 | 否 | 否 | 是 |
|  可以是代理人 | 否 | 否 | 是 |


<sup>1</sup>這個功能即將推出。

> [!NOTE]
> Office 365 系統管理員會控制來賓可用的功能。 

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="how-do-i-leave-an-organization-that-ive-been-invited-to"></a>如何離開受邀者的組織？
如果您受邀您不想成為客人的組織，您可以選擇離開該組織。 如需詳細資訊，請移至[將組織設為來賓使用者](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)。 或者，您也可以要求組織管理員將您從其租使用者中移除。 請注意，如果您想要在將來存取組織，您在任何一種情況下都必須重新受邀租使用者。

### <a name="do-guests-have-the-same-capabilities-as-team-members"></a>來賓與團隊成員的功能是否相同？
不。 如需訪客可以與不能執行哪些動作的詳細資訊，請參閱本文中[的小組成員和來賓功能比較](#comparison-of-team-member-and-guest-capabilities)。

### <a name="do-guests-have-access-to-onedrive-for-business"></a>來賓是否有權存取商務用 OneDrive？
不。

### <a name="do-guests-have-access-to-sharepoint-files"></a>來賓是否有存取 SharePoint 檔案的許可權？
是。

### <a name="can-guests-search-within-files"></a>來賓可以在檔案中搜尋嗎？
不。

### <a name="can-guests-attach-files"></a>來賓可以附加檔案嗎？
是的，來賓可以透過以下兩種方式附加檔案：

   - 在左窗格**中選取 [** 檔案]，然後流覽至檔案位置。
   - 從電腦上傳檔案。

### <a name="can-a-guest-download-a-file-in-a-private-chat"></a>來賓可以在私人聊天中下載檔案嗎？
是的，他們可以在私人聊天中接收成員的檔案，然後將檔案下載到他們的桌面。
