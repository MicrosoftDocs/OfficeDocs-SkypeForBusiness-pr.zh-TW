---
title: 對於 IPv6 的 Lync Server 2013： 移轉和共存考量
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
ms.openlocfilehash: 449e1fa516f4817afcda30ba6ffac7db04d89e56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="c64d3-102">Lync Server 2013 中的 IPv6 的移轉和共存考量</span><span class="sxs-lookup"><span data-stu-id="c64d3-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c64d3-103">_**主題上次修改日期：** 2012年-06-14_</span><span class="sxs-lookup"><span data-stu-id="c64d3-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="c64d3-104">Lync Server 2010 或 Office Communications Server 不支援 IP 第 6 版 (IPv6)。</span><span class="sxs-lookup"><span data-stu-id="c64d3-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="c64d3-105">以駕駛來說，您可以測試 Lync Server 2010 和 Lync Server 2013 雙重堆疊共存。</span><span class="sxs-lookup"><span data-stu-id="c64d3-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="c64d3-106">我們建議所有集區，以指定的中央網站升級至 Lync Server 2013 啟用 IPv6 之前 （雙重堆疊網路） 的任何集區。</span><span class="sxs-lookup"><span data-stu-id="c64d3-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="c64d3-107">如果您需要只能設定為 IPv6 的集區，我們建議您在測試實驗室環境中設定僅 IPv6 集區。</span><span class="sxs-lookup"><span data-stu-id="c64d3-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="c64d3-108">移轉和共存期間支援下列案例：</span><span class="sxs-lookup"><span data-stu-id="c64d3-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="c64d3-109">Lync Server 2013、 Lync Server 2010 及 Office Communications Server 2007 R2 處於 IPv4 模式的集區與 Lync Server 2013 共存在雙重堆疊模式中。</span><span class="sxs-lookup"><span data-stu-id="c64d3-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="c64d3-110">在僅 IPv6 模式中，如果僅 IPv6 集區獨立的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="c64d3-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

