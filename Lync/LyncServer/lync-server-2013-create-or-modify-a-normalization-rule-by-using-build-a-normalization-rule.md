---
title: 使用組建正常化規則建立或修改正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 527510ac9b683df191414f5dffe456353d9cf277
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="bfe57-102">在 Lync Server 2013 中使用組建正常化規則來建立或修改正常化規則</span><span class="sxs-lookup"><span data-stu-id="bfe57-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfe57-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bfe57-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bfe57-104">如果您想要在 Lync Server [控制台] 中建立或修改正常化規則，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="bfe57-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="bfe57-105">或者，如果您想要手動建立或修改正常化規則，請參閱[在 Lync Server 2013 中手動建立或修改正常化規則](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe57-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="bfe57-106">使用組建正常化規則定義規則</span><span class="sxs-lookup"><span data-stu-id="bfe57-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="bfe57-107">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="bfe57-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bfe57-108">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe57-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bfe57-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="bfe57-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bfe57-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe57-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bfe57-111">可選請遵循在[Lync server 2013](lync-server-2013-create-a-dial-plan.md)至步驟11中建立撥號計畫中的步驟，或透過步驟 10[修改 lync server 2013 中的撥號方案](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe57-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="bfe57-112">在**新的 [正常化規則**] 或 [**編輯正常化規則**] 中，輸入一個名稱，以在**名稱**中描述正常化的數位模式（例如， **5DigitExtension**）。</span><span class="sxs-lookup"><span data-stu-id="bfe57-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="bfe57-113">可選在 [**描述**] 中，輸入正常化規則的描述（例如，"轉譯5位數的延伸"）。</span><span class="sxs-lookup"><span data-stu-id="bfe57-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="bfe57-114">在 [**建立正常化規則**] 中，于下欄欄位中輸入值：</span><span class="sxs-lookup"><span data-stu-id="bfe57-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="bfe57-115">**起始位數**   （選用）指定您想要模式符合的撥號號碼的前導位數。</span><span class="sxs-lookup"><span data-stu-id="bfe57-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="bfe57-116">例如，如果您想要讓模式符合從425開始的撥入號碼，請輸入**425** 。</span><span class="sxs-lookup"><span data-stu-id="bfe57-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="bfe57-117">**[長度**   ]：指定相符模式中的數位位數，並選取您想要模式符合這個長度、與至少有此長度的撥號號碼相符，或與任何長度的撥入號碼相符。</span><span class="sxs-lookup"><span data-stu-id="bfe57-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="bfe57-118">**要移除**   的數位（選擇性）指定要從撥打的號碼中移除的起始位數，您想要讓模式符合該數位。</span><span class="sxs-lookup"><span data-stu-id="bfe57-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="bfe57-119">**要加**   上的位數（選擇性）指定要在撥打的號碼中加上您想要模式相符的數位。</span><span class="sxs-lookup"><span data-stu-id="bfe57-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="bfe57-120">您在這些欄位中輸入的值會反映在模式中，**以符合**與**翻譯規則**。</span><span class="sxs-lookup"><span data-stu-id="bfe57-120">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="bfe57-121">例如，如果您保留的**起始位數**為空白，請在**長度**欄位中輸入**7** ，然後選取 [**精確**]，然後指定要**移除**的 [ **0** ]，即**要與之相符**的正則運算式如下：</span><span class="sxs-lookup"><span data-stu-id="bfe57-121">For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="bfe57-122">**^ （\\d{7}） $**</span><span class="sxs-lookup"><span data-stu-id="bfe57-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="bfe57-123">在**翻譯規則**中，指定翻譯的 e. 164 電話號碼格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bfe57-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="bfe57-124">代表 [相符] 模式中指定之位數的值。</span><span class="sxs-lookup"><span data-stu-id="bfe57-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="bfe57-125">例如，如果 [相符] 模式是 **[^\\（{7}d）** ]，則翻譯規則中的 **$1**代表7位數的撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="bfe57-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="bfe57-126">可選在 [位數] 中輸入一個值，以指定要在已翻譯的數位前**加**上的位數（例如 **+ 1425**）。</span><span class="sxs-lookup"><span data-stu-id="bfe57-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="bfe57-127">例如，如果**要符合的模式**包含 **^ （\\d{7}） $** 做為撥打電話號碼和**翻譯規則**的模式，包含 **+ 1425 $ 1**做為 e.i 電話號碼的模式，規則會將5550100標準化至 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="bfe57-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="bfe57-128">可選如果正常化規則所產生的是貴組織內部的電話號碼，請選取 [**內部擴充**]。</span><span class="sxs-lookup"><span data-stu-id="bfe57-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="bfe57-129">可選輸入數位以測試正常化規則，**然後按一下 [** 執行]。</span><span class="sxs-lookup"><span data-stu-id="bfe57-129">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="bfe57-130">測試結果會顯示在 [**輸入要測試的號碼**] 下。</span><span class="sxs-lookup"><span data-stu-id="bfe57-130">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bfe57-131">您可以儲存尚未經過測試的正常化規則，稍後再重新設定。</span><span class="sxs-lookup"><span data-stu-id="bfe57-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="bfe57-132">如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="bfe57-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="bfe57-133">按一下 **[確定]** 以儲存正常化規則。</span><span class="sxs-lookup"><span data-stu-id="bfe57-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="bfe57-134">按一下 **[確定]** 儲存撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="bfe57-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="bfe57-135">在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="bfe57-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bfe57-136">每當您建立或變更正常化規則時，您必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="bfe57-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="bfe57-137">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="bfe57-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfe57-138">請參閱</span><span class="sxs-lookup"><span data-stu-id="bfe57-138">See Also</span></span>


[<span data-ttu-id="bfe57-139">在 Lync Server 2013 中手動建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="bfe57-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="bfe57-140">在 Lync Server 2013 中建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="bfe57-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="bfe57-141">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="bfe57-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="bfe57-142">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="bfe57-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="bfe57-143">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="bfe57-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

