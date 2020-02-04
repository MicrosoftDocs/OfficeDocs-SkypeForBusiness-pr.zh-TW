---
title: 使用 [建立翻譯規則] 工具建立或修改翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d45ca4e04146a175ec2782aa798ac27559fce495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="7867d-102">使用 Lync Server 2013 中的 [建立翻譯規則] 工具來建立或修改翻譯規則</span><span class="sxs-lookup"><span data-stu-id="7867d-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7867d-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="7867d-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="7867d-104">如果您想要定義翻譯規則，請在 [**建立翻譯規則**] 工具中輸入一組值，並啟用 Lync Server [控制台] 來為您產生對應的相符模式與翻譯規則，以執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7867d-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="7867d-105">或者，您也可以手動寫入正則運算式，以定義相符的模式和轉換規則。</span><span class="sxs-lookup"><span data-stu-id="7867d-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="7867d-106">如需詳細資訊，請參閱[在 Lync Server 2013 中手動建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="7867d-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="7867d-107">使用 [建立翻譯規則] 工具定義規則</span><span class="sxs-lookup"><span data-stu-id="7867d-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="7867d-108">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="7867d-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7867d-109">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="7867d-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="7867d-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7867d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7867d-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7867d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7867d-112">若要開始定義翻譯規則，請遵循在[Lync server 2013 的 [透過媒體旁路處理] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步驟，或在 lync server 2013 中的 [透過步驟 9][設定主幹，而不使用 [媒體旁路](lync-server-2013-configure-a-trunk-without-media-bypass.md)]。</span><span class="sxs-lookup"><span data-stu-id="7867d-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="7867d-113">在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 底下，輸入描述所翻譯之數位模式的名稱。</span><span class="sxs-lookup"><span data-stu-id="7867d-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="7867d-114">可選在 [**描述**] 底下，輸入翻譯規則的描述，例如**美國國際長途撥號**。</span><span class="sxs-lookup"><span data-stu-id="7867d-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="7867d-115">在對話方塊的 [**建立翻譯規則**] 區段中，于下欄欄位中輸入值：</span><span class="sxs-lookup"><span data-stu-id="7867d-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="7867d-116">**起始位數**：（選擇性）指定您想要模式符合的前置數位數位。</span><span class="sxs-lookup"><span data-stu-id="7867d-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="7867d-117">例如，在這個**+** 欄位中輸入，以符合 e.i 格式（開頭為 +）的數位。</span><span class="sxs-lookup"><span data-stu-id="7867d-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="7867d-118">**長度**：指定 [相符] 模式中的位數，並選取您想要模式與此長度完全相同、至少為此長度或任何長度。</span><span class="sxs-lookup"><span data-stu-id="7867d-118">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="7867d-119">例如，輸入**11** ，然後在下拉式清單中選取 [**至少**]，以符合長度至少為11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="7867d-119">For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="7867d-120">**要移除的位數**：（選用）指定要移除的起始位數數。</span><span class="sxs-lookup"><span data-stu-id="7867d-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="7867d-121">例如，輸入**1**來去掉**+** 數位開頭的。</span><span class="sxs-lookup"><span data-stu-id="7867d-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="7867d-122">**要加上的位數**：（選擇性）指定要在已翻譯數位前加上的數位。</span><span class="sxs-lookup"><span data-stu-id="7867d-122">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="7867d-123">例如，如果您想要在套用規則時將011附加到已翻譯的編號中，請輸入**011** 。</span><span class="sxs-lookup"><span data-stu-id="7867d-123">For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="7867d-124">您在這些欄位中輸入的值會反映在 [相符] 與 [**翻譯規則**] 欄位的**模式**中。</span><span class="sxs-lookup"><span data-stu-id="7867d-124">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="7867d-125">例如，如果您指定前面的範例值，則在 [模式] 中產生的正則運算式會與 field**相符**：</span><span class="sxs-lookup"><span data-stu-id="7867d-125">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="7867d-126">**^\\+ （\\d{9}\\d +） $**</span><span class="sxs-lookup"><span data-stu-id="7867d-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="7867d-127">[**翻譯規則**] 欄位會指定已翻譯數位格式的模式。</span><span class="sxs-lookup"><span data-stu-id="7867d-127">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="7867d-128">此模式有兩個部分：</span><span class="sxs-lookup"><span data-stu-id="7867d-128">This pattern has two parts:</span></span>
    
      - <span data-ttu-id="7867d-129">代表 [相符] 模式中之位數的值（例如， **$1**）</span><span class="sxs-lookup"><span data-stu-id="7867d-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="7867d-130">可選您可以在 [**要新增的數位**] 欄位中輸入的值。</span><span class="sxs-lookup"><span data-stu-id="7867d-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="7867d-131">使用上述範例值， **011 $ 1**會出現在 [**翻譯規則**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="7867d-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="7867d-132">套用此翻譯規則時，+ 441235551010 會變成011441235551010。</span><span class="sxs-lookup"><span data-stu-id="7867d-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="7867d-133">按一下 **[確定]** 儲存翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="7867d-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="7867d-134">按一下 **[確定]** 以儲存幹線設定。</span><span class="sxs-lookup"><span data-stu-id="7867d-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="7867d-135">在 [**幹線**設定] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="7867d-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7867d-136">每當您建立或修改翻譯規則時，您必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="7867d-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="7867d-137">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="7867d-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7867d-138">請參閱</span><span class="sxs-lookup"><span data-stu-id="7867d-138">See Also</span></span>


[<span data-ttu-id="7867d-139">在 Lync Server 2013 中手動建立或修改翻譯規則</span><span class="sxs-lookup"><span data-stu-id="7867d-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
<span data-ttu-id="7867d-140">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="7867d-140">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>  
[<span data-ttu-id="7867d-141">在 Lync Server 2013 中設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="7867d-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="7867d-142">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="7867d-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="7867d-143">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="7867d-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

