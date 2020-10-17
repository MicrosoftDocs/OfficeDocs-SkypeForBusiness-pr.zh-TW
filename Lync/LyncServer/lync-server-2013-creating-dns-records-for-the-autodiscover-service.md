---
title: Lync Server 2013：建立自動探索服務的 DNS 記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 928de572305cdbe19f5222f34e6616a8022e37b3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531540"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="ccc3d-102">在 Lync Server 2013 中建立自動探索服務的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ccc3d-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc3d-103">_**主題上次修改日期：** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="ccc3d-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="ccc3d-104">您的 Lync Mobile 使用者將需要您啟用自動探索功能，其中包含建立某些網域名稱系統 (DNS) 記錄的部分。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="ccc3d-105">視您的需求而定，您需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="ccc3d-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="ccc3d-106">內部 DNS 記錄，以支援從組織網路內部連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="ccc3d-107">支援從網際網路連線之行動使用者的外部或公用 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ccc3d-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="ccc3d-108">為何？</span><span class="sxs-lookup"><span data-stu-id="ccc3d-108">Why both?</span></span> <span data-ttu-id="ccc3d-109">您必須為每個 SIP 網域建立內部 DNS 記錄和外部 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="ccc3d-110">您建立的 DNS 記錄可以是 (主機，也可以是) 記錄或 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="ccc3d-111">為了協助您完成，我們將逐步說明如何建立下列內部和外部 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="ccc3d-112">如果您需要進一步閱讀行動使用者的 DNS 需求，您可以 [在 Lync Server 2013 中查看行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="ccc3d-113">建立內部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="ccc3d-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="ccc3d-114">若要建立內部 DNS 記錄，您必須使用 domain Admins 群組成員或 DnsAdmins 群組成員的網域帳戶，登入網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="ccc3d-115">開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="ccc3d-116">在 DNS 伺服器的主控台樹中，展開您的 Lync Server 2013 Director 集區和前端集區之 Active Directory 網域的 [ **正向對應區域** ]。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="ccc3d-117"> (例如，contoso) 本機。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="ccc3d-118">檢查並查看主機 A (AAAA for a IPv6) 記錄是否存在內部 DNS 記錄的 Director 集區。主機 A 記錄應該存在於 Director 集區的內部 Web 服務完整功能變數名稱 (FQDN) 例如，lyncwebdir01.contoso.local (。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="ccc3d-119">如果不在這裡，您可能不會使用 Director 集區，您也必須使用前端集區的 FQDN，或甚至是單一伺服器 FQDN （如果您設定的話）。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="ccc3d-120">請注意，請檢查並查看主機 A () IPv6 AAAA 是否存在用於內部 DNS 記錄的前端集區。主機 A (或 AAAA) 記錄應該存在於前端集區的內部 Web 服務 FQDN (例如，lyncwebpool01.contoso.local 的) 。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="ccc3d-121">如果不是，您需要記下前端伺服器或 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="ccc3d-122">知道存在 (或 AAAA) 記錄的主機之後，在 DNS 伺服器的主控台樹中，展開 SIP 網域的 [ **正向對應區域** ] (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="ccc3d-123">用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增別名 (CNAME)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="ccc3d-124">在 [ **別名**] 中，輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="ccc3d-125">在 [ \*\*完整功能變數名稱 (目標主機的 FQDN) \*\*] 中，輸入或流覽至 Director 集區的內部 WEB 服務 FQDN (例如，lyncwebdir01.contoso.local) ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="ccc3d-126">您必須在 Lync Server 2013 環境中所支援的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="ccc3d-127">建立外部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="ccc3d-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="ccc3d-128">若要建立外部 DNS CNAME 記錄，您必須連線至您的公用 DNS 提供者，然後依照我們的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="ccc3d-129">我們無法確切描述您在 DNS 提供者環境中所前往的位置，因為可能會有不同的方式來管理您的外部 DNS，但是我們希望這些步驟有所説明。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="ccc3d-130">使用可在該環境中建立 DNS 記錄的帳戶，登入您的外部 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="ccc3d-131">您應該已經為此環境建立 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="ccc3d-132">展開此 SIP 網域的 **正向對應區域** ，或根據所使用的外部 DNS 介面，加以選取。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="ccc3d-133">您應該會看到主機 A (AAAA IPv6 Director 集區的) 記錄 (例如 lyncwebexdir01.contoso.com) ，所以請確認已存在。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="ccc3d-134">如果不是，則您可能不是使用 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="ccc3d-135">如果是這種情況，您必須使用前端集區的 FQDN，或在您的 Front-End server 或 Standard Edition server 上執行這項操作的單一伺服器。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="ccc3d-136">您也需要確認主機 A IPv6) 記錄的 (AAAA 是否存在於您的外部 Web 服務完整功能變數名稱 (FQDN) 如 lyncwebextpool01.contoso.com (，或您的單一伺服器 FQDN （如果您沒有前端集區）的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="ccc3d-137">如先前的步驟所述，如果您沒有 Director 集區，則需要下列步驟。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="ccc3d-138">現在，在您的外部 DNS 提供者適當的格式中，選擇建立 \*\*新別名 (CNAME) \*\* (此選項可能是功能表選項或連結，視 DNS 提供者) 格式而定。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="ccc3d-139">您應輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱，才能使用一些形式的 **別名名稱** 文字方塊。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="ccc3d-140">在 [目標主機] 文字方塊的 FQDN) 中，也應該會有某種形式的 **完整功能變數名稱 (** ，您可以在這裡輸入您 Director 集區的外部 WEB 服務 FQDN (例如，lyncwebexdir01.contoso.com) 然後按一下 [確定]，或在外部 DNS 中執行任何動作，以接受此專案的建立。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="ccc3d-141">如以上的步驟4所述，如果您沒有 Director 集區，則需要使用您設定的前端集區 FQDN 或單一伺服器 FQDN （如果適用）。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="ccc3d-142">您必須在 Lync 2013 環境所支援的每個 SIP 網域的正向對應區域中，建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="ccc3d-143">建立內部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="ccc3d-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="ccc3d-144">若要建立內部 DNS 記錄，請使用 Domain Admins 群組成員的網域帳戶或 DnsAdmins 群組的成員，登入網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="ccc3d-145">開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="ccc3d-146">針對內部 DNS 記錄，在 DNS 伺服器的主控台樹中，展開 Active Directory 網域的 [ **正向對應區域** ] (例如，contoso) 會安裝 Lync Server 2013 Director 集區和前端集區的位置。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="ccc3d-147">檢查並查看主機 A (AAAA for a IPv6) 記錄是否存在內部 DNS 記錄的 Director 集區。主機 A 記錄應該存在於 Director 集區的內部 Web 服務完整功能變數名稱 (FQDN) 例如，lyncwebdir01.contoso.local (。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="ccc3d-148">如果不在這裡，您可能不會使用 Director 集區，您也必須使用前端集區的 IP 位址，或甚至單一伺服器 IP 位址（如果您設定的話）。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="ccc3d-149">請注意，請檢查並查看主機 A () IPv6 AAAA 是否存在用於內部 DNS 記錄的前端集區。主機 A (或 AAAA) 記錄應該存在於前端集區的內部 Web 服務 FQDN (例如，lyncwebpool01.contoso.local 的) 。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="ccc3d-150">如果不是，您需要記下前端伺服器或 Standard Edition server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="ccc3d-151">知道存在 (或 AAAA) 記錄的主機之後，在 DNS 伺服器的主控台樹中，展開 SIP 網域的 [ **正向對應區域** ] (例如，contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="ccc3d-152">用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增主機 (A 或 AAAA)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="ccc3d-153">在 [ **名稱**] 中，輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="ccc3d-154">在 [ **IP 位址**] 中，輸入 director (的內部 WEB 服務 IP 位址，或者，如果您使用負載平衡器，請輸入 director 負載平衡器) 的虛擬 IP (VIP) 。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="ccc3d-155">如以上步驟4所述，如果您不是使用 Director，您可能需要輸入前端伺服器或 Standard Edition 伺服器的 IP 位址，或者，如果使用負載平衡器，請輸入前端集區負載平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="ccc3d-156">按一下 [新增主機]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="ccc3d-157">若要建立額外的 A 或 AAAA 記錄，請重複步驟8到10，請記住，您必須在 Lync Server 2013 環境所支援的每個 SIP 網域的正向對應區域中建立新的自動探索 A 或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="ccc3d-158">完成建立 A (對於 IPv6 為 AAAA) 記錄時，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="ccc3d-159">建立外部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="ccc3d-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="ccc3d-160">若要建立外部 DNS 記錄，請連接到您的公用 DNS 提供者，然後依照我們的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="ccc3d-161">我們無法確切描述您在 DNS 提供者環境中所前往的位置，因為可能會有不同的方式來管理您的外部 DNS，但是我們希望這些步驟有所説明。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="ccc3d-162">您必須以帳戶的身分登入，才能在該環境中建立 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="ccc3d-163">針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="ccc3d-164">針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="ccc3d-165">您應該會看到 a a a a a a a a a a a a (AAAA IPv6 for a a a a a a a A a a a a A A a a A a a A a a a a a a a a) )  (record</span><span class="sxs-lookup"><span data-stu-id="ccc3d-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="ccc3d-166">如果不是，則您可能不是使用 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="ccc3d-167">如果是這種情況，您必須使用前端集區的 IP 位址，或為您的 Front-End server 或 Standard Edition server 進行單一伺服器的準備。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="ccc3d-168">請記住，您的伺服器也可能會在負載平衡器的背後，或使用反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="ccc3d-169">請記下可遵循下列步驟的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="ccc3d-170">您也需要確認主機 A IPv6) 記錄的 (AAAA 是否存在於您的外部 Web 服務完整功能變數名稱 (FQDN) 如 lyncwebextpool01.contoso.com (，或您的單一伺服器 Lync 安裝的 IP 位址（如果您沒有前端集區）。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="ccc3d-171">如先前的步驟所述，如果您沒有 Director 集區，則需要下列步驟。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="ccc3d-172">現在，在您的外部 DNS 提供者適當的格式中，選擇建立 **新主機 a 或 AAAA** (的選項。這可能是功能表選項或連結，視 DNS 提供者) 的格式而定。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="ccc3d-173">應該有輸入 **名稱**的地方，請輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="ccc3d-174">您也應該會有一個 **Ip 位址** 文字方塊，您可以在這裡為 Director 集區 (輸入 ip。例如，lyncwebexdir01.contoso.com) 或可能是集區的負載平衡器 (或反向 proxy ip，會產生相同) ，然後按一下 [確定] 或 [採取外部 DNS 中的任何動作，以接受此專案的建立。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="ccc3d-175">如以上的步驟4所述，如果您沒有 Director 集區，則需要根據需要使用您設定的前端集區 IP 位址或單一伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="ccc3d-176">您必須在 Lync 2013 環境所支援的每個 SIP 網域的正向對應區域中，建立新的自動探索 A 或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="ccc3d-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

