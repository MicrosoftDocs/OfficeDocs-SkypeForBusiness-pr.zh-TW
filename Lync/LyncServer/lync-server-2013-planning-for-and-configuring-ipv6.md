---
title: Lync Server 2013：規劃及設定 IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055dcf8de1d1a5e06e04e9b57bf4ffb44ab5a98f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515140"
---
# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="100f3-102">在 Lync Server 2013 中規劃及設定 IPv6</span><span class="sxs-lookup"><span data-stu-id="100f3-102">Planning for and configuring IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="100f3-103">_**主題上次修改日期：** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="100f3-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="100f3-104">Lync Server 2013 包含對 IP 版本 6 (IPv6) 位址的支援，以及對 IP 版本 4 (IPv4) 位址的支援。</span><span class="sxs-lookup"><span data-stu-id="100f3-104">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="100f3-105">IPv4 位址是 32 位元位址，可讓電腦透過網際網路進行通訊。</span><span class="sxs-lookup"><span data-stu-id="100f3-105">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="100f3-106">由於世界各地的裝置數目不斷增加，所以可用的 IPv4 位址已用盡。因此，許多新裝置會移至使用 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="100f3-106">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="100f3-107">IPv6 位址執行與 IPv4 位址相同的功能 (並增加一些功能)，但是 IPv6 位址使用 128 位元，而不是只使用 32 位元。</span><span class="sxs-lookup"><span data-stu-id="100f3-107">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="100f3-108">這不僅提供全新的一組位址，也提供更多的位址數目。</span><span class="sxs-lookup"><span data-stu-id="100f3-108">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="100f3-109">一般 IPv4 位址的外觀類似如下：192.0.2.235；而 IPv6 位址的外觀如下：2001:0db8:85a3:0000:0000:8a2e:0370:7334。</span><span class="sxs-lookup"><span data-stu-id="100f3-109">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="100f3-110">在您的 Lync Server 2013 安裝中，使用 IPv6 位址之裝置的格式設定和功能變更需要數個部署和設定考慮。</span><span class="sxs-lookup"><span data-stu-id="100f3-110">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="100f3-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="100f3-111">In This Section</span></span>

  - [<span data-ttu-id="100f3-112">Lync Server 2013 的 IP 位址類型概述</span><span class="sxs-lookup"><span data-stu-id="100f3-112">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="100f3-113">Lync Server 2013 中 IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="100f3-113">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="100f3-114">Lync Server 2013 中 IPv6 的遷移和共存考慮</span><span class="sxs-lookup"><span data-stu-id="100f3-114">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="100f3-115">在 Lync Server 2013 中設定 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="100f3-115">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

