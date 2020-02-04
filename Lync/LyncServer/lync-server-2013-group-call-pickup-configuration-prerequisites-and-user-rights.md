---
title: 群組呼叫裝貨配置先決條件與使用者權利
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
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="27984-102">Lync Server 2013 中的群組呼叫裝貨配置先決條件和使用者權利</span><span class="sxs-lookup"><span data-stu-id="27984-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27984-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="27984-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="27984-104">[群組通話挑選] 是在您部署企業語音時預設安裝的通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="27984-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="27984-105">本主題描述您必須具備的位置，才能設定群組呼叫拾取，以及執行設定工作所需的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="27984-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="27984-106">本節假設您已閱讀與群組通話相關的規劃檔（請參閱[在 Lync Server 2013 中規劃群組通話挑選](lync-server-2013-planning-for-group-call-pickup.md)）。</span><span class="sxs-lookup"><span data-stu-id="27984-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="27984-107">群組呼叫裝貨配置先決條件</span><span class="sxs-lookup"><span data-stu-id="27984-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="27984-108">群組呼叫挑選需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="27984-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="27984-109">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="27984-109">Application service</span></span>

  - <span data-ttu-id="27984-110">通話駐留應用程式</span><span class="sxs-lookup"><span data-stu-id="27984-110">Call Park application</span></span>

<span data-ttu-id="27984-111">當您部署企業語音時，系統會自動安裝這些元件。</span><span class="sxs-lookup"><span data-stu-id="27984-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="27984-112">群組通話配置使用者權利</span><span class="sxs-lookup"><span data-stu-id="27984-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="27984-113">您可以使用下列管理工具來設定群組呼叫挑選：</span><span class="sxs-lookup"><span data-stu-id="27984-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="27984-114">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="27984-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="27984-115">SEFAUtil 資源套件工具</span><span class="sxs-lookup"><span data-stu-id="27984-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="27984-116">使用 Lync Server 管理命令介面在 [通話駐留軌道] 表格中建立和管理呼叫挑選群組。</span><span class="sxs-lookup"><span data-stu-id="27984-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="27984-117">使用 SEFAUtil 資源套件工具指派呼叫挑選群組，並為使用者啟用群組呼叫分揀，或停用群組呼叫給使用者。</span><span class="sxs-lookup"><span data-stu-id="27984-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="27984-118">設定群組呼叫挑選需要下列任何系統管理角色，視任務而定：</span><span class="sxs-lookup"><span data-stu-id="27984-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="27984-119">**CsVoiceAdministrator：** 此系統管理員角色可以建立、設定及管理所有語音相關設定與原則。</span><span class="sxs-lookup"><span data-stu-id="27984-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="27984-120">**CsUserAdministrator：** 此系統管理員角色可以為使用者啟用群組呼叫分揀。</span><span class="sxs-lookup"><span data-stu-id="27984-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="27984-121">此系統管理員角色也具有所有語音設定的唯讀視圖存取權。</span><span class="sxs-lookup"><span data-stu-id="27984-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="27984-122">**CsServerAdministrator：** 這個系統管理員角色可以管理、監視及疑難排解伺服器與服務。</span><span class="sxs-lookup"><span data-stu-id="27984-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="27984-123">**CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="27984-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="27984-124">如需系統管理權利的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。</span><span class="sxs-lookup"><span data-stu-id="27984-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27984-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="27984-125">See Also</span></span>


[<span data-ttu-id="27984-126">在 Lync Server 2013 中部署企業版語音</span><span class="sxs-lookup"><span data-stu-id="27984-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="27984-127">規劃 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="27984-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

