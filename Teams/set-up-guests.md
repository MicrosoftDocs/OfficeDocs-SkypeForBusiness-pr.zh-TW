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
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: 瞭解如何以 Office 365 系統管理員身份在 Microsoft Teams 中開啟或關閉來賓存取功能。
ms.openlocfilehash: aaf37fda456f0e48d441e78f785a3ce450f1f42c
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786775"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>開啟或關閉 Microsoft Teams 的來賓存取

> [!Note]

> 在 **2021 年2月** 之前，來賓存取預設為關閉狀態。 在系統管理員或小組擁有者可以新增來賓之前，必須為 Teams 開啟來賓存取。 開啟來賓存取後，可能需要幾個小時的時間，變更才會生效。 如果使用者在您嘗試將來賓新增至其小組時，請 **與您的系統管理員聯繫** ，可能是因為沒有開啟來賓存取，或設定尚未生效。 

> **2021 年2月** 之後，對於尚未設定此設定的現有客戶 &，Microsoft 團隊中的來賓存取權會預設為開啟狀態。 在實施此變更時，如果您尚未在 Microsoft 團隊中設定來賓存取能力，該功能將會在您的租使用者中啟用。 如果您想讓您的組織仍停用來賓存取權，您必須確認 [來賓存取設定] 設定為 [ **關閉** ] 而不是 [ **服務預設值**]。

> [!IMPORTANT]
> 開啟來賓存取取決於 Azure Active Directory、Microsoft 365、SharePoint 和 Teams 的設定。 如需詳細資訊，請參閱 [在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。

## <a name="configure-guest-access-in-the-teams-admin-center"></a>在 Teams 系統管理中心設定來賓存取

1. 登入 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com/)。

2. 選取 **[全組織設定]** > **[來賓存取]**。

3. 將 **[允許 Microsoft Teams 中的來賓存取]** 設定為 **[開啟]**。

    ![允許來賓存取開關設定為開啟 ](media/set-up-guests-image1.png)

4. 在 **[通話]**、**[會議]** 和 **[通訊]** 下，根據要允許來賓使用者使用的功能，為每個功能選擇 **[開啟]** 或 **[關閉]**。

      - **進行私人通話** – **[開啟]** 此設定可允許來賓進行對等呼叫。
      - **允許 IP 視訊** - **[開啟]** 此設定可允許來賓在其通話和會議中使用視訊。
      - **螢幕畫面分享模式** – 此設定控制來賓使用者的螢幕畫面分享可用性。
          - 將此設定設定為 **[停用]** 以移除來賓在 Teams 中共用其螢幕的功能。
          - 將此設定設定為 **[單一應用程式]** 以允許共用單個應用程式。
          - 將此設定設定為 **[整個螢幕]** 以允許完整的螢幕畫面分享。
      - **允許立即開會** – **[開啟]** 此設定可允許來賓使用 Microsoft Teams 中的 [立即開會] 功能。
      - **編輯已傳送的訊息** - **[開啟]** 此設定可允許來賓編輯他們以前傳送的郵件。 
      - **來賓可刪除已傳送的訊息** - **[開啟]** 此設定可允許來賓刪除他們以前傳送的郵件。 
      - **聊天** –**[開啟]** 此設定可使來賓能够在 Teams 中使用聊天。
      - **在交談中使用 Giphy** – **[開啟]** 此設定可允許來賓在交談中使用 Giphys。 Giphy 是線上資料庫和搜尋引擎，允許使用者搜尋和共用 GIF 動畫檔案。 每個 Giphy 都有內容分級。
      - **Giphy 內容分級** –  從下拉式清單中選取分級：
          - **[允許所有內容]** - 來賓可以在聊天中插入所有 Giphy，而無論內容分級為何。
          - **[中等]**，來賓可以在聊天中插入 Giphy，但會適當限制成人內容。
          - [**嚴格**]-來賓可以在聊天中插入 giphy，但會限制插入成人內容。
      - **在交談中使用 Meme** – **[開啟]** 此設定可允許來賓在交談中使用 Meme。
      - **在交談中使用貼圖** – **[開啟]** 此設定可允許來賓在交談中使用貼圖。

    ![Teams 中的來賓權限設定](media/manage-guest-access-image1.png)

5. 選取 [ **儲存**]。

## <a name="external-access-federation-vs-guest-access"></a>外部存取 (同盟) 與來賓存取

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>另請參閱

[使用 Microsoft 365 設定安全的共同作業](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[封鎖特定小組的來賓使用者](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
