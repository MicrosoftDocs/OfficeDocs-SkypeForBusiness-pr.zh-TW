---
title: Lync Server 2013：部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c7c7d6be1ee0e73ee87d71676dddfdcf7954d03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="abe54-102">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe54-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abe54-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="abe54-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="abe54-104">部署 Lync Server 2013 通訊套裝軟體括準備 Active Directory 網域服務、部署前端伺服器及其他核心 Lync Server 2013 內部元件，然後部署任何其他的伺服器角色與功能，您的組織可能需要（例如外部使用者存取和企業語音）。</span><span class="sxs-lookup"><span data-stu-id="abe54-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="abe54-105">本檔說明部署 Lync Server 2013 的三種案例：</span><span class="sxs-lookup"><span data-stu-id="abe54-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="abe54-106">新部署 Lync Server 2013 （企業版）</span><span class="sxs-lookup"><span data-stu-id="abe54-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="abe54-107">Lync Server 2013 的新部署（標準版）</span><span class="sxs-lookup"><span data-stu-id="abe54-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="abe54-108">新的 Lync Server 2013 標準版或企業版部署至現有的 Lync Server 2010 標準版或企業版部署</span><span class="sxs-lookup"><span data-stu-id="abe54-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="abe54-109">如需在現有的 Microsoft Office 通訊伺服器2007或 Microsoft Office 通訊伺服器 2007 R2 環境中部署 Lync Server 2013 的詳細資訊，請參閱[遷移](migration.md)檔。</span><span class="sxs-lookup"><span data-stu-id="abe54-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="abe54-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="abe54-110">In This Section</span></span>

  - [<span data-ttu-id="abe54-111">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abe54-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="abe54-112">在 Lync Server 2013 中部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="abe54-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="abe54-113">在 Lync Server 2013 中部署企業版語音</span><span class="sxs-lookup"><span data-stu-id="abe54-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="abe54-114">在 Lync Server 2013 中部署監視</span><span class="sxs-lookup"><span data-stu-id="abe54-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="abe54-115">在 Lync Server 2013 中部署封存</span><span class="sxs-lookup"><span data-stu-id="abe54-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="abe54-116">在 Lync Server 2013 中設定撥入會議</span><span class="sxs-lookup"><span data-stu-id="abe54-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="abe54-117">在 Lync Server 2013 中規劃及部署影片</span><span class="sxs-lookup"><span data-stu-id="abe54-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="abe54-118">在 Lync Server 2013 中部署分支網站</span><span class="sxs-lookup"><span data-stu-id="abe54-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="abe54-119">在 Lync Server 2013 中部署常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="abe54-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="abe54-120">在 Lync Server 2013 中部署用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="abe54-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="abe54-121">在 Lync Server 2013 中規劃與部署整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="abe54-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="abe54-122">在 Lync Server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="abe54-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="abe54-123">從 Lync Server 2013 評估版更新</span><span class="sxs-lookup"><span data-stu-id="abe54-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="abe54-124">在 Lync Server 2013 中部署遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="abe54-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="abe54-125">在 Lync Server 2013 中部署行動性</span><span class="sxs-lookup"><span data-stu-id="abe54-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="abe54-126">設定 Office Web Apps Server 與 Lync Server 2013 的整合</span><span class="sxs-lookup"><span data-stu-id="abe54-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="abe54-127">Lync Server 2013 中的健康配置</span><span class="sxs-lookup"><span data-stu-id="abe54-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

