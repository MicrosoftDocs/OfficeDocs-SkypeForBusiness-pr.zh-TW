---
title: Lync Server 2013：支援的伺服器轉移路徑和並存案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="25121-102">Lync Server 2013 中支援的伺服器轉移路徑和並存案例</span><span class="sxs-lookup"><span data-stu-id="25121-102">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25121-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="25121-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="25121-104">Lync Server 2013 支援從下列其中一項進行遷移：</span><span class="sxs-lookup"><span data-stu-id="25121-104">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="25121-105">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="25121-105">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="25121-106">Microsoft Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="25121-106">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="25121-107">不支援從執行這兩個舊版版本的環境進行遷移。</span><span class="sxs-lookup"><span data-stu-id="25121-107">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="25121-108">不支援從較舊的版本（例如 Microsoft Office 通訊伺服器2007或即時通訊伺服器2005）遷移。</span><span class="sxs-lookup"><span data-stu-id="25121-108">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="25121-109">如果您先前的部署包含群組聊天，您必須另行遷移。</span><span class="sxs-lookup"><span data-stu-id="25121-109">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="25121-110">遷移方法</span><span class="sxs-lookup"><span data-stu-id="25121-110">Migration Methods</span></span>

<span data-ttu-id="25121-111">支援遷移所有 Lync Server 拓撲和伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="25121-111">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="25121-112">您可以從一個拓撲遷移至不同拓撲，包括從標準版伺服器到企業版伺服器。</span><span class="sxs-lookup"><span data-stu-id="25121-112">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="25121-113">Lync Server 2013 只支援下列遷移方法：</span><span class="sxs-lookup"><span data-stu-id="25121-113">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="25121-114">**並行遷移。**</span><span class="sxs-lookup"><span data-stu-id="25121-114">**Side-by-side migration.**</span></span> <span data-ttu-id="25121-115">在並列式遷移中，Lync Server 2013 是與現有的 Microsoft Lync Server 2010 或 Office 通訊伺服器 2007 R2 部署一起部署，然後您將作業轉移到新的伺服器，並將使用者移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="25121-115">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="25121-116">這個方法需要其他伺服器平臺，包括硬體和軟體，在遷移期間，系統名稱和池名稱在新的配置中是不一樣的。</span><span class="sxs-lookup"><span data-stu-id="25121-116">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="25121-117">如果需要回滾到前一個版本，您可以將作業移回先前的伺服器。</span><span class="sxs-lookup"><span data-stu-id="25121-117">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="25121-118">不支援跨 Active Directory 網域服務林的遷移。</span><span class="sxs-lookup"><span data-stu-id="25121-118">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="25121-119">建議的遷移路徑是分階段的方法。</span><span class="sxs-lookup"><span data-stu-id="25121-119">The recommended migration path is a phased approach.</span></span> <span data-ttu-id="25121-120">如需從舊版進行遷移的詳細資料，包括元件部署的適當分段，請參閱遷移檔中的下列主題：</span><span class="sxs-lookup"><span data-stu-id="25121-120">For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="25121-121">從 Lync Server 2010 移轉到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25121-121">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="25121-122">從 Office Communications Server 2007 R2 移轉至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25121-122">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="25121-123">從 Lync Server 2010 群組聊天或 Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013 常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="25121-123">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="25121-124">共存案例</span><span class="sxs-lookup"><span data-stu-id="25121-124">Coexistence Scenarios</span></span>

<span data-ttu-id="25121-125">Lync Server 2013 可與 Lync Server 2010 部署或 Office 通訊伺服器 2007 R2 部署的元件共存。</span><span class="sxs-lookup"><span data-stu-id="25121-125">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="25121-126">同時使用 Lync Server 2010 和 Office 通訊伺服器 2007 R2 （這三個版本的並行部署）不支援同時部署 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="25121-126">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="25121-127">在第一次使用新的 Lync server 2013 部署 coexists 暫時的 Lync Server 2010 或 Office 通訊伺服器 2007 R2 部署期間，混合版本路由的支援會受到限制。</span><span class="sxs-lookup"><span data-stu-id="25121-127">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="25121-128">如需詳細資訊，請參閱遷移檔。</span><span class="sxs-lookup"><span data-stu-id="25121-128">For details, see the Migration documentation.</span></span>

<span data-ttu-id="25121-129">您必須針對 Lync Server 2013 資料庫實例，使用個別且獨立的電腦執行 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="25121-129">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="25121-130">您無法針對 Lync Server 2010 或 Office 通訊伺服器 2007 R2 前端池使用的 Lync Server 2013 前端池使用相同的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="25121-130">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="25121-131">如果您在拓撲建立器中針對已部署 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的部署定義並設定 Lync Server 2013，拓撲建立器將不允許您定義已在其中使用的 Lync Server 2013 實例拓撲。</span><span class="sxs-lookup"><span data-stu-id="25121-131">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="25121-132">[拓撲建立器] 會顯示下列訊息，告知您有這個問題：「SQL \[server FQDN\]已包含託管角色 ' 使用者存儲」的 sql 實例。」</span><span class="sxs-lookup"><span data-stu-id="25121-132">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store'."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25121-133">如果您想要部署 Lync Server 2013 部署中新的伺服器角色，您應該先升級現有的部署，如以下所述：遷移檔和部署檔中所述，然後部署新的伺服器角色，如中所述。規劃檔與部署檔。</span><span class="sxs-lookup"><span data-stu-id="25121-133">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="25121-134">如果您要遷移舊版群組聊天，請在完成將所有其他元件從 Lync Server 2010 或 Office 通訊伺服器 2007 R2 遷移之後，再將它遷移到最後一個版本。</span><span class="sxs-lookup"><span data-stu-id="25121-134">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="25121-135">如需特定的共存需求，以及有關 Lync Server 2010 或 Office 通訊伺服器 2007 R2 和 Lync Server 2013 元件的共存與遷移的其他詳細資料，請參閱[從 Lync server 2010 遷移至 Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) ，以及[從 Office 通訊伺服器 2007 R2 遷移到 lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) （在遷移檔中）。</span><span class="sxs-lookup"><span data-stu-id="25121-135">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="25121-136">如需用戶端混合版本支援的詳細資料，請參閱[Lync Server 2013 中先前部署的支援的用戶端](lync-server-2013-supported-clients-from-previous-deployments.md)。</span><span class="sxs-lookup"><span data-stu-id="25121-136">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

