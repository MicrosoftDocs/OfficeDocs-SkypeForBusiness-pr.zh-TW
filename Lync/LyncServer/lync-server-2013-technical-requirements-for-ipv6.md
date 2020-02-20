---
title: Lync Server 2013 的 IPv6 的技術需求
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
ms.openlocfilehash: 6513af4598f36aa510181e6971ccb6962cd44f91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="82765-102">Lync Server 2013 中的 IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="82765-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82765-103">_**主題上次修改日期：** 2012年-10-30_</span><span class="sxs-lookup"><span data-stu-id="82765-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="82765-104">如果您打算針對 IPv6 設定 Lync Server 2013，請注意下列需求：</span><span class="sxs-lookup"><span data-stu-id="82765-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="82765-105">若要使用 IPv6 位址與 Lync Server，您需要建立網域名稱系統 (DNS) 記錄的記錄，必須能夠探索及解析至 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="82765-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="82765-106">IPv6 DNS 使用主機 AAAA (四 A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="82765-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="82765-107">如果您部署中使用 IPv4 和 IPv6，最好是設定及維護主機 A 記錄的 IPv4 和 IPv6 的主機 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="82765-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="82765-108">即使當您完全部署轉換到 IPv6，您可能仍需要 IPv4 DNS 主機記錄仍在使用 IPv4 的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="82765-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="82765-109">在您開始使用 IPv6 之前，您可以部署 IPv6 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="82765-109">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="82765-110">如果用戶端或伺服器不會使用 IPv6，就不會參考記錄。</span><span class="sxs-lookup"><span data-stu-id="82765-110">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="82765-111">過渡時期技術會使若要使用，記錄決策轉換技術組態與原則為基礎。</span><span class="sxs-lookup"><span data-stu-id="82765-111">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="82765-112">每個 IPv6 位址具有範圍。</span><span class="sxs-lookup"><span data-stu-id="82765-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="82765-113">您可以使用 IPv6 定址的三個範圍是 IPv6 全域位址 （類似公用 IPv4 位址）、 IPv6 唯一本機位址 （類似私人 IPv4 位址範圍），以及 IPv6 連結本機位址 （類似於自動私人 IP 位址Windows Server 的 IPv4)。</span><span class="sxs-lookup"><span data-stu-id="82765-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="82765-114">集區中的所有伺服器都應有相同範圍的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="82765-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="82765-115">IPv6 是複雜的主題，必須進行審慎規劃您的網路小組與您的網際網路提供者，以協助確保您指定 Windows 伺服器層級和 Lync Server 2013 層級的地址，如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="82765-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="82765-116">請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。</span><span class="sxs-lookup"><span data-stu-id="82765-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82765-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="82765-117">See Also</span></span>


[<span data-ttu-id="82765-118">IP 版本 6 定址架構</span><span class="sxs-lookup"><span data-stu-id="82765-118">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="82765-119">IPv6 全域單點傳播位址格式</span><span class="sxs-lookup"><span data-stu-id="82765-119">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="82765-120">唯一本機 IPv6 單點傳播位址</span><span class="sxs-lookup"><span data-stu-id="82765-120">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

