---
title: Lync Server 2013： 部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56d0ce8ddd96ec0e77136e95cf7d415acec7a96b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="a5c4a-102">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5c4a-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5c4a-103">_**主題上次修改日期：** 2012年-10-18_</span><span class="sxs-lookup"><span data-stu-id="a5c4a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a5c4a-104">部署 Lync Server 2013 通訊軟體包括準備 Active Directory 網域服務、 部署前端伺服器和其他核心 Lync Server 2013 的內部元件，並再部署任何其他伺服器角色和功能所您的組織可能需要，例如外部使用者存取和 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="a5c4a-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="a5c4a-105">本文件說明三種部署 Lync Server 2013 案例：</span><span class="sxs-lookup"><span data-stu-id="a5c4a-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="a5c4a-106">Lync Server 2013，企業版的新部署</span><span class="sxs-lookup"><span data-stu-id="a5c4a-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="a5c4a-107">Lync Server 2013，標準版的新部署</span><span class="sxs-lookup"><span data-stu-id="a5c4a-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="a5c4a-108">新部署的 Lync Server 2013 Standard Edition 或 Enterprise Edition 到現有的 Lync Server 2010 Standard Edition 或 Enterprise Edition 部署</span><span class="sxs-lookup"><span data-stu-id="a5c4a-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="a5c4a-109">如需部署在現有的 Microsoft Office Communications Server 2007 或 Microsoft Office Communications Server 2007 R2 環境中的 Lync Server 2013 的資訊，請參閱[移轉](migration.md)文件。</span><span class="sxs-lookup"><span data-stu-id="a5c4a-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a5c4a-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="a5c4a-110">In This Section</span></span>

  - [<span data-ttu-id="a5c4a-111">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5c4a-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="a5c4a-112">部署 Lync Server 2013 中的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="a5c4a-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="a5c4a-113">部署 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="a5c4a-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="a5c4a-114">部署 Lync Server 2013 中監視</span><span class="sxs-lookup"><span data-stu-id="a5c4a-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="a5c4a-115">部署 Lync Server 2013 中的封存</span><span class="sxs-lookup"><span data-stu-id="a5c4a-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="a5c4a-116">在 Lync Server 2013 中設定電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="a5c4a-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="a5c4a-117">規劃及部署 Lync Server 2013 中的影片</span><span class="sxs-lookup"><span data-stu-id="a5c4a-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="a5c4a-118">部署 Lync Server 2013 中的分支網站</span><span class="sxs-lookup"><span data-stu-id="a5c4a-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="a5c4a-119">部署 Lync Server 2013 中的常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="a5c4a-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="a5c4a-120">部署用戶端和 Lync Server 2013 中的裝置</span><span class="sxs-lookup"><span data-stu-id="a5c4a-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="a5c4a-121">規劃及部署整合的連絡人儲存在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5c4a-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="a5c4a-122">管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式</span><span class="sxs-lookup"><span data-stu-id="a5c4a-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="a5c4a-123">從 Lync Server 2013 的評估版本更新</span><span class="sxs-lookup"><span data-stu-id="a5c4a-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="a5c4a-124">部署 Lync Server 2013 中的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="a5c4a-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="a5c4a-125">部署 Lync Server 2013 中的行動性</span><span class="sxs-lookup"><span data-stu-id="a5c4a-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="a5c4a-126">設定與 Office Web Apps Server 及 Lync Server 2013 整合</span><span class="sxs-lookup"><span data-stu-id="a5c4a-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="a5c4a-127">Lync Server 2013 中的健康情況設定</span><span class="sxs-lookup"><span data-stu-id="a5c4a-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

