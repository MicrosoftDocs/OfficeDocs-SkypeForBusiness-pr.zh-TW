---
title: Lync Server 2013：建立或編輯新聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f0abaf45034918873a17adc8a0f396ddc5d6fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516840"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="f7b0b-102">在 Lync Server 2013 中建立或編輯新聊天室</span><span class="sxs-lookup"><span data-stu-id="f7b0b-102">Creating or editing a new room in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7b0b-103">_**主題上次修改日期：** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="f7b0b-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="f7b0b-104">設定 Persistent 聊天室通常是由使用者處理;Persistent Chat 系統管理員通常不會設定或管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="f7b0b-105">管理聊天室的 Windows PowerShell Cmdlet 僅可供 **CsPersistentChatAdministrator** 系統管理員使用。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="f7b0b-106">屬於任何特定類別之建立 **者** 的使用者可以使用 Lync 用戶端來建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="f7b0b-107">指定為特定聊天室管理員的使用者也可以執行會議室的持續管理，例如編輯會議室屬性或成員資格。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f7b0b-108">Persistent Chat 系統管理員也可以是建立者，且不受限於建立者的限制。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="f7b0b-109">（選用）如果您是 Persistent Chat 系統管理員，可以使用使用者介面來建立及管理聊天室，而不是使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="f7b0b-110">若要這麼做，SIP 會為持久聊天伺服器啟用系統管理員，然後使用 Lync 用戶端來建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="f7b0b-111">如果您想要為使用者建立自訂聊天室管理工作流程，您可以設定 Persistent Chat Server 設定上的 **RoomManagementUrl** 屬性，將使用者重新導向至您在 Lync 用戶端的自訂解決方案。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="f7b0b-112">如需使用 Windows PowerShell 命令列介面設定聊天室的詳細資訊，請參閱 [使用 windows PowerShell Cmdlet 設定 Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="f7b0b-113">如需有關設定聊天室的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定聊天室](lync-server-2013-configure-rooms.md) 。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7b0b-114">Persistent Chat Server 可讓使用者為特定網站建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="f7b0b-115">不過，使用者無法在相同的拓撲中建立或管理其他網站上的聊天室。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="f7b0b-116">請務必為您組織中的所有網站指定聊天室建立者和主管。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f7b0b-117">在 Lync Server Survivable Branch 裝置上的使用者無法建立新聊天室或查看現有聊天室的會議室卡片。</span><span class="sxs-lookup"><span data-stu-id="f7b0b-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

