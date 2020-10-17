---
title: 使用組建轉譯規則工具建立或修改轉譯規則
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
ms.openlocfilehash: 2a2adc9d0ca10382aa7faa7abf6f9ea46eb6cf51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525810"
---
# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="a2e5a-102">在 Lync Server 2013 中使用組建轉譯規則工具建立或修改轉譯規則</span><span class="sxs-lookup"><span data-stu-id="a2e5a-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2e5a-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a2e5a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a2e5a-104">若要定義轉譯規則，請在 [ **組建轉譯規則** ] 工具中輸入一組值，並讓 Lync Server 控制台為您產生對應的符合模式和轉譯規則時，遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="a2e5a-105">或者，您可以手動寫入正則運算式，以定義符合的模式和轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="a2e5a-106">如需詳細資訊，請參閱 [在 Lync Server 2013 中手動建立或修改轉譯規則](lync-server-2013-create-or-modify-a-translation-rule-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="a2e5a-107">使用組建轉譯規則工具定義規則</span><span class="sxs-lookup"><span data-stu-id="a2e5a-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="a2e5a-108">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a2e5a-109">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a2e5a-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a2e5a-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a2e5a-112">若要開始定義轉譯規則，請遵循在 lync server 2013 中的「透過 [媒體旁路」設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md) 中的步驟，或在 [lync Server 2013 中設定](lync-server-2013-configure-a-trunk-without-media-bypass.md) 具有媒體旁路的主幹（透過步驟9）。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="a2e5a-113">在 [**新增轉譯規則**] 或 [**編輯轉譯規則**] 頁面的 [**名稱**] 下，輸入描述所轉譯之號碼模式的名稱。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="a2e5a-114"> (選用) 在 [ **描述**] 底下，輸入轉譯規則的描述，例如 **美國國際長途撥號**。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="a2e5a-115">在對話方塊的 [ **組建轉譯規則** ] 區段中，于下欄欄位中輸入值：</span><span class="sxs-lookup"><span data-stu-id="a2e5a-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="a2e5a-116">**開始位數**： (選用) 指定您想要模式比對的數位前置位數。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="a2e5a-117">例如， **+** 在此欄位中輸入，以比對以 +) 開頭的 (164 格式的數位。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="a2e5a-118">**Length**：指定比對模式中的位數，並選取是否要讓模式比對此長度的數位完全一致、至少此長度或任何長度。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-118">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="a2e5a-119">例如，輸入 **11** ， **至少** 在下拉式清單中選取，以比對長度至少為11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-119">For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="a2e5a-120">**要移除的位數**： (選用) 指定要移除的開始數位的數目。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="a2e5a-121">例如，輸入 **1** 以 **+** 從號碼的開頭抽出。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="a2e5a-122">**要新增的位數**： (選用) 指定要預先編號為已轉譯之數位的位數。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-122">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="a2e5a-123">例如，如果您希望在套用規則時，將011預先加入翻譯的編號，請輸入 **011** 。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-123">For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="a2e5a-124">您在這些欄位中輸入的值，會反映在 [ **要搭配的模式** ] 和 [ **轉譯規則** ] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-124">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="a2e5a-125">例如，如果您指定前面的範例值，就會在 [ **要搭配的模式** ] 欄位中產生正則運算式：</span><span class="sxs-lookup"><span data-stu-id="a2e5a-125">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="a2e5a-126">**^\\+ (\\ d {9} \\ d +) $**</span><span class="sxs-lookup"><span data-stu-id="a2e5a-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="a2e5a-127">**轉譯規則**欄位會指定轉譯後的數位格式的模式。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-127">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="a2e5a-128">這種模式分為兩個部分：</span><span class="sxs-lookup"><span data-stu-id="a2e5a-128">This pattern has two parts:</span></span>
    
      - <span data-ttu-id="a2e5a-129">值 (例如， **$1**) ，代表比對模式中的數位數目</span><span class="sxs-lookup"><span data-stu-id="a2e5a-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="a2e5a-130"> (選用) 您可以在 [ **要加入的數位** ] 欄位中輸入值，以進行前置計算</span><span class="sxs-lookup"><span data-stu-id="a2e5a-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="a2e5a-131">使用上述範例值， **011 $ 1** 會出現在 **轉譯規則** 欄位中。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="a2e5a-132">套用此轉譯規則時，+ 441235551010 會變成011441235551010。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="a2e5a-133">按一下 \*\* [確定]\*\* 儲存轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="a2e5a-134">按一下 \*\* [確定]\*\* 儲存主幹組態。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="a2e5a-135">在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a2e5a-136">當您建立或修改轉譯規則時，您都必須執行 [全部認可]<STRONG></STRONG> 命令才能發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a2e5a-137">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="a2e5a-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2e5a-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a2e5a-138">See Also</span></span>


[<span data-ttu-id="a2e5a-139">在 Lync Server 2013 中手動建立或修改轉譯規則</span><span class="sxs-lookup"><span data-stu-id="a2e5a-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="a2e5a-140">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="a2e5a-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="a2e5a-141">在 Lync Server 2013 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="a2e5a-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="a2e5a-142">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="a2e5a-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="a2e5a-143">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="a2e5a-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

