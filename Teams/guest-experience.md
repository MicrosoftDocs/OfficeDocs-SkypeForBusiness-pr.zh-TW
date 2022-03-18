---
title: 來賓在 Microsoft Teams
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
ms.custom: seo-marvel-apr2020
description: 本文將說明來賓Microsoft Teams使用的功能。
ms.openlocfilehash: c7052eb22a68b146c3ee998b57ba877da82e11b4
ms.sourcegitcommit: 640f55fe6144ff867b41b57e52f45b8a64cf779e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2022
ms.locfileid: "63556629"
---
# <a name="guest-experience-in-teams"></a>來賓在 Teams

當來賓受邀加入團隊時，他們會收到歡迎電子郵件訊息。 此訊息包含團隊的一些相關資訊，以及他們成為成員後預期的結果。 來賓必須先選取電子郵件訊息中的 **Microsoft Teams，才能** 存取團隊及其頻道，以接受邀請。

> [!NOTE]
> 將來賓新加入團隊後，可能需要數小時才能存取。
    
![顯示歡迎電子郵件訊息範例的螢幕擷取畫面。](media/guest-experience-image1.png)
    
所有小組成員在頻道執行緒中都看到一則訊息，宣告團隊擁有者已新增來賓，並提供來賓的名稱。 團隊中每個人都可以輕鬆識別誰是來賓。 頻道討論串右上角的標籤會指出團隊中的來賓人數， (來賓 **) 標籤** 會出現在每個來賓名稱旁。

![顯示標記的螢幕擷取畫面，指出團隊中的來賓人數。](media/guest-experience-image2.png)

請觀看以下影片，瞭解以下Teams：
- [以來賓Teams加入會議](https://support.microsoft.com/office/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [在會議與外部來賓Teams合作](https://support.microsoft.com/office/work-with-external-guests-180ed260-d3ef-4247-9f24-1984fc76d5f0)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>比較團隊成員和來賓功能

下表比較Teams小組成員及其來賓可用的功能。 Teams系統管理員控制來賓可用的功能。

| 在 Teams | Teams組織中的使用者 | 客人 |
|:-----|:-----|:-----|
|建立頻道  <br/>  *團隊擁有者控制此設定。*  <br/> |&#x2713;|&#x2713;|
|參與私人聊天  <br/> |&#x2713;|&#x2713;|
|參與頻道交談  <br/> |&#x2713;|&#x2713;|
|張貼、刪除及編輯郵件  <br/> |&#x2713;|&#x2713;|
|共用頻道檔案  <br/> |&#x2713;|&#x2713;|
|存取SharePoint檔案<br/> |&#x2713;|&#x2713;|
|附加檔案<br/> |&#x2713;|僅頻道文章|
|下載私人聊天檔案<br/> |&#x2713;|&#x2713;|
|在檔案中搜尋<br/> |&#x2713;||
|共用聊天檔案  <br/> |&#x2713;||
|新增應用程式 (、Bot 或連接器)   <br/> |&#x2713;||
|建立會議或存取排程  <br/> |&#x2713;||
|存取商務用 OneDrive儲存空間  <br/> |&#x2713;||
|建立全租使用者和團隊/頻道來賓存取政策  <br/> |&#x2713;||
|邀請組織網域Microsoft 365或Office 365使用者 <br/>  *團隊擁有者控制此設定。*  <br/> <br/> |&#x2713;||
|建立團隊  <br/> |&#x2713;||
|探索並加入公用小組  <br/> |&#x2713;||
|查看組織結構  <br/> |&#x2713;||
|使用內嵌翻譯  <br/> |&#x2713;||
|成為團隊擁有者  <br/> |&#x2713;||

下表顯示與其他類型的使用者比較，來賓可以使用的通話和會議功能。

| 通話功能 | 客人 | E1 和 E3 使用者 | E5 和 企業語音使用者 |
| --------------- | ----- | -------------- | -------------- |
| VOIP 通話 | 是 | 是 | 是 |
| 群組通話 | 是 | 是 | 是 |
| 支援核心通話控制項， (、靜音、視音訊開/關、螢幕)  | 是 | 是 | 是 |
| 傳輸目標 | 是 | 是 | 是 |
| 可以轉接通話 | 是 | 是 | 是 |
| 可進行諮詢轉移 | 是 | 是 | 是 |
| 可以透過 VOIP 將其他使用者新增到通話中 | 是 | 是 | 是 |
| 可以按電話號碼將使用者新增到通話中 | 否 | 否 | 是 |
| 轉場目標 | 否 | 是 | 是 |
| 通話群組目標 | 否 | 是 | 是 |
| 未解說的目標 | 否 | 是 | 是 |
| 可以是聯盟通話的目標 | 否 | 是 | 是 |
| 可以撥打聯盟電話 | 否 | 是 | 是 |
| 可以立即轉呼叫 | 否 | 否 | 是 |
| 可以同時撥打他們的電話 | 否 | 否 | 是 |
| 可以路由未接聽的通話 | 否 | 否 | 是 |
| 未接來電可以進入語音信箱 | 否 | <sup>No1</sup> |是 |
| 有可以接聽電話的電話號碼 | 否 | 否 | 是 |
| 可以撥打電話號碼 | 否 | 否 | 是 |
| 可以存取通話設定 | 否 | 否 | 是 |
| 可以變更語音信箱問候語 | 否 | <sup>No1</sup> | 是 |
| 可以變更鈴聲 | 否 | 否  | 是 |
| 支援 TTY | 否 | 否 | 是 |
| 可以有代理人 | 否 | 否 | 是 |
|  可以是代理人 | 否 | 否 | 是 |

<sup>1</sup> 這項功能即將推出。

> [!NOTE]
> 來賓 **使用者存取限制** Azure Active Directory (Azure AD) 決定目錄中來賓的許可權。 有三個原則選項。
>  - **[來賓使用者的存取權和成員相同 (最包容)]** 設定表示來賓擁有的目錄資料存取權，與目錄中的一般使用者相同。
>  - **[來賓使用者對目錄物件的屬性和成員資格擁有有限的存取權]** 設定表示來賓沒有特定目錄工作的權限，例如列舉使用者、群組，或使用 Microsoft Graph 的其他目錄資源。
>  - **[來賓使用者存取權受限於其自身目錄物件的屬性和成員資格 (最受限制)]** 設定表示來賓只能存取自己的目錄物件。
>
>若要深入了解，請參閱 [Azure Active Directory 中的預設使用者權限為何？](/azure/active-directory/fundamentals/users-default-permissions)

## <a name="related-topics"></a>相關主題

[離開組織做為來賓](/azure/active-directory/b2b/leave-the-organization)

[使用來賓存取和外部存取與組織外的人員共同作業](communicate-with-users-from-other-organizations.md)
