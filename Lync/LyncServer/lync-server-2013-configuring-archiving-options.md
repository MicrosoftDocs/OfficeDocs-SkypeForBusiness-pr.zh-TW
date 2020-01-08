---
title: Lync Server 2013：設定存檔選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98356b53940c6189abac5a4b554769093f84dd2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="53254-102">在 Lync Server 2013 中設定封存選項</span><span class="sxs-lookup"><span data-stu-id="53254-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53254-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="53254-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="53254-104">在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存設定] 來指定歸檔的實施方式。</span><span class="sxs-lookup"><span data-stu-id="53254-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="53254-105">這包括下列歸檔設定：</span><span class="sxs-lookup"><span data-stu-id="53254-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="53254-106">當您部署 Lync Server 2013 時預設會建立的全域配置。</span><span class="sxs-lookup"><span data-stu-id="53254-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="53254-107">您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。</span><span class="sxs-lookup"><span data-stu-id="53254-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="53254-108">您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。</span><span class="sxs-lookup"><span data-stu-id="53254-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="53254-109">在 Lync Server 2013**的 [控制台**] 中，您可以使用 [封存**與監控**] 群組的 [封存設定] 頁面，來管理全域層級、網站層級和池層級的設定。</span><span class="sxs-lookup"><span data-stu-id="53254-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="53254-110">如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。</span><span class="sxs-lookup"><span data-stu-id="53254-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="53254-111">如需有關如何在部署之後管理設定的詳細資訊，請參閱在作業檔中[針對貴組織、網站和池管理 Lync Server 2013 中的 [封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)]。</span><span class="sxs-lookup"><span data-stu-id="53254-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53254-112">若要使用封存，您必須設定封存原則，以指定是否要針對內部通訊啟用封存，或針對駐留在 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="53254-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="53254-113">根據預設，不會針對內部或外部通訊啟用封存。</span><span class="sxs-lookup"><span data-stu-id="53254-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="53254-114">在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="53254-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="53254-115">如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="53254-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="53254-116">如果您不是針對您部署中的所有使用者使用 Microsoft Exchange 整合，您必須設定存檔原則，以指定是否要針對內部通訊（針對外部通訊），或兩者啟用封存。</span><span class="sxs-lookup"><span data-stu-id="53254-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="53254-117">根據預設，在使用 Lync Server 2013 封存資料庫時，不會針對內部或外部通訊啟用封存來存檔資料。</span><span class="sxs-lookup"><span data-stu-id="53254-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="53254-118">在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="53254-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="53254-119">如需啟用封存以搭配 Lync Server 2013 存檔資料庫的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync server 2013 中的存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="53254-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="53254-120">本節內容</span><span class="sxs-lookup"><span data-stu-id="53254-120">In This Section</span></span>

  - [<span data-ttu-id="53254-121">在 Lync Server 2013 的全域層級設定封存選項</span><span class="sxs-lookup"><span data-stu-id="53254-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="53254-122">在 Lync Server 2013 中設定網站的存檔選項</span><span class="sxs-lookup"><span data-stu-id="53254-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="53254-123">在 Lync Server 2013 中設定文件庫的封存選項</span><span class="sxs-lookup"><span data-stu-id="53254-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

