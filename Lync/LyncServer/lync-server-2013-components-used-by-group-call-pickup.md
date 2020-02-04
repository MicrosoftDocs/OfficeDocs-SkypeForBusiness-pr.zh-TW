---
title: Lync Server 2013：由群組呼叫挑選使用的元件
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
ms.openlocfilehash: 7b9c810d5835d113a26bd3a15295f75a71552590
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="cb643-102">在 Lync Server 2013 中由群組呼叫挑選使用的元件</span><span class="sxs-lookup"><span data-stu-id="cb643-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb643-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="cb643-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="cb643-104">當您部署企業語音及通話駐留應用程式時，系統會自動部署群組通話拾取。</span><span class="sxs-lookup"><span data-stu-id="cb643-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="cb643-105">您可以透過設定 [通話駐留軌道投影片] 表格，並將指定為 [呼叫挑選] 群組數位的數位範圍分開，然後將使用者指派給他們呼叫挑選群組，並讓使用者進行群組通話挑選，來啟用群組通話。</span><span class="sxs-lookup"><span data-stu-id="cb643-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="cb643-106">下列 Lync Server 元件支援群組呼叫拾取：</span><span class="sxs-lookup"><span data-stu-id="cb643-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="cb643-107">**應用程式服務**   應用程式服務提供部署、託管及管理整合通訊應用程式（例如通話駐留應用程式）的平臺。</span><span class="sxs-lookup"><span data-stu-id="cb643-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="cb643-108">應用程式服務會自動安裝在前端池的每個前端伺服器上，以及每個標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="cb643-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="cb643-109">**通話駐留應用**   程式通話駐留應用程式是由應用程式服務託管的其中一個整合通訊應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb643-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="cb643-110">[群組呼叫挑選] 是以 [通話駐留] 應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="cb643-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="cb643-111">**Lync server 管理命令**   介面使用 lync server 管理命令介面管理群組呼叫挑選群組。</span><span class="sxs-lookup"><span data-stu-id="cb643-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="cb643-112">**SEFAUtil 資源套件工具**   您可以使用次要延伸功能啟用實用程式（SEFAUtil），將使用者指派給呼叫挑選群組，以及啟用或停用使用者的通話分揀。</span><span class="sxs-lookup"><span data-stu-id="cb643-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

