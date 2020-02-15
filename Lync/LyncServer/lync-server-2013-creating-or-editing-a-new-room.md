---
title: Lync Server 2013： 建立或編輯新聊天室
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
ms.openlocfilehash: c445513cf112b335ce900ab8e39660210f0b5ef4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="af4c6-102">建立或編輯新聊天室 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="af4c6-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af4c6-103">_**主題上次修改日期：** 2015年-03-19_</span><span class="sxs-lookup"><span data-stu-id="af4c6-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="af4c6-104">設定常設聊天室的使用者; 通常用於常設聊天室管理員通常不設定或管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="af4c6-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="af4c6-105">Windows PowerShell cmdlet 來管理聊天室僅**CsPersistentChatAdministrator**系統管理員可用。</span><span class="sxs-lookup"><span data-stu-id="af4c6-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="af4c6-106">在任何指定的類別中**建立者**的使用者可用於建立及管理聊天室的 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="af4c6-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="af4c6-107">已指定為特定聊天室管理員的使用者也可以執行會議室，例如編輯會議室內容或成員資格的持續進行的管理。</span><span class="sxs-lookup"><span data-stu-id="af4c6-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="af4c6-108">常設聊天室系統管理員也可以建立者，並不受限制之規範。</span><span class="sxs-lookup"><span data-stu-id="af4c6-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="af4c6-109">（選用） 如果您是常設聊天室管理員，您可以運用使用者介面，以建立及管理聊天室，而不是使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af4c6-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="af4c6-110">若要這麼做，Persistent Chat Server，並再使用 Lync 用戶端建立及管理聊天室管理員啟用 SIP 功能。</span><span class="sxs-lookup"><span data-stu-id="af4c6-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="af4c6-111">如果您想要建立自訂聊天室管理工作流程為您的使用者，您可以在您將使用者重新導向至您的自訂解決方案從 Lync 用戶端的 Persistent Chat Server 組態設定**roommanagementurl** 。</span><span class="sxs-lookup"><span data-stu-id="af4c6-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="af4c6-112">如需使用 Windows PowerShell 命令列介面來設定聊天室的詳細資訊，請參閱[使用 Windows PowerShell cmdlet 的 Configuring Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 「 聊天室管理 」。</span><span class="sxs-lookup"><span data-stu-id="af4c6-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="af4c6-113">如需設定聊天室的詳細資訊，請參閱部署文件中的[Lync Server 2013 中的 Configure rooms](lync-server-2013-configure-rooms.md) 。</span><span class="sxs-lookup"><span data-stu-id="af4c6-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af4c6-114">Persistent Chat Server 可讓使用者建立及管理特定網站的聊天室。</span><span class="sxs-lookup"><span data-stu-id="af4c6-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="af4c6-115">使用者無法，不過，建立或管理在相同拓撲內其他網站上的聊天室。</span><span class="sxs-lookup"><span data-stu-id="af4c6-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="af4c6-116">請務必指定聊天室建立者及管理員在組織中的所有網站。</span><span class="sxs-lookup"><span data-stu-id="af4c6-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="af4c6-117">位於 Lync Server Survivable Branch Appliance 的使用者將無法建立新聊天室或檢視現有的會議室的會議室卡片。</span><span class="sxs-lookup"><span data-stu-id="af4c6-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

