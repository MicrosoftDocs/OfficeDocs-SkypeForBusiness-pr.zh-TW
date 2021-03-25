---
title: 在商務用 Skype Server 中建立或修改呼叫者識別碼簡報的轉譯規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 摘要：瞭解如何使用商務用 Skype Server [控制台] 設定來電者識別碼。
ms.openlocfilehash: 2ffe547927c9f4d6df16a06cc8c95dff9814fc7f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113029"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="c836c-103">在商務用 Skype Server 中建立或修改呼叫者識別碼簡報的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="c836c-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="c836c-104">**摘要：** 瞭解如何使用商務用 Skype Server [控制台] 設定來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="c836c-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="c836c-105">在商務用 Skype Server 中，被叫方的電話號碼 (也就是說，稱為) 的電話號碼可以從 e.164 格式轉譯成  _主幹對等_ (（即相關聯的閘道、專用交換機 (PBX) 或 SIP 主幹) ）所需的本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="c836c-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="c836c-106">若要執行此項作業，您必須定義一或多個轉譯規則，以在將其路由傳送至主幹對等之前轉譯要求 URI。</span><span class="sxs-lookup"><span data-stu-id="c836c-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="c836c-107">商務用 Skype 伺服器也可讓您選擇翻譯通話方的電話號碼 (也就是說，來電者撥打的電話號碼會從) （e.164 格式）為主幹對等項所需的本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="c836c-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="c836c-108">例如，您可撰寫轉譯規則，來將撥號字串開頭的 +44 移除，並以 0144 來取代。</span><span class="sxs-lookup"><span data-stu-id="c836c-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c836c-109">使用商務用 Skype Server 控制台設定來電者識別碼</span><span class="sxs-lookup"><span data-stu-id="c836c-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c836c-110">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c836c-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c836c-111">在左導覽列中，按一下 **[語音路由]**，然後按一下 **[主幹組態]**。</span><span class="sxs-lookup"><span data-stu-id="c836c-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="c836c-112">在 **[主幹組態]** 頁面上，按兩下現有的主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c836c-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="c836c-113">若要設定來電者 ID 呈現方式：</span><span class="sxs-lookup"><span data-stu-id="c836c-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="c836c-114">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="c836c-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="c836c-115">在 **[來電號碼轉譯規則]** 中，按一下您想要與主幹建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c836c-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="c836c-116">若要定義新的轉譯規則並將其與主幹建立關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c836c-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="c836c-117">如需定義新規則的詳細資訊，請參閱部署檔中的  [定義轉譯規則](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) 。</span><span class="sxs-lookup"><span data-stu-id="c836c-117">For details about defining a new rule, see  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

   - <span data-ttu-id="c836c-118">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="c836c-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="c836c-119">如需詳細資訊，請參閱部署文件中的[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)。</span><span class="sxs-lookup"><span data-stu-id="c836c-119">For details, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

   - <span data-ttu-id="c836c-120">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="c836c-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="c836c-121">如需詳細資訊，＜[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)＞。</span><span class="sxs-lookup"><span data-stu-id="c836c-121">For details, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).</span></span>

   - <span data-ttu-id="c836c-122">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="c836c-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="c836c-123">如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="c836c-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>