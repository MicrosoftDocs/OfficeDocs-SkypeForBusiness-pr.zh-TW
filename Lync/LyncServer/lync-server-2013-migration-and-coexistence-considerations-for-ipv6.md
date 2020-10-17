---
title: Lync Server 2013： IPv6 的遷移和共存考慮
description: Lync Server 2013： IPv6 的遷移和共存考慮。
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
ms.openlocfilehash: e8618cc14ff3c2467ea41df34e39f5094d1206dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560989"
---
# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="4902e-103">Lync Server 2013 中 IPv6 的遷移和共存考慮</span><span class="sxs-lookup"><span data-stu-id="4902e-103">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4902e-104">_**主題上次修改日期：** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="4902e-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="4902e-105">Lync Server 2010 或 Office 通訊伺服器不支援 IP 版本 6 (IPv6) 。</span><span class="sxs-lookup"><span data-stu-id="4902e-105">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="4902e-106">出於試驗目的，您可以測試 Lync Server 2010 和 Lync Server 2013 雙堆疊共存。</span><span class="sxs-lookup"><span data-stu-id="4902e-106">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="4902e-107">建議您將指定中央網站的所有集區升級至 Lync Server 2013，然後再為任何集區啟用 IPv6 (雙堆疊網路) 。</span><span class="sxs-lookup"><span data-stu-id="4902e-107">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="4902e-108">[！附注] 如果您只需要為 IPv6 設定集區，建議您在實驗室環境中設定 IPv6 專用集區以進行測試。</span><span class="sxs-lookup"><span data-stu-id="4902e-108">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="4902e-109">在遷移和共存期間支援下列案例：</span><span class="sxs-lookup"><span data-stu-id="4902e-109">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="4902e-110">Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器 2007 R2 集區中 IPv4 模式，與 Lync Server 2013 在雙堆疊模式中共存。</span><span class="sxs-lookup"><span data-stu-id="4902e-110">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="4902e-111">在僅限 IPv6 模式中的 Lync Server 2013 集區，如果僅限 IPv6 集區為孤立的集區。</span><span class="sxs-lookup"><span data-stu-id="4902e-111">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

