---
title: Lync Server 2013：指派會議原則以支援匿名使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 167fe5c772e765c5f78ac2253c23d66550e0e712
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="2f95f-102">在 Lync Server 2013 中指派會議原則以支援匿名使用者</span><span class="sxs-lookup"><span data-stu-id="2f95f-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f95f-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2f95f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2f95f-104">根據預設，禁止所有使用者邀請匿名使用者參與會議。</span><span class="sxs-lookup"><span data-stu-id="2f95f-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="2f95f-105">您可以設定會議原則來支援匿名使用者，並將該會議原則套用至特定使用者，以控制誰可以邀請匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="2f95f-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="2f95f-106">如需如何設定會議原則以支援匿名使用者的詳細資訊，請參閱 [在 Lync server 2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md) ，以及 [管理 lync server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="2f95f-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="2f95f-107">使用本節中的程序，將已建立的會議原則套用至一或多個使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="2f95f-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f95f-108">除了設定及套用原則以讓使用者邀請匿名使用者之外，您還必須啟用組織的匿名使用者支援。</span><span class="sxs-lookup"><span data-stu-id="2f95f-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="2f95f-109">如需詳細資訊，請參閱 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure 原則 to control public user access In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="2f95f-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="2f95f-110">為會議的匿名參與設定使用者原則</span><span class="sxs-lookup"><span data-stu-id="2f95f-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="2f95f-111">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2f95f-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2f95f-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2f95f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f95f-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2f95f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f95f-114">在左導覽列中，按一下 **[會議]**，然後執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="2f95f-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="2f95f-p104">若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。在指出使用者原則所涵蓋內容的 **[名稱]** 欄位中建立唯一名稱 (例如，**EnableAnonymous** 表示啟用與匿名使用者通訊的使用者原則)。</span><span class="sxs-lookup"><span data-stu-id="2f95f-p104">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="2f95f-117">若要設定現有使用者原則，請按一下表格中列出的適當原則，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="2f95f-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="2f95f-118">在 **[會議原則]** 對話方塊中，選取 **[允許參與者邀請匿名使用者]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2f95f-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="2f95f-119">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="2f95f-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="2f95f-120">在左導覽列中，按一下 **[使用者]**，並搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2f95f-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="2f95f-121">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="2f95f-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="2f95f-122">在 **[會議原則]** 的 **[編輯 Lync Server 使用者]** 中，選取含有想要套用至此使用者之匿名使用者存取設定的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="2f95f-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f95f-123"><STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設的伺服器安裝設定，而且會自動套用至伺服器。</span><span class="sxs-lookup"><span data-stu-id="2f95f-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="2f95f-124">若要允許使用者邀請匿名使用者加入會議，您也必須在組織中啟用匿名使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="2f95f-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="2f95f-125">如需詳細資訊，請參閱部署檔或作業檔中的 [設定原則，以控制 Lync Server 2013 中的公用使用者存取](lync-server-2013-configure-policies-to-control-public-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="2f95f-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

