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
ms.openlocfilehash: 7bd0fdbce300f417764e093fec3acb8705b2d17b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="4e61c-102">在 Lync Server 2013 中建立或編輯新聊天室</span><span class="sxs-lookup"><span data-stu-id="4e61c-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e61c-103">_**主題上次修改日期：** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="4e61c-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="4e61c-104">設定持久聊天室通常是由使用者處理;持續聊天管理員通常不會設定或管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="4e61c-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="4e61c-105">管理聊天室的 Windows PowerShell Cmdlet 只提供給**CsPersistentChatAdministrator**管理員使用。</span><span class="sxs-lookup"><span data-stu-id="4e61c-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="4e61c-106">在任何指定類別中，擁有**者**的使用者都可以使用 Lync 用戶端來建立及管理會議室。</span><span class="sxs-lookup"><span data-stu-id="4e61c-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="4e61c-107">指定為特定聊天室之管理員的使用者也可以執行會議室的持續管理，例如編輯聊天室屬性或成員資格。</span><span class="sxs-lookup"><span data-stu-id="4e61c-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4e61c-108">持續性聊天管理員也可以是創意者，而且不受限於創意者所施加的限制。</span><span class="sxs-lookup"><span data-stu-id="4e61c-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="4e61c-109">或者，如果您是永久性聊天管理員，您可以使用使用者介面來建立和管理聊天室，而不是使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4e61c-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4e61c-110">若要執行這項作業，請使用 SIP 啟用持久聊天伺服器的管理員，然後使用 Lync 用戶端來建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="4e61c-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="4e61c-111">如果您想要為使用者建立自訂會議室管理工作流程，您可以在持續聊天伺服器設定上設定**RoomManagementUrl**屬性，將使用者從 Lync 用戶端重新導向至您的自訂方案。</span><span class="sxs-lookup"><span data-stu-id="4e61c-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="4e61c-112">如需使用 Windows PowerShell 命令列介面來設定聊天室的詳細資料，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。</span><span class="sxs-lookup"><span data-stu-id="4e61c-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="4e61c-113">如需有關設定聊天室的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定會議室](lync-server-2013-configure-rooms.md)。</span><span class="sxs-lookup"><span data-stu-id="4e61c-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e61c-114">持續聊天伺服器可讓使用者建立及管理特定網站的聊天室。</span><span class="sxs-lookup"><span data-stu-id="4e61c-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="4e61c-115">不過，使用者無法在同一拓朴中建立或管理其他網站上的聊天室。</span><span class="sxs-lookup"><span data-stu-id="4e61c-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="4e61c-116">請務必為貴組織中的所有網站指定聊天室製作者和管理員。</span><span class="sxs-lookup"><span data-stu-id="4e61c-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4e61c-117">駐留在 Lync Server Survivable 分支裝置上的使用者無法建立新的聊天室，或無法查看現有聊天室的聊天室卡片。</span><span class="sxs-lookup"><span data-stu-id="4e61c-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

