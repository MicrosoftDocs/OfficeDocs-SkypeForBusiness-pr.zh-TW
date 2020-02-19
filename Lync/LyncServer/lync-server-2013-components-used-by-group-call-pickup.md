---
title: 群組來電接聽所使用的 Lync Server 2013： 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05f41b7420f15c2815ababa0f85d8aca43898dd2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="03b99-102">群組來電接聽 Lync Server 2013 中所使用的元件</span><span class="sxs-lookup"><span data-stu-id="03b99-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03b99-103">_**上次修改主題：** 2013年-01-30_</span><span class="sxs-lookup"><span data-stu-id="03b99-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="03b99-104">當您部署企業語音和通話駐留應用程式時，會自動部署群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="03b99-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="03b99-105">您啟用群組來電接聽通話駐留軌道表使用設定為通話收取群組數字，及指定的數字的個別範圍然後所指派到呼叫收取群組的使用者，然後為使用者啟用群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="03b99-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="03b99-106">群組來電接聽支援下列的 Lync Server 元件：</span><span class="sxs-lookup"><span data-stu-id="03b99-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="03b99-107">**應用程式服務**   應用程式服務提供的平台的部署，裝載，及管理整合通訊應用程式，例如通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="03b99-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="03b99-108">在每個前端伺服器上的前端集區中，每個 Standard Edition server 上，會自動安裝應用程式服務。</span><span class="sxs-lookup"><span data-stu-id="03b99-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="03b99-109">**通話駐留應用程式**   通話駐留應用程式是下列其中一個裝載的應用程式服務的整合的通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="03b99-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="03b99-110">群組來電接聽為基礎的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="03b99-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="03b99-111">**Lync Server 管理命令介面**   您使用 Lync Server 管理命令介面來管理群組來電接聽群組。</span><span class="sxs-lookup"><span data-stu-id="03b99-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="03b99-112">**SEFAUtil resource kit 工具**   呼叫收取群組指派給使用者和要啟用或停用使用者的來電接聽使用次要分機功能啟用公用程式 (SEFAUtil)。</span><span class="sxs-lookup"><span data-stu-id="03b99-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

