---
title: Lync Server 2013：設定原則以控制遠端使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f1687a26e5bf464191b742d046bc28e8c8a329a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="44435-102">在 Lync Server 2013 中設定控制遠端使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="44435-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44435-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="44435-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="44435-104">您可以設定一或多個外部使用者存取原則，以控制遠端使用者是否可以與內部 Lync Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="44435-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="44435-105">若要控制遠端使用者存取，您可以在全域、網站及使用者層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="44435-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="44435-106">網站原則會覆寫全域原則，而使用者原則會覆寫網站和全域原則。</span><span class="sxs-lookup"><span data-stu-id="44435-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="44435-107">如需您可以設定之原則類型的詳細資訊，請參閱[管理 Lync Server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="44435-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="44435-108">套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="44435-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="44435-109">Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。</span><span class="sxs-lookup"><span data-stu-id="44435-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="44435-110">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="44435-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44435-111">即使您沒有為組織啟用遠端使用者存取，您也可以設定原則來控制遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="44435-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="44435-112">不過，您設定的原則只有當您為組織啟用遠端使用者存取時才會生效。</span><span class="sxs-lookup"><span data-stu-id="44435-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="44435-113">如需啟用遠端使用者存取的詳細資訊，請參閱<A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and PUBLIC IM connectivity In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="44435-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="44435-114">此外，如果您指定用來控制遠端使用者存取的使用者原則，此原則只適用于已啟用 Lync Server 且設定為使用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="44435-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="44435-115">如需指定可以從遠端位置登入 Lync Server 之使用者的詳細資訊，請參閱<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">將外部使用者存取原則指派給 Lync server 2013 中啟用 lync 功能的使用者</A>。</span><span class="sxs-lookup"><span data-stu-id="44435-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="44435-116">使用下列程式可設定每個要用來控制遠端使用者存取的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="44435-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44435-117">此程式說明如何設定原則，只啟用與遠端使用者的通訊，但設定為支援遠端使用者存取的每個原則也可以設定同盟使用者存取和公用使用者存取。</span><span class="sxs-lookup"><span data-stu-id="44435-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="44435-118">如需設定支援同盟使用者之原則的詳細資訊，請參閱<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</A>。</span><span class="sxs-lookup"><span data-stu-id="44435-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="44435-119">如需設定原則以支援公用使用者的詳細資訊，請參閱<A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</A>。</span><span class="sxs-lookup"><span data-stu-id="44435-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="44435-120">設定外部存取原則以支援遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="44435-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="44435-121">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="44435-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44435-122">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="44435-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="44435-123">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="44435-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="44435-124">在左導覽列中，依序按一下 [外部使用者存取]\*\*\*\* 及 [外部存取原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44435-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="44435-125">在「外部存取原則」\*\*\*\* 頁面中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="44435-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="44435-126">若要設定全域原則以支援遠端使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="44435-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="44435-p105">若要建立新的網站原則，請按一下 **[新增]**，然後按一下 **[站台原則]**。在 **[選取站台]** 的清單中按一下適當網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="44435-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="44435-129">若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。</span><span class="sxs-lookup"><span data-stu-id="44435-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="44435-130">在 [**新增外部存取原則**] 中，在 [**名稱**] 欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容 (例如，針對為遠端使用者) 啟用通訊的使用者原則，請**EnableRemoteUsers** 。</span><span class="sxs-lookup"><span data-stu-id="44435-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="44435-131">若要變更現有原則，按一下表中所列之適當原則，然後按一下 [編輯]\*\*\*\*，接著按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44435-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="44435-132">(選用) 如果您想要新增或編輯說明，請在 [說明]\*\*\*\* 中指定原則資訊。</span><span class="sxs-lookup"><span data-stu-id="44435-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="44435-133">執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="44435-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="44435-134">若要啟用原則的遠端使用者存取，請選取 [**啟用與遠端使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="44435-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="44435-135">若要停用原則的遠端使用者存取，請清除 [**啟用與遠端使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="44435-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="44435-136">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="44435-136">Click **Commit**.</span></span>

<span data-ttu-id="44435-137">若要啟用遠端使用者存取，您也必須啟用組織中遠端使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="44435-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="44435-138">如需詳細資訊，請參閱部署檔或作業檔中的[Enable 或 disable federation and PUBLIC IM connectivity In Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 。</span><span class="sxs-lookup"><span data-stu-id="44435-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="44435-139">如果這是使用者原則，您也必須將原則套用至您要能夠遠端連線的使用者。</span><span class="sxs-lookup"><span data-stu-id="44435-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="44435-140">如需詳細資訊，請參閱部署檔或作業檔中的[指派外部使用者存取原則給 Lync Server 2013 中的 lync 啟用使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="44435-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

