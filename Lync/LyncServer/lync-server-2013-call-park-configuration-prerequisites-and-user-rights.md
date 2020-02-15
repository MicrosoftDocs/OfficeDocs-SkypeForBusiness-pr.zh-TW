---
title: Lync Server 2013： 通話駐留組態先決條件和使用者權限
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
ms.openlocfilehash: 19a677b7b1a76c0956b5edc663e8932716ce5fb6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="de400-102">通話駐留組態先決條件和 Lync Server 2013 中的使用者權限</span><span class="sxs-lookup"><span data-stu-id="de400-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de400-103">_**主題上次修改日期：** 2012年-09-10_</span><span class="sxs-lookup"><span data-stu-id="de400-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="de400-104">通話駐留是當您部署企業語音時，會將預設安裝的通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="de400-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="de400-105">本主題說明您需要備妥之前您可以設定通話駐留以及您需要先執行組態工作的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="de400-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="de400-106">通話駐留應用程式的自訂等候音樂上保留檔案不會備份 Lync Server 2013 災害復原程序的一部分，如果損毀、 損毀，或清除上傳至集區的檔案，檔案將會遺失。</span><span class="sxs-lookup"><span data-stu-id="de400-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="de400-107">永遠保持個別檔案的備份自訂等候音樂上保留已上傳的通話駐留。</span><span class="sxs-lookup"><span data-stu-id="de400-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="de400-108">本節假設您已閱讀規劃通話駐留與相關的文件 （請參閱[Planning for Lync Server 2013 中的通話管理功能](lync-server-2013-planning-for-call-management-features.md)）。</span><span class="sxs-lookup"><span data-stu-id="de400-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="de400-109">通話駐留組態先決條件</span><span class="sxs-lookup"><span data-stu-id="de400-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="de400-110">通話駐留需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="de400-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="de400-111">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="de400-111">Application service</span></span>

  - <span data-ttu-id="de400-112">Call Park application</span><span class="sxs-lookup"><span data-stu-id="de400-112">Call Park application</span></span>

<span data-ttu-id="de400-113">當您部署企業語音時，都會自動安裝這些元件。</span><span class="sxs-lookup"><span data-stu-id="de400-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="de400-114">如果希望來電者在通話駐留時可以聽到音樂，則需要等候音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="de400-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="de400-115">當您部署企業語音時，會自動安裝預設的等候音樂上保留檔案。</span><span class="sxs-lookup"><span data-stu-id="de400-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="de400-116">您可以用自己的等候音樂檔案取代預設檔案。</span><span class="sxs-lookup"><span data-stu-id="de400-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="de400-117">通話駐留使用檔案存放區來保留音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="de400-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="de400-118">通話駐留設定使用者權限</span><span class="sxs-lookup"><span data-stu-id="de400-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="de400-119">您可以使用下列系統管理工具來設定通話駐留：</span><span class="sxs-lookup"><span data-stu-id="de400-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="de400-120">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="de400-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="de400-121">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="de400-121">Lync Server Management Shell</span></span>

<span data-ttu-id="de400-122">若要設定通話駐留軌道表，並設定通話保留所使用的其他設定，您可以使用這些工具。</span><span class="sxs-lookup"><span data-stu-id="de400-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="de400-123">設定通話駐留要求任何下列系統管理角色，視工作而定：</span><span class="sxs-lookup"><span data-stu-id="de400-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="de400-124">**CsVoiceAdministrator:** 此系統管理員角色可以建立、 設定及管理所有語音相關設定和原則。</span><span class="sxs-lookup"><span data-stu-id="de400-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="de400-125">**CsUserAdministrator:** 此系統管理員角色可以在語音原則中啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="de400-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="de400-126">其也具有所有語音設定的唯讀檢視存取權。</span><span class="sxs-lookup"><span data-stu-id="de400-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="de400-127">**CsServerAdministrator:** 此系統管理員角色可以管理、 監控及疑難排解伺服器和服務。</span><span class="sxs-lookup"><span data-stu-id="de400-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="de400-128">**CsAdministrator:** 此系統管理員角色可以執行所有 CsVoiceAdministrator、 CsServerAdministrator 和 CsUserAdministrator 的工作。</span><span class="sxs-lookup"><span data-stu-id="de400-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de400-129">如需系統管理權限的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</A>。</span><span class="sxs-lookup"><span data-stu-id="de400-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="de400-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="de400-130">See Also</span></span>


[<span data-ttu-id="de400-131">部署 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="de400-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="de400-132">規劃 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="de400-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

