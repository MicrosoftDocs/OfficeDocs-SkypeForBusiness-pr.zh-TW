---
title: Lync Server 2013：回應群組使用的元件
description: Lync Server 2013：回應群組使用的元件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a1e916d9e4bf986bf0337a6f1f1dd918ff2772e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571699"
---
# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="ede31-103">Lync Server 2013 中回應群組使用的元件</span><span class="sxs-lookup"><span data-stu-id="ede31-103">Components used by Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ede31-104">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="ede31-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ede31-105">當您部署企業語音時，回應群組應用程式會自動啟用。</span><span class="sxs-lookup"><span data-stu-id="ede31-105">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ede31-106">本節說明支援回應群組應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="ede31-106">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="ede31-107">回應群組元件</span><span class="sxs-lookup"><span data-stu-id="ede31-107">Response Group Components</span></span>

<span data-ttu-id="ede31-108">下列 Microsoft Lync Server 2013 元件支援回應群組應用程式：</span><span class="sxs-lookup"><span data-stu-id="ede31-108">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="ede31-109">**應用程式服務**    Application service 提供一個平臺，用以部署、裝載和管理整合通訊應用程式，例如回應群組。</span><span class="sxs-lookup"><span data-stu-id="ede31-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="ede31-110">應用程式服務會自動安裝在前端集區和每個 Standard Edition server 上的每一部前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ede31-110">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="ede31-111">**回應群組應用程式**    回應群組應用程式是由應用程式服務主控的整合通訊應用程式之一。</span><span class="sxs-lookup"><span data-stu-id="ede31-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="ede31-112">當您部署回應群組時，會自動包含它。</span><span class="sxs-lookup"><span data-stu-id="ede31-112">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="ede31-113">回應群組應用程式會將傳入的呼叫路由傳送至代理群組。</span><span class="sxs-lookup"><span data-stu-id="ede31-113">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="ede31-114">**語言套件**    需要有語言套件，才能支援文字語音轉換和語音辨識。</span><span class="sxs-lookup"><span data-stu-id="ede31-114">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="ede31-115">在您設定訊息 (如歡迎訊息與其他提示) 以及互動式語音回應 (IVR) 的問題與回答時，都會用到這些語音技術。</span><span class="sxs-lookup"><span data-stu-id="ede31-115">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="ede31-116">根據預設，當您部署 Lync Server 2013 時，會安裝26個支援的語言套件。</span><span class="sxs-lookup"><span data-stu-id="ede31-116">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="ede31-117">**音訊檔**    音訊檔案用於郵件和等候音樂。</span><span class="sxs-lookup"><span data-stu-id="ede31-117">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="ede31-118">**檔存放區**    回應群組會使用檔案存放區來儲存音訊檔。</span><span class="sxs-lookup"><span data-stu-id="ede31-118">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="ede31-119">多個回應群組集區可以使用相同的檔案存放區實例。</span><span class="sxs-lookup"><span data-stu-id="ede31-119">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="ede31-120">**回應群組設定工具**    回應群組設定工具是用來建立和設定回應群組的 web 式工具。</span><span class="sxs-lookup"><span data-stu-id="ede31-120">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="ede31-121">當您安裝 Web 服務時，會包含回應群組設定工具。</span><span class="sxs-lookup"><span data-stu-id="ede31-121">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="ede31-122">**Microsoft Lync Server 2013 控制台**    您可以使用 Lync Server 控制台來設定和設定回應群組的代理人群組和佇列。</span><span class="sxs-lookup"><span data-stu-id="ede31-122">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="ede31-123">**Lync Server 管理命令**     介面您可以使用 Lync Server 管理命令介面 Cmdlet 來設定所有回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="ede31-123">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="ede31-124">**Microsoft Lync 2013**    正式代理 (代理程式必須先登入群組，才可接受群組的呼叫) 使用 Lync 2013 登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="ede31-124">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="ede31-125">如果代理群組是針對正式代理程式設定，則代理程式會按一下 Lync 2013 中的功能表項目，以開啟 Internet Explorer，並顯示網頁主控台以供登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="ede31-125">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="ede31-126">**Web 服務**    回應群組設定工具、代理程式的登入和登出主控台、Lync Server 控制台及回應群組用戶端 web 服務是必要的 web 服務。</span><span class="sxs-lookup"><span data-stu-id="ede31-126">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="ede31-127">**回應群組用戶端 Web 服務**    回應群組應用程式提供用戶端 web 服務，可供協力廠商應用程式使用，以取得代理程式、代理群組成員資格、代理登入狀態、群組的通話狀態，以及支援匿名呼叫的群組的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ede31-127">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="ede31-128">Lync 2013 和 Lync 2010 語音應答使用回應群組用戶端 Web 服務，以取得代理人可用於進行匿名呼叫的回應群組清單。</span><span class="sxs-lookup"><span data-stu-id="ede31-128">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="ede31-129">用戶端 Web 服務會在您安裝 Web 服務時納入。</span><span class="sxs-lookup"><span data-stu-id="ede31-129">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

