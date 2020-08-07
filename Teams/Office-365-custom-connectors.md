---
title: 使用 Microsoft 365 和自訂連接器
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
ms.openlocfilehash: e704dd6a9a796be4f9e361972cd2e6b38e48ce51
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582470"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="74621-103">在 Microsoft 團隊中使用 Microsoft 365 和自訂連接器</span><span class="sxs-lookup"><span data-stu-id="74621-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="74621-104">連接器可將經常使用的內容和服務更新直接傳送到頻道，讓您的團隊保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="74621-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="74621-105">透過連接器，您的 Microsoft 團隊使用者可以在其團隊的聊天串流內，從 Twitter、Trello、Wunderlist、GitHub 以及 Azure DevOps 服務等流行服務接收更新。</span><span class="sxs-lookup"><span data-stu-id="74621-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="74621-106">如果小組許可權允許，小組中的任何成員都可以將其小組與流行的雲端服務連線，而且所有小組成員都會收到來自該服務的活動通知。</span><span class="sxs-lookup"><span data-stu-id="74621-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="74621-107">連接器在最初設定連接器的成員已離開之後，仍能繼續運作。</span><span class="sxs-lookup"><span data-stu-id="74621-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="74621-108">任何擁有 add\remove 許可權的小組成員都可以修改其他成員的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="74621-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="74621-109">Microsoft 365 連接器可搭配 Microsoft 團隊和 Microsoft 365 群組使用，讓所有成員都能更輕鬆地保持同步並快速接收相關資訊。</span><span class="sxs-lookup"><span data-stu-id="74621-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="74621-110">Microsoft 團隊和 Exchange 都使用相同的連接器模型，這可讓您在這兩個平臺中使用相同的連接器。</span><span class="sxs-lookup"><span data-stu-id="74621-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="74621-111">不過，請注意，停用小組所依賴的 Microsoft 365 群組的連接器將會停用為該小組建立連接器的能力。</span><span class="sxs-lookup"><span data-stu-id="74621-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="74621-112">在頻道中新增連接器</span><span class="sxs-lookup"><span data-stu-id="74621-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="74621-113">目前，您可以使用 Microsoft 團隊桌面與網頁用戶端來新增連接器。</span><span class="sxs-lookup"><span data-stu-id="74621-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="74621-114">不過，您可以在**所有用戶端**（包括行動裝置）上查看透過這些連接器發佈的資訊。</span><span class="sxs-lookup"><span data-stu-id="74621-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="74621-115">若要新增連接器至頻道，請按一下頻道名稱右側的**省略號 ( ... ) \*\* ]，然後按一下 [**連接器\*\*]。</span><span class="sxs-lookup"><span data-stu-id="74621-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![已選取 [連接器] 選項的 [小組介面] 螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="74621-117">您可以從各種可用的連接器中進行選取，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="74621-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![顯示可用連接器之 [連接器] 對話方塊的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="74621-119">填入所選連接器所需的資訊，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="74621-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="74621-120">每個連接器都需要一組不同的資訊才能正常運作，而某些可能需要您使用連接器設定頁面上提供的連結登入服務。</span><span class="sxs-lookup"><span data-stu-id="74621-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS 連接器之 [設定] 頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="74621-122">連接器所提供的資料會自動發佈到頻道。</span><span class="sxs-lookup"><span data-stu-id="74621-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![[團隊] 介面的螢幕擷取畫面，顯示頻道中的交談。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="74621-124">開發自訂連接器</span><span class="sxs-lookup"><span data-stu-id="74621-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="74621-125">您也可以建立自訂連接器，以及接收和外寄 webhooks。</span><span class="sxs-lookup"><span data-stu-id="74621-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="74621-126">如需詳細資訊，請參閱我們的[開發人員文件](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。</span><span class="sxs-lookup"><span data-stu-id="74621-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
