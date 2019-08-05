---
title: DNS 基本概念
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有可提供 DNS 服務的內建軟體, 因此您可能會想要查看可用的檔, 例如 DNS 策略案例指南。 如果您想要的話, 您可以選擇協力廠商方案。
ms.openlocfilehash: c1084a756a79ebcf15b8e99eef049690b5dcd9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192969"
---
# <a name="dns-basics"></a><span data-ttu-id="e18ea-104">DNS 基本概念</span><span class="sxs-lookup"><span data-stu-id="e18ea-104">DNS basics</span></span>
 
<span data-ttu-id="e18ea-105">Windows Server 2016 具有可提供 DNS 服務的內建軟體, 因此您可能會想要查看可用的檔, 例如[DNS 策略案例指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。</span><span class="sxs-lookup"><span data-stu-id="e18ea-105">Windows Server 2016 has built-in software that can provide DNS services, so you may want to review the available documentation such as the [DNS Policy Scenario Guide](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide).</span></span> <span data-ttu-id="e18ea-106">如果您想要的話, 您可以選擇協力廠商方案。</span><span class="sxs-lookup"><span data-stu-id="e18ea-106">You can choose a third-party solution if you prefer.</span></span>
  
<span data-ttu-id="e18ea-107">我們建議您最好的做法是, 在您的部署中專門指定特定伺服器來提供 DNS。</span><span class="sxs-lookup"><span data-stu-id="e18ea-107">We recommend that as a best practice you dedicate a specific server in your implementation to provide DNS.</span></span> <span data-ttu-id="e18ea-108">您可能會將它設定為專用於其中一個商務用 Skype 伺服器角色的其中一個伺服器, 但如果該伺服器也是某個擁有者的一部分, 且事故中的商務用 Skype 已解除授權, 直到重新建立 DNS 服務為止。</span><span class="sxs-lookup"><span data-stu-id="e18ea-108">You could potentially set it up on one of the servers dedicated to one of the Skype for Business server roles, but if that server was also part of a pool and got decommissioned by accident Skype for Business would malfunction until DNS services were re-established.</span></span>
  
## <a name="dns-records"></a><span data-ttu-id="e18ea-109">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="e18ea-109">DNS Records</span></span>

<span data-ttu-id="e18ea-110">每個名稱對應至 IP 位址 (且可能是 IPv4 或 IPv6 位址), 都儲存在 DNS 伺服器上的 DNS 記錄中。</span><span class="sxs-lookup"><span data-stu-id="e18ea-110">Each mapping of a name to an IP address (and that could be an IPv4 or IPv6 address) is stored in a DNS record on the DNS server.</span></span> <span data-ttu-id="e18ea-111">此名稱在 DNS 報告中描述為 FQDN (完整功能變數名稱)。</span><span class="sxs-lookup"><span data-stu-id="e18ea-111">The name is described in the DNS Report specifically as an FQDN — a Fully Qualified Domain Name.</span></span> <span data-ttu-id="e18ea-112">雖然*contoso.com*是有效的\* \*\* 功能變數名稱, 但它是 contoso.com 的簡寫, 所以它不明確, 而且可能會參照網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="e18ea-112">While  *contoso.com*  is a valid domain name, it's shorthand for *\*.contoso.com*  , so it's ambiguous and could possibly refer to any server in the domain.</span></span> <span data-ttu-id="e18ea-113">在網域中, 會參照單一伺服器的 FQDN 範例可能會**meeting01.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="e18ea-113">An example of an FQDN that would refer to a single server in your domain might be **meeting01.contoso.com**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e18ea-114">根據預設, 未加入網域之電腦的電腦名稱稱是主機名稱, 而不是完全限定的功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e18ea-114">By default the computer name of a computer that is not joined to a domain is a host name, and not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="e18ea-115">拓撲建造器使用 Fqdn, 而不是主機名稱。</span><span class="sxs-lookup"><span data-stu-id="e18ea-115">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="e18ea-116">因此, 您必須在要部署為邊緣伺服器且未加入網域的電腦名稱稱上設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="e18ea-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="e18ea-117">**僅使用標準字元**(包括 A-z、a-z、0-9 和連字號) 將 Fqdn 指派給執行商務用 Skype Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e18ea-117">**Use only standard characters** (including A-Z, a-z, 0-9, and hyphens) when assigning FQDNs to your servers running Skype for Business Server.</span></span> <span data-ttu-id="e18ea-118">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="e18ea-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="e18ea-119">外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元 (也就是當 FQDN 必須指派給憑證中的 SN) 時。</span><span class="sxs-lookup"><span data-stu-id="e18ea-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>
  
<span data-ttu-id="e18ea-120">除了 IP 位址之外, FQDN 可以對應至**VIP** (虛擬 IP 位址)。</span><span class="sxs-lookup"><span data-stu-id="e18ea-120">In addition to an IP address, the FQDN could map to a **VIP** — A virtual IP address.</span></span> <span data-ttu-id="e18ea-121">VIP 是不對應至實際物理網路介面的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e18ea-121">A VIP is an IP address that doesn't correspond to an actual physical network interface.</span></span> <span data-ttu-id="e18ea-122">VIP 通常指向執行伺服器角色的伺服器池, 或針對為冗余和容錯所設定的一組伺服器。</span><span class="sxs-lookup"><span data-stu-id="e18ea-122">A VIP often points to a pool of servers performing a server role, or to a pair of servers configured for redundancy and fault-tolerance.</span></span>
  
<span data-ttu-id="e18ea-123">DNS 記錄有數種類型, 與此討論最相關的記錄類型如下:</span><span class="sxs-lookup"><span data-stu-id="e18ea-123">There are several types of DNS record, the ones that are most relevant to this discussion are:</span></span> 
  
- <span data-ttu-id="e18ea-124">**A** : 地址記錄或主機記錄, 會傳回32位的 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="e18ea-124">**A** — an Address record or Host record, Returns a 32-bit IPv4 address.</span></span> <span data-ttu-id="e18ea-125">最常見的用途是將主機名稱對應到主機的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e18ea-125">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="e18ea-126">**AAAA** -IPv6 地址記錄。</span><span class="sxs-lookup"><span data-stu-id="e18ea-126">**AAAA** — an IPv6 address record.</span></span> <span data-ttu-id="e18ea-127">傳回128位 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="e18ea-127">Returns a 128-bit IPv6 address.</span></span> <span data-ttu-id="e18ea-128">最常見的用途是將主機名稱對應到主機的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e18ea-128">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="e18ea-129">**CNAME** -標準名稱記錄。</span><span class="sxs-lookup"><span data-stu-id="e18ea-129">**CNAME** — a Canonical name record.</span></span> <span data-ttu-id="e18ea-130">這會將一個名稱解析為另一個名稱: DNS 查閱會使用新名稱來重試查閱。</span><span class="sxs-lookup"><span data-stu-id="e18ea-130">This resolves one name to another: the DNS lookup will retry the lookup with the new name.</span></span>
    
- <span data-ttu-id="e18ea-131">**SRV** : 服務記錄 (srv 記錄) 指定服務 (伺服器上的進程), 可在特定埠和 IP 組合中存取。</span><span class="sxs-lookup"><span data-stu-id="e18ea-131">**SRV** — a Service record (SRV record) specifies a service (a process on a server) that is accessed on a specific port and IP combination.</span></span> <span data-ttu-id="e18ea-132">需要修正服務記錄的服務名稱, 而且不能在您的 SIP 網域中進行自訂。</span><span class="sxs-lookup"><span data-stu-id="e18ea-132">The names of services requiring a service record are fixed, and can't be customized beyond making them part of your SIP domain.</span></span> <span data-ttu-id="e18ea-133">有些使用者服務會使用簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="e18ea-133">Some user services use Simple URLs.</span></span> <span data-ttu-id="e18ea-134">SRV 記錄必須指向同一個 SIP 網域中的位置, 所以如果您有多個網域, 則特定的服務會需要多個 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="e18ea-134">An SRV record must point to a location in the same SIP domain, so if you have multiple domains you'll need multiple SRV records for a given service.</span></span>
    
## <a name="how-to-choose-a-sip-domain-name"></a><span data-ttu-id="e18ea-135">如何選擇 SIP 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="e18ea-135">How to choose a SIP domain name</span></span>
<span data-ttu-id="e18ea-136"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="e18ea-136"></span></span>

<span data-ttu-id="e18ea-137">組織的 SIP 功能變數名稱通常會與使用者所提供的電子郵件地址相符。</span><span class="sxs-lookup"><span data-stu-id="e18ea-137">An organization's SIP domain name usually aligns with the email addresses given to its users.</span></span> <span data-ttu-id="e18ea-138">如果貴組織中的使用者會擁有電子郵件地址 (例如 Brown@contoso.com), \<則只有 contoso.com\>才能擁有 contoso.com 功能變數名稱的組織的首選 sip-網域。</span><span class="sxs-lookup"><span data-stu-id="e18ea-138">If a user in your organization would have an email address like Brown@contoso.com, the preferred \<sip-domain\> for an organization with the contoso.com domain name is simply contoso.com.</span></span>
  
### <a name="multiple-sip-domains"></a><span data-ttu-id="e18ea-139">多個 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="e18ea-139">Multiple SIP domains</span></span>

 <span data-ttu-id="e18ea-140">在某些情況下, 您的組織可能需要幾個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="e18ea-140">Your organization might in some cases need several SIP domains.</span></span> <span data-ttu-id="e18ea-141">舉例來說, 如果 Fabrikam.com 是由 contoso.com 取得, 您可能需要建立新的 SIP 網域, 讓商務用 Skype 伺服器辨識並接受連線。</span><span class="sxs-lookup"><span data-stu-id="e18ea-141">As an example, if Fabrikam.com was acquired by contoso.com, you might need to create a new SIP domain that Skype for Business Server recognizes and will accept connection from.</span></span> <span data-ttu-id="e18ea-142">當您這麼做時, 您必須建立一組使用 contoso.com 的所有 DNS 記錄, 並在新的 Fqdn 中顯示在何處傳送 Fabrikam 的要求。</span><span class="sxs-lookup"><span data-stu-id="e18ea-142">When you do this, you'd need to create an additional set of all the DNS records that use contoso.com, with new FQDNs that show where to send requests for Fabrikam.</span></span>
  
## <a name="dns-load-balancing"></a><span data-ttu-id="e18ea-143">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="e18ea-143">DNS Load Balancing</span></span>
<span data-ttu-id="e18ea-144"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="e18ea-144"></span></span>

<span data-ttu-id="e18ea-145">您可以在設定為伺服器池中的數個伺服器之間, 使用 DNS 來共用流量負載。</span><span class="sxs-lookup"><span data-stu-id="e18ea-145">You can use DNS to share traffic load among several servers that are set up as a server pool.</span></span> <span data-ttu-id="e18ea-146">若要這樣做, 您可以為池的 FQDN 建立數個記錄, 每個記錄都指向池中節點的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e18ea-146">To do this, you would create several A records for the pool's FQDN, each of which points to the IP address of a node in the pool.</span></span>
  
<span data-ttu-id="e18ea-147">若要進一步討論負載平衡, 請參閱[DNS 負載平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)。</span><span class="sxs-lookup"><span data-stu-id="e18ea-147">See [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) for additional discussions of load balancing.</span></span>
  

