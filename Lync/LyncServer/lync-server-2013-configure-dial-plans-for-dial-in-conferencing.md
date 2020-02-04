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
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="36ac8-102">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</span><span class="sxs-lookup"><span data-stu-id="36ac8-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ac8-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="36ac8-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="36ac8-104">當您部署電話撥入式會議時，您需要建立或修改路由撥入存取電話號碼的一個或多個撥號方案。</span><span class="sxs-lookup"><span data-stu-id="36ac8-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="36ac8-105">確定每個撥號方案中至少有一個正常化規則會將電話分機轉換成以 E 為164格式的完整電話號碼。</span><span class="sxs-lookup"><span data-stu-id="36ac8-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="36ac8-106">電話撥入式會議以已驗證的企業使用者身分加入會議的使用者，只要輸入其個人識別碼（PIN）及他們的電話號碼即可。</span><span class="sxs-lookup"><span data-stu-id="36ac8-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="36ac8-107">您需要正常化規則，將延伸轉換成完整的電話號碼，讓使用者在輸入電話分機時就能進行驗證。</span><span class="sxs-lookup"><span data-stu-id="36ac8-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="36ac8-108">若要為電話撥入式會議設定撥號方案，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="36ac8-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="36ac8-109">不論是否要部署企業語音，請修改全域撥號方案以新增電話撥入式會議區域，並確認正常化規則正確地轉換您的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="36ac8-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="36ac8-110">如需詳細指示，請參閱[在 Lync Server 2013 中修改撥號方案](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="36ac8-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="36ac8-111">如果您沒有部署企業語音，請為電話撥入式會議存取號碼建立撥號方案。</span><span class="sxs-lookup"><span data-stu-id="36ac8-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="36ac8-112">請務必包含電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="36ac8-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="36ac8-113">如需詳細指示，請參閱[在 Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="36ac8-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="36ac8-114">如果您已部署企業語音，請根據需要修改企業語音撥號方案，以加入地區，並針對撥入存取號碼使用適當的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="36ac8-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="36ac8-115">如需詳細指示，請參閱[在 Lync Server 2013 中修改撥號方案](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="36ac8-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="36ac8-116">您也可以建立只用于撥入存取號碼的專用撥號方案。</span><span class="sxs-lookup"><span data-stu-id="36ac8-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="36ac8-117">如需詳細指示，請參閱[在 Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="36ac8-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="36ac8-118">如需規劃地區的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36ac8-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36ac8-119">本節內容</span><span class="sxs-lookup"><span data-stu-id="36ac8-119">In This Section</span></span>

  - [<span data-ttu-id="36ac8-120">在 Lync Server 2013 中查看撥號方案資訊</span><span class="sxs-lookup"><span data-stu-id="36ac8-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="36ac8-121">在 Lync Server 2013 中建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="36ac8-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="36ac8-122">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="36ac8-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="36ac8-123">在 Lync Server 2013 中定義正規化規則</span><span class="sxs-lookup"><span data-stu-id="36ac8-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

