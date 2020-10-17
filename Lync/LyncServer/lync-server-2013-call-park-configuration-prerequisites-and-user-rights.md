---
title: Lync Server 2013：通話駐留設定必要條件和使用者權限
description: Lync Server 2013：通話駐留設定必要條件和使用者權限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01187ad32fa7338765c0fa5b409b4e185e8ad35
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563529"
---
# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="07496-103">Lync Server 2013 中的通話駐留設定必要條件和使用者權限</span><span class="sxs-lookup"><span data-stu-id="07496-103">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07496-104">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="07496-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="07496-105">通話駐留是當您部署企業語音時，預設會安裝的通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="07496-105">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="07496-106">本主題說明您必須準備好的功能，才能設定通話駐留和執行設定工作所需的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="07496-106">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07496-107">通話駐留應用程式的自訂封存暫止檔案不會做為 Lync Server 2013 嚴重損壞修復程式的一部分，而且如果上傳至集區的檔案損毀、損毀或清除，檔案也會遺失。</span><span class="sxs-lookup"><span data-stu-id="07496-107">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="07496-108">請永遠為通話保留，保留您為通話保留所上傳之自訂音樂暫止檔案的個別備份副本。</span><span class="sxs-lookup"><span data-stu-id="07496-108">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="07496-109">本節假設您已閱讀與通話駐留相關的規劃檔 (請參閱 [在 Lync Server 2013) 中規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="07496-109">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="07496-110">通話駐留設定必要條件</span><span class="sxs-lookup"><span data-stu-id="07496-110">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="07496-111">通話駐留需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="07496-111">Call Park requires the following components:</span></span>

  - <span data-ttu-id="07496-112">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="07496-112">Application service</span></span>

  - <span data-ttu-id="07496-113">Call Park application</span><span class="sxs-lookup"><span data-stu-id="07496-113">Call Park application</span></span>

<span data-ttu-id="07496-114">當您部署企業語音時，會自動安裝這些元件。</span><span class="sxs-lookup"><span data-stu-id="07496-114">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="07496-115">如果希望來電者在通話駐留時可以聽到音樂，則需要等候音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="07496-115">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="07496-116">當您部署企業語音時，會自動安裝預設的等候音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="07496-116">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="07496-117">您可以用自己的等候音樂檔案取代預設檔案。</span><span class="sxs-lookup"><span data-stu-id="07496-117">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="07496-118">通話駐留使用檔案存放區以保留音訊檔。</span><span class="sxs-lookup"><span data-stu-id="07496-118">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="07496-119">通話駐留設定使用者權限</span><span class="sxs-lookup"><span data-stu-id="07496-119">Call Park Configuration User Rights</span></span>

<span data-ttu-id="07496-120">您可以使用下列系統管理工具來設定通話駐留：</span><span class="sxs-lookup"><span data-stu-id="07496-120">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="07496-121">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="07496-121">Lync Server Control Panel</span></span>

  - <span data-ttu-id="07496-122">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="07496-122">Lync Server Management Shell</span></span>

<span data-ttu-id="07496-123">您可以使用這些工具來設定通話駐留軌道表格，並設定通話駐留使用的其他設定。</span><span class="sxs-lookup"><span data-stu-id="07496-123">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="07496-124">設定通話駐留需要下列任何系統管理角色，視任務而定：</span><span class="sxs-lookup"><span data-stu-id="07496-124">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="07496-125">**CsVoiceAdministrator：** 此系統管理員角色可以建立、設定及管理所有語音相關設定和原則。</span><span class="sxs-lookup"><span data-stu-id="07496-125">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="07496-126">**CsUserAdministrator：** 此系統管理員角色可以啟用語音原則中的通話駐留。</span><span class="sxs-lookup"><span data-stu-id="07496-126">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="07496-127">其也具有所有語音設定的唯讀檢視存取權。</span><span class="sxs-lookup"><span data-stu-id="07496-127">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="07496-128">**CsServerAdministrator：** 此系統管理員角色可以管理、監控及疑難排解伺服器和服務。</span><span class="sxs-lookup"><span data-stu-id="07496-128">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="07496-129">**CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator、CsServerAdministrator 及 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="07496-129">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07496-130">如需系統管理許可權的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="07496-130">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07496-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="07496-131">See Also</span></span>


[<span data-ttu-id="07496-132">在 Lync Server 2013 中部署企業語音</span><span class="sxs-lookup"><span data-stu-id="07496-132">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="07496-133">在 Lync Server 2013 中規劃通話管理功能</span><span class="sxs-lookup"><span data-stu-id="07496-133">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

