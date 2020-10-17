---
title: 群組呼叫收取設定必要條件和使用者權限
description: 群組呼叫收取設定必要條件和使用者權限。
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
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554449"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="7c7a6-103">Lync Server 2013 中的群組呼叫收取設定必要條件和使用者權限</span><span class="sxs-lookup"><span data-stu-id="7c7a6-103">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c7a6-104">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="7c7a6-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="7c7a6-105">「群組呼叫收取」是在您部署企業語音時，預設會安裝的通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-105">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="7c7a6-106">本主題說明您必須準備好的功能，才能設定群組呼叫收取和執行設定工作所需的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-106">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="7c7a6-107">本節假設您已閱讀與群組呼叫收取相關的規劃檔 (請參閱 [在 Lync Server 2013) 中規劃群組呼叫收取](lync-server-2013-planning-for-group-call-pickup.md) 。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-107">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="7c7a6-108">群組呼叫收取設定必要條件</span><span class="sxs-lookup"><span data-stu-id="7c7a6-108">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="7c7a6-109">群組呼叫收取需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="7c7a6-109">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="7c7a6-110">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="7c7a6-110">Application service</span></span>

  - <span data-ttu-id="7c7a6-111">Call Park application</span><span class="sxs-lookup"><span data-stu-id="7c7a6-111">Call Park application</span></span>

<span data-ttu-id="7c7a6-112">當您部署企業語音時，會自動安裝這些元件。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-112">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="7c7a6-113">群組呼叫收取設定使用者權限</span><span class="sxs-lookup"><span data-stu-id="7c7a6-113">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="7c7a6-114">您可以使用下列系統管理工具來設定群組呼叫收取：</span><span class="sxs-lookup"><span data-stu-id="7c7a6-114">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="7c7a6-115">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="7c7a6-115">Lync Server Management Shell</span></span>

  - <span data-ttu-id="7c7a6-116">SEFAUtil 資源套件工具</span><span class="sxs-lookup"><span data-stu-id="7c7a6-116">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="7c7a6-117">使用 Lync Server 管理命令介面來建立及管理通話駐留軌道表格中的呼叫收取群組。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-117">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="7c7a6-118">使用 SEFAUtil resource 工具組工具指派呼叫收取群組，並為使用者啟用群組呼叫收取，或停用群組呼叫收取給使用者。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-118">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="7c7a6-119">設定群組呼叫收取需要下列任何系統管理角色，視任務而定：</span><span class="sxs-lookup"><span data-stu-id="7c7a6-119">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="7c7a6-120">**CsVoiceAdministrator：** 此系統管理員角色可以建立、設定及管理所有語音相關設定和原則。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-120">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="7c7a6-121">**CsUserAdministrator：** 此系統管理員角色可以為使用者啟用群組呼叫收取功能。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-121">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="7c7a6-122">其也具有所有語音設定的唯讀檢視存取權。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-122">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="7c7a6-123">**CsServerAdministrator：** 此系統管理員角色可以管理、監控及疑難排解伺服器和服務。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-123">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="7c7a6-124">**CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator、CsServerAdministrator 及 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-124">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7c7a6-125">如需系統管理許可權的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="7c7a6-125">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c7a6-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7c7a6-126">See Also</span></span>


[<span data-ttu-id="7c7a6-127">在 Lync Server 2013 中部署企業語音</span><span class="sxs-lookup"><span data-stu-id="7c7a6-127">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="7c7a6-128">在 Lync Server 2013 中規劃通話管理功能</span><span class="sxs-lookup"><span data-stu-id="7c7a6-128">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

