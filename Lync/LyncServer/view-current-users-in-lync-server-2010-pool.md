---
title: 在 Lync Server 2010 集區中查看目前的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View current users in Lync Server 2010 pool
ms:assetid: c0986800-8ee4-4d50-9e9c-39f7c4e67bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721870(v=OCS.15)
ms:contentKeyID: 49733804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96ace0fe20c0fa1256db7806b571b0a40593aad4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517980"
---
# <a name="view-current-users-in-lync-server-2010-pool"></a><span data-ttu-id="3a6f2-102">在 Lync Server 2010 集區中查看目前的使用者</span><span class="sxs-lookup"><span data-stu-id="3a6f2-102">View current users in Lync Server 2010 pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a6f2-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="3a6f2-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="3a6f2-104">在深入瞭解您可以在集區之間移動使用者的各種方式之前，必須先判斷舊版 Lync Server 2010 集區中存在的使用者。</span><span class="sxs-lookup"><span data-stu-id="3a6f2-104">Prior to learning the various ways you can move users between pools, we must first determine what users exist in the legacy Lync Server 2010 pool.</span></span> <span data-ttu-id="3a6f2-105">在下圖中，[註冊集區集區] 欄可識別為舊版 Lync Server 2010 集區設定的六位使用者。</span><span class="sxs-lookup"><span data-stu-id="3a6f2-105">In the image below, the Registrar pool column identifies six users who are configured for the legacy Lync Server 2010 pool.</span></span> <span data-ttu-id="3a6f2-106">這些是我們將要移至 Lync Server 2013 集區的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="3a6f2-106">These are the test users we will move to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="3a6f2-107">**若要查看 Lync Server 2010 集區中的使用者清單**</span><span class="sxs-lookup"><span data-stu-id="3a6f2-107">**To see the list of users in the Lync Server 2010 pool**</span></span>

1.  <span data-ttu-id="3a6f2-108">使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員帳戶，登入 Lync Server 2010 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="3a6f2-108">Log on to the Lync Server 2010 Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="3a6f2-109">開啟 [ **Lync Server 控制台**]。</span><span class="sxs-lookup"><span data-stu-id="3a6f2-109">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="3a6f2-110">按一下 [ **使用者**]，按一下 [搜尋]，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="3a6f2-110">Click **Users**, click Search, and then click **Find**.</span></span>

<span data-ttu-id="3a6f2-111">**Lync Server 15 控制台**</span><span class="sxs-lookup"><span data-stu-id="3a6f2-111">**The Lync Server 15 Control Panel**</span></span>

<span data-ttu-id="3a6f2-112">![Lync Server 控制台，移動使用者對話方塊](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server 控制台，移動使用者對話方塊")</span><span class="sxs-lookup"><span data-stu-id="3a6f2-112">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

