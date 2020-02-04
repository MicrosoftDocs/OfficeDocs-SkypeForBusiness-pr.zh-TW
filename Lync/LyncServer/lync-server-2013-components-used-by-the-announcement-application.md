---
title: Lync Server 2013：宣告應用程式所使用的元件
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
ms.openlocfilehash: 52ef0b1da665f8797f29582e9ce9e1d311287d61
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="44202-102">Lync Server 2013 中的宣告應用程式所使用的元件</span><span class="sxs-lookup"><span data-stu-id="44202-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44202-103">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="44202-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="44202-104">在 Lync Server 2013 中，宣告應用程式是回應群組應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="44202-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="44202-105">當您部署企業語音時，宣告應用程式會自動安裝並與回應群組應用程式一起啟用。</span><span class="sxs-lookup"><span data-stu-id="44202-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="44202-106">本節說明支援宣告應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="44202-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="44202-107">宣告應用程式元件</span><span class="sxs-lookup"><span data-stu-id="44202-107">Announcement Application Components</span></span>

<span data-ttu-id="44202-108">下列 Lync 伺服器元件支援宣告應用程式：</span><span class="sxs-lookup"><span data-stu-id="44202-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="44202-109">**應用程式服務**   應用程式服務提供部署、託管及管理整合通訊應用程式的平臺。</span><span class="sxs-lookup"><span data-stu-id="44202-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="44202-110">應用程式服務會自動安裝在前端池的每個前端伺服器上，以及每個標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="44202-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="44202-111">**回應群組應用**   程式：回應群組應用程式是由應用程式服務託管的其中一個整合通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="44202-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="44202-112">當未指派的電話號碼範圍設定為傳送給宣告時，必須使用回應群組申請，才能傳送電話號碼所撥的通話。</span><span class="sxs-lookup"><span data-stu-id="44202-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="44202-113">（如果所有範圍都設定為路由到 Exchange 整合通訊（UM），則不需要回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="44202-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="44202-114">**音訊**檔案是用來進行宣告的。   </span><span class="sxs-lookup"><span data-stu-id="44202-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="44202-115">**檔案存放**   ：宣告應用程式會使用檔案存放區來儲存其音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="44202-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="44202-116">**Lync server [控制台**   ] 您可以使用 lync server [控制台] 來設定 [未指定的數位] 資料表。</span><span class="sxs-lookup"><span data-stu-id="44202-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="44202-117">**Lync server 管理命令**   介面：您可以使用 lync server 管理命令介面 Cmdlet 來設定宣告設定和未指定的數位資料表。</span><span class="sxs-lookup"><span data-stu-id="44202-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

