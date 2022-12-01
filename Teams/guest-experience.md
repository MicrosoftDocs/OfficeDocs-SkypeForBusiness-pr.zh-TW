---
title: Microsoft Teams 的來賓體驗
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
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
description: 本文將說明來賓可使用的Microsoft Teams 功能。
ms.openlocfilehash: 960688d49f634ff5665fe4e1da2436e9bad669ac
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198905"
---
# <a name="guest-experience-in-teams"></a>Teams 中的來賓體驗

當來賓受邀加入團隊時，他們會收到歡迎電子郵件訊息。 此訊息包含小組的一些相關資訊，以及他們成為成員後預期的情況。 來賓必須在電子郵件訊息中選 **取 [開啟 Microsoft Teams**] 以接受邀請，才能存取團隊及其頻道。

> [!NOTE]
> 新增來賓至團隊後，可能需要幾個小時才能存取。
    
![顯示歡迎電子郵件訊息範例的螢幕擷取畫面。](media/guest-experience-image1.png)
    
所有團隊成員都會在頻道對話中看到一則訊息，宣佈團隊擁有者已新增來賓並提供來賓名稱。 團隊中的每個人都可以輕鬆識別誰是來賓。 頻道對話右上角的標籤會指出團隊中的來賓人數，而每位來賓名稱旁會顯示 **(來賓)** 標籤。

![顯示標記的螢幕擷取畫面，指出團隊中的來賓數目。](media/guest-experience-image2.png)

請觀看以下有關 Teams 來賓體驗的影片：
- [以來賓身分加入 Teams 會議](https://support.microsoft.com/office/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [在 Teams 會議中與外部來賓合作](https://support.microsoft.com/office/work-with-external-guests-180ed260-d3ef-4247-9f24-1984fc76d5f0)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>團隊成員和來賓功能的比較

下表將比較組織成員及其來賓可用的 Teams 功能。 Teams 系統管理員可控制來賓可用的功能。

| Teams 中的功能 | 組織中的 Teams 使用者 | 客人 |
|:-----|:-----|:-----|
|建立頻道  <br/>  *團隊擁有者會控制此設定。*  <br/> |&#x2713;|&#x2713;|
|參與私人聊天  <br/> |&#x2713;|&#x2713;|
|參與頻道交談  <br/> |&#x2713;|&#x2713;|
|張貼、刪除及編輯訊息  <br/> |&#x2713;|&#x2713;|
|共用頻道檔案  <br/> |&#x2713;|&#x2713;|
|存取 SharePoint 檔案<br/> |&#x2713;|&#x2713;|
|附加檔案<br/> |&#x2713;|僅限頻道文章|
|下載私人聊天檔案<br/> |&#x2713;|&#x2713;|
|在檔案內搜尋<br/> |&#x2713;||
|共用聊天檔案  <br/> |&#x2713;||
|新增應用程式 (索引標籤、Bot 或連接器)   <br/> |&#x2713;||
|建立會議或存取排程  <br/> |&#x2713;||
|存取商務用 OneDrive儲存空間  <br/> |&#x2713;||
|建立全租使用者和團隊/頻道來賓存取原則  <br/> |&#x2713;||
|邀請Microsoft 365 或Office 365組織網域以外的使用者 <br/>  *團隊擁有者會控制此設定。*  <br/> <br/> |&#x2713;||
|建立團隊  <br/> |&#x2713;||
|探索並加入公開團隊  <br/> |&#x2713;||
|檢視組織結構  <br/> |&#x2713;||
|使用內嵌翻譯  <br/> |&#x2713;||
|成為團隊擁有者  <br/> |&#x2713;||

下表顯示來賓可使用的通話和會議功能，與其他類型的使用者比較。

| 通話功能 | 客人 | E1 和 E3 使用者 | E5 和 企業語音 使用者 |
| --------------- | ----- | -------------- | -------------- |
| VOIP 通話 | 是 | 是 | 是 |
| 群組通話 | 是 | 是 | 是 |
| 支援的核心通話控制 (保留、靜音、開啟/關閉視訊、螢幕畫面分享)  | 是 | 是 | 是 |
| 轉移目標 | 是 | 是 | 是 |
| 可以轉接電話 | 是 | 是 | 是 |
| 可以傳送傳輸 | 是 | 是 | 是 |
| 可以透過 VOIP 新增其他使用者至通話 | 是 | 是 | 是 |
| 可以透過電話號碼將使用者新增至通話 | 否 | 否 | 是 |
| 轉寄目標 | 否 | 是 | 是 |
| 通話群組目標 | 否 | 是 | 是 |
| 未回答的目標 | 否 | 是 | 是 |
| 可以是同盟通話的目標 | 否 | 是 | 是 |
| 可以撥打同盟電話 | 否 | 是 | 是 |
| 可以立即傳輸他們的來電 | 否 | 否 | 是 |
| 可以同時撥打他們的來電 | 否 | 否 | 是 |
| 可以路由未接聽的電話 | 否 | 否 | 是 |
| 未接來電可以移至語音信箱 | 否 | 否<sup>1</sup> |是 |
| 有可接聽來電的電話號碼 | 否 | 否 | 是 |
| 可以撥打電話號碼 | 否 | 否 | 是 |
| 可以存取通話設定 | 否 | 否 | 是 |
| 可以變更語音信箱問候語 | 否 | 否<sup>1</sup> | 是 |
| 可以變更鈴聲 | 否 | 否  | 是 |
| 支援 TTY | 否 | 否 | 是 |
| 可以有代理人 | 否 | 否 | 是 |
|  可以是代理人 | 否 | 否 | 是 |

<sup>1</sup> 這項功能即將推出。

> [!NOTE]
> Azure Active Directory (Azure AD) 中的來 **賓使用者存取限制** 原則決定目錄中來賓的許可權。 有三個原則選項。
>  - **[來賓使用者的存取權和成員相同 (最包容)]** 設定表示來賓擁有的目錄資料存取權，與目錄中的一般使用者相同。
>  - **[來賓使用者對目錄物件的屬性和成員資格擁有有限的存取權]** 設定表示來賓沒有特定目錄工作的權限，例如列舉使用者、群組，或使用 Microsoft Graph 的其他目錄資源。
>  - **[來賓使用者存取權受限於其自身目錄物件的屬性和成員資格 (最受限制)]** 設定表示來賓只能存取自己的目錄物件。
>
>若要深入了解，請參閱 [Azure Active Directory 中的預設使用者權限為何？](/azure/active-directory/fundamentals/users-default-permissions)

## <a name="related-topics"></a>相關主題

[以來賓身分離開組織](/azure/active-directory/b2b/leave-the-organization)

[使用來賓存取和外部存取與組織外的人員共同作業](communicate-with-users-from-other-organizations.md)
