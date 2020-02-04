---
title: Lync Server 2013：管理組織、網站和池的封存配置選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59db9765b9e9ee0b453268ea9c22d897f10ba662
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="a287f-102">管理您組織、網站和池的 Lync Server 2013 中的封存配置選項</span><span class="sxs-lookup"><span data-stu-id="a287f-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a287f-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a287f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a287f-104">在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存設定] 來指定歸檔的實施方式。</span><span class="sxs-lookup"><span data-stu-id="a287f-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="a287f-105">這包括下列歸檔設定：</span><span class="sxs-lookup"><span data-stu-id="a287f-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="a287f-106">當您部署 Lync Server 2013 時預設會建立的全域配置。</span><span class="sxs-lookup"><span data-stu-id="a287f-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="a287f-107">您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。</span><span class="sxs-lookup"><span data-stu-id="a287f-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="a287f-108">您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。</span><span class="sxs-lookup"><span data-stu-id="a287f-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="a287f-109">在 Lync Server 2013**的 [控制台**] 中，您可以使用 [封存**與監控**] 群組的 [封存設定] 頁面，來管理全域層級、網站層級和池層級的設定。</span><span class="sxs-lookup"><span data-stu-id="a287f-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="a287f-110">如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的[存檔在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="a287f-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a287f-111">若要使用封存，您必須設定存檔原則，以指定是否要針對內部通訊啟用封存，或針對所有駐留在 Lync Server 2013 的使用者，進行這兩者。</span><span class="sxs-lookup"><span data-stu-id="a287f-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="a287f-112">根據預設，不會針對內部或外部通訊啟用封存。</span><span class="sxs-lookup"><span data-stu-id="a287f-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="a287f-113">如果您使用的是 Microsoft Exchange 整合，您必須啟用並設定 Exchange 2013，以支援所有駐留在已將其信箱放在就地保留中之 Exchange 2013 的使用者的存檔。</span><span class="sxs-lookup"><span data-stu-id="a287f-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="a287f-114">在啟用封存之前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔設定，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="a287f-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="a287f-115">如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="a287f-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="a287f-116">**若要使用 Windows PowerShell Cmdlet 來查看封存配置資訊**</span><span class="sxs-lookup"><span data-stu-id="a287f-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="a287f-117">您可以使用 Windows PowerShell 和**CsArchivingConfiguration** Cmdlet 來查看封存配置資訊。</span><span class="sxs-lookup"><span data-stu-id="a287f-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="a287f-118">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a287f-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a287f-119">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="a287f-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="a287f-120">在 Lync Server 管理命令介面中，請使用下列命令來查看所有存檔設定設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="a287f-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="a287f-121">本節內容</span><span class="sxs-lookup"><span data-stu-id="a287f-121">In This Section</span></span>

  - [<span data-ttu-id="a287f-122">在 Lync Server 2013 中建立存檔設定，以管理特定網站或池中的存檔</span><span class="sxs-lookup"><span data-stu-id="a287f-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="a287f-123">在 Lync Server 2013 中啟用或停用 IM 或會議會話的封存</span><span class="sxs-lookup"><span data-stu-id="a287f-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="a287f-124">啟用或停用 Lync Server 2013 中已歸檔的資料清除</span><span class="sxs-lookup"><span data-stu-id="a287f-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - <span data-ttu-id="a287f-125">[啟用或停用 Lync Server 2013 中的 [重要模式]，以封鎖或允許 IM 和網路會議會話（如果歸檔失敗）](lync-server-2013-enable-disable-critical-mode.md)</span><span class="sxs-lookup"><span data-stu-id="a287f-125">[Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails](lync-server-2013-enable-disable-critical-mode.md)</span></span>

  - [<span data-ttu-id="a287f-126">在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能</span><span class="sxs-lookup"><span data-stu-id="a287f-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="a287f-127">啟用或停用 Lync Server 2013 與 Exchange 儲存空間的整合</span><span class="sxs-lookup"><span data-stu-id="a287f-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="a287f-128">在 Lync Server 2013 中刪除封存配置</span><span class="sxs-lookup"><span data-stu-id="a287f-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a287f-129">請參閱</span><span class="sxs-lookup"><span data-stu-id="a287f-129">See Also</span></span>


[<span data-ttu-id="a287f-130">管理 Lync Server 2013 封存</span><span class="sxs-lookup"><span data-stu-id="a287f-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

