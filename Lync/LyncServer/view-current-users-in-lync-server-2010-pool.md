---
title: Lync Server 2010 集區中的檢視目前使用者
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
ms.openlocfilehash: fadc7b822fe1bdd04c170031407fe0441bfdc2f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-current-users-in-lync-server-2010-pool"></a><span data-ttu-id="ef22c-102">Lync Server 2010 集區中的檢視目前使用者</span><span class="sxs-lookup"><span data-stu-id="ef22c-102">View current users in Lync Server 2010 pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef22c-103">_**主題上次修改日期：** 2012年-09-26_</span><span class="sxs-lookup"><span data-stu-id="ef22c-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="ef22c-104">之前了解您可以在集區之間移動使用者的各種方式，我們必須先決定哪些使用者存在於舊版 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="ef22c-104">Prior to learning the various ways you can move users between pools, we must first determine what users exist in the legacy Lync Server 2010 pool.</span></span> <span data-ttu-id="ef22c-105">下圖登錄器集區] 欄會識別已為舊版的 Lync Server 2010 集區的六個使用者。</span><span class="sxs-lookup"><span data-stu-id="ef22c-105">In the image below, the Registrar pool column identifies six users who are configured for the legacy Lync Server 2010 pool.</span></span> <span data-ttu-id="ef22c-106">以下是我們將會移到 Lync Server 2013 集區的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="ef22c-106">These are the test users we will move to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="ef22c-107">**若要查看的 Lync Server 2010 集區中的使用者清單**</span><span class="sxs-lookup"><span data-stu-id="ef22c-107">**To see the list of users in the Lync Server 2010 pool**</span></span>

1.  <span data-ttu-id="ef22c-108">Lync Server 2010 前端伺服器是 RTCUniversalServerAdmins 群組的成員或是 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="ef22c-108">Log on to the Lync Server 2010 Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="ef22c-109">開啟**Lync Server 控制台**。</span><span class="sxs-lookup"><span data-stu-id="ef22c-109">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="ef22c-110">按一下 [**使用者**]，按一下 [搜尋]，然後按一下 [**尋找**。</span><span class="sxs-lookup"><span data-stu-id="ef22c-110">Click **Users**, click Search, and then click **Find**.</span></span>

<span data-ttu-id="ef22c-111">**Lync Server 15 控制台**</span><span class="sxs-lookup"><span data-stu-id="ef22c-111">**The Lync Server 15 Control Panel**</span></span>

<span data-ttu-id="ef22c-112">![Lync Server Control Panel，移動使用者] 對話方塊](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel，移動使用者] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="ef22c-112">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

