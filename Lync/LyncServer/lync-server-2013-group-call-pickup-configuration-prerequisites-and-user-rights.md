---
title: 群組呼叫收取組態先決條件和使用者權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d0127ff5c196c14dc7844c6958ced9ae5478113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="2dda3-102">群組呼叫收取組態先決條件和 Lync Server 2013 中的使用者權限</span><span class="sxs-lookup"><span data-stu-id="2dda3-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dda3-103">_**上次修改主題：** 2013年-01-30_</span><span class="sxs-lookup"><span data-stu-id="2dda3-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="2dda3-104">群組來電接聽是當您部署企業語音時，會將預設安裝的通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="2dda3-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="2dda3-105">本主題說明您需要備妥之前您可以設定群組來電接聽與您需要先執行組態工作的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="2dda3-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="2dda3-106">本節假設您已閱讀群組來電接聽與相關的規劃文件 （請參閱[Planning for Lync Server 2013 中的 [群組來電接聽](lync-server-2013-planning-for-group-call-pickup.md)）。</span><span class="sxs-lookup"><span data-stu-id="2dda3-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="2dda3-107">群組通話收取組態先決條件</span><span class="sxs-lookup"><span data-stu-id="2dda3-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="2dda3-108">群組來電接聽需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="2dda3-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="2dda3-109">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="2dda3-109">Application service</span></span>

  - <span data-ttu-id="2dda3-110">Call Park application</span><span class="sxs-lookup"><span data-stu-id="2dda3-110">Call Park application</span></span>

<span data-ttu-id="2dda3-111">當您部署企業語音時，都會自動安裝這些元件。</span><span class="sxs-lookup"><span data-stu-id="2dda3-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="2dda3-112">群組通話收取設定使用者權限</span><span class="sxs-lookup"><span data-stu-id="2dda3-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="2dda3-113">您可以使用下列系統管理工具來設定群組來電接聽：</span><span class="sxs-lookup"><span data-stu-id="2dda3-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="2dda3-114">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="2dda3-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="2dda3-115">SEFAUtil resource kit 工具</span><span class="sxs-lookup"><span data-stu-id="2dda3-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="2dda3-116">使用 Lync Server 管理命令介面來建立及管理通話駐留軌道表中的呼叫收取群組。</span><span class="sxs-lookup"><span data-stu-id="2dda3-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="2dda3-117">使用 SEFAUtil resource kit 工具，來指派通話收取群組，並為使用者啟用群組來電接聽或停用使用者的群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="2dda3-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="2dda3-118">設定群組來電接聽需要下列管理角色，根據任務的任何項目：</span><span class="sxs-lookup"><span data-stu-id="2dda3-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="2dda3-119">**CsVoiceAdministrator:** 此系統管理員角色可以建立、 設定及管理所有語音相關設定和原則。</span><span class="sxs-lookup"><span data-stu-id="2dda3-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="2dda3-120">**CsUserAdministrator:** 此系統管理員角色可以針對使用者啟用群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="2dda3-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="2dda3-121">其也具有所有語音設定的唯讀檢視存取權。</span><span class="sxs-lookup"><span data-stu-id="2dda3-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="2dda3-122">**CsServerAdministrator:** 此系統管理員角色可以管理、 監控及疑難排解伺服器和服務。</span><span class="sxs-lookup"><span data-stu-id="2dda3-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="2dda3-123">**CsAdministrator:** 此系統管理員角色可以執行所有 CsVoiceAdministrator、 CsServerAdministrator 和 CsUserAdministrator 的工作。</span><span class="sxs-lookup"><span data-stu-id="2dda3-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2dda3-124">如需系統管理權限的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</A>。</span><span class="sxs-lookup"><span data-stu-id="2dda3-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2dda3-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2dda3-125">See Also</span></span>


[<span data-ttu-id="2dda3-126">部署 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="2dda3-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="2dda3-127">規劃 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="2dda3-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

