---
title: Lync Server 2013：宣告應用程式所使用的元件
description: Lync Server 2013：宣告應用程式所使用的元件。
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
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577689"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="5e146-103">Lync Server 2013 的宣告應用程式所使用的元件</span><span class="sxs-lookup"><span data-stu-id="5e146-103">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e146-104">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="5e146-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="5e146-105">在 Lync Server 2013 中，宣告應用程式是回應群組應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="5e146-105">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="5e146-106">當您部署企業語音時，會自動安裝宣告應用程式，並隨回應群組應用程式一起啟用。</span><span class="sxs-lookup"><span data-stu-id="5e146-106">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="5e146-107">本節說明支援宣告應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="5e146-107">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="5e146-108">宣告應用程式元件</span><span class="sxs-lookup"><span data-stu-id="5e146-108">Announcement Application Components</span></span>

<span data-ttu-id="5e146-109">下列 Lync Server 元件支援宣告應用程式：</span><span class="sxs-lookup"><span data-stu-id="5e146-109">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="5e146-110">**應用程式服務**    Application service 提供平臺，用以部署、裝載和管理整合通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e146-110">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="5e146-111">應用程式服務會自動安裝在前端集區和每個 Standard Edition server 上的每一部前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="5e146-111">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="5e146-112">**回應群組應用程式**    回應群組應用程式是由應用程式服務主控的整合通訊應用程式之一。</span><span class="sxs-lookup"><span data-stu-id="5e146-112">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="5e146-113">當未指派的電話號碼範圍設定為路由傳送至宣告時，需要回應群組應用程式，才能將撥打給電話號碼的電話傳送給電話號碼。</span><span class="sxs-lookup"><span data-stu-id="5e146-113">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="5e146-114">如果所有範圍都設定為路由傳送至 Exchange 整合通訊 (UM) ，則不需要 (回應群組應用程式。 ) </span><span class="sxs-lookup"><span data-stu-id="5e146-114">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="5e146-115">**音訊檔**    音訊檔案用於宣告。</span><span class="sxs-lookup"><span data-stu-id="5e146-115">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="5e146-116">**檔存放區**    宣告應用程式會使用檔案存放區儲存其音訊檔。</span><span class="sxs-lookup"><span data-stu-id="5e146-116">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="5e146-117">**Lync Server 控制台**    您可以使用 Lync Server 控制台設定未指派的號碼表。</span><span class="sxs-lookup"><span data-stu-id="5e146-117">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="5e146-118">**Lync Server 管理命令**     介面您可以使用 Lync Server 管理命令介面 Cmdlet 來設定宣告設定及未指派號碼表格。</span><span class="sxs-lookup"><span data-stu-id="5e146-118">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

