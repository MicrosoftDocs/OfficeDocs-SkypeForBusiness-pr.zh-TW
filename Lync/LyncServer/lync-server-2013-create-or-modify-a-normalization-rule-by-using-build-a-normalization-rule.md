---
title: 使用組建正常化規則建立或修改正規化規則
description: 使用建立正規化規則來建立或修改正規化規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 824936359c070090ad4225a3ead6e8e46fe14785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574599"
---
# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="0752a-103">在 Lync Server 2013 中使用組建標準化規則來建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="0752a-103">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0752a-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0752a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0752a-105">如果您想要在 Lync Server [控制台] 中建立或修改正規化規則，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="0752a-105">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="0752a-106">或者，如果您想要手動建立或修改正規化規則，請參閱 [在 Lync Server 2013 中手動建立或修改正規化規則](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="0752a-106">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="0752a-107">使用組建正常化規則定義規則</span><span class="sxs-lookup"><span data-stu-id="0752a-107">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="0752a-108">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="0752a-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0752a-109">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="0752a-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0752a-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="0752a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0752a-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0752a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0752a-112"> (選用) 請遵循在 [lync server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md) 對應表中的步驟，在 [lync server 2013](lync-server-2013-modify-a-dial-plan.md) 中透過步驟10修改撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0752a-112">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="0752a-113">在 [ **新增正規化規則** ] 或 [編輯正規化 **規則**] 中，輸入描述 [ **名稱** ] 中正規化的號碼模式的名稱 (例如， **5DigitExtension**) 。</span><span class="sxs-lookup"><span data-stu-id="0752a-113">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="0752a-114"> (選用) 在 [ **描述**] 中，輸入正規化規則的描述 (例如，「轉譯5位數分機」 ) 。</span><span class="sxs-lookup"><span data-stu-id="0752a-114">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="0752a-115">在 [ **建立正規化規則**] 中，在下欄欄位中輸入值：</span><span class="sxs-lookup"><span data-stu-id="0752a-115">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="0752a-116">**起始位數**     (選用) 指定您想要模式符合的撥號號碼的前置位數。</span><span class="sxs-lookup"><span data-stu-id="0752a-116">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="0752a-117">例如，如果您希望模式比對從425開始的撥號號碼，請輸入 **425** 。</span><span class="sxs-lookup"><span data-stu-id="0752a-117">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="0752a-118">**長度**    指定比對模式中的位數，然後選取是否要讓模式完全符合此長度、比對至少一個長度的撥號號碼，或比對任何長度的撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="0752a-118">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="0752a-119">**要移除**     的位數 (選用) 指定您想要與模式相符的撥號號碼中所要移除的開始數位數位。</span><span class="sxs-lookup"><span data-stu-id="0752a-119">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="0752a-120">**要新增**     的位數 (選用) 指定要新增至您想要模式符合的撥號號碼的數位。</span><span class="sxs-lookup"><span data-stu-id="0752a-120">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="0752a-121">您在這些欄位中輸入的值會反映在模式中， **以符合** 和 **轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="0752a-121">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="0752a-122">例如，如果您保留空白的**開始數位**，請在**長度**欄位中輸入**7** ，然後選取 [**完全相同**]，並指定**要移除的數位** **0** ，在**模式**中所產生的正則運算式會比對：</span><span class="sxs-lookup"><span data-stu-id="0752a-122">For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="0752a-123">**^ (\\ d {7}) $**</span><span class="sxs-lookup"><span data-stu-id="0752a-123">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="0752a-124">在 [ **轉譯規則**] 中，指定轉譯的 e.164 電話號碼格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0752a-124">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="0752a-125">代表匹配模式中指定之位數的值。</span><span class="sxs-lookup"><span data-stu-id="0752a-125">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="0752a-126">例如，如果相符的模式是 **^ (\\ d {7}) $** 後 **$1** 的轉譯規則代表7位數撥號碼。</span><span class="sxs-lookup"><span data-stu-id="0752a-126">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="0752a-127"> (選用) 在 [ **要新增的位數** ] 欄位中輸入值，以指定要附加到已翻譯的號碼的位數 (例如， **+ 1425**) 。</span><span class="sxs-lookup"><span data-stu-id="0752a-127">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="0752a-128">例如，如果 **要比對的模式** 包含 **^ (\\ d {7}) $** ，表示撥號號碼和 **轉譯規則** 的模式包含 **+ 1425 $ 1** 做為 e.164 電話號碼的模式，該規則會將5550100標準化為 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="0752a-128">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="0752a-129"> (選用) 如果正規化規則會產生您組織內部的電話號碼，請選取 [ **內部分機**]。</span><span class="sxs-lookup"><span data-stu-id="0752a-129">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="0752a-130"> (選用) 請輸入號碼以測試正規化規則，然後按一下 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="0752a-130">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="0752a-131">測試結果會顯示在 [ **輸入要測試的號碼**] 底下。</span><span class="sxs-lookup"><span data-stu-id="0752a-131">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0752a-132">您可以儲存尚未通過測試的正規化規則，然後稍後再加以重新設定。</span><span class="sxs-lookup"><span data-stu-id="0752a-132">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="0752a-133">如需詳細資訊，請參閱 <A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="0752a-133">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="0752a-134">按一下 **[確定]** 儲存正規化規則。</span><span class="sxs-lookup"><span data-stu-id="0752a-134">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="0752a-135">按一下 **[確定]** 儲存撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0752a-135">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="0752a-136">在 [ **撥號** 對應表] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="0752a-136">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0752a-137">當您建立或變更正規化規則時，您必須執行 [ <STRONG>全部認可</STRONG> ] 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="0752a-137">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="0752a-138">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="0752a-138">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0752a-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0752a-139">See Also</span></span>


[<span data-ttu-id="0752a-140">在 Lync Server 2013 中手動建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="0752a-140">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="0752a-141">在 Lync Server 2013 中建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="0752a-141">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="0752a-142">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="0752a-142">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="0752a-143">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="0752a-143">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="0752a-144">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="0752a-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

