---
title: Lync Server 2013：通話駐留所使用的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f74161230504ee3f24ed19780e0a62ad4e7d08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="35ee0-102">Lync Server 2013 中通話駐留所使用的元件</span><span class="sxs-lookup"><span data-stu-id="35ee0-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ee0-103">_**主題上次修改日期：** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="35ee0-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="35ee0-104">當您部署企業語音時，會自動安裝通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="35ee0-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="35ee0-105">您可以透過設定語音原則來啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="35ee0-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="35ee0-106">下列 Lync Server 2013 元件支援通話駐留應用程式：</span><span class="sxs-lookup"><span data-stu-id="35ee0-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="35ee0-107">**應用程式服務**   應用程式服務提供部署、託管及管理整合通訊應用程式（例如通話駐留應用程式）的平臺。</span><span class="sxs-lookup"><span data-stu-id="35ee0-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="35ee0-108">應用程式服務會自動安裝在前端池的每個前端伺服器上，以及每個標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="35ee0-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="35ee0-109">**通話駐留應用**   程式通話駐留應用程式是由應用程式服務託管的其中一個整合通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="35ee0-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="35ee0-110">當您部署企業語音時，系統會自動包含此檔案。</span><span class="sxs-lookup"><span data-stu-id="35ee0-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="35ee0-111">通話駐留公園並檢索來電，並管理通話駐留軌道式。</span><span class="sxs-lookup"><span data-stu-id="35ee0-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="35ee0-112">**[音樂封存-**   檔案] 如果 [啟用中的音樂]，音樂檔案會在通話暫停時播放。</span><span class="sxs-lookup"><span data-stu-id="35ee0-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="35ee0-113">安裝通話公園應用程式時，會包含預設的音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="35ee0-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="35ee0-114">**檔案存放區**   通話駐留應用程式使用檔案存放區來儲存自訂音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="35ee0-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="35ee0-115">**Lync server [控制台**   ] 您可以使用 lync server [控制台] 來設定 [通話駐留軌道] 表格，並為使用者啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="35ee0-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="35ee0-116">**Lync server management shell**   ：您可以使用 lync server 管理命令介面 Cmdlet 來執行所有通話駐留應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="35ee0-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

