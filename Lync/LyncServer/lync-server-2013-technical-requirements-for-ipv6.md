---
title: Lync Server 2013 IPv6 的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972b59ba2ea01f967d5cfb8a7767a4f322bcb2fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="b3a97-102">Lync Server 2013 中 IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="b3a97-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3a97-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="b3a97-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="b3a97-104">如果您打算為 IPv6 設定 Lync Server 2013，請記住下列需求：</span><span class="sxs-lookup"><span data-stu-id="b3a97-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="b3a97-105">若要將 IPv6 位址搭配 Lync Server 使用，您需要針對必須發現並解析為 IPv6 位址的記錄，建立網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="b3a97-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="b3a97-106">IPv6 DNS 使用主機 AAAA （四 A）記錄。</span><span class="sxs-lookup"><span data-stu-id="b3a97-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="b3a97-107">如果您在部署中同時使用 IPv4 和 IPv6，最好是針對 IPv6 與主機 AAAA 記錄，設定及維護主機 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="b3a97-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="b3a97-108">即使您將部署完全轉換為 IPv6，您仍然可能需要仍使用 IPv4 之外部使用者的 IPv4 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="b3a97-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="b3a97-109">您可以先部署 IPv6 DNS 主機記錄，然後再開始使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b3a97-109">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="b3a97-110">如果用戶端或伺服器不使用 IPv6，將不會參照該記錄。</span><span class="sxs-lookup"><span data-stu-id="b3a97-110">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="b3a97-111">轉場技術將根據轉換技術設定與原則，決定要使用哪一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="b3a97-111">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="b3a97-112">每個 IPv6 位址都有一個範圍。</span><span class="sxs-lookup"><span data-stu-id="b3a97-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="b3a97-113">您可以用來進行 IPv6 定址的三個作用域是 IPv6 全域位址（類似公用 IPv4 位址）、IPv6 唯一本機位址（類似于專用 IPv4 位址範圍），以及 IPv6 鏈路本機位址（類似中的自動私人 IP 位址）適用于 IPv4 的 Windows Server）。</span><span class="sxs-lookup"><span data-stu-id="b3a97-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="b3a97-114">一個池內的所有伺服器都應該有相同範圍的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="b3a97-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3a97-115">IPv6 是一個複雜的主題，需要謹慎規劃您的網路小組和 Internet 提供者，以協助確保您在 Windows Server 層級和 Lync Server 2013 層級指派的位址如期運作。</span><span class="sxs-lookup"><span data-stu-id="b3a97-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="b3a97-116">如需有關 IPv6 定址與規劃的其他資源，請參閱本主題結尾的連結。</span><span class="sxs-lookup"><span data-stu-id="b3a97-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3a97-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="b3a97-117">See Also</span></span>


[<span data-ttu-id="b3a97-118">IP 版本6定址架構</span><span class="sxs-lookup"><span data-stu-id="b3a97-118">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="b3a97-119">IPv6 全域單播位址格式</span><span class="sxs-lookup"><span data-stu-id="b3a97-119">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="b3a97-120">唯一的局部 IPv6 單播位址</span><span class="sxs-lookup"><span data-stu-id="b3a97-120">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

