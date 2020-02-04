---
title: Lync Server 2013：手動建立或修改翻譯規則
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
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="e4783-102">在 Lync Server 2013 中手動建立或修改翻譯規則</span><span class="sxs-lookup"><span data-stu-id="e4783-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4783-103">_**主題上次修改日期：** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="e4783-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="e4783-104">如果您想要定義翻譯規則，方法是撰寫相符模式與翻譯規則的正則運算式，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="e4783-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="e4783-105">或者，您也可以在 [**建立翻譯規則**] 工具中輸入一組值，然後啟用 Lync Server [控制台] 來為您產生對應的相符模式與翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="e4783-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="e4783-106">如需詳細資訊，請參閱[使用 Lync Server 2013 中的 [建立翻譯規則] 工具建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="e4783-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="e4783-107">手動定義翻譯規則</span><span class="sxs-lookup"><span data-stu-id="e4783-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="e4783-108">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="e4783-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e4783-109">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e4783-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e4783-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e4783-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4783-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e4783-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4783-112">若要開始定義翻譯規則，請遵循在[Lync server 2013 的 [透過媒體旁路處理] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步驟，或在 lync server 2013 中的 [透過步驟 9][設定主幹，而不使用 [媒體旁路](lync-server-2013-configure-a-trunk-without-media-bypass.md)]。</span><span class="sxs-lookup"><span data-stu-id="e4783-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="e4783-113">在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 欄位中，輸入描述所翻譯之數位模式的名稱。</span><span class="sxs-lookup"><span data-stu-id="e4783-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="e4783-114">可選在 [**描述**] 中，輸入翻譯規則的描述，例如**美國國際長途撥號**。</span><span class="sxs-lookup"><span data-stu-id="e4783-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="e4783-115">按一下 [**組建翻譯規則**] 區段底部的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e4783-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="e4783-116">在 [輸入**正則運算式**] 中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="e4783-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="e4783-117">在 [**符合這個模式**] 中，指定將用來符合要翻譯之數位的模式。</span><span class="sxs-lookup"><span data-stu-id="e4783-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="e4783-118">在**翻譯規則**中，指定翻譯數位格式的模式。</span><span class="sxs-lookup"><span data-stu-id="e4783-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="e4783-119">例如，如果您在**翻譯規則**中輸入\*\* ^ \\+ （\\{9}\\d d +） $\*\* **與此模式**和**011 $ 1** ，規則會將 + 441235551010 轉換為011441235551010。</span><span class="sxs-lookup"><span data-stu-id="e4783-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="e4783-120">按一下 **[確定]** 儲存翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="e4783-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="e4783-121">按一下 **[確定]** 以儲存幹線設定。</span><span class="sxs-lookup"><span data-stu-id="e4783-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="e4783-122">在 [**幹線**設定] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="e4783-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4783-123">每當您建立或修改翻譯規則時，您必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="e4783-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="e4783-124">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="e4783-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4783-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="e4783-125">See Also</span></span>


<span data-ttu-id="e4783-126">[使用 Lync Server 2013 中的 [建立翻譯規則] 工具來建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)</span><span class="sxs-lookup"><span data-stu-id="e4783-126">[Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)</span></span>  
<span data-ttu-id="e4783-127">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="e4783-127">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>  
[<span data-ttu-id="e4783-128">在 Lync Server 2013 中設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="e4783-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="e4783-129">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="e4783-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="e4783-130">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="e4783-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

