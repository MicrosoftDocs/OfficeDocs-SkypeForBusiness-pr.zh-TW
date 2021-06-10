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
ms.openlocfilehash: 77b1c99847ca35de51af5e062593a29c18e98999
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855792"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="62c08-103">在 Microsoft 365 中使用自訂連接器Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="62c08-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="62c08-104">連接器可直接將常用的內容和服務更新傳送至頻道，讓您的小組保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="62c08-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="62c08-105">有了連接器，Microsoft Teams使用者就可以在其小組的聊天串流中接收來自熱門服務的更新，例如 Trello、Wunderlist、GitHub 和 Azure DevOps Services。</span><span class="sxs-lookup"><span data-stu-id="62c08-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="62c08-106">如果小組許可權允許，任何小組成員都可以使用連接器將其小組連接到熱門雲端服務，而且所有小組成員都會收到該服務的活動通知。</span><span class="sxs-lookup"><span data-stu-id="62c08-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="62c08-107">連接器會繼續運作，即使最初設定連接器的成員已經離開。</span><span class="sxs-lookup"><span data-stu-id="62c08-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="62c08-108">任何具有新增\移除許可權的小組成員都可以修改其他成員的連接器設定。</span><span class="sxs-lookup"><span data-stu-id="62c08-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="62c08-109">Microsoft 365連接器可同時用於Microsoft Teams Microsoft 365群組，讓所有成員更容易保持同步，並快速接收相關資訊。</span><span class="sxs-lookup"><span data-stu-id="62c08-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members to stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="62c08-110">兩Microsoft Teams Exchange都使用相同的連接器模型，這可讓您在兩個平臺上使用相同的連接器。</span><span class="sxs-lookup"><span data-stu-id="62c08-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="62c08-111">不過，值得注意的是，停用小組所依存之 Microsoft 365 群組的連接器也會停用該團隊建立連接器的能力。</span><span class="sxs-lookup"><span data-stu-id="62c08-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> [!NOTE]
> <span data-ttu-id="62c08-112">連接器預設會停用GCC環境。</span><span class="sxs-lookup"><span data-stu-id="62c08-112">Connectors are disabled by default in GCC environments.</span></span> <span data-ttu-id="62c08-113">如果您需要啟用，請設定 ConnectorsEnabled 或 ConnectorsEnabledForTeams 參數，$true [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) Cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="62c08-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet.</span></span> <span data-ttu-id="62c08-114">您先前需要[連接到 powerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="62c08-114">You previously need to [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="62c08-115">根據預設，在政府雲端和環境中，連接器Community (GCC) 停用。</span><span class="sxs-lookup"><span data-stu-id="62c08-115">Connectors are disabled by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="62c08-116">如果您需要啟用，請設定 ConnectorsEnabled 或 ConnectorsEnabledForTeams 參數，$true [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) Cmdlet 設定。</span><span class="sxs-lookup"><span data-stu-id="62c08-116">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="62c08-117">您先前需要連接到[PowerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="62c08-117">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="62c08-118">新增連接器至頻道</span><span class="sxs-lookup"><span data-stu-id="62c08-118">Add a connector to a channel</span></span>

<span data-ttu-id="62c08-119">目前，您可以使用桌面和 web 用戶端Microsoft Teams連接器。</span><span class="sxs-lookup"><span data-stu-id="62c08-119">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="62c08-120">不過，這些連接器張貼的資訊可在所有用戶端 ，包括行動用戶端 **中查看** 。</span><span class="sxs-lookup"><span data-stu-id="62c08-120">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="62c08-121">若要新增連接器至頻道，請按一下頻道名稱 **(...) 的** 省略號，然後按一下 [ **連接器**。</span><span class="sxs-lookup"><span data-stu-id="62c08-121">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="62c08-122">![已選取連接器Teams介面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="62c08-122">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="62c08-123">您可以選取各種可用的連接器，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="62c08-123">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="62c08-124">![顯示可用連接器的 [連接器」 對話方塊螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="62c08-124">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="62c08-125">填寫所選連接器的所需資訊，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="62c08-125">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="62c08-126">每個連接器都需要各種不同的資訊，以正常運作，有些連接器可能會要求您使用連接器設定頁面上提供的連結來登錄服務。</span><span class="sxs-lookup"><span data-stu-id="62c08-126">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="62c08-127">![RSS 連接器組組頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="62c08-127">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="62c08-128">連接器提供的資料會自動張貼到頻道。</span><span class="sxs-lookup"><span data-stu-id="62c08-128">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="62c08-129">![顯示頻道Teams交談之介面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="62c08-129">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="62c08-130">**連接器 URL 更新通知**</span><span class="sxs-lookup"><span data-stu-id="62c08-130">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="62c08-131">連接器Teams轉換至新的 URL，以增強安全性。</span><span class="sxs-lookup"><span data-stu-id="62c08-131">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="62c08-132">在此轉換期間，您會收到特定通知，將您配置的連接器更新為使用新 URL。</span><span class="sxs-lookup"><span data-stu-id="62c08-132">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="62c08-133">強烈建議您立即更新連接器，以防止連接器服務中斷。</span><span class="sxs-lookup"><span data-stu-id="62c08-133">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="62c08-134">更新 URL 時，必須遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="62c08-134">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="62c08-135">在連接器組組頁面中，需要更新之連接的 「管理」按鈕下會顯示「注意需要」訊息。</span><span class="sxs-lookup"><span data-stu-id="62c08-135">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="62c08-136">![「需要注意」訊息的螢幕擷取畫面。](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="62c08-136">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="62c08-137">對於內接網頁連結連接器，使用者只要選取更新 **URL，** 然後使用新產生的 web上手 URL，即可重新建立連接。</span><span class="sxs-lookup"><span data-stu-id="62c08-137">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="62c08-138">![「更新 URL」按鈕的螢幕擷取畫面。](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="62c08-138">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="62c08-139">對於其他連接器類型，使用者必須移除連接器，然後重新進行連接器組式。</span><span class="sxs-lookup"><span data-stu-id="62c08-139">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="62c08-140">成功更新 URL 之後，您就會看到「URL 為最新」訊息。</span><span class="sxs-lookup"><span data-stu-id="62c08-140">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="62c08-141">![「URL 為最新」訊息的螢幕擷取畫面。](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="62c08-141">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="62c08-142">開發自訂連接器</span><span class="sxs-lookup"><span data-stu-id="62c08-142">Develop custom connectors</span></span>


<span data-ttu-id="62c08-143">您也可以建立自訂連接器，以及內建和外接網頁連結。</span><span class="sxs-lookup"><span data-stu-id="62c08-143">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="62c08-144">如需詳細資訊，請參閱我們的[開發人員文件](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。</span><span class="sxs-lookup"><span data-stu-id="62c08-144">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
