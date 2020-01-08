---
title: 管理聊天室
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f611b3cb6d54711557c8a172b1213127696c9b3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="81751-102">管理聊天室</span><span class="sxs-lookup"><span data-stu-id="81751-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81751-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="81751-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="81751-104">若要建立新的持續聊天伺服器機房</span><span class="sxs-lookup"><span data-stu-id="81751-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="81751-105">-如果下列其中一項為 true，則不需要 PersistentChatPoolFqdn：</span><span class="sxs-lookup"><span data-stu-id="81751-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="81751-106">只有一個持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="81751-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="81751-107">您可以將池 FQDN 提供給類別。</span><span class="sxs-lookup"><span data-stu-id="81751-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="81751-108">您提供一個 [池 FQDN] 來新增聊天室。</span><span class="sxs-lookup"><span data-stu-id="81751-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="81751-109">變更現有的持續聊天伺服器機房</span><span class="sxs-lookup"><span data-stu-id="81751-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="81751-110">Windows PowerShell：可以同時設定成員、管理員與簡報者。</span><span class="sxs-lookup"><span data-stu-id="81751-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="81751-111">它們都應該是主機類別的 AllowedMembers 減去 DeniedMembers 子集。</span><span class="sxs-lookup"><span data-stu-id="81751-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="81751-112">類型 = normal 的聊天室不能包含簡報者。</span><span class="sxs-lookup"><span data-stu-id="81751-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="81751-113">建立、取得、設定、清除或移除聊天室</span><span class="sxs-lookup"><span data-stu-id="81751-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="81751-114">若要建立新的聊天室</span><span class="sxs-lookup"><span data-stu-id="81751-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="81751-115">若要設定會議室</span><span class="sxs-lookup"><span data-stu-id="81751-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="81751-116">取得聊天室</span><span class="sxs-lookup"><span data-stu-id="81751-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="81751-117">或</span><span class="sxs-lookup"><span data-stu-id="81751-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="81751-118">where –篩選只支援名稱和描述，並可協助您尋找名稱/描述項合關鍵字字串的聊天室。</span><span class="sxs-lookup"><span data-stu-id="81751-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="81751-119">PoolFqdn 在指定的持續聊天伺服器池中搜尋。</span><span class="sxs-lookup"><span data-stu-id="81751-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="81751-120">清除聊天室並清除聊天室中的訊息</span><span class="sxs-lookup"><span data-stu-id="81751-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="81751-121">或</span><span class="sxs-lookup"><span data-stu-id="81751-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="81751-122">移除會議室</span><span class="sxs-lookup"><span data-stu-id="81751-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="81751-123">或</span><span class="sxs-lookup"><span data-stu-id="81751-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

