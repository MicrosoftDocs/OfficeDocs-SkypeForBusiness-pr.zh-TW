---
title: 管理類別
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c07c143bf74084042a937d0f5bb0c65f3ec73835
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a><span data-ttu-id="0abba-102">管理類別</span><span class="sxs-lookup"><span data-stu-id="0abba-102">Manage categories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0abba-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="0abba-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0abba-104">若要建立新常設聊天室伺服器的類別</span><span class="sxs-lookup"><span data-stu-id="0abba-104">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0abba-105">如果有多個 Persistent Chat Server 集區，需要 PersistentChatPoolFqdn。</span><span class="sxs-lookup"><span data-stu-id="0abba-105">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="0abba-106">若要變更的現有常設聊天室伺服器分類</span><span class="sxs-lookup"><span data-stu-id="0abba-106">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="0abba-107">Windows PowerShell: AllowedMembers、 DeniedMembers，以及建立者可以同時設定。</span><span class="sxs-lookup"><span data-stu-id="0abba-107">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="0abba-108">Creators 應為 AllowedMembers 扣除 DeniedMembers 的子集。</span><span class="sxs-lookup"><span data-stu-id="0abba-108">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="0abba-109">您也可以在設定成員和建立者同時設定類別的內容。</span><span class="sxs-lookup"><span data-stu-id="0abba-109">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="0abba-110">建立、取得、設定或移除類別</span><span class="sxs-lookup"><span data-stu-id="0abba-110">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="0abba-111">若要建立新類別</span><span class="sxs-lookup"><span data-stu-id="0abba-111">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="0abba-112">若要取得類別</span><span class="sxs-lookup"><span data-stu-id="0abba-112">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="0abba-113">或</span><span class="sxs-lookup"><span data-stu-id="0abba-113">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="0abba-114">若要設定類別</span><span class="sxs-lookup"><span data-stu-id="0abba-114">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="0abba-115">或</span><span class="sxs-lookup"><span data-stu-id="0abba-115">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="0abba-116">若要移除類別</span><span class="sxs-lookup"><span data-stu-id="0abba-116">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="0abba-117">或</span><span class="sxs-lookup"><span data-stu-id="0abba-117">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

