---
title: Lync Server 2013：設定與指派封存原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b4e49bb6ba25fb9c7230cdf171dc7d31433619
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="35a21-102">在 Lync Server 2013 中設定和指派封存原則</span><span class="sxs-lookup"><span data-stu-id="35a21-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35a21-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="35a21-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="35a21-104">在 Lync Server 2013 中，您可以使用原則來啟用和停用內部通訊的封存，以及在 Lync Server 2013 上的使用者的外部通訊封存。</span><span class="sxs-lookup"><span data-stu-id="35a21-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="35a21-105">這包括下列封存原則：</span><span class="sxs-lookup"><span data-stu-id="35a21-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="35a21-106">當您部署 Lync Server 2013 時，預設會建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="35a21-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="35a21-107">您可以選擇性建立的網站層級和使用者層級原則，並用來指定如何針對特定的網站或使用者實作封存。</span><span class="sxs-lookup"><span data-stu-id="35a21-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="35a21-108">您最初可以在部署封存時設定封存，但可在部署之後變更、新增及刪除原則。</span><span class="sxs-lookup"><span data-stu-id="35a21-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="35a21-109">在 [Lync Server 2013 控制台] 中，您可以使用 [封存**與監控**] 群組的 [封存**原則**] 頁面，以管理全域層級、網站層級和使用者層級的原則。</span><span class="sxs-lookup"><span data-stu-id="35a21-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35a21-110">若要控制封存的實作，您必須在封存設定中指定選項，例如，是否要封存 IM 或會議、使用關鍵模式及清除選項。</span><span class="sxs-lookup"><span data-stu-id="35a21-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="35a21-111">依預設，不會在全域封存設定或是任何網站或集區封存設定中啟用任何選項。</span><span class="sxs-lookup"><span data-stu-id="35a21-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="35a21-112">您應該先在封存設定中指定所有適當的選項，然後才能在封存原則中啟用對內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="35a21-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="35a21-113">如需詳細資訊，請參閱 Operations 檔中的<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">管理組織、網站及集區的 Lync Server 2013 中的封存配置選項</A>。</span><span class="sxs-lookup"><span data-stu-id="35a21-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="35a21-114">[！注意] 如果您將 Lync Server storage 與 Exchange 2013 儲存整合，則 Exchange 使用者原則優先于 Lync Server 2013 封存原則，但僅限於位於 Exchange 2013 之使用者已將其信箱置於 In-Place 保留狀態的使用者。</span><span class="sxs-lookup"><span data-stu-id="35a21-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="35a21-115">如需如何實施原則的詳細資訊，包括原則的階層，請參閱規劃檔、部署檔或作業檔中的封存[在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="35a21-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="35a21-116">如需如何在部署後管理原則的詳細資訊，請參閱 Operations 檔中的[管理 Lync Server 2013 中的內部和外部通訊](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="35a21-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="35a21-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="35a21-117">In This Section</span></span>

  - [<span data-ttu-id="35a21-118">在 Lync Server 2013 中設定封存的全域原則</span><span class="sxs-lookup"><span data-stu-id="35a21-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="35a21-119">在 Lync Server 2013 中設定封存的網站原則</span><span class="sxs-lookup"><span data-stu-id="35a21-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="35a21-120">在 Lync Server 2013 中設定使用者的封存原則</span><span class="sxs-lookup"><span data-stu-id="35a21-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

