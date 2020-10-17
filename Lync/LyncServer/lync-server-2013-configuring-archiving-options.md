---
title: Lync Server 2013：設定封存選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdb8eda57f027c9776de11a6e36795dd57dc661a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502260"
---
# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="5f620-102">在 Lync Server 2013 中設定封存選項</span><span class="sxs-lookup"><span data-stu-id="5f620-102">Configuring Archiving options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f620-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="5f620-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="5f620-104">在 [Lync Server 2013 控制台] 中，您可以使用封存設定來指定封存的實施方式。</span><span class="sxs-lookup"><span data-stu-id="5f620-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="5f620-105">這包含下列封存組態：</span><span class="sxs-lookup"><span data-stu-id="5f620-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="5f620-106">當您部署 Lync Server 2013 時，預設會建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="5f620-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="5f620-107">選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。</span><span class="sxs-lookup"><span data-stu-id="5f620-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="5f620-108">您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。</span><span class="sxs-lookup"><span data-stu-id="5f620-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="5f620-109">在 [Lync Server 2013 控制台] 中，您可以**使用 [封存\*\*\*\*與監控**] 群組的 [封存設定] 頁面，以管理全域層級、網站層級及集區層級的設定。</span><span class="sxs-lookup"><span data-stu-id="5f620-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="5f620-110">如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="5f620-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="5f620-111">如需如何在部署後管理設定的詳細資訊，請參閱 Operations 檔中的 [管理組織、網站及集區之 Lync Server 2013 中的封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 。</span><span class="sxs-lookup"><span data-stu-id="5f620-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f620-112">若要使用封存，您必須設定封存原則，以指定是否啟用內部通訊、外部通訊或同時適用于 Lync Server 2013 的使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="5f620-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="5f620-113">依據預設，都不會啟用內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="5f620-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="5f620-114">在任何原則中啟用封存之前，您應該為您的部署指定適當的封存設定，以及針對特定網站和集區（選用）指定適當的封存設定，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="5f620-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="5f620-115">如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。</span><span class="sxs-lookup"><span data-stu-id="5f620-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="5f620-116">如果您部署中的所有使用者未使用 Microsoft Exchange 整合，您必須設定封存原則，以指定是否要啟用內部通訊、外部通訊或兩者的封存。</span><span class="sxs-lookup"><span data-stu-id="5f620-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="5f620-117">根據預設，使用 Lync Server 2013 封存資料庫時，未啟用內部或外部通訊的封存資料的封存。</span><span class="sxs-lookup"><span data-stu-id="5f620-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="5f620-118">以任何原則啟用封存之前，您應先為部署指定適用的封存組態，然後如上一節中所述，選用地針對網站與集區指定封存組態。</span><span class="sxs-lookup"><span data-stu-id="5f620-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="5f620-119">如需啟用封存以用於 Lync Server 2013 封存資料庫的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync server 2013</A> 中的封存原則。</span><span class="sxs-lookup"><span data-stu-id="5f620-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f620-120">本章節內容</span><span class="sxs-lookup"><span data-stu-id="5f620-120">In This Section</span></span>

  - [<span data-ttu-id="5f620-121">在 Lync Server 2013 中設定全域層級的封存選項</span><span class="sxs-lookup"><span data-stu-id="5f620-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="5f620-122">在 Lync Server 2013 中設定網站的封存選項</span><span class="sxs-lookup"><span data-stu-id="5f620-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="5f620-123">在 Lync Server 2013 中設定集區的封存選項</span><span class="sxs-lookup"><span data-stu-id="5f620-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

