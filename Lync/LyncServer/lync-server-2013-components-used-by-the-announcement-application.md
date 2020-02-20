---
title: 宣告應用程式所使用的 Lync Server 2013： 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a16690a1dee49c3b28b1f951894c216666d1eec9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="f8609-102">Lync Server 2013 中的宣告應用程式所使用的元件</span><span class="sxs-lookup"><span data-stu-id="f8609-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8609-103">_**主題上次修改日期：** 2012年-09-13_</span><span class="sxs-lookup"><span data-stu-id="f8609-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="f8609-104">在 Lync Server 2013 中，宣告應用程式是回應群組應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="f8609-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="f8609-105">當您部署企業語音時，宣告應用程式會自動安裝及啟動以及回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="f8609-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="f8609-106">本節說明支援宣告應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="f8609-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="f8609-107">宣告應用程式元件</span><span class="sxs-lookup"><span data-stu-id="f8609-107">Announcement Application Components</span></span>

<span data-ttu-id="f8609-108">宣告應用程式支援下列的 Lync Server 元件：</span><span class="sxs-lookup"><span data-stu-id="f8609-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="f8609-109">**應用程式服務**   應用程式服務提供的平台的部署，裝載，及管理整合通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="f8609-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="f8609-110">在每個前端伺服器上的前端集區中，每個 Standard Edition server 上，會自動安裝應用程式服務。</span><span class="sxs-lookup"><span data-stu-id="f8609-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="f8609-111">**回應群組應用程式**   回應群組應用程式是下列其中一個裝載的應用程式服務的整合的通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="f8609-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="f8609-112">當設定未指派的電話號碼範圍來路由傳送的通知，回應群組應用程式，才能路由傳送至電話號碼所進行的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8609-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="f8609-113">(如果已設定所有的範圍，不需要回應群組應用程式來路由傳送至 Exchange 整合通訊 (UM)。)</span><span class="sxs-lookup"><span data-stu-id="f8609-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="f8609-114">**音訊檔案**   音訊檔案用於宣告。</span><span class="sxs-lookup"><span data-stu-id="f8609-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="f8609-115">**檔案存放區**   宣告應用程式使用檔案存放區儲存其音訊檔。</span><span class="sxs-lookup"><span data-stu-id="f8609-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="f8609-116">**Lync Server Control Panel**   您可以使用 Lync Server 控制台來設定未指派號碼表。</span><span class="sxs-lookup"><span data-stu-id="f8609-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="f8609-117">**Lync Server 管理命令介面**   您可以使用 Lync Server 管理命令介面 cmdlet 來設定宣告設定和未指派號碼表。</span><span class="sxs-lookup"><span data-stu-id="f8609-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

