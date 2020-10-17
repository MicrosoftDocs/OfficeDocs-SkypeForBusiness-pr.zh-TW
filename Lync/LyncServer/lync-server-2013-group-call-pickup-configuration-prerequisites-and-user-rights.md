---
title: 群組呼叫收取設定必要條件和使用者權限
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
ms.openlocfilehash: 46b15be02b48c5e3f95a9b05475bea42284ec275
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498790"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="e70ef-102">Lync Server 2013 中的群組呼叫收取設定必要條件和使用者權限</span><span class="sxs-lookup"><span data-stu-id="e70ef-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e70ef-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e70ef-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e70ef-104">「群組呼叫收取」是在您部署企業語音時，預設會安裝的通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="e70ef-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e70ef-105">本主題說明您必須準備好的功能，才能設定群組呼叫收取和執行設定工作所需的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="e70ef-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="e70ef-106">本節假設您已閱讀與群組呼叫收取相關的規劃檔 (請參閱 [在 Lync Server 2013) 中規劃群組呼叫收取](lync-server-2013-planning-for-group-call-pickup.md) 。</span><span class="sxs-lookup"><span data-stu-id="e70ef-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="e70ef-107">群組呼叫收取設定必要條件</span><span class="sxs-lookup"><span data-stu-id="e70ef-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="e70ef-108">群組呼叫收取需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="e70ef-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="e70ef-109">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="e70ef-109">Application service</span></span>

  - <span data-ttu-id="e70ef-110">Call Park application</span><span class="sxs-lookup"><span data-stu-id="e70ef-110">Call Park application</span></span>

<span data-ttu-id="e70ef-111">當您部署企業語音時，會自動安裝這些元件。</span><span class="sxs-lookup"><span data-stu-id="e70ef-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="e70ef-112">群組呼叫收取設定使用者權限</span><span class="sxs-lookup"><span data-stu-id="e70ef-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="e70ef-113">您可以使用下列系統管理工具來設定群組呼叫收取：</span><span class="sxs-lookup"><span data-stu-id="e70ef-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="e70ef-114">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="e70ef-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="e70ef-115">SEFAUtil 資源套件工具</span><span class="sxs-lookup"><span data-stu-id="e70ef-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="e70ef-116">使用 Lync Server 管理命令介面來建立及管理通話駐留軌道表格中的呼叫收取群組。</span><span class="sxs-lookup"><span data-stu-id="e70ef-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="e70ef-117">使用 SEFAUtil resource 工具組工具指派呼叫收取群組，並為使用者啟用群組呼叫收取，或停用群組呼叫收取給使用者。</span><span class="sxs-lookup"><span data-stu-id="e70ef-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="e70ef-118">設定群組呼叫收取需要下列任何系統管理角色，視任務而定：</span><span class="sxs-lookup"><span data-stu-id="e70ef-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="e70ef-119">**CsVoiceAdministrator：** 此系統管理員角色可以建立、設定及管理所有語音相關設定和原則。</span><span class="sxs-lookup"><span data-stu-id="e70ef-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="e70ef-120">**CsUserAdministrator：** 此系統管理員角色可以為使用者啟用群組呼叫收取功能。</span><span class="sxs-lookup"><span data-stu-id="e70ef-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="e70ef-121">其也具有所有語音設定的唯讀檢視存取權。</span><span class="sxs-lookup"><span data-stu-id="e70ef-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="e70ef-122">**CsServerAdministrator：** 此系統管理員角色可以管理、監控及疑難排解伺服器和服務。</span><span class="sxs-lookup"><span data-stu-id="e70ef-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="e70ef-123">**CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator、CsServerAdministrator 及 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="e70ef-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e70ef-124">如需系統管理許可權的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="e70ef-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e70ef-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e70ef-125">See Also</span></span>


[<span data-ttu-id="e70ef-126">在 Lync Server 2013 中部署企業語音</span><span class="sxs-lookup"><span data-stu-id="e70ef-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="e70ef-127">在 Lync Server 2013 中規劃通話管理功能</span><span class="sxs-lookup"><span data-stu-id="e70ef-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

