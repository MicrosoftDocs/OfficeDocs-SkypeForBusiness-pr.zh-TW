---
title: Lync Server 2013：宣告設定必要條件和角色
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
ms.openlocfilehash: 46b5dac5c800f2e11829940445f9ebfe28c1a95c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531690"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="43736-102">Lync Server 2013 中的宣告設定必要條件和角色</span><span class="sxs-lookup"><span data-stu-id="43736-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43736-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="43736-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="43736-104">宣告是企業語音通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="43736-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="43736-105">本主題說明您必須準備好的功能，才能設定宣告以及執行設定工作所需的角色指派。</span><span class="sxs-lookup"><span data-stu-id="43736-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="43736-106">本節假設您已閱讀與宣告 (相關的規劃檔，請參閱 [在 Lync Server 2013) 中規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="43736-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="43736-107">宣告設定先決條件</span><span class="sxs-lookup"><span data-stu-id="43736-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="43736-108">宣告應用程式需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="43736-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="43736-109">應用程式服務</span><span class="sxs-lookup"><span data-stu-id="43736-109">Application service</span></span>

  - <span data-ttu-id="43736-110">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="43736-110">Response Group application</span></span>

  - <span data-ttu-id="43736-111">用來存放音訊檔案的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="43736-111">File Store, to hold audio files</span></span>

<span data-ttu-id="43736-112">當您部署企業語音時，預設會安裝上述所有元件。</span><span class="sxs-lookup"><span data-stu-id="43736-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="43736-113">宣告設定角色</span><span class="sxs-lookup"><span data-stu-id="43736-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="43736-114">您可以使用下列系統管理工具來設定宣告：</span><span class="sxs-lookup"><span data-stu-id="43736-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="43736-115">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="43736-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="43736-116">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="43736-116">Lync Server Management Shell</span></span>

<span data-ttu-id="43736-117">設定宣告應用程式需要下列其中一個系統管理角色：</span><span class="sxs-lookup"><span data-stu-id="43736-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="43736-118">**CsVoiceAdministrator**    此系統管理員角色可以建立、設定及管理所有與語音相關的設定和原則（包括宣告設定）。</span><span class="sxs-lookup"><span data-stu-id="43736-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="43736-119">**CsServerAdministrator**    此系統管理員角色可以管理、監控及疑難排解伺服器和服務，以及設定所有宣告設定。</span><span class="sxs-lookup"><span data-stu-id="43736-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="43736-120">**CsAdministrator**    此系統管理員角色可以執行所有系統管理工作並修改所有設定。</span><span class="sxs-lookup"><span data-stu-id="43736-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="43736-121">**CsViewOnlyAdministrator**    此系統管理員角色可以查看部署，以監視部署的健康情況。</span><span class="sxs-lookup"><span data-stu-id="43736-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43736-122">如需系統管理使用者權限的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="43736-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43736-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="43736-123">See Also</span></span>


[<span data-ttu-id="43736-124">在 Lync Server 2013 中部署企業語音</span><span class="sxs-lookup"><span data-stu-id="43736-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="43736-125">在 Lync Server 2013 中規劃通話管理功能</span><span class="sxs-lookup"><span data-stu-id="43736-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

