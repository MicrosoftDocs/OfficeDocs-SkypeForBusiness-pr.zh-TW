---
title: Lync Server 2013：群組呼叫收取所使用的元件
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
ms.openlocfilehash: 062dc114534abb7d2a011c31b9747c2d6a0a45bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502360"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="5dc20-102">Lync Server 2013 中群組呼叫收取所使用的元件</span><span class="sxs-lookup"><span data-stu-id="5dc20-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dc20-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5dc20-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5dc20-104">當您部署企業語音和通話駐留應用程式時，會自動部署群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="5dc20-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="5dc20-105">您可以將通話駐留軌道表設定為呼叫收取群組的號碼，然後指派使用者呼叫收取群組，並為使用者啟用群組通話收取，以啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="5dc20-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="5dc20-106">下列 Lync Server 元件支援群組呼叫收取：</span><span class="sxs-lookup"><span data-stu-id="5dc20-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="5dc20-107">**應用程式服務**    Application service 提供平臺，用來部署、裝載和管理整合通訊應用程式，例如通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="5dc20-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="5dc20-108">應用程式服務會自動安裝在前端集區和每個 Standard Edition server 上的每一部前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="5dc20-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="5dc20-109">**通話駐留應用程式**    通話駐留應用程式是由應用程式服務主控的整合通訊應用程式之一。</span><span class="sxs-lookup"><span data-stu-id="5dc20-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="5dc20-110">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="5dc20-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="5dc20-111">**Lync Server 管理命令**     介面您可以使用 Lync Server 管理命令介面來管理群組呼叫收取群組。</span><span class="sxs-lookup"><span data-stu-id="5dc20-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="5dc20-112">**SEFAUtil 資源套件工具**    您可以使用 [次要分機] 功能啟用實用程式 (SEFAUtil) 指派使用者至來電收取群組，以及啟用或停用使用者的電話收取。</span><span class="sxs-lookup"><span data-stu-id="5dc20-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

