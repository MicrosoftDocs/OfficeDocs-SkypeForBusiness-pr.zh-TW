---
title: Lync Server 2013：主要安全性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="9d748-102">Lync Server 2013 的主要安全性功能</span><span class="sxs-lookup"><span data-stu-id="9d748-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d748-103">_**主題上次修改日期：** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="9d748-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="9d748-104">Lync Server 2013 包含數種安全性功能，包括伺服器到伺服器驗證、以角色為基礎的存取控制，以及集中式儲存配置資料。</span><span class="sxs-lookup"><span data-stu-id="9d748-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="9d748-105">這篇文章提供 Lync Server 2013 安全性的高層次概覽。</span><span class="sxs-lookup"><span data-stu-id="9d748-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="9d748-106">Lync Server 2013 的主要安全性功能</span><span class="sxs-lookup"><span data-stu-id="9d748-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="9d748-107">安全性是一個非常廣泛的主題。</span><span class="sxs-lookup"><span data-stu-id="9d748-107">Security is a very broad topic.</span></span> <span data-ttu-id="9d748-108">每個 Lync Server 2013 的功能，以及組成 Lync 生態系統的資料庫、服務和硬體，都能達到安全性。</span><span class="sxs-lookup"><span data-stu-id="9d748-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="9d748-109">本文概述 Lync Server 2013 中的部分功能，特別是針對安全性設計的。</span><span class="sxs-lookup"><span data-stu-id="9d748-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="9d748-110">規劃和設計工具</span><span class="sxs-lookup"><span data-stu-id="9d748-110">Planning and Design Tools</span></span>

<span data-ttu-id="9d748-111">Lync Server 2013 提供兩種工具，可協助規劃及設計並減少 misconfiguring Lync Server 元件的機率。</span><span class="sxs-lookup"><span data-stu-id="9d748-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="9d748-112">**拓撲規劃工具**自動化了許多拓撲設計程式。</span><span class="sxs-lookup"><span data-stu-id="9d748-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="9d748-113">您可以將規劃工具的結果匯出至 [拓撲建立器]，這是安裝每個執行 Lync Server 2013 的伺服器所需的工具。</span><span class="sxs-lookup"><span data-stu-id="9d748-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="9d748-114">**拓撲**建立器會將所有配置資訊儲存在中央管理儲存區中。</span><span class="sxs-lookup"><span data-stu-id="9d748-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="9d748-115">如需這些工具的詳細資訊，請參閱[規劃 Lync Server 2013](lync-server-2013-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="9d748-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="9d748-116">中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="9d748-116">Central Management Store</span></span>

<span data-ttu-id="9d748-117">在 Lync Server 2013 中，伺服器與服務的設定資料是集中式管理儲存體的一部分。</span><span class="sxs-lookup"><span data-stu-id="9d748-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="9d748-118">[中央管理] 商店提供資料的強健、schematized 儲存，以定義、設定、維護、管理、描述及操作 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="9d748-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="9d748-119">它也會驗證資料，以確保配置一致性。</span><span class="sxs-lookup"><span data-stu-id="9d748-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="9d748-120">此設定資料的所有變更都會出現在中央管理商店，消除「不同步」問題。</span><span class="sxs-lookup"><span data-stu-id="9d748-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="9d748-121">唯讀複本會將資料複製到拓撲中的所有伺服器，包括 Edge 伺服器和 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="9d748-121">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances.</span></span> <span data-ttu-id="9d748-122">複製是由預設會在網路服務內容下執行的服務所管理，可減少電腦上簡單使用者的權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="9d748-122">Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="9d748-123">伺服器對伺服器驗證</span><span class="sxs-lookup"><span data-stu-id="9d748-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="9d748-124">在 Lync Server 2013 中，您可以使用開啟授權（OAuth）通訊協定，在伺服器之間設定驗證。</span><span class="sxs-lookup"><span data-stu-id="9d748-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="9d748-125">例如，您可以設定 Lync Server 2013，以使用執行 Exchange Server 2013 的伺服器進行驗證。</span><span class="sxs-lookup"><span data-stu-id="9d748-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="9d748-126">使用 OAuth 通訊協定，Lync server 和 Exchange 伺服器可以相互信任。</span><span class="sxs-lookup"><span data-stu-id="9d748-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="9d748-127">這能讓您以流暢的方式整合產品。</span><span class="sxs-lookup"><span data-stu-id="9d748-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="9d748-128">如需詳細資訊，請參閱[在 Lync server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="9d748-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="9d748-129">Windows PowerShell 式管理和網路式管理介面</span><span class="sxs-lookup"><span data-stu-id="9d748-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="9d748-130">Lync Server 2013 提供功能強大的管理介面（在 Windows PowerShell 命令列介面上建立）。</span><span class="sxs-lookup"><span data-stu-id="9d748-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="9d748-131">它包含管理安全性的 Cmdlet，而且預設會啟用 Windows PowerShell 安全性功能，讓使用者不會輕易或無意中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="9d748-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="9d748-132">這表示軟體預設值會設定為自動協助最大化安全性並減少攻擊途徑。</span><span class="sxs-lookup"><span data-stu-id="9d748-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="9d748-133">如需 Lync Server 2013 中的 Windows PowerShell 管理支援的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="9d748-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="9d748-134">以角色為基礎的存取控制（RBAC）</span><span class="sxs-lookup"><span data-stu-id="9d748-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="9d748-135">Microsoft Lync Server 2013 提供以角色為基礎的存取控制（RBAC），可讓您委派管理工作，同時維持高安全性的標準。</span><span class="sxs-lookup"><span data-stu-id="9d748-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="9d748-136">您可以使用 RBAC 遵循「最低許可權」的原則，在此原則中，使用者只會得到他們工作所需的管理許可權。</span><span class="sxs-lookup"><span data-stu-id="9d748-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="9d748-137">Lync Server 2013 引入了建立新角色的功能，也是修改現有角色的功能。</span><span class="sxs-lookup"><span data-stu-id="9d748-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="9d748-138">如需詳細資訊，請參閱[在 Lync Server 2013 中規劃以角色為基礎的存取控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9d748-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="9d748-139">網路位址轉譯（NAT）</span><span class="sxs-lookup"><span data-stu-id="9d748-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="9d748-140">Lync Server 2013 不支援在 Edge 伺服器的內部介面使用網路位址轉譯（NAT），但它支援將存取邊緣服務、Web 會議邊緣服務的外部介面與路由器或防火牆後面的 A/V 邊緣服務搭配執行，可針對單一和縮放的合併邊緣伺服器拓撲進行網路位址轉譯（NAT）。</span><span class="sxs-lookup"><span data-stu-id="9d748-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="9d748-141">在硬體負載平衡器後的多個邊緣伺服器無法使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="9d748-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="9d748-142">如果有多個邊緣伺服器在其外部介面上使用 NAT，則需要網功能變數名稱稱系統（DNS）負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9d748-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="9d748-143">接著，您可以使用 DNS 負載平衡，在 Edge 伺服器池中減少每個邊緣伺服器的公用 IP 位址數目。</span><span class="sxs-lookup"><span data-stu-id="9d748-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="9d748-144">如需詳細資訊，請參閱[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9d748-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9d748-145">如果您是與已安裝 Microsoft Office 通訊伺服器2007部署的企業聯盟，而且您需要在企業與同盟企業之間使用音訊/視頻，則埠需求就會是部署的較舊版本的邊緣伺服器的需求。</span><span class="sxs-lookup"><span data-stu-id="9d748-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="9d748-146">例如，必須針對兩個企業開啟這些較舊版本所需的埠範圍，直到聯盟合作夥伴將其 Edge 伺服器升級到 Lync Server 2013 為止。</span><span class="sxs-lookup"><span data-stu-id="9d748-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="9d748-147">此時，您可以根據新設定來審查並減少埠需求。</span><span class="sxs-lookup"><span data-stu-id="9d748-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="9d748-148">簡化的邊緣伺服器憑證</span><span class="sxs-lookup"><span data-stu-id="9d748-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="9d748-149">[部署嚮導] 可自動填入消費者名稱（SNs）和消費者備用名稱（San），減少包括不必要和可能不安全的專案的可能性。</span><span class="sxs-lookup"><span data-stu-id="9d748-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="9d748-150">可信計算安全性開發週期（SDL）</span><span class="sxs-lookup"><span data-stu-id="9d748-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="9d748-151">Lync Server 2013 的設計與開發符合 Microsoft 高可信計算安全性開發週期（SDL），其說明如下<http://go.microsoft.com/fwlink/?linkid=68761>。</span><span class="sxs-lookup"><span data-stu-id="9d748-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <http://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="9d748-152">**根據設計**   ，建立更安全的整合通訊系統中的第一個步驟，就是設計威脅模型並測試每個功能的設計。</span><span class="sxs-lookup"><span data-stu-id="9d748-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="9d748-153">此外，Microsoft 還會在設計的行為以外執行測試，以找出意外產品行為所產生的安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="9d748-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="9d748-154">編碼程式與做法內建了多個安全性相關的改良功能。</span><span class="sxs-lookup"><span data-stu-id="9d748-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="9d748-155">在將程式碼簽入最終產品之前，組建時間工具會偵測緩衝區溢位及其他潛在安全性威脅。</span><span class="sxs-lookup"><span data-stu-id="9d748-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="9d748-156">當然，可能無法針對所有未知的安全性威脅進行設計。</span><span class="sxs-lookup"><span data-stu-id="9d748-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="9d748-157">任何系統都不能保證完整的安全性。</span><span class="sxs-lookup"><span data-stu-id="9d748-157">No system can guarantee complete security.</span></span> <span data-ttu-id="9d748-158">不過，由於產品開發採用來自開始的安全設計原則，因此 Lync Server 2013 將業界標準安全技術納入其架構的基本部分。</span><span class="sxs-lookup"><span data-stu-id="9d748-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="9d748-159">**預設為可信**   ： Lync Server 2013 的網路通訊是經過加密的。</span><span class="sxs-lookup"><span data-stu-id="9d748-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="9d748-160">由於所有伺服器都使用憑證和 Kerberos 驗證、TLS、安全的即時傳輸通訊協定（SRTP），以及其他業界標準的加密技術，包括128位進階加密標準（AES）加密，幾乎都是所有 Lync網路上的伺服器資料受到保護。</span><span class="sxs-lookup"><span data-stu-id="9d748-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="9d748-161">此外，角色式存取控制能讓您部署執行 Lync Server 2013 的伺服器，讓每個伺服器角色只執行服務，而且只有與這些服務相關聯的許可權，這些都適用于伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="9d748-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="9d748-162">**受部署**   信任：所有 Lync Server 2013 檔都包含最佳做法與建議，以協助您決定並設定您的部署的最佳安全等級，並評估啟用非預設選項的安全性風險。</span><span class="sxs-lookup"><span data-stu-id="9d748-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

