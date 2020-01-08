---
title: Lync Server 2013：本機號碼簡報
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 016913ad68865f7d93512cc7383f2cfb47497ebe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="d88ae-102">Lync Server 2013 中的本機號碼簡報</span><span class="sxs-lookup"><span data-stu-id="d88ae-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d88ae-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d88ae-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d88ae-104">使用 Lync Server 2010 時，呼叫方的電話號碼（也就是呼叫的電話號碼）可以從164格式翻譯成幹線對等（也就是相關閘道、私人分支 exchange （PBX）或 SIP 主幹）所需的本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="d88ae-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="d88ae-105">若要這樣做，您必須先定義一或多個翻譯規則，才能轉換要求 URI，然後再將它傳送到幹線對等。</span><span class="sxs-lookup"><span data-stu-id="d88ae-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="d88ae-106">Lync Server 2013 提供了選項，可將呼叫方的電話號碼（也就是呼叫者撥打的電話號碼）從 E-164 格式轉換為幹線對等所需的本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="d88ae-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="d88ae-107">例如，您可以撰寫翻譯規則，以從撥號字串開頭移除 + 44，然後將它取代為0144。</span><span class="sxs-lookup"><span data-stu-id="d88ae-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="d88ae-108">**使用 Lync Server [控制台] 設定本機號碼**</span><span class="sxs-lookup"><span data-stu-id="d88ae-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="d88ae-109">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="d88ae-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d88ae-110">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d88ae-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d88ae-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d88ae-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d88ae-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d88ae-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d88ae-113">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="d88ae-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="d88ae-114">在 [**幹線**設定] 頁面上，按兩下現有的主幹（例如 [**全域**幹線]），以顯示 [**編輯主幹**設定] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="d88ae-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="d88ae-115">若要設定本機號碼方式：</span><span class="sxs-lookup"><span data-stu-id="d88ae-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="d88ae-116">若要從企業語音部署中所有可用的翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="d88ae-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d88ae-117">在 [**呼叫編號翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d88ae-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d88ae-118">若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d88ae-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="d88ae-119">如需有關定義新規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="d88ae-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d88ae-120">若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d88ae-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="d88ae-121">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="d88ae-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d88ae-122">若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="d88ae-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="d88ae-123">如需詳細資訊，請參閱[在 Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="d88ae-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="d88ae-124">若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="d88ae-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d88ae-125">如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="d88ae-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

