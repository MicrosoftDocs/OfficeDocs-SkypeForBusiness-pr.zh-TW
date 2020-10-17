---
title: Lync Server 2013：管理主控語音信箱原則
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
ms.openlocfilehash: 315bd908b8369a107c4c9ddedcf5ce9911fc48f0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534500"
---
# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="4de1d-102">在 Lync Server 2013 中管理主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="4de1d-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4de1d-103">_**主題上次修改日期：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="4de1d-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="4de1d-104">「裝載 *語音信箱原則* 」會為 Lync Server 2013 ExUM 路由應用程式提供資訊，告知其信箱位於裝載 Exchange 服務上之使用者的通話位置。</span><span class="sxs-lookup"><span data-stu-id="4de1d-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4de1d-p101">通常只需要一個裝載語音信箱原則。在許多情況下，您可以修改全域原則來符合您的所有需求。如果您建立網站範圍的原則，系統會自動將它指派給位於指定網站的所有使用者。如果您建立個別使用者範圍的原則，您必須明確將它指派給使用者、群組和連絡人物件。您可以部署多個裝載語音信箱原則，但在此情況下，必須針對個別使用者指派原則。</span><span class="sxs-lookup"><span data-stu-id="4de1d-p101">Typically, only one hosted voice mail policy is required. In many cases, you can modify the global policy to meet all your needs. If you create a policy with site scope, it is assigned automatically to all users homed at the specified site. If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects. It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="4de1d-110">如需規劃主控語音信箱原則的詳細資訊，請參閱規劃檔中的 [hosted voice mail 原則 In Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="4de1d-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4de1d-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4de1d-111">In This Section</span></span>

  - [<span data-ttu-id="4de1d-112">在 Lync Server 2013 中修改全域主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="4de1d-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="4de1d-113">在 Lync Server 2013 中建立網站層級主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="4de1d-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="4de1d-114">在 Lync Server 2013 中建立個別使用者的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="4de1d-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="4de1d-115">在 Lync Server 2013 中指派每位使用者的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="4de1d-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

