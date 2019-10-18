---
title: 在 Microsoft 團隊中使用 Office 365 和自訂連接器
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: 連接器可提供您經常直接在頻道中使用之服務的內容和更新，讓您的團隊保持最新狀態。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1dc57bbe3d216ee779f962ef4b2fc1152e2161
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569840"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>在 Microsoft 團隊中使用 Office 365 和自訂連接器
=======================================================

連接器可將經常使用的內容和服務更新直接傳送到頻道，讓您的團隊保持在最新狀態。 透過連接器，您的 Microsoft 團隊使用者可以在其團隊的聊天串流內，從 Twitter、Trello、Wunderlist、GitHub 以及 Azure DevOps 服務等流行服務接收更新。

如果小組許可權允許，小組中的任何成員都可以將其小組與流行的雲端服務連線，而且所有小組成員都會收到來自該服務的活動通知。 連接器在最初設定連接器的成員已離開之後，仍能繼續運作。 任何擁有 add\remove 許可權的小組成員都可以修改其他成員的連接器設定。

Office 365 連接器可搭配 Microsoft 團隊和 Office 365 群組使用，讓所有成員都能更輕鬆地保持同步並快速取得相關資訊。 Microsoft 團隊和 Exchange 都使用相同的連接器模型，這可讓您在這兩個平臺中使用相同的連接器。 不過，請注意，針對小組所依賴的 Office 365 群組停用連接器，也會停用為該小組建立連接器的能力。

<a name="add-a-connector-to-a-channel"></a>在頻道中新增連接器
----------------------------

目前，您可以使用 Microsoft 團隊桌面與網頁用戶端來新增連接器。 不過，您可以在**所有用戶端**（包括行動裝置）上查看透過這些連接器發佈的資訊。

1. 若要新增連接器至頻道，請按一下頻道名稱右側的**省略號（...）** ，然後按一下 [**連接器**]。

    ![已選取 [連接器] 選項的 [小組介面] 螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 您可以從各種可用的連接器中進行選取，然後按一下 [**新增**]。

    ![顯示可用連接器之 [連接器] 對話方塊的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 填入所選連接器所需的資訊，然後按一下 [**儲存**]。 每個連接器都需要一組不同的資訊才能正常運作，而某些可能需要您使用連接器設定頁面上提供的連結登入服務。

    ![RSS 連接器之 [設定] 頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. 連接器所提供的資料會自動發佈到頻道。

    ![[團隊] 介面的螢幕擷取畫面，顯示頻道中的交談。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>開發自訂連接器
-----------------------------

開發可與您的企業運營（LOB）應用程式整合的自訂連接器相當容易。 您可以使用內建的**內向 Webhook**連接器來建立通道的端點，以使用 HTTP post 方法從任何應用程式提取資料。

1. 新增**傳入 Webhook** ，就像任何其他連接器一樣。

    ![新增內向 Webhook 連接器之選項的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. 若要建立 Webhook，請指定**名稱**、更新 Webhook 影像（如果有必要的話），然後按一下 [**建立**]。

    ![傳入 Webhook 連接器之 [設定] 頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. 將資料推送到此通道的應用程式需要 Webhook 連接器 URL。 建立 Webhook 時會建立唯一的 URL。 與您的開發人員共用此 URL，讓他們可以根據需要將其應用程式設定成推入資料。

    ![Webhook 之唯一 URL 的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. 當外部應用程式將資料推入連接器時，該訊息會顯示在通道交談清單中，作為一封稱為**連接器卡片**訊息的特殊訊息。

    ![顯示連接器卡片訊息之 [小組] 介面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     開發人員可以使用簡單的 JSON 負載傳送 HTTP 要求至團隊的 Webhook 位址（這是由嚮導提供的那一個端點的唯一 URL），來設定應用程式來建立這些卡片。 請您的開發人員參考 Microsoft 開發人員網路上的[Office 365 連接器](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors)，其中包含詳細指示與連接器範例。 其他資源包括[將 app 連線到 Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)和[Office 開發人員中心-Microsoft 團隊](https://go.microsoft.com/fwlink/?linkid=855784)中的群組。
