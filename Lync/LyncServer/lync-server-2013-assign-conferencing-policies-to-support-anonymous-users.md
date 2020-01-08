---
title: Lync Server 2013：指派會議原則以支援匿名使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94ff3fe520b776d6f6043abb66f9926da5acaa22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="d0b74-102">在 Lync Server 2013 中指派會議原則以支援匿名使用者</span><span class="sxs-lookup"><span data-stu-id="d0b74-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0b74-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d0b74-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d0b74-104">根據預設，所有使用者都會被禁止邀請匿名使用者參與會議。</span><span class="sxs-lookup"><span data-stu-id="d0b74-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="d0b74-105">您可以將會議原則設定為支援匿名使用者，並將該會議原則套用到特定使用者，以控制誰能邀請匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="d0b74-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="d0b74-106">如需有關如何設定會議原則以支援匿名使用者的詳細資料，請參閱[在 Lync server 2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)，以及[管理 lync server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="d0b74-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="d0b74-107">使用本節中的程式，將您已建立的會議原則套用至一或多個使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d0b74-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0b74-108">除了設定及套用原則以讓使用者邀請匿名使用者，您也必須為貴組織啟用匿名使用者支援。</span><span class="sxs-lookup"><span data-stu-id="d0b74-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="d0b74-109">如需詳細資訊，請參閱<A href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中設定控制公用使用者存取的原則</A>。</span><span class="sxs-lookup"><span data-stu-id="d0b74-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="d0b74-110">設定匿名參與會議的使用者原則</span><span class="sxs-lookup"><span data-stu-id="d0b74-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="d0b74-111">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d0b74-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0b74-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d0b74-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0b74-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d0b74-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0b74-114">在左側導覽列中，按一下 [**會議**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d0b74-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="d0b74-115">若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="d0b74-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="d0b74-116">在 [Name] （**名稱**）欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容（例如，允許與匿名使用者進行通訊的使用者原則**EnableAnonymous** ）。</span><span class="sxs-lookup"><span data-stu-id="d0b74-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="d0b74-117">若要設定現有的使用者原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d0b74-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="d0b74-118">在 [**會議原則**] 對話方塊中，選取 [**允許參與者邀請匿名使用者**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d0b74-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="d0b74-119">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0b74-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="d0b74-120">在左側導覽列中，按一下 [**使用者**]，搜尋您要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d0b74-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="d0b74-121">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0b74-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="d0b74-122">在 [**會議原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用至此使用者之 [匿名使用者存取設定] 的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="d0b74-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0b74-123">[ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用預設伺服器安裝設定，且由伺服器自動套用。</span><span class="sxs-lookup"><span data-stu-id="d0b74-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="d0b74-124">若要讓使用者邀請匿名使用者加入會議，您也必須在組織中啟用匿名使用者支援。</span><span class="sxs-lookup"><span data-stu-id="d0b74-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="d0b74-125">如需詳細資訊，請參閱在部署檔或操作檔中，[設定控制在 Lync Server 2013 中的公用使用者存取的原則](lync-server-2013-configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="d0b74-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

