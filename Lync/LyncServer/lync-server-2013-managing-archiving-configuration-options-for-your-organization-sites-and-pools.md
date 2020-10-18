---
title: Lync Server 2013：管理組織、網站及集區的封存配置選項
description: Lync Server 2013：管理組織、網站及集區的封存配置選項。
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
ms.openlocfilehash: 41eca448fcb9863f117bcb7e52e3290270fefa47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576619"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="643f0-103">為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項</span><span class="sxs-lookup"><span data-stu-id="643f0-103">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="643f0-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="643f0-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="643f0-105">在 [Lync Server 2013 控制台] 中，您可以使用封存設定來指定封存的實施方式。</span><span class="sxs-lookup"><span data-stu-id="643f0-105">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="643f0-106">這包含下列封存組態：</span><span class="sxs-lookup"><span data-stu-id="643f0-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="643f0-107">當您部署 Lync Server 2013 時，預設會建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="643f0-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="643f0-108">選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。</span><span class="sxs-lookup"><span data-stu-id="643f0-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="643f0-109">您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。</span><span class="sxs-lookup"><span data-stu-id="643f0-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="643f0-110">在 [Lync Server 2013 控制台] 中，您可以**使用 [封存\*\*\*\*與監控**] 群組的 [封存設定] 頁面，以管理全域層級、網站層級及集區層級的設定。</span><span class="sxs-lookup"><span data-stu-id="643f0-110">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="643f0-111">如需如何執行封存設定的詳細資訊（包括您可以指定哪些選項），以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="643f0-111">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="643f0-112">若要使用封存，您必須設定封存原則，以指定是否啟用內部通訊的封存、外部通訊的封存，或同時針對駐留在 Lync Server 2013 的所有使用者啟用封存。</span><span class="sxs-lookup"><span data-stu-id="643f0-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="643f0-113">依據預設，都不會啟用內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="643f0-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="643f0-114">如果您使用 Microsoft Exchange 整合，您必須啟用和設定 Exchange 2013，以支援所有駐留在 Exchange 2013 上的使用者，且其信箱已 In-Place 保留中的使用者。</span><span class="sxs-lookup"><span data-stu-id="643f0-114">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="643f0-115">在啟用封存之前，應針對部署 (及選擇性針對特定網站和集區) 指定適當的封存組態，如本區段所述。</span><span class="sxs-lookup"><span data-stu-id="643f0-115">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="643f0-116">如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。</span><span class="sxs-lookup"><span data-stu-id="643f0-116">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="643f0-117">**使用 Windows PowerShell Cmdlet 來查看封存設定資訊**</span><span class="sxs-lookup"><span data-stu-id="643f0-117">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="643f0-118">您可以使用 Windows PowerShell 和 **Get-CsArchivingConfiguration** Cmdlet 來查看封存設定資訊。</span><span class="sxs-lookup"><span data-stu-id="643f0-118">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="643f0-119">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="643f0-119">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="643f0-120">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="643f0-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="643f0-121">在 Lync Server 管理命令介面中，使用下列命令來查看所有封存設定設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="643f0-121">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="643f0-122">本章節內容</span><span class="sxs-lookup"><span data-stu-id="643f0-122">In This Section</span></span>

  - [<span data-ttu-id="643f0-123">在 Lync Server 2013 中建立封存設定，以管理特定網站或集區的封存</span><span class="sxs-lookup"><span data-stu-id="643f0-123">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="643f0-124">啟用或停用 Lync Server 2013 中的 IM 或會議會話的封存</span><span class="sxs-lookup"><span data-stu-id="643f0-124">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="643f0-125">啟用或停用 Lync Server 2013 中的封存資料清除功能</span><span class="sxs-lookup"><span data-stu-id="643f0-125">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="643f0-126">啟用或停用 Lync Server 2013 中的重要模式，以在封存失敗時封鎖或允許 IM 和 web 會議會話</span><span class="sxs-lookup"><span data-stu-id="643f0-126">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="643f0-127">在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能</span><span class="sxs-lookup"><span data-stu-id="643f0-127">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="643f0-128">啟用或停用與 Exchange storage 的 Lync Server 2013 整合</span><span class="sxs-lookup"><span data-stu-id="643f0-128">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="643f0-129">在 Lync Server 2013 中刪除封存設定</span><span class="sxs-lookup"><span data-stu-id="643f0-129">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="643f0-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="643f0-130">See Also</span></span>


[<span data-ttu-id="643f0-131">管理 Lync Server 2013 封存</span><span class="sxs-lookup"><span data-stu-id="643f0-131">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

