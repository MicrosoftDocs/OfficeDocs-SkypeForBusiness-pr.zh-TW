---
title: Lync Server 2013： 建立 DNS 記錄的自動探索服務
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
ms.openlocfilehash: 0a3c9e3b3aaecef519a2fbc23d5955a5be4fa0d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="21c9d-102">Lync Server 2013 中的自動探索服務建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="21c9d-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21c9d-103">_**上次修改主題：** 2014年-06-20 個_</span><span class="sxs-lookup"><span data-stu-id="21c9d-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="21c9d-104">Lync 行動使用者必須先啟用自動探索，以及的一部分，包括建立一些網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="21c9d-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="21c9d-105">根據您的需求，您需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="21c9d-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="21c9d-106">內部 DNS 記錄，以支援行動裝置正在從網際網路連接貴組織的網路內的使用者。</span><span class="sxs-lookup"><span data-stu-id="21c9d-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="21c9d-107">外部或公用 DNS 記錄，以支援從網際網路連接的行動使用者</span><span class="sxs-lookup"><span data-stu-id="21c9d-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="21c9d-108">為什麼兩者嗎？</span><span class="sxs-lookup"><span data-stu-id="21c9d-108">Why both?</span></span> <span data-ttu-id="21c9d-109">您必須建立內部 DNS 記錄和外部 DNS 記錄每個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="21c9d-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="21c9d-110">您建立的 DNS 記錄可以是其中一個 A （主機），記錄或 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="21c9d-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="21c9d-111">為了協助您取出，我們將逐步解說如何建立這些內部和外部 DNS 記錄下方。</span><span class="sxs-lookup"><span data-stu-id="21c9d-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="21c9d-112">如果您需要執行一些進一步閱讀行動使用者的 DNS 需求，您可以查看[Lync Server 2013 中的行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="21c9d-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="21c9d-113">建立內部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="21c9d-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="21c9d-114">若要讓內部 DNS 記錄，您需要登入是 Domain Admins 群組的成員或 DnsAdmins 群組成員的網域帳戶與您網路中 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="21c9d-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="21c9d-115">開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21c9d-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="21c9d-116">在 [DNS 伺服器的主控台樹狀目錄中，依序展開 [**正向對應區域**安裝 Lync Server 2013 Director 集區與前端集區的 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="21c9d-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="21c9d-117">(例如 contoso.local)。</span><span class="sxs-lookup"><span data-stu-id="21c9d-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="21c9d-118">檢查，請參閱是否 (對於 IPv6 為 AAAA) 記錄存在，您的 Director 集區，針對內部 DNS 記錄的主機，主機 A 記錄應該存在於內部 Web 服務完整的網域名稱 (FQDN) Director 集區 (例如 lyncwebdir01.contoso.local)。</span><span class="sxs-lookup"><span data-stu-id="21c9d-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="21c9d-119">如果它不是在這裡，您不使用 Director 集區]，而您將需要您的前端集區或甚至是在單一伺服器 FQDN] 中，使用 FQDN，如果這是您的設定。</span><span class="sxs-lookup"><span data-stu-id="21c9d-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="21c9d-120">請記住，，檢查並查看是否 (對於 IPv6 為 AAAA) 記錄存在，您的前端集區，針對內部 DNS 記錄的主機，主機 A （或 AAAA） 記錄應存在於您的前端集區的內部 Web 服務 fqdn （例如lyncwebpool01.contoso.local)。</span><span class="sxs-lookup"><span data-stu-id="21c9d-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="21c9d-121">如果沒有，您需要記前端伺服器或 Standard Edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="21c9d-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="21c9d-122">一旦您知道哪些主機 A （或 AAAA） 的記錄存在，您的 DNS 伺服器的主控台樹狀目錄中展開 SIP 網域 (例如，contoso.com) 的 [**正向對應區域**。</span><span class="sxs-lookup"><span data-stu-id="21c9d-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="21c9d-123">用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增別名 (CNAME)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21c9d-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="21c9d-124">在 [**別名名稱**] 中，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="21c9d-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="21c9d-125">在**完整目標主機的網域名稱 (FQDN)**，輸入或瀏覽至您的 Director 集區 (例如 lyncwebdir01.contoso.local) 的內部 Web 服務 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="21c9d-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="21c9d-126">您必須在您支援 Lync Server 2013 環境中的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="21c9d-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="21c9d-127">建立外部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="21c9d-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="21c9d-128">若要建立外部 DNS CNAME 記錄，您即將需要連線至公用 DNS 提供者，並依照我們的步驟。</span><span class="sxs-lookup"><span data-stu-id="21c9d-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="21c9d-129">我們無法說明完全其中您即將 DNS 提供者的環境中可能有不同的方式，管理您的外部 DNS，但是我們希望這些步驟協助。</span><span class="sxs-lookup"><span data-stu-id="21c9d-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="21c9d-130">登入外部 DNS 提供者可以在該環境中建立 DNS 記錄的帳戶。</span><span class="sxs-lookup"><span data-stu-id="21c9d-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="21c9d-131">您應該已建立此環境的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="21c9d-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="21c9d-132">依序展開 [**正向對應區域**此 SIP 網域，或否則根據所使用的外部 DNS 介面選取它。</span><span class="sxs-lookup"><span data-stu-id="21c9d-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="21c9d-133">您應該已如 Director 集區 （例如 lyncwebexdir01.contoso.com)，請參閱主機 A (對於 IPv6 為 AAAA) 記錄，因此確認它有。</span><span class="sxs-lookup"><span data-stu-id="21c9d-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="21c9d-134">如果不是，那麼您可能不使用 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="21c9d-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="21c9d-135">如果是這種情況，您需要使用的 FQDN，您前端集區，或如果您正在執行此動作的單一伺服器，您的前端伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="21c9d-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="21c9d-136">您也需要確認是否您不有任何前端集區的主機 A (對於 IPv6 為 AAAA) 記錄存在您外部 Web 服務完整完整網域名稱 (FQDN) （例如 lyncwebextpool01.contoso.com)、 前端集區或單一伺服器 fqdn 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="21c9d-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="21c9d-137">上一個步驟所述，您將需要這個下方如果您不需要 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="21c9d-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="21c9d-138">現在，在外部 DNS 提供者的適當格式，選擇 [建立**新別名 (CNAME)** （可能是功能表選項或連結，視 DNS 提供者的格式） 中的選項。</span><span class="sxs-lookup"><span data-stu-id="21c9d-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="21c9d-139">為使用內部 DNS 中，您應該輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱時，則應該是某種形式的**別名名稱**] 文字方塊。</span><span class="sxs-lookup"><span data-stu-id="21c9d-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="21c9d-140">也應某種形式的**完整網域名稱 (FQDN) 目標主機的**文字] 方塊中，以下其中您將為您的 Director 集區 (例如，lyncwebexdir01.contoso.com) 輸入外部 Web 服務 FQDN 然後按一下 [確定] 或接受此項目建立外部 DNS 中採取動作。</span><span class="sxs-lookup"><span data-stu-id="21c9d-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="21c9d-141">如上所述在步驟 4 中，如果您沒有 Director 集區]，您需要使用前端集區的 FQDN 或單一伺服器 FQDN 您已設定好，視需要。</span><span class="sxs-lookup"><span data-stu-id="21c9d-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="21c9d-142">您需要在 Lync 2013 環境中支援的每個 SIP 網域的正向對應區域中進行新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="21c9d-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="21c9d-143">建立內部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="21c9d-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="21c9d-144">若要讓內部 DNS 記錄，登入是 Domain Admins 群組的成員或 DnsAdmins 群組成員的網域帳戶與您網路的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="21c9d-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="21c9d-145">開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [DNS]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21c9d-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="21c9d-146">針對內部 DNS 記錄，DNS 伺服器的主控台樹狀目錄中展開 Active Directory 網域 (例如 contoso.local) 安裝 Lync Server 2013 Director 集區與前端集區的 [**正向對應區域**。</span><span class="sxs-lookup"><span data-stu-id="21c9d-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="21c9d-147">檢查，請參閱是否 (對於 IPv6 為 AAAA) 記錄存在，您的 Director 集區，針對內部 DNS 記錄的主機，主機 A 記錄應該存在於內部 Web 服務完整的網域名稱 (FQDN) Director 集區 (例如 lyncwebdir01.contoso.local)。</span><span class="sxs-lookup"><span data-stu-id="21c9d-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="21c9d-148">如果它不是在這裡，您不使用 Director 集區，而您將需要使用 IP 位址前端集區或甚至是單一伺服器的 IP 位址，如果這是您的設定。</span><span class="sxs-lookup"><span data-stu-id="21c9d-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="21c9d-149">請記住，，檢查並查看是否 (對於 IPv6 為 AAAA) 記錄存在，您的前端集區，針對內部 DNS 記錄的主機，主機 A （或 AAAA） 記錄應存在於您的前端集區的內部 Web 服務 fqdn （例如lyncwebpool01.contoso.local)。</span><span class="sxs-lookup"><span data-stu-id="21c9d-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="21c9d-150">如果沒有，您需要記前端伺服器或 Standard Edition 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="21c9d-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="21c9d-151">一旦您知道哪些主機 A （或 AAAA） 的記錄存在，您的 DNS 伺服器的主控台樹狀目錄中展開 SIP 網域 (例如，contoso.com) 的 [**正向對應區域**。</span><span class="sxs-lookup"><span data-stu-id="21c9d-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="21c9d-152">用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增主機 (A 或 AAAA)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21c9d-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="21c9d-153">在 [**名稱**] 中，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="21c9d-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="21c9d-154">在 [ **IP 位址**] 中，輸入 Director 的內部 Web 服務 IP 位址 （或者，如果您使用負載平衡器，請輸入虛擬 IP (VIP) Director 負載平衡器）。</span><span class="sxs-lookup"><span data-stu-id="21c9d-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="21c9d-155">如如果您不使用 Director，與上述步驟 4 中所述，您可能需要輸入前端伺服器或 Standard Edition server 的 IP 位址，或如果您使用負載平衡器中，輸入前端集區負載平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="21c9d-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="21c9d-156">按一下 [新增主機]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21c9d-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="21c9d-157">若要建立其他的 A 或 AAAA 記錄，重複步驟 8 到 10，請記住，您需要建立新的自動探索 A 或 AAAA 記錄中有支援 Lync Server 2013 環境中的每個 SIP 網域的正向對應區域。</span><span class="sxs-lookup"><span data-stu-id="21c9d-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="21c9d-158">完成建立 A (對於 IPv6 為 AAAA) 記錄時，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21c9d-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="21c9d-159">建立外部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="21c9d-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="21c9d-160">若要建立外部 DNS 記錄，連線至公用 DNS 提供者，並依照我們的步驟。</span><span class="sxs-lookup"><span data-stu-id="21c9d-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="21c9d-161">我們無法說明完全其中您即將 DNS 提供者的環境中可能有不同的方式，管理您的外部 DNS，但是我們希望這些步驟協助。</span><span class="sxs-lookup"><span data-stu-id="21c9d-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="21c9d-162">您需要的帳戶，可以在該環境中建立 DNS 記錄以登入。</span><span class="sxs-lookup"><span data-stu-id="21c9d-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="21c9d-163">針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21c9d-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="21c9d-164">針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21c9d-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="21c9d-165">您應該已如 Director 集區 （例如 lyncwebexdir01.contoso.com)，請參閱主機 A (對於 IPv6 為 AAAA) 記錄，因此請先確認有且 IP 位址是。</span><span class="sxs-lookup"><span data-stu-id="21c9d-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="21c9d-166">如果不是，那麼您可能不使用 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="21c9d-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="21c9d-167">如果是這種情況，您需要使用 IP 位址的您前端集區，或如果您正在執行此動作的單一伺服器，您的前端伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="21c9d-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="21c9d-168">請記住，您的伺服器也可能背後的負載平衡器，或使用反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="21c9d-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="21c9d-169">記下的 IP 位址以及遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="21c9d-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="21c9d-170">您也需要確認主機 A (對於 IPv6 為 AAAA) 記錄存在您外部 Web 服務完整完整網域名稱 (FQDN) （例如 lyncwebextpool01.contoso.com)、 前端集區或單一伺服器 Lync 安裝 IP 位址。 是否您不有任何前端集區。</span><span class="sxs-lookup"><span data-stu-id="21c9d-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="21c9d-171">上一個步驟所述，您將需要這個下方如果您不需要 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="21c9d-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="21c9d-172">現在，在外部 DNS 提供者的適當格式，選擇 [建立**新的主機 A 或 AAAA** （可能是功能表選項或連結，視 DNS 提供者的格式） 中的選項。</span><span class="sxs-lookup"><span data-stu-id="21c9d-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="21c9d-173">應該輸入的**名稱**、 輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱的位置。</span><span class="sxs-lookup"><span data-stu-id="21c9d-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="21c9d-174">也應**IP 位址**] 文字方塊中，以下是您要在其中輸入的 IP 您的 Director 集區 (例如，lyncwebexdir01.contoso.com) 或可能是 IP 集區的負載平衡器 （或反向 proxy IP 通往相同） 然後按一下 [確定] 或接受此項目建立外部 DNS 中採取動作。</span><span class="sxs-lookup"><span data-stu-id="21c9d-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="21c9d-175">如上所述在步驟 4 中，如果您沒有 Director 集區]，您需要使用的前端集區 IP 位址或您已設定好，單一伺服器 IP 位址為適當。</span><span class="sxs-lookup"><span data-stu-id="21c9d-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="21c9d-176">您需要在 Lync 2013 環境中支援的每個 SIP 網域的正向對應區域中進行新的自動探索 A 或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="21c9d-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

