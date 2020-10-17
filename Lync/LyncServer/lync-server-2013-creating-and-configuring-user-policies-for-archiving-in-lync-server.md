---
title: 在 Lync Server 中建立及設定封存的使用者原則
description: 在 Lync Server 中建立及設定封存的使用者原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dad260910f01e10c71dbbde67af98ea9a207e33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563089"
---
# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="8a825-103">在 Lync Server 2013 中建立及設定封存的使用者原則</span><span class="sxs-lookup"><span data-stu-id="8a825-103">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a825-104">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8a825-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8a825-105">若要針對駐留在 Lync Server 上的特定使用者啟用或停用封存，您必須先建立使用者原則，然後將原則套用至一或多個使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="8a825-105">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="8a825-106">如需將使用者原則套用至特定使用者和使用者群組的詳細資訊，請參閱部署檔中的將 [Lync server 封存原則套用至 Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="8a825-106">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8a825-107">如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="8a825-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8a825-108">如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="8a825-108">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8a825-109">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。</span><span class="sxs-lookup"><span data-stu-id="8a825-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="8a825-110">啟用封存前，應在封存組態中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="8a825-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="8a825-111">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A> 中設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="8a825-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="8a825-112">為駐留在 Lync Server 上的使用者設定封存原則</span><span class="sxs-lookup"><span data-stu-id="8a825-112">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="8a825-113">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8a825-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8a825-114">開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="8a825-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="8a825-115">如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8a825-115">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a825-116">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="8a825-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="8a825-117">依序按一下 **[新增]** 和 **[使用者原則]**。</span><span class="sxs-lookup"><span data-stu-id="8a825-117">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="8a825-118">在 [新增封存原則]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8a825-118">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="8a825-119">在 [名稱]\*\*\*\* 中，指定使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="8a825-119">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="8a825-120">在 [描述]\*\*\*\* 中，提供何謂使用者原則的相關資訊 (例如，適用於法務部門的使用者原則)。</span><span class="sxs-lookup"><span data-stu-id="8a825-120">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="8a825-121">若要控制使用者原則的內部通訊封存，請選取或清除 [封存內部通訊]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8a825-121">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="8a825-122">若要控制使用者原則的外部通訊封存，請選取或清除 [封存外部通訊]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8a825-122">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="8a825-123">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8a825-123">Click **Commit**.</span></span>

<span data-ttu-id="8a825-124">使用者原則僅會套用至您指派該原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="8a825-124">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="8a825-125">如需將使用者原則套用至特定使用者的詳細資訊，請參閱部署檔中的將 [Lync server 封存原則套用至 Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="8a825-125">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

