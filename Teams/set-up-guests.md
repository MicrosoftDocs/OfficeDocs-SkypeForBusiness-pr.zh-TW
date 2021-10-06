---
title: 開啟或關閉 Microsoft Teams 的來賓存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: 瞭解如何以 Office 365 系統管理員身份在 Microsoft Teams 中開啟或關閉來賓存取功能。
ms.openlocfilehash: 2b444b8357d8edef9aaa1c9c8e72ae6762f5bd52
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138239"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>開啟或關閉 Microsoft Teams 的來賓存取

> [!Note]
>
> 在 **2021 年 2** 月之前，來賓存取預設為關閉。 在系統管理員或小組擁有者可以新增來賓之前，必須為 Teams 開啟來賓存取。 開啟來賓存取權後，變更可能需要幾個小時才能生效。 如果使用者在嘗試將來賓新到小組時看到訊息，請連上您的系統管理員，可能是來賓存取權尚未開啟，或是設定尚未生效。
>
> **2021** 年 2 月之後，Microsoft Teams 中的來賓存取預設會針對尚未設定此設定&現有客戶開啟。 當此變更已執行時，如果您尚未在 Microsoft Teams 中配置來賓存取功能，該功能就會在租使用者中啟用。 如果您希望貴組織的來賓存取保持停用狀態，您必須確認來賓存取設定已設定為 **關閉，而非****服務預設值**。

> [!IMPORTANT]
> 開啟來賓存取取決於 Azure Active Directory、Microsoft 365、SharePoint 和 Teams 的設定。 如需詳細資訊，請參閱 [在小組中與來賓共同作業](/microsoft-365/solutions/collaborate-as-team)。

## <a name="configure-guest-access-in-the-teams-admin-center"></a>在 Teams 系統管理中心設定來賓存取

1. 登入 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com/)。

2. 選取 **使用者**  >  **來賓存取**。

3. 在 **中將允許來賓存取Teams** 設為 **On**。

    ![允許來賓存取開關設定為開啟。](media/guest-access-setting.png)

4. 在 **通話**、**會議** 及 **傳** 訊下，依您想要允許來賓的功能，針對每個功能選取開或關閉。

      - **進行私人通話** – **[開啟]** 此設定可允許來賓進行對等呼叫。
      - **IP 影片** - **開啟此設定** ，讓來賓在通話和會議中使用視像。
      - **螢幕畫面共用模式** – 此設定控制來賓的螢幕共用可用性。
          - 將此設定設定為 **[停用]** 以移除來賓在 Teams 中共用其螢幕的功能。
          - 將此設定設定為 **[單一應用程式]** 以允許共用單個應用程式。
          - 將此設定設定為 **[整個螢幕]** 以允許完整的螢幕畫面分享。
      - **現在開會**– 開啟 **此設定**，讓來賓在會議Microsoft Teams。
      - **編輯已傳送的訊息** - **[開啟]** 此設定可允許來賓編輯他們以前傳送的郵件。 
      - **刪除已寄郵件** - 開啟 **此設定，** 以允許來賓刪除他們先前寄來的郵件。
      - **聊天** –**[開啟]** 此設定可使來賓能够在 Teams 中使用聊天。
      - **交談中的 Giphy** – 開啟此 **設定** ，允許來賓在交談中使用 Giphys。 Giphy 是線上資料庫和搜尋引擎，允許使用者搜尋和共用 GIF 動畫檔案。 每個 Giphy 都有內容分級。
      - **Giphy 內容分級** –  從下拉式清單中選取分級：
          - **[允許所有內容]** - 來賓可以在聊天中插入所有 Giphy，而無論內容分級為何。
          - **[中等]**，來賓可以在聊天中插入 Giphy，但會適當限制成人內容。
          - **嚴格** - 來賓可以在聊天中插入 Giphys，但禁止插入成人內容。
      - **交談中的 Meme** - 開啟 **此設定，** 以允許來賓在交談中使用 Memes。
      - **交談中的貼圖** - 開啟此 **設定，** 讓來賓在交談中使用貼圖。
      - **郵件的浸入式閱讀程式**- 開啟 **此設定，** 以允許來賓在 [Teams。](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a)

    ![來賓許可權設定在 Teams。](media/manage-guest-access-image1.png)

5. 選取 [儲存 **]**。

## <a name="external-access-federation-vs-guest-access"></a>外部存取 (同盟) 與來賓存取

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>另請參閱

[使用 Microsoft 365 設定安全的共同作業](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[封鎖特定團隊的來賓](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
