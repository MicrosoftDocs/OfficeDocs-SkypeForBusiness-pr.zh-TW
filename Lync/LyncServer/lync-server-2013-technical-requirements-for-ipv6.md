---
title: Lync Server 2013 IPv6 的技術需求
description: Lync Server 2013 IPv6 的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c54dfbdba56c45f19e7664db075331591c8e87cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559459"
---
# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="8ca30-103">Lync Server 2013 中 IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="8ca30-103">Technical requirements for IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ca30-104">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="8ca30-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="8ca30-105">如果您打算為 IPv6 設定 Lync Server 2013，請牢記下列需求：</span><span class="sxs-lookup"><span data-stu-id="8ca30-105">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="8ca30-106">若要使用 Lync Server 的 IPv6 位址，您必須為必須探索並解析為 IPv6 位址的記錄，建立網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="8ca30-106">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="8ca30-107">IPv6 DNS 使用主機 AAAA (四 A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="8ca30-107">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="8ca30-108">如果您在部署中同時使用 IPv4 和 IPv6，最好是設定及維護主機 A 記錄，以供 IPv6 的 IPv4 和裝載 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="8ca30-108">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="8ca30-109">即使您完全將部署轉換為 IPv6，您仍然可能需要 IPv4 仍在使用 IPv4 的外部使用者的 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="8ca30-109">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="8ca30-110">您可以在開始使用 IPv6 之前，先部署 IPv6 的 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="8ca30-110">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="8ca30-111">如果用戶端或伺服器不使用 IPv6，將不會參照記錄。</span><span class="sxs-lookup"><span data-stu-id="8ca30-111">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="8ca30-112">過渡技術會根據轉換技術設定和原則，決定要使用哪個記錄。</span><span class="sxs-lookup"><span data-stu-id="8ca30-112">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="8ca30-113">每個 IPv6 位址都有一個範圍。</span><span class="sxs-lookup"><span data-stu-id="8ca30-113">Each IPv6 address has a scope.</span></span> <span data-ttu-id="8ca30-114">您可以用於 IPv6 定址的三個範圍是 IPv6 的全域位址 (類似公用 IPv4 位址) 、IPv6 唯一本機位址 (類似專用 IPv4 位址範圍) ，以及 IPv6 連結本機位址 (類似于 Windows Server 中 IPv4) 的自動私人 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="8ca30-114">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="8ca30-115">集區中的所有伺服器都應有相同範圍的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="8ca30-115">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8ca30-116">IPv6 是一個複雜的主題，需要仔細規劃網路小組和 Internet 提供者，以協助確保您在 Windows Server 層級和 Lync Server 2013 層級所指派的位址如期運作。</span><span class="sxs-lookup"><span data-stu-id="8ca30-116">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="8ca30-117">請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。</span><span class="sxs-lookup"><span data-stu-id="8ca30-117">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ca30-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8ca30-118">See Also</span></span>


[<span data-ttu-id="8ca30-119">IP 版本6定址架構</span><span class="sxs-lookup"><span data-stu-id="8ca30-119">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="8ca30-120">IPv6 全域單路廣播位址格式</span><span class="sxs-lookup"><span data-stu-id="8ca30-120">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="8ca30-121">唯一的本地 IPv6 單播位址</span><span class="sxs-lookup"><span data-stu-id="8ca30-121">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

