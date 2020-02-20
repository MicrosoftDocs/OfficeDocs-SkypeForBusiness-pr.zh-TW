---
title: Lync Server 2013： 宣告組態先決條件和角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dde28cac806b517a410f5edfa7ecbcf19176ed4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="e4ba7-102">宣告組態先決條件和 Lync Server 2013 中的角色</span><span class="sxs-lookup"><span data-stu-id="e4ba7-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4ba7-103">_**上次修改主題：** 2013年-02-25_</span><span class="sxs-lookup"><span data-stu-id="e4ba7-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="e4ba7-104">宣告是企業語音通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="e4ba7-105">本主題說明您需要備妥之前您可以設定宣告和角色指派，您需要先執行組態工作。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="e4ba7-106">本節假設您已閱讀有關宣告的規劃文件 （請參閱[Planning for Lync Server 2013 中的通話管理功能](lync-server-2013-planning-for-call-management-features.md)）。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="e4ba7-107">宣告設定先決條件</span><span class="sxs-lookup"><span data-stu-id="e4ba7-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="e4ba7-108">宣告應用程式需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="e4ba7-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="e4ba7-109">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="e4ba7-109">Application service</span></span>

  - <span data-ttu-id="e4ba7-110">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="e4ba7-110">Response Group application</span></span>

  - <span data-ttu-id="e4ba7-111">用來存放音訊檔案的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="e4ba7-111">File Store, to hold audio files</span></span>

<span data-ttu-id="e4ba7-112">當您部署企業語音時，預設會安裝上述所有元件。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="e4ba7-113">宣告設定角色</span><span class="sxs-lookup"><span data-stu-id="e4ba7-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="e4ba7-114">您可以使用下列系統管理工具來設定宣告：</span><span class="sxs-lookup"><span data-stu-id="e4ba7-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="e4ba7-115">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="e4ba7-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="e4ba7-116">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="e4ba7-116">Lync Server Management Shell</span></span>

<span data-ttu-id="e4ba7-117">設定應用程式需要下列其中一個下列管理角色的宣告：</span><span class="sxs-lookup"><span data-stu-id="e4ba7-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="e4ba7-118">**CsVoiceAdministrator**   此系統管理員角色可以建立、 設定及管理所有語音相關設定和原則，包括宣告設定。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="e4ba7-119">**CsServerAdministrator**   此系統管理員角色可以管理、 監控及疑難排解伺服器和服務，及設定所有宣告設定。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="e4ba7-120">**CsAdministrator**   此系統管理員角色可以執行所有系統管理工作，並修改所有設定。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="e4ba7-121">**CsViewOnlyAdministrator**   此系統管理員角色可以檢視部署，以監控部署健康情況。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4ba7-122">如需管理使用者權限的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</A>。</span><span class="sxs-lookup"><span data-stu-id="e4ba7-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4ba7-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e4ba7-123">See Also</span></span>


[<span data-ttu-id="e4ba7-124">部署 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e4ba7-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="e4ba7-125">規劃 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="e4ba7-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

