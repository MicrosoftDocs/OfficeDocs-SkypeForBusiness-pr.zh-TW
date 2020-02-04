---
title: Lync Server 2013：確定撥號對應表具有指派的區域
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
ms.openlocfilehash: cd8790671157b823464a3b4b594ea8428a888f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="8f728-102">確認 Lync Server 2013 已指派地區的撥號方案</span><span class="sxs-lookup"><span data-stu-id="8f728-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f728-103">_**主題上次修改日期：** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="8f728-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="8f728-104">電話撥入式會議所用的撥號方案需要將電話撥**入**式會議區域指定為與適當的撥號方案關聯電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="8f728-104">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="8f728-105">當您設定撥號方案時，請指定適用于該撥號方案的電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="8f728-105">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="8f728-106">接著，當您建立撥入存取號碼時，請選取將存取號碼與適當的撥號方案相關聯的地區。</span><span class="sxs-lookup"><span data-stu-id="8f728-106">Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="8f728-107">由於對所有撥號方案指定區域很重要，因此建議您使用此程式來確認所有撥號方案都有地區。</span><span class="sxs-lookup"><span data-stu-id="8f728-107">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions.</span></span> <span data-ttu-id="8f728-108">此為選用步驟。</span><span class="sxs-lookup"><span data-stu-id="8f728-108">This step is optional.</span></span>

<span data-ttu-id="8f728-109">使用**CsDialPlan** Cmdlet 來驗證該區域是否已針對所有電話撥入式會議撥號方案進行設定。</span><span class="sxs-lookup"><span data-stu-id="8f728-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="8f728-110">如果撥號方案中的區域遺失，您可以使用**CsDialPlan** Cmdlet 來設定區域。</span><span class="sxs-lookup"><span data-stu-id="8f728-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="8f728-111">您也可以使用 Lync Server [控制台] 來更新現有撥號方案中的區域。</span><span class="sxs-lookup"><span data-stu-id="8f728-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="8f728-112">如需使用 Lync Server [控制台] 的詳細資料，請參閱[在 Lync server 2013 中修改撥號方案](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="8f728-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="8f728-113">驗證撥號方案是否已設定 region 屬性</span><span class="sxs-lookup"><span data-stu-id="8f728-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="8f728-114">以 RTCUniversalServerAdmins 群組的成員或**cs-VoiceAdministrator**、 **cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="8f728-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="8f728-115">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="8f728-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8f728-116">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8f728-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="8f728-117">例如：</span><span class="sxs-lookup"><span data-stu-id="8f728-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="8f728-118">在這個範例中，會傳回為貴組織設定的所有撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="8f728-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="8f728-119">查看傳回的撥號方案，以找出遺失電話撥入式會議區域的任何專案。</span><span class="sxs-lookup"><span data-stu-id="8f728-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="8f728-120">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="8f728-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="8f728-121">若要設定撥號方案的 region 屬性</span><span class="sxs-lookup"><span data-stu-id="8f728-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="8f728-122">以 RTCUniversalServerAdmins 群組的成員或**cs-VoiceAdministrator**、 **cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="8f728-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="8f728-123">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="8f728-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8f728-124">針對遺失電話撥入式會議區域的任何撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="8f728-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="8f728-125">例如：</span><span class="sxs-lookup"><span data-stu-id="8f728-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="8f728-126">在這個範例中，會修改具有雷德蒙者身分識別的撥號計畫，以將 DialinConferencingRegion 屬性設為 "US West Coast"。</span><span class="sxs-lookup"><span data-stu-id="8f728-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="8f728-127">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="8f728-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

