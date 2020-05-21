---
title: 開啟或關閉 Microsoft 團隊的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 瞭解如何開啟或關閉 Microsoft 團隊中的來賓存取功能做為 Office 365 系統管理員。
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: e434a85693226252ecef2a5b4c251024524e698f
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326560"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>開啟或關閉 Microsoft 團隊的來賓存取權
===================================================

根據預設，來賓存取權會關閉。 就像 Office 365 管理員一樣，您必須先開啟團隊的來賓存取權，管理員或團隊擁有者才能新增來賓。 若要開啟來賓存取，請使用[來賓存取檢查清單](guest-access-checklist.md)。 

開啟來賓存取後，可能需要幾個小時的時間，變更才會生效。 當使用者嘗試將來賓新增到其小組時，如果使用者看到「與您的系統管理員聯繫」訊息，可能是因為來賓存取尚未開啟，或是設定尚未生效。

> [!IMPORTANT]
> 開啟來賓存取權視 Azure Active Directory、Office 365、SharePoint Online 和團隊中的設定而定。 如需詳細資訊，請參閱[核准團隊中的來賓存取權](Teams-dependencies.md)。



## <a name="configure-guest-access-in-the-teams-admin-center"></a>在團隊系統管理中心設定來賓存取

1.    登入 Microsoft 團隊系統管理中心。

2.    選取 [全**組織性設定**  >  **來賓存取**]。

3. 將**Microsoft 團隊中的 [允許來賓存取**權設定為 [**開啟**]。

    ![[允許來賓存取開關設定為開啟] ](media/set-up-guests-image1.png)

4.    在 [**通話**]、[**會議**] 和 [**訊息**] 底下，針對每個功能選取 [**開啟**] 或 [**關閉**]，視您想要來賓使用者的需求而定。

    - **撥打私人電話** **–開啟此設定可**讓來賓進行對等通話。
    - [**允許 IP 影片**] **-開啟此設定可**讓來賓在通話和會議中使用影片。
    - **螢幕共用模式**–此設定會控制來賓使用者螢幕共用的可用性。 
       - 將此設定設為 [**停用**]，移除來賓在小組中共用畫面的功能。 
       - 將此設定轉換為 [**單一應用程式**] 以允許共用個別的應用程式。 
       - 將此設定設為 [**整個畫面**] 以允許完整的螢幕共用。
    - [**允許立即開會**] –開啟**此設定可讓來賓在 Microsoft**團隊中使用 [立即開會] 功能。
    - **編輯已傳送的郵件** **-開啟此設定，** 允許來賓編輯先前傳送的郵件。
    - **來賓可以刪除已傳送的郵件**–開啟**此設定，** 允許來賓刪除先前傳送的郵件。
    - [**聊天**] **：開啟此設定可**讓客人在團隊中使用聊天功能。
    - **在交談中使用 giphy** –開啟此**設定可讓來賓在交談**中使用 giphy。 Giphy 是線上資料庫和搜尋引擎，可讓使用者搜尋及共用動畫 GIF 檔案。 每個 Giphy 都會獲指派內容評級。
    - **Giphy 內容分級**–從下拉式清單中選取評分：
       - [**允許所有內容**-來賓] 能在聊天中插入所有 giphy，無論內容分級為何。
       - [**適中**]-訪客將能在聊天中插入 giphy，但將會針對成人內容適度地限制。
       - [**嚴格**]-來賓將能在聊天中插入 giphy，但會限制插入成人內容。
    - **在交談中使用 meme** -開啟此**設定可讓來賓在交談**中使用 meme。
    - **在交談中使用不乾膠**圖示，請**開啟此設定，** 以允許來賓在交談中使用不乾膠圖示。 


5.    按一下 [儲存]****。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>使用 PowerShell 開啟或關閉來賓存取
已閱讀 [[使用 PowerShell] 開啟或關閉來賓存取](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)


## <a name="video-adding-guests-in-teams"></a>影片：在團隊中新增來賓

|  |  |
|---------|---------|
| 在 Microsoft 團隊中新增來賓   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a>外部存取 (同盟) 與來賓存取

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]