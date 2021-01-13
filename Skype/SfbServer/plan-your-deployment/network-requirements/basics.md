---
title: DNS 基本知識
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有可提供 DNS 服務的內建軟體，所以您可能想要查看可用的檔，例如 DNS 原則案例指南。 您可以選擇協力廠商的解決方案（如果您願意）。
ms.openlocfilehash: dc60bab84220cad306deee408a6a09fc16df5a10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825583"
---
# <a name="dns-basics"></a><span data-ttu-id="a9aa9-104">DNS 基本知識</span><span class="sxs-lookup"><span data-stu-id="a9aa9-104">DNS basics</span></span>
 
<span data-ttu-id="a9aa9-105">Windows Server 2016 具有可提供 DNS 服務的內建軟體，所以您可能想要查看可用的檔，例如 [DNS 原則案例指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-105">Windows Server 2016 has built-in software that can provide DNS services, so you may want to review the available documentation such as the [DNS Policy Scenario Guide](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide).</span></span> <span data-ttu-id="a9aa9-106">您可以選擇協力廠商的解決方案（如果您願意）。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-106">You can choose a third-party solution if you prefer.</span></span>
  
<span data-ttu-id="a9aa9-107">建議的最佳作法是，在您的實施中指定特定的伺服器，以提供 DNS。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-107">We recommend that as a best practice you dedicate a specific server in your implementation to provide DNS.</span></span> <span data-ttu-id="a9aa9-108">您可以在其中一個專用於商務用 Skype server 角色的伺服器上進行設定，但是如果該伺服器也是集區的一部分，而在意外的商務用 Skype 中取得解除授權，直到重新建立 DNS 服務為止。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-108">You could potentially set it up on one of the servers dedicated to one of the Skype for Business server roles, but if that server was also part of a pool and got decommissioned by accident Skype for Business would malfunction until DNS services were re-established.</span></span>
  
## <a name="dns-records"></a><span data-ttu-id="a9aa9-109">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="a9aa9-109">DNS Records</span></span>

<span data-ttu-id="a9aa9-110">名稱對應至 IP 位址的每個對應 (，也可以是 IPv4 或 IPv6 的位址) 儲存在 DNS 伺服器上的 DNS 記錄中。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-110">Each mapping of a name to an IP address (and that could be an IPv4 or IPv6 address) is stored in a DNS record on the DNS server.</span></span> <span data-ttu-id="a9aa9-111">在 DNS 報告中，特別是以 FQDN （即完整功能變數名稱）說明的名稱。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-111">The name is described in the DNS Report specifically as an FQDN — a Fully Qualified Domain Name.</span></span> <span data-ttu-id="a9aa9-112">雖然 *contoso.com* 是有效的功能變數名稱，但它是 *\* contoso.com* 的簡寫，所以是不明確的，而且可能會參照網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-112">While  *contoso.com*  is a valid domain name, it's shorthand for *\*.contoso.com*  , so it's ambiguous and could possibly refer to any server in the domain.</span></span> <span data-ttu-id="a9aa9-113">在您的網域中，會參照單一伺服器的 FQDN 範例可能是 **meeting01.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-113">An example of an FQDN that would refer to a single server in your domain might be **meeting01.contoso.com**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a9aa9-114">依預設，未加入網域之電腦的電腦名稱稱為主機名稱，而不是完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-114">By default the computer name of a computer that is not joined to a domain is a host name, and not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="a9aa9-115">拓撲產生器使用 Fqdn，而非主機名稱。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-115">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="a9aa9-116">因此，在未加入網域但要部署為 Edge Server 電腦的電腦名稱中，您必須設定 DNS 尾碼。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a9aa9-117">將 Fqdn 指派給執行商務用 Skype 伺服器的伺服器時，**只能使用標準字元** (包括 A-Z、a-z、0-9 和連字號) 。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-117">**Use only standard characters** (including A-Z, a-z, 0-9, and hyphens) when assigning FQDNs to your servers running Skype for Business Server.</span></span> <span data-ttu-id="a9aa9-118">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a9aa9-119">也就是當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>
  
<span data-ttu-id="a9aa9-120">除了 IP 位址，FQDN 也可以對應至 **VIP** （虛擬 IP 位址）。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-120">In addition to an IP address, the FQDN could map to a **VIP** — A virtual IP address.</span></span> <span data-ttu-id="a9aa9-121">VIP 是不會對應至實際實體網路介面的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-121">A VIP is an IP address that doesn't correspond to an actual physical network interface.</span></span> <span data-ttu-id="a9aa9-122">VIP 通常是指執行伺服器角色的伺服器集區，或是一對設定為冗余及容錯的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-122">A VIP often points to a pool of servers performing a server role, or to a pair of servers configured for redundancy and fault-tolerance.</span></span>
  
<span data-ttu-id="a9aa9-123">有幾種 DNS 記錄類型，與本討論最相關的 DNS 記錄類型包括：</span><span class="sxs-lookup"><span data-stu-id="a9aa9-123">There are several types of DNS record, the ones that are most relevant to this discussion are:</span></span> 
  
- <span data-ttu-id="a9aa9-124">**A** --a address Record 或 Host record 會傳回32位 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-124">**A** — an Address record or Host record, Returns a 32-bit IPv4 address.</span></span> <span data-ttu-id="a9aa9-125">最常用於將主機名稱對應至主機的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-125">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="a9aa9-126">**AAAA** -a IPv6 address record。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-126">**AAAA** — an IPv6 address record.</span></span> <span data-ttu-id="a9aa9-127">會傳回128位 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-127">Returns a 128-bit IPv6 address.</span></span> <span data-ttu-id="a9aa9-128">最常用於將主機名稱對應至主機的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-128">Most commonly used to map hostnames to an IP address of the host.</span></span>
    
- <span data-ttu-id="a9aa9-129">**CNAME** --正常化名稱記錄。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-129">**CNAME** — a Canonical name record.</span></span> <span data-ttu-id="a9aa9-130">這會將一個名稱解析為另一個名稱： DNS 查閱會以新名稱重試查閱。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-130">This resolves one name to another: the DNS lookup will retry the lookup with the new name.</span></span>
    
- <span data-ttu-id="a9aa9-131">**Srv** —服務記錄 (srv 記錄) 指定服務 (在特定埠和 IP 組合上存取之伺服器) 上的處理常式。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-131">**SRV** — a Service record (SRV record) specifies a service (a process on a server) that is accessed on a specific port and IP combination.</span></span> <span data-ttu-id="a9aa9-132">需要服務記錄的服務名稱是固定的，而且無法自訂，只是讓他們成為 SIP 網域的一部分。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-132">The names of services requiring a service record are fixed, and can't be customized beyond making them part of your SIP domain.</span></span> <span data-ttu-id="a9aa9-133">部分使用者服務使用簡單 URLs。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-133">Some user services use Simple URLs.</span></span> <span data-ttu-id="a9aa9-134">SRV 記錄必須指向相同 SIP 網域中的位置，因此如果您有多個網域，您會需要一個指定服務的多個 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-134">An SRV record must point to a location in the same SIP domain, so if you have multiple domains you'll need multiple SRV records for a given service.</span></span>
    
## <a name="how-to-choose-a-sip-domain-name"></a><span data-ttu-id="a9aa9-135">如何選擇 SIP 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="a9aa9-135">How to choose a SIP domain name</span></span>
<span data-ttu-id="a9aa9-136"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="a9aa9-136"><a name="BK_NameSIP"> </a></span></span>

<span data-ttu-id="a9aa9-137">組織的 SIP 功能變數名稱通常會與其使用者提供的電子郵件地址對齊。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-137">An organization's SIP domain name usually aligns with the email addresses given to its users.</span></span> <span data-ttu-id="a9aa9-138">如果您組織中的使用者會擁有類似 Brown@contoso.com 的電子郵件地址，則 \<sip-domain\> 使用 contoso.com 功能變數名稱的組織偏好只是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-138">If a user in your organization would have an email address like Brown@contoso.com, the preferred \<sip-domain\> for an organization with the contoso.com domain name is simply contoso.com.</span></span>
  
### <a name="multiple-sip-domains"></a><span data-ttu-id="a9aa9-139">多個 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="a9aa9-139">Multiple SIP domains</span></span>

 <span data-ttu-id="a9aa9-140">在某些情況下，您的組織可能需要數個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-140">Your organization might in some cases need several SIP domains.</span></span> <span data-ttu-id="a9aa9-141">例如，如果 Fabrikam.com 是由 contoso.com 取得，您可能需要建立新的 SIP 網域，以供商務用 Skype 伺服器辨識，並接受來自的連接。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-141">As an example, if Fabrikam.com was acquired by contoso.com, you might need to create a new SIP domain that Skype for Business Server recognizes and will accept connection from.</span></span> <span data-ttu-id="a9aa9-142">當您執行此動作時，您必須建立所有使用 contoso.com 的 DNS 記錄的其他集合，並顯示新的 Fqdn，以顯示要傳送 Fabrikam 之要求的位置。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-142">When you do this, you'd need to create an additional set of all the DNS records that use contoso.com, with new FQDNs that show where to send requests for Fabrikam.</span></span>
  
## <a name="dns-load-balancing"></a><span data-ttu-id="a9aa9-143">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="a9aa9-143">DNS Load Balancing</span></span>
<span data-ttu-id="a9aa9-144"><a name="BK_NameSIP"> </a></span><span class="sxs-lookup"><span data-stu-id="a9aa9-144"><a name="BK_NameSIP"> </a></span></span>

<span data-ttu-id="a9aa9-145">您可以使用 DNS 在設定成伺服器集區的數部伺服器間共用流量負載。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-145">You can use DNS to share traffic load among several servers that are set up as a server pool.</span></span> <span data-ttu-id="a9aa9-146">若要這麼做，您可以為集區的 FQDN 建立數個記錄，每個記錄指向集區中節點的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-146">To do this, you would create several A records for the pool's FQDN, each of which points to the IP address of a node in the pool.</span></span>
  
<span data-ttu-id="a9aa9-147">請參閱 [DNS 負載平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 以取得額外的負載平衡討論。</span><span class="sxs-lookup"><span data-stu-id="a9aa9-147">See [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) for additional discussions of load balancing.</span></span>
  

