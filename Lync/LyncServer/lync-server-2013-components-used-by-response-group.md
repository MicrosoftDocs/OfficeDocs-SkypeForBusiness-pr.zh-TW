---
title: Lync Server 2013：回應群組使用的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f52ceb18c355f6d867b5b3b4485434df83683d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="e1dfa-102">Lync Server 2013 中回應群組使用的元件</span><span class="sxs-lookup"><span data-stu-id="e1dfa-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1dfa-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e1dfa-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e1dfa-104">當您部署企業語音時，系統會自動啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e1dfa-105">本節將說明支援回應群組應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="e1dfa-106">回應群組元件</span><span class="sxs-lookup"><span data-stu-id="e1dfa-106">Response Group Components</span></span>

<span data-ttu-id="e1dfa-107">下列 Microsoft Lync Server 2013 元件支援回應群組應用程式：</span><span class="sxs-lookup"><span data-stu-id="e1dfa-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="e1dfa-108">**應用程式服務**   應用程式服務提供部署、託管及管理整合通訊應用程式（例如回應群組）的平臺。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="e1dfa-109">應用程式服務會自動安裝在前端池的每個前端伺服器上，以及每個標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="e1dfa-110">**回應群組應用**   程式：回應群組應用程式是由應用程式服務託管的其中一個整合通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="e1dfa-111">當您部署回應群組時，系統會自動包含此檔案。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="e1dfa-112">回應群組應用程式會將來電路由及佇列傳送給代理群組。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="e1dfa-113">**語言套件**   需要語言套件才能支援文字轉換語音和語音辨識。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="e1dfa-114">當您設定郵件時，會使用這些語音技術，例如歡迎訊息及其他提示，以及互動式語音回應（IVR）問題與解答。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="e1dfa-115">根據預設，當您部署 Lync Server 2013 時，會安裝26個支援的語言套件。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="e1dfa-116">**音訊**檔案是用於郵件和等候音樂。   </span><span class="sxs-lookup"><span data-stu-id="e1dfa-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="e1dfa-117">\*\*\*\*    [檔案存放] 回應群組使用 [檔案存放區] 儲存音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="e1dfa-118">多個回應群組池可以使用相同的檔案存放區實例。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="e1dfa-119">**[回應群組**   設定] 工具： [回應群組設定] 工具是用來建立及設定回應群組的 web 型工具。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="e1dfa-120">當您安裝 Web 服務時，系統會隨附 [回應群組設定] 工具。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="e1dfa-121">**Microsoft lync server 2013 [控制台**   ] 您可以使用 Lync server [控制台] 來設定及設定回應群組的代理程式群組和佇列。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="e1dfa-122">**Lync server 管理命令**   介面：您可以使用 Lync server 管理命令介面 Cmdlet 來設定所有回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="e1dfa-123">**Microsoft Lync 2013**   正式代理（需要登入群組才能接受群組呼叫的工程師），請使用 Lync 2013 登入群組並登出。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="e1dfa-124">如果為正式代理程式設定了代理群組，則代理程式會按一下 Lync 2013 中的功能表項目來開啟 Internet Explorer，並顯示可登入和登出群組的網頁主控台。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="e1dfa-125">\*\*\*\*    在回應群組設定工具、代理程式的登入和登出主控台、Lync Server 控制台及回應群組用戶端 Web 服務中，都需要 web services web 服務。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="e1dfa-126">**回應群組用戶端 web 服務**   回應群組應用程式會提供用戶端 web 服務，這可以由協力廠商應用程式用來取得代理程式、代理群組成員資格、代理登入狀態的相關資訊、呼叫群組的狀態，以及支援匿名呼叫的群組。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="e1dfa-127">Lync 2013 和 Lync 2010 的人員使用回應群組用戶端 Web 服務來取得回應群組清單，讓代理程式可以用來進行匿名通話。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="e1dfa-128">當您安裝 Web 服務時，會包含用戶端 web 服務。</span><span class="sxs-lookup"><span data-stu-id="e1dfa-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

