---
title: 在 Microsoft 團隊中進行 eDiscovery 調查內容
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 瞭解當您需要提交以電子形式儲存的法律訴訟資訊時, 要採取的動作。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54ccb21e33c6acc1747023fc7c3eb174040d5746
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181602"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="69f7f-103">在 Microsoft 團隊中進行 eDiscovery 調查內容</span><span class="sxs-lookup"><span data-stu-id="69f7f-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="69f7f-104">大型企業通常會面臨大量要求提交所有以電子方式儲存資訊 (ESI) 的法律訴訟。</span><span class="sxs-lookup"><span data-stu-id="69f7f-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="69f7f-105">所有團隊1:1 或群組聊天都會在各個使用者的信箱中進行歸檔, 而所有通道訊息都會在代表小組的群組信箱中傳送。</span><span class="sxs-lookup"><span data-stu-id="69f7f-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="69f7f-106">上傳的檔案包含在 SharePoint Online 和商務用 OneDrive 的 eDiscovery 功能底下。</span><span class="sxs-lookup"><span data-stu-id="69f7f-106">Files uploaded are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

1.  <span data-ttu-id="69f7f-107">若要使用 Microsoft 團隊內容進行 eDiscovery 調查, 請參閱[此](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)連結中的步驟1。</span><span class="sxs-lookup"><span data-stu-id="69f7f-107">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="69f7f-108">Microsoft 團隊資料會以 IM 或交談的方式顯示在 Excel eDiscovery 匯出輸出中, 而且您可以裝載。[PST] (Outlook) 來查看匯出後的郵件。</span><span class="sxs-lookup"><span data-stu-id="69f7f-108">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="69f7f-109">裝載時。針對團隊的 PST, 請注意, 所有交談都會保留在 [交談記錄] 底下的 [小組聊天] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="69f7f-109">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="69f7f-110">郵件標題會對應到 [小組] 和 [頻道]。</span><span class="sxs-lookup"><span data-stu-id="69f7f-110">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="69f7f-111">從 [查看] 下方的影像, 您可以看到來自 Bob 的訊息, messaged 製造規格小組的專案7頻道。</span><span class="sxs-lookup"><span data-stu-id="69f7f-111">From reviewing the image below, you can see this message from Bob who messaged the Project 7 channel of the Manufacturing Specs team.</span></span>

    ![Outlook 中使用者信箱的小組聊天資料夾螢幕擷取畫面](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="69f7f-113">若要查看使用者信箱中的私人聊天, 他們也位於 [交談歷程記錄] 底下的 [小組聊天] 資料夾內。</span><span class="sxs-lookup"><span data-stu-id="69f7f-113">To see private chats in a user’s Mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="69f7f-114">電子檔探索訪客與來賓聊天</span><span class="sxs-lookup"><span data-stu-id="69f7f-114">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="69f7f-115">若沒有信箱, 來賓對訪客的聊天 (沒有家用租使用者的1xN 聊天) 就不會被編制索引, 因此也不會包含在 eDiscovery 中。</span><span class="sxs-lookup"><span data-stu-id="69f7f-115">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="69f7f-116">若要協助電子檔探索以進行來賓對訪客聊天, 會建立一個雲端信箱 (或幻影信箱) 來儲存1xN 資料。</span><span class="sxs-lookup"><span data-stu-id="69f7f-116">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="69f7f-117">在將團隊聊天資料儲存在雲端型信箱之後, 就會針對 eDiscovery 與合規性內容搜尋編制索引。</span><span class="sxs-lookup"><span data-stu-id="69f7f-117">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="69f7f-118">下圖顯示 eDiscovery 如何針對沒有信箱的來賓對訪客聊天進行運作。</span><span class="sxs-lookup"><span data-stu-id="69f7f-118">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![來賓-訪客-聊天-無信箱](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
