---
title: 防止服務的工作階段
description: 防止服務的會話。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563689"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="0a75c-103">防止服務的工作階段</span><span class="sxs-lookup"><span data-stu-id="0a75c-103">Prevent sessions for services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a75c-104">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="0a75c-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="0a75c-105">您可以使用 Microsoft Lync Server 2010 控制台，以防止在特定電腦上執行的所有 Lync Server 2010 服務的新會話，或阻止特定 Lync Server 2010 服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="0a75c-105">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="0a75c-106">阻止所有 Lync Server 服務的新工作階段於電腦上執行</span><span class="sxs-lookup"><span data-stu-id="0a75c-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="0a75c-107">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0a75c-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="0a75c-108">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="0a75c-108">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="0a75c-109">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="0a75c-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="0a75c-110">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="0a75c-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="0a75c-111">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="0a75c-111">Click **Action**.</span></span>

6.  <span data-ttu-id="0a75c-112">按一下 **[阻止對所有服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="0a75c-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="0a75c-113">阻止特定服務的新工作階段</span><span class="sxs-lookup"><span data-stu-id="0a75c-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="0a75c-114">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0a75c-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="0a75c-115">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="0a75c-115">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="0a75c-116">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="0a75c-116">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="0a75c-117">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="0a75c-117">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="0a75c-118">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="0a75c-118">Click **Properties**.</span></span>

6.  <span data-ttu-id="0a75c-119">視需要排序服務清單，然後按一下要阻止新工作階段的服務。</span><span class="sxs-lookup"><span data-stu-id="0a75c-119">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="0a75c-120">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="0a75c-120">Click **Action**.</span></span>

8.  <span data-ttu-id="0a75c-121">按一下 **[阻止對服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="0a75c-121">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="0a75c-122">按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="0a75c-122">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

