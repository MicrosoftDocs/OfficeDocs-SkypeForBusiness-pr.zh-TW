---
title: 使用Microsoft 365連接器
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 連接器透過將您經常使用的服務中的內容和更新直接發送到頻道中，進而使您的團隊保持最新狀態。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3cc7bcd060caf737b23193e006dad20e316eec7
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011767"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>在 Microsoft 365 中使用自訂連接器Microsoft Teams 

連接器可直接將常用的內容和服務更新傳送至頻道，讓您的小組保持在最新狀態。 有了連接器，您的Microsoft Teams使用者就可以在其小組的聊天串流中接收來自熱門服務的更新，例如 Trello、Wunderlist、GitHub 和 Azure DevOps Services。 

如果小組許可權允許，任何小組成員都可以使用連接器將其小組連接到熱門雲端服務，而且所有小組成員都會收到該服務的活動通知。 連接器會繼續運作，即使最初設定連接器的成員已經離開。 任何具有新增\移除許可權的小組成員都可以修改其他成員的連接器設定。

Microsoft 365連接器可同時用於Microsoft Teams Microsoft 365群組，讓所有成員都更容易保持同步，並快速接收相關資訊。 兩Microsoft Teams Exchange都使用相同的連接器模型，這可讓您在兩個平臺上使用相同的連接器。 不過，值得注意的是，停用小組所依存之 Microsoft 365 群組的連接器也會停用該團隊建立連接器的能力。

> [!NOTE]
> 在政府雲端和雲端環境中，連接器Community (GCC) 停用。 如果您需要啟用，請設定 ConnectorsEnabled 或 ConnectorsEnabledForTeams 參數，$true SetOrganizationConfig Cmdlet 來設定。 您需要連接到[PowerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)

## <a name="add-a-connector-to-a-channel"></a>新增連接器至頻道

目前，您可以使用桌面和 web 用戶端Microsoft Teams連接器。 不過，這些連接器張貼的資訊可在所有用戶端 ，包括行動用戶端 **中查看** 。

1. 若要新增連接器至頻道，請按一下頻道名稱 **(...) 的** 省略號，然後按一下 [ **連接器**。

    > [!div class="mx-imgBorder"]
    > ![已選取連接器Teams介面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 您可以選取各種可用的連接器，然後按一下 [ **新增**。

    > [!div class="mx-imgBorder"]
    > ![顯示可用連接器的 [連接器」 對話方塊螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 填寫所選連接器的所需資訊，然後按一下 [ **儲存**。 每個連接器都需要各種不同的資訊，以正常運作，有些連接器可能會要求您使用連接器設定頁面上提供的連結來登錄服務。

    > [!div class="mx-imgBorder"]
    > ![RSS 連接器組組頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. 連接器提供的資料會自動張貼到頻道。

    > [!div class="mx-imgBorder"]
    > ![顯示頻道Teams交談之介面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **連接器 URL 更新通知**
>
> 連接器Teams轉換至新的 URL，以增強安全性。 在此轉換期間，您會收到特定通知，將您配置的連接器更新為使用新 URL。 強烈建議您立即更新連接器，以防止連接器服務中斷。 更新 URL 時，必須遵循下列步驟：
> 1. 在連接器組組頁面中，需要更新之連接的「管理」按鈕下會顯示「注意需要」訊息。
> ![「需要注意」訊息的螢幕擷取畫面。](media/Teams_Attention_Required_message.png)
> 2. 對於內接網頁連結連接器，使用者只要選取更新 **URL，** 然後使用新產生的 web上手 URL，即可重新建立連接。
> ![「更新 URL」按鈕的螢幕擷取畫面。](media/Teams_update_URL_button.png)
> 3. 對於其他連接器類型，使用者必須移除連接器，然後重新進行連接器組式。
> 4. 成功更新 URL 之後，您就會看到「URL 為最新」訊息。
> ![「URL 為最新」訊息的螢幕擷取畫面。](media/Teams_URL_up_to_date.png)


## <a name="develop-custom-connectors"></a>開發自訂連接器


您也可以建立自訂連接器，以及內建和外接網頁連結。 如需詳細資訊，請參閱我們的[開發人員文件](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。
