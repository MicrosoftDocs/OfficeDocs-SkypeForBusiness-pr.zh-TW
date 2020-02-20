---
title: Lync Server 2013： 執行、 授與、 取得、 移除或設定常設聊天室原則
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
ms.openlocfilehash: 85f28c4a358c0ccb09b62c7d453746f3a5570763
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-grant-get-remove-or-set-persistent-chat-policy-in-lync-server-2013"></a>執行、 授與、 取得、 移除或 Lync Server 2013 中設定常設聊天室原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

若要建立新的常設聊天室原則

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

若要授與常設聊天室原則

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

若要取得的常設聊天室原則

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

若要移除常設聊天室原則

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

若要設定常設聊天室原則

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

</div>

<span> </span>

</div>

</div>

</div>

