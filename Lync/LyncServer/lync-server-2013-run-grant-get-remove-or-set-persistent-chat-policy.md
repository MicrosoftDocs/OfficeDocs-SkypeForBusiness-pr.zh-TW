---
title: Lync Server 2013：執行、授與、取得、移除或設定常設聊天室原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run, grant, get, remove, or set Persistent Chat Policy
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204810(v=OCS.15)
ms:contentKeyID: 48183857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48f07207387a27701041f3decc36417b4cb30b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-grant-get-remove-or-set-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="b04f2-102">在 Lync Server 2013 中執行、授與、取得、移除或設定常設聊天室原則</span><span class="sxs-lookup"><span data-stu-id="b04f2-102">Run, grant, get, remove, or set Persistent Chat Policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b04f2-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b04f2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b04f2-104">建立新的持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="b04f2-104">To create a new Persistent Chat policy</span></span>

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

<span data-ttu-id="b04f2-105">若要准許永久聊天原則</span><span class="sxs-lookup"><span data-stu-id="b04f2-105">To grant Persistent Chat policy</span></span>

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="b04f2-106">取得持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="b04f2-106">To get Persistent Chat policy</span></span>

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

<span data-ttu-id="b04f2-107">移除持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="b04f2-107">To remove Persistent Chat policy</span></span>

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="b04f2-108">設定持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="b04f2-108">To set Persistent Chat policy</span></span>

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

</div>

<span> </span>

</div>

</div>

</div>

