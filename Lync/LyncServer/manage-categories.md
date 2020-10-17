---
title: 管理類別
description: 管理類別。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf335b96c455647ebeb665364944e15d2e463fbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545929"
---
# <a name="manage-categories"></a><span data-ttu-id="451b8-103">管理類別</span><span class="sxs-lookup"><span data-stu-id="451b8-103">Manage categories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="451b8-104">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="451b8-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="451b8-105">若要建立新的持久聊天伺服器類別</span><span class="sxs-lookup"><span data-stu-id="451b8-105">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="451b8-106">只有有一個以上的 Persistent Chat Server 集區時，才需要 PersistentChatPoolFqdn。</span><span class="sxs-lookup"><span data-stu-id="451b8-106">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="451b8-107">若要變更現有的持久聊天伺服器類別</span><span class="sxs-lookup"><span data-stu-id="451b8-107">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="451b8-108">可以同時設定 Windows PowerShell: AllowedMembers、DeniedMembers 及建立者。</span><span class="sxs-lookup"><span data-stu-id="451b8-108">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="451b8-109">Creators 應為 AllowedMembers 扣除 DeniedMembers 的子集。</span><span class="sxs-lookup"><span data-stu-id="451b8-109">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="451b8-110">您也可以在設定成員和建立者同時設定類別的內容。</span><span class="sxs-lookup"><span data-stu-id="451b8-110">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="451b8-111">建立、取得、設定或移除類別</span><span class="sxs-lookup"><span data-stu-id="451b8-111">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="451b8-112">若要建立新類別</span><span class="sxs-lookup"><span data-stu-id="451b8-112">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="451b8-113">若要取得類別</span><span class="sxs-lookup"><span data-stu-id="451b8-113">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="451b8-114">或</span><span class="sxs-lookup"><span data-stu-id="451b8-114">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="451b8-115">若要設定類別</span><span class="sxs-lookup"><span data-stu-id="451b8-115">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="451b8-116">或</span><span class="sxs-lookup"><span data-stu-id="451b8-116">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="451b8-117">若要移除類別</span><span class="sxs-lookup"><span data-stu-id="451b8-117">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="451b8-118">或</span><span class="sxs-lookup"><span data-stu-id="451b8-118">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

