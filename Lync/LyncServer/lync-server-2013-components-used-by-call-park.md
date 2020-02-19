---
title: 通話保留所使用的 Lync Server 2013： 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4a833736368fe6060dad4fbb62e6a528e91b6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="0fa39-102">Lync Server 2013 中的通話保留所使用的元件</span><span class="sxs-lookup"><span data-stu-id="0fa39-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fa39-103">_**主題上次修改日期：** 2012年-09-13_</span><span class="sxs-lookup"><span data-stu-id="0fa39-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="0fa39-104">當您部署企業語音時，會自動安裝的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="0fa39-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0fa39-105">您可以設定語音原則，以啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="0fa39-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="0fa39-106">通話駐留應用程式支援下列的 Lync Server 2013 元件：</span><span class="sxs-lookup"><span data-stu-id="0fa39-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="0fa39-107">**應用程式服務**   應用程式服務提供的平台的部署，裝載，及管理整合通訊應用程式，例如通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="0fa39-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="0fa39-108">在每個前端伺服器上的前端集區中，每個 Standard Edition server 上，會自動安裝應用程式服務。</span><span class="sxs-lookup"><span data-stu-id="0fa39-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="0fa39-109">**通話駐留應用程式**   通話駐留應用程式是下列其中一個裝載的應用程式服務的整合的通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="0fa39-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="0fa39-110">自動當您部署企業語音時，它是包含在內。</span><span class="sxs-lookup"><span data-stu-id="0fa39-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0fa39-111">通話駐留公園與擷取通話，並管理通話駐留軌道。</span><span class="sxs-lookup"><span data-stu-id="0fa39-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="0fa39-112">**等候音樂上保留檔案**   駐留通話時，如果音樂中的啟用，播放音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="0fa39-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="0fa39-113">通話駐留應用程式已安裝時，包含預設的等候音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="0fa39-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="0fa39-114">**檔案存放區**   通話駐留應用程式會使用檔案存放區來保留自訂音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="0fa39-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="0fa39-115">**Lync Server Control Panel**   設定通話駐留軌道表，並為使用者啟用通話駐留，您可以使用 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="0fa39-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="0fa39-116">**Lync Server 管理命令介面**   可以使用 Lync Server 管理命令介面指令程式執行所有通話駐留應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="0fa39-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

