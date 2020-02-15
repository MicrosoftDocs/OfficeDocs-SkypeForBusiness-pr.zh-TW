---
title: Lync Server 2013： 規劃和設定 IPv6
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
ms.openlocfilehash: 2c706503ac334e6af3077e1f64418962bc825718
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="bebbe-102">規劃和設定 Lync Server 2013 中的 IPv6</span><span class="sxs-lookup"><span data-stu-id="bebbe-102">Planning for and configuring IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bebbe-103">_**主題上次修改日期：** 2012年-06-14_</span><span class="sxs-lookup"><span data-stu-id="bebbe-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="bebbe-104">Lync Server 2013 包含支援對於 IP 版本 6 (IPv6) 位址，以及持續支援 IP 版本 4 (IPv4) 的地址。</span><span class="sxs-lookup"><span data-stu-id="bebbe-104">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="bebbe-105">IPv4 位址是 32 位元位址，可讓電腦透過網際網路進行通訊。</span><span class="sxs-lookup"><span data-stu-id="bebbe-105">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="bebbe-106">全球的裝置數目增加，因為可用的 IPv4 位址有完為止。因此，許多新的裝置，要將移至使用 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="bebbe-106">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="bebbe-107">IPv6 位址執行與 IPv4 位址相同的功能 (並增加一些功能)，但是 IPv6 位址使用 128 位元，而不是只使用 32 位元。</span><span class="sxs-lookup"><span data-stu-id="bebbe-107">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="bebbe-108">這不僅提供全新的一組位址，也提供更多的位址數目。</span><span class="sxs-lookup"><span data-stu-id="bebbe-108">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="bebbe-109">一般 IPv4 位址的外觀類似如下：192.0.2.235；而 IPv6 位址的外觀如下：2001:0db8:85a3:0000:0000:8a2e:0370:7334。</span><span class="sxs-lookup"><span data-stu-id="bebbe-109">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="bebbe-110">變更格式設定和使用 IPv6 位址的裝置的功能需要數個部署和設定考量您的 Lync Server 2013 安裝。</span><span class="sxs-lookup"><span data-stu-id="bebbe-110">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bebbe-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="bebbe-111">In This Section</span></span>

  - [<span data-ttu-id="bebbe-112">Lync Server 2013 的 IP 位址類型概觀</span><span class="sxs-lookup"><span data-stu-id="bebbe-112">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="bebbe-113">Lync Server 2013 中的 IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="bebbe-113">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="bebbe-114">Lync Server 2013 中的 IPv6 的移轉和共存考量</span><span class="sxs-lookup"><span data-stu-id="bebbe-114">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="bebbe-115">在 Lync Server 2013 中設定 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="bebbe-115">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

