---
title: 在 Microsoft 團隊中使用 Office 365 和自訂連接器
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: 連接器可提供您經常直接在頻道中使用之服務的內容和更新, 讓您的團隊保持最新狀態。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce087aed26c22fb97a0ad9b5161927f6a6afea4d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184419"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="d7a3e-103">在 Microsoft 團隊中使用 Office 365 和自訂連接器</span><span class="sxs-lookup"><span data-stu-id="d7a3e-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="d7a3e-104">連接器可將經常使用的內容和服務更新直接傳送到頻道, 讓您的團隊保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="d7a3e-105">透過連接器, 您的 Microsoft 團隊使用者可以在其團隊的聊天串流內, 從 Twitter、Trello、Wunderlist、GitHub 以及 Azure DevOps 服務等流行服務接收更新。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="d7a3e-106">如果小組許可權允許, 小組中的任何成員都可以將其小組與流行的雲端服務連線, 而且所有小組成員都會收到來自該服務的活動通知。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="d7a3e-107">連接器在最初設定連接器的成員已離開之後, 仍能繼續運作。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="d7a3e-108">任何擁有 add\remove 許可權的小組成員都可以修改其他成員的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="d7a3e-109">Office 365 連接器可搭配 Microsoft 團隊和 Office 365 群組使用, 讓所有成員都能更輕鬆地保持同步並快速取得相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="d7a3e-110">Microsoft 團隊和 Exchange 都使用相同的連接器模型, 這可讓您在這兩個平臺中使用相同的連接器。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="d7a3e-111">不過, 請注意, 針對小組所依賴的 Office 365 群組停用連接器, 也會停用為該小組建立連接器的能力。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="d7a3e-112">在頻道中新增連接器</span><span class="sxs-lookup"><span data-stu-id="d7a3e-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="d7a3e-113">目前, 您可以使用 Microsoft 團隊桌面與網頁用戶端來新增連接器。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="d7a3e-114">不過, 您可以在**所有用戶端**(包括行動裝置) 上查看透過這些連接器發佈的資訊。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="d7a3e-115">若要新增連接器至頻道, 請按一下頻道名稱右側的**省略號 (...)** , 然後按一下 [**連接器**]。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![已選取 [連接器] 選項的 [小組介面] 螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="d7a3e-117">您可以從各種可用的連接器中進行選取, 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![顯示可用連接器之 [連接器] 對話方塊的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="d7a3e-119">填入所選連接器所需的資訊, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="d7a3e-120">每個連接器都需要一組不同的資訊才能正常運作, 而某些可能需要您使用連接器設定頁面上提供的連結登入服務。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS 連接器之 [設定] 頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="d7a3e-122">連接器所提供的資料會自動發佈到頻道。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![[團隊] 介面的螢幕擷取畫面, 顯示頻道中的交談。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="d7a3e-124">開發自訂連接器</span><span class="sxs-lookup"><span data-stu-id="d7a3e-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="d7a3e-125">開發可與您的企業運營 (LOB) 應用程式整合的自訂連接器相當容易。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="d7a3e-126">您可以使用內建的**內向 Webhook**連接器來建立通道的端點, 以使用 HTTP post 方法從任何應用程式提取資料。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="d7a3e-127">新增**傳入 Webhook** , 就像任何其他連接器一樣。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![新增內向 Webhook 連接器之選項的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="d7a3e-129">若要建立 Webhook, 請指定**名稱**、更新 Webhook 影像 (如果有必要的話), 然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![傳入 Webhook 連接器之 [設定] 頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="d7a3e-131">將資料推送到此通道的應用程式需要 Webhook 連接器 URL。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="d7a3e-132">建立 Webhook 時會建立唯一的 URL。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="d7a3e-133">與您的開發人員共用此 URL, 讓他們可以根據需要將其應用程式設定成推入資料。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Webhook 之唯一 URL 的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="d7a3e-135">當外部應用程式將資料推入連接器時, 該訊息會顯示在通道交談清單中, 作為一封稱為**連接器卡片**訊息的特殊訊息。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![顯示連接器卡片訊息之 [小組] 介面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="d7a3e-137">開發人員可以使用簡單的 JSON 負載傳送 HTTP 要求至團隊的 Webhook 位址 (這是由嚮導提供的那一個端點的唯一 URL), 來設定應用程式來建立這些卡片。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="d7a3e-138">請您的開發人員參考 Microsoft 開發人員網路上的[Office 365 連接器](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), 其中包含詳細指示與連接器範例。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="d7a3e-139">其他資源包括[將 app 連線到 Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)和[Office 開發人員中心-Microsoft 團隊](https://go.microsoft.com/fwlink/?linkid=855784)中的群組。</span><span class="sxs-lookup"><span data-stu-id="d7a3e-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
