---
title: Microsoft 團隊中的來賓體驗
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 本文將說明來賓使用者提供的 Microsoft 團隊功能。
ms.openlocfilehash: a2c4bcf380eb90f7c0a00c8f6f4f9141b80f8460
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030289"
---
# <a name="guest-experience-in-teams"></a>團隊中的來賓體驗

當客人邀請您加入小組時，他們會收到歡迎電子郵件訊息。 此訊息包含小組的一些相關資訊，以及該小組所預期的成員。 來賓必須先選取電子郵件訊息中的 [ **開啟 Microsoft 團隊** ]，然後才能存取團隊和其頻道，以接受邀請。
    
![顯示歡迎電子郵件訊息範例的螢幕擷取畫面](media/guest-experience-image1.png)
    
所有團隊成員都會在頻道執行緒中看到一則訊息，宣佈小組擁有者已新增來賓並提供來賓的名稱。 小組中的每個人都可以輕鬆識別誰是來賓。 頻道螺紋右上角的標籤會指出小組中的來賓人數，以及每個來賓名稱旁會出現 **(來賓)** 標籤。

![螢幕擷取畫面顯示代表小組訪客人數的標記](media/guest-experience-image2.png)

請參閱以下有關團隊訪客體驗的影片：
- [以來賓身分加入團隊](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [使用來賓加入團隊會議](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>比較小組成員與來賓的功能

下表比較組織小組成員及其來賓的可用團隊功能。 [團隊管理員] 控制來賓可用的功能。

|**團隊中的功能**|**組織中的小組使用者**|**來賓使用者**|
|:-----|:-----|:-----|
|建立頻道  <br/>  *小組擁有者控制此設定。*  <br/> |&#x2713;|&#x2713;|
|參與私人聊天  <br/> |&#x2713;|&#x2713;|
|參與頻道交談  <br/> |&#x2713;|&#x2713;|
|張貼、刪除及編輯郵件  <br/> |&#x2713;|&#x2713;|
|共用頻道檔案  <br/> |&#x2713;|&#x2713;|
|存取 SharePoint 檔案<br/> |&#x2713;|&#x2713;|
|附加檔案<br/> |&#x2713;|&#x2713;|
|下載私人聊天檔案<br/> |&#x2713;|&#x2713;|
|在檔案中搜尋<br/> |&#x2713;||
|共用聊天檔案  <br/> |&#x2713;||
|在索引標籤、bot 或連接器上新增應用程式 ()   <br/> |&#x2713;||
|建立會議或存取排程  <br/> |&#x2713;||
|存取商務用 OneDrive 儲存空間  <br/> |&#x2713;||
|建立整個租使用者與團隊/頻道來賓存取原則  <br/> |&#x2713;||
|邀請 Microsoft 365 或 Office 365 組織網域以外的使用者 <br/>  *小組擁有者控制此設定。*  <br/> <br/> |&#x2713;||
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
| 核心呼叫控制支援的 (保留、靜音、影片開啟/關閉、螢幕共用)  | 是 | 是 | 是 |
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

<sup>1</sup> 這個功能即將推出。

> [!NOTE]
> Azure Active Directory 中的 **來賓使用者存取限制** 原則 (azure AD) 決定目錄中來賓的許可權。 有三個原則選項。
>  - **[來賓使用者的存取權和成員相同 (最包容)]** 設定表示來賓擁有的目錄資料存取權，與目錄中的一般使用者相同。
>  - **[來賓使用者對目錄物件的屬性和成員資格擁有有限的存取權]** 設定表示來賓沒有特定目錄工作的權限，例如列舉使用者、群組，或使用 Microsoft Graph 的其他目錄資源。
>  - **[來賓使用者存取權受限於其自身目錄物件的屬性和成員資格 (最受限制)]** 設定表示來賓只能存取自己的目錄物件。
>
>若要深入了解，請參閱 [Azure Active Directory 中的預設使用者權限為何？](https://go.microsoft.com/fwlink/?linkid=2135493)

## <a name="related-topics"></a>相關主題

[將組織保留為來賓使用者](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)
