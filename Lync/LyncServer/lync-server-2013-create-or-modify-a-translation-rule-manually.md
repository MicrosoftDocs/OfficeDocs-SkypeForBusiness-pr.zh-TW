---
title: Lync Server 2013：手動建立或修改轉譯規則
description: Lync Server 2013：手動建立或修改轉譯規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f393ca1983e072090cc27d47b142dace8b566c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574499"
---
# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="ceb71-103">在 Lync Server 2013 中手動建立或修改轉譯規則</span><span class="sxs-lookup"><span data-stu-id="ceb71-103">Create or modify a translation rule manually in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceb71-104">_**主題上次修改日期：** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="ceb71-104">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="ceb71-105">若要撰寫相符樣式及轉譯規則的規則運算式以定義轉譯規則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="ceb71-105">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="ceb71-106">或者，您也可以在 **組建轉譯規則** 工具中輸入一組值，並讓 Lync Server 控制台為您產生對應的符合模式和轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="ceb71-106">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="ceb71-107">如需詳細資訊，請參閱 [使用 Lync Server 2013 中的組建轉譯規則工具建立或修改轉譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="ceb71-107">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="ceb71-108">若要手動定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="ceb71-108">To define a translation rule manually</span></span>

1.  <span data-ttu-id="ceb71-109">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ceb71-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ceb71-110">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="ceb71-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ceb71-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ceb71-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ceb71-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ceb71-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ceb71-113">若要開始定義轉譯規則，請遵循在 lync server 2013 中的「透過 [媒體旁路」設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md) 中的步驟，或在 [lync Server 2013 中設定](lync-server-2013-configure-a-trunk-without-media-bypass.md) 具有媒體旁路的主幹（透過步驟9）。</span><span class="sxs-lookup"><span data-stu-id="ceb71-113">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="ceb71-114">在 **[新增轉譯規則]** 或 **[編輯轉譯規則]** 頁面的 **[名稱]** 欄位中，輸入可描述所轉譯號碼模式的名稱。</span><span class="sxs-lookup"><span data-stu-id="ceb71-114">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="ceb71-115">(選用) 在 [描述]\*\*\*\* 中，輸入轉譯規則的描述，例如**美國國際長途撥號**。</span><span class="sxs-lookup"><span data-stu-id="ceb71-115">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="ceb71-116">按一下 **[建置轉譯規則]** 區段底部的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="ceb71-116">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="ceb71-117">在 [輸入規則運算式]\*\*\*\* 中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="ceb71-117">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="ceb71-118">在 [符合此模式]\*\*\*\* 中，指定用來比對要轉譯之號碼的模式。</span><span class="sxs-lookup"><span data-stu-id="ceb71-118">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="ceb71-119">在 [轉譯規則]\*\*\*\* 中，指定轉譯號碼的格式模式。</span><span class="sxs-lookup"><span data-stu-id="ceb71-119">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="ceb71-120">例如，如果您在**符合此模式**的情況下輸入\*\* ^ \\ + (\\ d {9} \\ +) $\*\* 和**轉譯規則**中的**011 $ 1** ，則此規則會將 + 441235551010 轉譯為011441235551010。</span><span class="sxs-lookup"><span data-stu-id="ceb71-120">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="ceb71-121">按一下 \*\* [確定]\*\* 儲存轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="ceb71-121">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="ceb71-122">按一下 \*\* [確定]\*\* 儲存主幹組態。</span><span class="sxs-lookup"><span data-stu-id="ceb71-122">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="ceb71-123">在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="ceb71-123">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ceb71-124">當您建立或修改轉譯規則時，您都必須執行 [全部認可]<STRONG></STRONG> 命令才能發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="ceb71-124">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ceb71-125">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="ceb71-125">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ceb71-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ceb71-126">See Also</span></span>


[<span data-ttu-id="ceb71-127">在 Lync Server 2013 中使用組建轉譯規則工具建立或修改轉譯規則</span><span class="sxs-lookup"><span data-stu-id="ceb71-127">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="ceb71-128">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="ceb71-128">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="ceb71-129">在 Lync Server 2013 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="ceb71-129">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="ceb71-130">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="ceb71-130">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ceb71-131">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="ceb71-131">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

