---
title: Lync Server 2013：設定 Persistent Chat Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a9661c3e9695bde240225b7d0bcd8ca1e54df09
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520440"
---
# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="05a8a-102">在 Lync Server 2013 中設定 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="05a8a-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05a8a-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="05a8a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="05a8a-104">若要建立新的持久聊天設定</span><span class="sxs-lookup"><span data-stu-id="05a8a-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="05a8a-105">若要取得持續聊天設定</span><span class="sxs-lookup"><span data-stu-id="05a8a-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="05a8a-106">移除持續聊天設定</span><span class="sxs-lookup"><span data-stu-id="05a8a-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="05a8a-107">設定 Persistent Chat 設定</span><span class="sxs-lookup"><span data-stu-id="05a8a-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="05a8a-108">對於 Lync Server 2013，Lync Server 2013，前端伺服器支援所有 web 服務流量。</span><span class="sxs-lookup"><span data-stu-id="05a8a-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="05a8a-109">因此，不需要在 Persistent Chat Server 上的 gcweb01 位址。</span><span class="sxs-lookup"><span data-stu-id="05a8a-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="05a8a-110">我們仍然支援內部 web 服務存取，因為我們只會對 *內部* 網站提供檔案上傳/下載 web 服務，而不是 () 遠端使用者的 *外部* 網站。</span><span class="sxs-lookup"><span data-stu-id="05a8a-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

