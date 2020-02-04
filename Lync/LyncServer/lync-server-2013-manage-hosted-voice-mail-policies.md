---
title: Lync Server 2013：管理裝載語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 434cc1eb721635f4a56be33f48802da3bc6db0e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="02b59-102">在 Lync Server 2013 中管理裝載語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="02b59-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02b59-103">_**主題上次修改日期：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="02b59-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="02b59-104">已*託管的語音信箱原則*會提供資訊給 Lync Server 2013 ExUM 路由應用程式，讓您在何處路由其信箱位於託管 Exchange 服務的使用者。</span><span class="sxs-lookup"><span data-stu-id="02b59-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02b59-105">通常只需要一個寄宿的語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="02b59-105">Typically, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="02b59-106">在許多情況下，您可以修改全域原則，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="02b59-106">In many cases, you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="02b59-107">如果您建立擁有網站範圍的原則，系統會自動將它指派給駐留在指定網站的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="02b59-107">If you create a policy with site scope, it is assigned automatically to all users homed at the specified site.</span></span> <span data-ttu-id="02b59-108">如果您建立擁有每個使用者範圍的原則，您必須將它明確指派給使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="02b59-108">If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects.</span></span> <span data-ttu-id="02b59-109">您可以部署多個寄宿的語音信箱原則，但在這種情況下，必須在每位使用者指派原則。</span><span class="sxs-lookup"><span data-stu-id="02b59-109">It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="02b59-110">如需規劃託管語音信箱原則的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的託管語音信箱原則](lync-server-2013-hosted-voice-mail-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="02b59-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02b59-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="02b59-111">In This Section</span></span>

  - [<span data-ttu-id="02b59-112">在 Lync Server 2013 中修改全域託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="02b59-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="02b59-113">在 Lync Server 2013 中建立網站層級託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="02b59-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="02b59-114">在 Lync Server 2013 中建立每使用者託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="02b59-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="02b59-115">在 Lync Server 2013 中指派每個使用者託管的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="02b59-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

