---
title: Lync Server 2013：將 Lync Server 存檔原則套用至使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7b82fd0d42aa6a34533f6b5005e15edd2aa5cbd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a><span data-ttu-id="c5d15-102">在 Lync Server 2013 中將 Lync Server 存檔原則套用至使用者</span><span class="sxs-lookup"><span data-stu-id="c5d15-102">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5d15-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="c5d15-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="c5d15-104">在建立 Lync Server 使用者原則之後，您必須將其套用至 Lync Server 2013 上所駐留的特定使用者或使用者群組，才能讓它生效。</span><span class="sxs-lookup"><span data-stu-id="c5d15-104">After creating a Lync Server user policy, you must apply it to specific the users or user groups that are homed on Lync Server 2013 before it can take effect.</span></span> <span data-ttu-id="c5d15-105">如需針對特定使用者建立使用者原則的詳細資料，請參閱在部署檔中[建立及設定 Lync Server 2013 中的存檔使用者原則](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d15-105">For details about creating user policies for specific users, see [Creating and configuring user policies for Archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c5d15-106">如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 存檔中的運作方式](lync-server-2013-how-archiving-works.md)]。</span><span class="sxs-lookup"><span data-stu-id="c5d15-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5d15-107">若要設定及使用封存，您必須先部署封存。</span><span class="sxs-lookup"><span data-stu-id="c5d15-107">In order to configure and use archiving, you must first deploy archiving.</span></span> <span data-ttu-id="c5d15-108">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-deploying-archiving.md">Lync Server 2013</A>中的 [部署存檔]。</span><span class="sxs-lookup"><span data-stu-id="c5d15-108">For details, see <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c5d15-109">如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="c5d15-109">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="c5d15-110">如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="c5d15-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c5d15-111">在啟用封存前，您應該先在封存配置中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="c5d15-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="c5d15-112">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。</span><span class="sxs-lookup"><span data-stu-id="c5d15-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a><span data-ttu-id="c5d15-113">將 Lync Server 存檔原則套用至使用者</span><span class="sxs-lookup"><span data-stu-id="c5d15-113">To apply a Lync Server archiving policy to a user</span></span>

1.  <span data-ttu-id="c5d15-114">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c5d15-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c5d15-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c5d15-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c5d15-116">如需可用於啟動 Lync Server 2013 [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d15-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5d15-117">在左側導覽列中，按一下 [**使用者**]，然後搜尋您要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c5d15-117">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="c5d15-118">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5d15-118">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c5d15-119">在 [**存檔原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的存檔使用者原則。</span><span class="sxs-lookup"><span data-stu-id="c5d15-119">In **Edit Lync Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5d15-120">[ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用預設伺服器安裝設定。</span><span class="sxs-lookup"><span data-stu-id="c5d15-120">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="c5d15-121">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="c5d15-121">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="c5d15-122">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5d15-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

