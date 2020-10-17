---
title: Lync Server 2013：請確定撥號對應表具有指派的區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9f9a67a65b870edd75259bca7c74a1fae2749f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534560"
---
# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="cb399-102">確定撥號對應表 Lync Server 2013 具有指派的區域</span><span class="sxs-lookup"><span data-stu-id="cb399-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb399-103">_**主題上次修改日期：** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="cb399-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="cb399-p101">用於電話撥入式會議的撥號對應表，需要指定 **[電話撥入式會議區域]**，才能讓電話撥入式會議存取號碼與適當的撥號對應表產生關聯。設定撥號對應表時，您會指定適用於該撥號對應表的電話撥入式會議區域。之後建立撥入存取號碼時，您會選取使存取號碼關聯至適當撥號對應表的區域。</span><span class="sxs-lookup"><span data-stu-id="cb399-p101">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan. When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="cb399-p102">因為替所有撥號對應表指定區域十分重要，因此建議您使用以下程序來確認所有撥號對應表都具有區域。這是選用步驟。</span><span class="sxs-lookup"><span data-stu-id="cb399-p102">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions. This step is optional.</span></span>

<span data-ttu-id="cb399-109">使用 **Get-CsDialPlan** Cmdlet 確認是否已為所有電話撥入式會議撥號對應表設定區域。</span><span class="sxs-lookup"><span data-stu-id="cb399-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="cb399-110">如果撥號對應表缺少區域，您可以使用 **Set-CsDialPlan** Cmdlet 來設定區域。</span><span class="sxs-lookup"><span data-stu-id="cb399-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="cb399-111">您也可以使用 Lync Server 控制台更新現有撥號對應表中的區域。</span><span class="sxs-lookup"><span data-stu-id="cb399-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="cb399-112">如需使用 Lync Server 控制台的詳細資訊，請參閱 [在 Lync server 2013 中修改撥號](lync-server-2013-modify-a-dial-plan.md)對應表。</span><span class="sxs-lookup"><span data-stu-id="cb399-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="cb399-113">若要確認撥號對應表是否已設定區域屬性</span><span class="sxs-lookup"><span data-stu-id="cb399-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="cb399-114">以 RTCUniversalServerAdmins 群組成員或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="cb399-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="cb399-115">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="cb399-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cb399-116">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cb399-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="cb399-117">例如：</span><span class="sxs-lookup"><span data-stu-id="cb399-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="cb399-118">在此範例中，會傳回組織中所有已設定的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="cb399-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="cb399-119">檢閱傳回的撥號對應表，檢查是否有任何一項缺少電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="cb399-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="cb399-120">如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。</span><span class="sxs-lookup"><span data-stu-id="cb399-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="cb399-121">若要設定撥號對應表的區域屬性</span><span class="sxs-lookup"><span data-stu-id="cb399-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="cb399-122">以 RTCUniversalServerAdmins 群組成員或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="cb399-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="cb399-123">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="cb399-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cb399-124">針對任何缺少電話撥入式會議區域的撥號對應表，執行：</span><span class="sxs-lookup"><span data-stu-id="cb399-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="cb399-125">例如：</span><span class="sxs-lookup"><span data-stu-id="cb399-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="cb399-126">在此範例中，將修改識別為 Redmond 的撥號對應表，以將其 DialinConferencingRegion 屬性設為 "US West Coast"。</span><span class="sxs-lookup"><span data-stu-id="cb399-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="cb399-127">如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。</span><span class="sxs-lookup"><span data-stu-id="cb399-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

