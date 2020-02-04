---
title: Lync Server 2013：IPv6 的移轉與共存考量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5785b270aa3070c2b1592112ab4d5ae582e52bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="e0216-102">Lync Server 2013 中 IPv6 的移轉與共存考量</span><span class="sxs-lookup"><span data-stu-id="e0216-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0216-103">_**主題上次修改日期：** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="e0216-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="e0216-104">Lync Server 2010 或 Office 通訊伺服器不支援 IP 版本6（IPv6）。</span><span class="sxs-lookup"><span data-stu-id="e0216-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="e0216-105">針對試驗目的，您可以測試 Lync Server 2010 和 Lync Server 2013 雙堆疊共存。</span><span class="sxs-lookup"><span data-stu-id="e0216-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="e0216-106">我們建議您先將指定中央網站的所有池升級至 Lync Server 2013，然後再針對任何一個池啟用 IPv6 （雙堆疊網路）。</span><span class="sxs-lookup"><span data-stu-id="e0216-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="e0216-107">如果您只需要設定適用于 IPv6 的 pool，我們建議您在實驗室環境中設定 IPv6 專用池以進行測試。</span><span class="sxs-lookup"><span data-stu-id="e0216-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="e0216-108">在遷移和共存期間支援下列案例：</span><span class="sxs-lookup"><span data-stu-id="e0216-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="e0216-109">Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器2007在 IPv4 模式中與 Lync Server 2013 共存的 R2 池（在雙堆疊模式中共存）。</span><span class="sxs-lookup"><span data-stu-id="e0216-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="e0216-110">如果僅限 IPv6 池是各自為政的，則 Lync Server 2013 池處於僅限 IPv6 模式。</span><span class="sxs-lookup"><span data-stu-id="e0216-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

