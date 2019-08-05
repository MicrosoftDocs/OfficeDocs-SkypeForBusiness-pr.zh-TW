---
title: 在商務用 Skype Server 中建立或修改呼叫者識別碼簡報的翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '摘要: 瞭解如何使用商務用 Skype Server [控制台] 來設定本機號碼。'
ms.openlocfilehash: a305d420171fa10253f387e1fcbcfa2a50d72753
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190090"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="a2d37-103">在商務用 Skype Server 中建立或修改呼叫者識別碼簡報的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="a2d37-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="a2d37-104">**摘要:** 瞭解如何使用商務用 Skype Server [控制台] 設定本機號碼。</span><span class="sxs-lookup"><span data-stu-id="a2d37-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="a2d37-105">在商務用 Skype Server 中, 呼叫方的電話號碼 (也就是呼叫的電話號碼) 可以從. 164 格式翻譯成_中繼對端_所需的本機撥號格式 (也就是關聯的閘道、私人分支交換 (PBX) 或 SIP 幹線)。</span><span class="sxs-lookup"><span data-stu-id="a2d37-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="a2d37-106">若要這樣做, 您必須先定義一或多個翻譯規則, 才能轉換要求 URI, 然後再將它傳送到幹線對等。</span><span class="sxs-lookup"><span data-stu-id="a2d37-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="a2d37-107">商務用 Skype 伺服器也會提供將呼叫方的電話號碼 (也就是呼叫者撥打的電話號碼) 從 E-164 格式轉換為幹線對等所需的本機撥號格式的選項。</span><span class="sxs-lookup"><span data-stu-id="a2d37-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="a2d37-108">例如, 您可以撰寫翻譯規則, 以從撥號字串開頭移除 + 44, 然後將它取代為0144。</span><span class="sxs-lookup"><span data-stu-id="a2d37-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a2d37-109">使用商務用 Skype Server [控制台] 設定本機號碼</span><span class="sxs-lookup"><span data-stu-id="a2d37-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a2d37-110">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="a2d37-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a2d37-111">在左側導覽列中, 按一下 [**語音路由**], 然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="a2d37-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="a2d37-112">在 [**幹線**設定] 頁面上, 按兩下現有的主幹 (例如 [**全域**幹線]), 以顯示 [**編輯主幹**設定] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="a2d37-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="a2d37-113">若要設定本機號碼方式:</span><span class="sxs-lookup"><span data-stu-id="a2d37-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="a2d37-114">若要從企業語音部署中所有可用的翻譯規則清單中選擇一或多個規則, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="a2d37-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a2d37-115">在 [**呼叫編號翻譯規則**] 中, 按一下您要與主幹建立關聯的規則, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a2d37-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="a2d37-116">若要定義新的翻譯規則, 並將其與骨幹建立關聯, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="a2d37-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="a2d37-117">如需有關定義新規則的詳細資料, 請參閱在部署檔中[定義翻譯規則](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2d37-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="a2d37-118">若要編輯已經與主幹建立關聯的翻譯規則, 請按一下規則名稱, 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="a2d37-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="a2d37-119">如需詳細資訊, 請參閱在部署檔中[定義翻譯規則](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2d37-119">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="a2d37-120">若要複製現有的翻譯規則, 以做為定義新規則的起點, 請按一下規則名稱, 然後按一下 [**複製**], 然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="a2d37-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="a2d37-121">如需詳細資訊, 請參閱[定義翻譯規則](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a2d37-121">For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="a2d37-122">若要從主幹中移除翻譯規則, 請將規則名稱醒目提示, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="a2d37-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="a2d37-123">如果您已在關聯的中繼對等上設定翻譯規則, 請不要將翻譯規則與幹線建立關聯, 因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="a2d37-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


