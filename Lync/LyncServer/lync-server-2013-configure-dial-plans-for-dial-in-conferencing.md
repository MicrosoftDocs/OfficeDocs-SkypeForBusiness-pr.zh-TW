---
title: Lync Server 2013：設定電話撥入式會議的撥號對應表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a86bf3061c714089ee326a729d0dd43ef267b8e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="0cbee-102">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</span><span class="sxs-lookup"><span data-stu-id="0cbee-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cbee-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0cbee-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0cbee-104">當您部署電話撥入式會議時，您必須建立或修改一或多個用於路由撥入存取電話號碼的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0cbee-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="0cbee-105">請確定每個撥號對應表中至少有一個正規化規則，以 e.164 格式將電話分機號碼轉換成完整的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0cbee-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="0cbee-106">使用電話撥入式會議加入會議的使用者，將其個人身分識別號碼 (PIN) 和其電話號碼輸入，以供已驗證的企業使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="0cbee-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="0cbee-107">您需要正規化規則，將分機轉換成完整的電話號碼，讓使用者在輸入電話分機時可驗證。</span><span class="sxs-lookup"><span data-stu-id="0cbee-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="0cbee-108">若要設定電話撥入式會議的撥號對應表，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0cbee-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="0cbee-109">不論您是部署企業語音，請修改全域撥號對應表，以加入電話撥入式會議區域，並確定正規化規則正確地轉換您的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="0cbee-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="0cbee-110">如需詳細指示，請參閱 [在 Lync Server 2013 中修改撥號](lync-server-2013-modify-a-dial-plan.md)對應表。</span><span class="sxs-lookup"><span data-stu-id="0cbee-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="0cbee-111">如果您未部署企業語音，請建立電話撥入式會議存取號碼的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0cbee-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="0cbee-112">請務必加入電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="0cbee-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="0cbee-113">如需詳細指示，請參閱 [Create a 撥號 plan In Lync Server 2013](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="0cbee-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="0cbee-114">如果您部署了企業語音，請視需要修改 Enterprise Voice 撥號對應表，以包含地區，並使用適當的正規化規則來撥打撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="0cbee-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="0cbee-115">如需詳細指示，請參閱 [在 Lync Server 2013 中修改撥號](lync-server-2013-modify-a-dial-plan.md)對應表。</span><span class="sxs-lookup"><span data-stu-id="0cbee-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="0cbee-116">您也可以建立專用的撥號對應表，只用于撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="0cbee-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="0cbee-117">如需詳細指示，請參閱 [Create a 撥號 plan In Lync Server 2013](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="0cbee-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="0cbee-118">如需規劃地區的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="0cbee-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0cbee-119">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0cbee-119">In This Section</span></span>

  - [<span data-ttu-id="0cbee-120">在 Lync Server 2013 中查看撥號對應表資訊</span><span class="sxs-lookup"><span data-stu-id="0cbee-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="0cbee-121">在 Lync Server 2013 中建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="0cbee-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="0cbee-122">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="0cbee-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="0cbee-123">在 Lync Server 2013 中定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="0cbee-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

