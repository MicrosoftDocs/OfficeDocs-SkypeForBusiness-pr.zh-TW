---
title: Lync Server 2013：手動建立或修改正規化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="28368-102">在 Lync Server 2013 中手動建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="28368-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28368-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="28368-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="28368-104">如果您想要手動建立或修改正常化規則，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="28368-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="28368-105">如果您想要使用在 Lync Server [控制台] 中建立正常化規則來建立或修改正常化規則，請參閱[使用 Lync server 2013 中的 [建立正常化規則] 來建立或修改正常化](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)規則。</span><span class="sxs-lookup"><span data-stu-id="28368-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="28368-106">手動定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="28368-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="28368-107">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="28368-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="28368-108">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="28368-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="28368-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="28368-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28368-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="28368-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="28368-111">可選遵循在[Lync server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)中的步驟，或在[lync Server 2013 中修改撥號計畫](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="28368-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="28368-112">在**新的 [正常化規則**] 或 [**編輯正常化規則**] 中，輸入描述**名稱**中要正常化之數位模式的名稱（例如，將 [正常化規則**5DigitExtension**] 命名）。</span><span class="sxs-lookup"><span data-stu-id="28368-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="28368-113">可選在 [**描述**] 欄位中，輸入正常化規則的描述（例如，「轉譯5位數的延伸」）。</span><span class="sxs-lookup"><span data-stu-id="28368-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="28368-114">在 [**建立正常化規則**] 中，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="28368-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="28368-115">在 [輸入**正則運算式**] 中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="28368-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="28368-116">在 [**符合這個模式**] 中，指定您要用來與撥打的電話號碼相符的模式。</span><span class="sxs-lookup"><span data-stu-id="28368-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="28368-117">在 [**翻譯規則**] 中，指定翻譯的 e. （164個電話號碼）格式的模式。</span><span class="sxs-lookup"><span data-stu-id="28368-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="28368-118">例如，如果您在**翻譯規則\*\*\*\*中輸入** **^\\（d{7}） $** 和 **+ 1425 $ 1** ，規則會將5550100標準化至 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="28368-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="28368-119">可選如果正常化規則所產生的是貴組織內部的電話號碼，請選取 [**內部擴充**]。</span><span class="sxs-lookup"><span data-stu-id="28368-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="28368-120">可選輸入數位以測試正常化規則，**然後按一下 [** 執行]。</span><span class="sxs-lookup"><span data-stu-id="28368-120">(Optional) Enter a number to test the normalization rule and then click **Go**.</span></span> <span data-ttu-id="28368-121">測試結果會顯示在 [**輸入要測試的號碼**] 下。</span><span class="sxs-lookup"><span data-stu-id="28368-121">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28368-122">您可以儲存尚未經過測試的正常化規則，稍後再重新設定。</span><span class="sxs-lookup"><span data-stu-id="28368-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="28368-123">如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="28368-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="28368-124">按一下 **[確定]** 以儲存正常化規則。</span><span class="sxs-lookup"><span data-stu-id="28368-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="28368-125">按一下 **[確定]** 儲存撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="28368-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="28368-126">在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="28368-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28368-127">每當您建立或變更正常化規則時，您必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="28368-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="28368-128">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="28368-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28368-129">請參閱</span><span class="sxs-lookup"><span data-stu-id="28368-129">See Also</span></span>


[<span data-ttu-id="28368-130">在 Lync Server 2013 中使用組建正常化規則來建立或修改正常化規則</span><span class="sxs-lookup"><span data-stu-id="28368-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="28368-131">在 Lync Server 2013 中建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="28368-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="28368-132">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="28368-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="28368-133">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="28368-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="28368-134">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="28368-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

