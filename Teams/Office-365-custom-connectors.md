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
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076415"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="c7c8c-103">在 Microsoft 團隊中使用 Microsoft 365 和自訂連接器</span><span class="sxs-lookup"><span data-stu-id="c7c8c-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="c7c8c-104">連接器可將經常使用的內容和服務更新直接傳送到頻道，讓您的團隊保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="c7c8c-105">透過連接器，您的 Microsoft 團隊使用者可以在其小組中的聊天串流內，從流行服務（例如 Trello、Wunderlist、GitHub 及 Azure DevOps 服務）接收更新。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="c7c8c-106">如果小組許可權允許，小組中的任何成員都可以將其小組與流行的雲端服務連線，而且所有小組成員都會收到來自該服務的活動通知。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="c7c8c-107">連接器在最初設定連接器的成員已離開之後，仍能繼續運作。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="c7c8c-108">任何擁有 add\remove 許可權的小組成員都可以修改其他成員的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="c7c8c-109">Microsoft 365 連接器可搭配 Microsoft 團隊和 Microsoft 365 群組使用，讓所有成員都能更輕鬆地保持同步並快速接收相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="c7c8c-110">Microsoft 團隊和 Exchange 都使用相同的連接器模型，這可讓您在這兩個平臺中使用相同的連接器。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="c7c8c-111">不過，請注意，停用小組所依賴的 Microsoft 365 群組的連接器將會停用為該小組建立連接器的能力。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="c7c8c-112">在頻道中新增連接器</span><span class="sxs-lookup"><span data-stu-id="c7c8c-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="c7c8c-113">目前，您可以使用 Microsoft 團隊桌面與網頁用戶端來新增連接器。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="c7c8c-114">不過，您可以在 **所有用戶端** （包括行動裝置）上查看透過這些連接器發佈的資訊。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="c7c8c-115">若要新增連接器至頻道，請按一下頻道名稱右側的 **省略號 ( ... )** ]，然後按一下 [ **連接器**]。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c7c8c-116">![已選取 [連接器] 選項的 [小組介面] 螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="c7c8c-116">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="c7c8c-117">您可以從各種可用的連接器中進行選取，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c7c8c-118">![顯示可用連接器之 [連接器] 對話方塊的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="c7c8c-118">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="c7c8c-119">填入所選連接器所需的資訊，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="c7c8c-120">每個連接器都需要一組不同的資訊才能正常運作，而某些可能需要您使用連接器設定頁面上提供的連結登入服務。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c7c8c-121">![RSS 連接器之 [設定] 頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="c7c8c-121">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="c7c8c-122">連接器所提供的資料會自動發佈到頻道。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-122">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c7c8c-123">![[團隊] 介面的螢幕擷取畫面，顯示頻道中的交談。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="c7c8c-123">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="c7c8c-124">**連接器 URL 更新通知**</span><span class="sxs-lookup"><span data-stu-id="c7c8c-124">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="c7c8c-125">團隊連接器會轉換成新的 URL，以增強安全性。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-125">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="c7c8c-126">在此轉場期間，您會收到一些通知，以更新您設定的連接器以使用新的 URL。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-126">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="c7c8c-127">強烈建議您立即更新連接器，以避免任何對連接器服務的中斷。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-127">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="c7c8c-128">若要更新 URL，必須遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c7c8c-128">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="c7c8c-129">在 [連接器設定] 頁面上，[注意事項] 訊息會顯示在需要更新之連線的 [管理] 按鈕底下。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-129">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="c7c8c-130">![[注意事項] 訊息的螢幕擷取畫面。](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="c7c8c-130">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="c7c8c-131">對於內向 webhook 連接器，使用者只要選取 [ **更新 URL** ] 並使用新產生的 webhook URL，即可重新建立連線。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-131">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="c7c8c-132">![[更新 URL] 按鈕的螢幕擷取畫面。](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="c7c8c-132">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="c7c8c-133">針對其他連接器類型，使用者必須移除連接器，然後重新建立連接器設定。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-133">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="c7c8c-134">成功更新 URL 之後，您會看到「URL 是最新的」訊息。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-134">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="c7c8c-135">![[URL 是最新的] 訊息的螢幕擷取畫面。](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="c7c8c-135">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


<a name="develop-custom-connectors"></a><span data-ttu-id="c7c8c-136">開發自訂連接器</span><span class="sxs-lookup"><span data-stu-id="c7c8c-136">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="c7c8c-137">您也可以建立自訂連接器，以及接收和外寄 webhooks。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-137">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="c7c8c-138">如需詳細資訊，請參閱我們的[開發人員文件](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。</span><span class="sxs-lookup"><span data-stu-id="c7c8c-138">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
