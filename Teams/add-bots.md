---
title: 在 Microsoft 團隊中新增私人聊天和頻道的機器人
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: 瞭解如何在 Microsoft 團隊中新增機器人，以進行個人聊天、群組聊天和頻道，以及上傳您自己的機器人來進行個人聊天、群組聊天和頻道。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7837fd3a832a1764cfde3968b73337069762dab3
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "37516834"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>在 Microsoft 團隊中新增個人聊天、群組聊天和頻道的機器人
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Bot 是能回應查詢或提供更新和通知的自動程式，讓使用者覺得有趣或想要掌握相關資訊。 Bot 可讓使用者透過 Microsoft 團隊中的聊天交談，與工作管理、排程及輪詢等雲端服務互動。 小組的 bot 是在[Microsoft Bot 架構](https://go.microsoft.com/fwlink/?linkid=854370)中建立的。 您可以輕鬆地為團隊啟用使用這個架構開發的 bot。 如需詳細資訊，請參閱[管理貴組織的 Microsoft 團隊設定](enable-features-office-365.md)。

目前，團隊在小組中支援個人聊天、群組聊天和頻道中的 bot。 系統管理員可以控制是否允許或禁止在 Office 365 租使用者內使用 bot。<span id="_T-Bot" class="anchor"></span>

您可以在團隊中利用社區開發的 bot。 您必須先在租使用者層級啟用 bot 的功能和上傳自訂應用程式（也稱為側載），才能正常運作。 您可以在個人聊天、群組聊天和頻道中使用機器人。 對於頻道，小組擁有者或成員可以新增機器人。

如需詳細資訊，請參閱[應用程式和服務](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)。

> [!IMPORTANT]
> 建議您不要針對除測試用途以外的任何專案，依 GUID 新增 bot。 這麼做會嚴重限制 bot 的功能。 您應該將在生產中使用的 bot 新增至團隊做為應用程式的一部分。 請參閱[建立 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create)並[測試及調試 Microsoft 團隊 bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>建立 Microsoft 團隊的自訂 bot
--------------------------------------

您可以使用 Microsoft Bot 架構，輕鬆建立與 LOB 應用程式整合的 bot。 若要瞭解如何開發及發佈自己的機器人，請參閱[建立及測試 Microsoft 團隊的 bot](https://go.microsoft.com/fwlink/?linkid=854371) 。

當您建立 bot 並將它註冊至 Bot 架構時，您可以選擇發佈它。 如果您沒有發佈，bot 會保持為私人。 您也可以在使用 bot 前，要求使用者登入。 如果需要登入，只需確認貴組織的員工就能存取 bot，即使 bot 的應用程式識別碼變成已知也一樣。 如需如何使用 bot 針對您的 Active Directory 進行驗證的程式碼範例，請參閱 GitHub 上的[*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) 。

您可以在將 bot 部署到您的小組之前，使用[Bot 架構模擬器](https://go.microsoft.com/fwlink/?linkid=854373)來測試機器人。

<a name="upload-your-bot-for-personal-chat"></a>上傳您的 bot 以進行個人聊天
---------------------------------------

1. 建立您的 bot 之後，請移至您所開發 bot 的 [**應用程式設定**]，然後在 [**應用程式設定**] 底下，複製**MicrosoftAppId**設定的值。![Bot 的 [應用程式設定] 頁面的螢幕擷取畫面](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  在 [團隊] 的 [**聊天**] 窗格中，選取 [**新增聊天] 圖示**。 在**To**中，貼上您 Bot 的**MICROSOFT 應用程式識別碼**。 ![醒目提示 [聊天] 窗格的螢幕擷取畫面，其中顯示 Microsoft 應用程式識別碼](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. 應用程式識別碼將解析到您的**bot 名稱，** 然後您就可以開始與該 bot 進行聊天交談。

<a name="upload-your-bot-for-group-chats-or-channels"></a>上傳 [群組聊天] 或 [頻道] 的 bot
-----------------------------------

如果您想要與同事共用您的 bot，以下說明如何將其新增至群組聊天或不同小組的頻道：

1. 在您[為 bot 建立應用程式套件](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)之後，請開啟 [小組]，然後流覽至您要上傳 bot 的小組。
2. 將**[應用程式製作](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)** 者、app 新增至團隊。
3. 在 App Studio 中，選取 [**資訊清單編輯器**] 索引標籤。 ![[資訊清單編輯器] 索引標籤的螢幕擷取畫面](media/Adding_Bot_To_Teams.png)
4. 若要新增您的 bot，請在 [功能] 中選取 bot，然後選擇 [新增現有的 bot]。 然後，選擇現有的 bot，或輸入現有 bot 的 Id。
![顯示選取您已建立的 bot。](media/Select_Existing_Bot.png)
5. 流覽至您的應用程式套件的位置，選取它，然後按一下 [**開啟**]。
6. 選取您 bot 的名稱。 （請不要忘記選取 [範圍] 區段底下的 [**群組聊天**] 或 [**小組**] 核取方塊）。
7. 選取 [**測試併發布**]。
8. 選取您要將 bot 連線至其中的群組聊天或團隊。

    您的 bot 將可在小組中的群組聊天或團隊中使用。
