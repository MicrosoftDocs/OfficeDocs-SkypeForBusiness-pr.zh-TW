---
title: Lync Server 2013：重要安全性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a1ff88b11c7d0ce007fc3bac38e7e3618771fb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514020"
---
# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="f5c4a-102">Lync Server 2013 中的重要安全性功能</span><span class="sxs-lookup"><span data-stu-id="f5c4a-102">Key security features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5c4a-103">_**主題上次修改日期：** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="f5c4a-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="f5c4a-104">Lync Server 2013 包含數個安全性功能，包括伺服器對伺服器驗證、角色型存取控制，以及設定資料的集中式儲存區。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="f5c4a-105">本文提供 Lync Server 2013 安全性的高層次概述。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="f5c4a-106">Lync Server 2013 中的重要安全性功能</span><span class="sxs-lookup"><span data-stu-id="f5c4a-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="f5c4a-107">安全性是非常廣泛的主題。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-107">Security is a very broad topic.</span></span> <span data-ttu-id="f5c4a-108">每個 Lync Server 2013 功能的安全性，以及構成 Lync 生態系統之資料庫、服務和硬體的安全性。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="f5c4a-109">本文概述 Lync Server 2013 中的部分功能，尤其是針對安全性設計。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="f5c4a-110">規劃及設計工具</span><span class="sxs-lookup"><span data-stu-id="f5c4a-110">Planning and Design Tools</span></span>

<span data-ttu-id="f5c4a-111">Lync Server 2013 提供兩個工具，可協助規劃及設計，並減少 kerberos Lync Server 元件的機率。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="f5c4a-112">**拓撲規劃工具** 會使大部分的拓撲設計程式自動化。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="f5c4a-113">您可以將規劃工具的結果匯出至拓撲產生器，這是安裝每一部執行 Lync Server 2013 的伺服器所需的工具。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="f5c4a-114">**拓撲** 產生器會將所有設定資訊儲存在中央管理存放區中。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="f5c4a-115">如需這些工具的詳細資訊，請參閱 [規劃 Lync Server 2013](lync-server-2013-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="f5c4a-116">Central Management Store</span><span class="sxs-lookup"><span data-stu-id="f5c4a-116">Central Management Store</span></span>

<span data-ttu-id="f5c4a-117">在 Lync Server 2013 中，有關伺服器和服務的設定資料是中央管理存放區的一部分。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="f5c4a-118">中央管理存放區為定義、設定、維護、管理、描述及操作 Lync Server 部署所需的資料提供了可靠的 schematized 儲存。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="f5c4a-119">它也驗證資料，以確保設定一致性。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="f5c4a-120">對此設定資料所做的所有變更都會發生在中央管理存放區，消除「不同步」的問題。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="f5c4a-121">資料的唯讀複本會複製到拓撲中的所有伺服器，包括 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-121">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances.</span></span> <span data-ttu-id="f5c4a-122">複寫是由預設會在網路服務內容下執行的服務所管理，可減少電腦上的簡易使用者的權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-122">Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="f5c4a-123">Server-to-Server 驗證</span><span class="sxs-lookup"><span data-stu-id="f5c4a-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="f5c4a-124">在 Lync Server 2013 中，您可以使用「開啟授權 (OAuth) 通訊協定，在伺服器之間設定驗證。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="f5c4a-125">例如，您可以設定 Lync Server 2013，以與執行 Exchange Server 2013 的伺服器進行驗證。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="f5c4a-126">Lync server 與 Exchange server 可以相互信任，使用 OAuth 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="f5c4a-127">這讓您能夠以無縫的方式整合產品。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="f5c4a-128">如需詳細資訊，請參閱 [管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式的 Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="f5c4a-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="f5c4a-129">Windows PowerShell 型管理和以網路為基礎的管理介面</span><span class="sxs-lookup"><span data-stu-id="f5c4a-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="f5c4a-130">Lync Server 2013 提供強大的管理介面，以 Windows PowerShell 命令列介面為基礎。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="f5c4a-131">它包含管理安全性的 Cmdlet，預設會啟用 Windows PowerShell 安全性功能，讓使用者無法輕易或無意中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="f5c4a-132">這表示軟體預設值設為自動協助最大化安全性，並減少攻擊途徑。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="f5c4a-133">如需 Lync Server 2013 中 Windows PowerShell 管理支援的詳細資訊，請參閱 [Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="f5c4a-134">角色型存取控制 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="f5c4a-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="f5c4a-135">Microsoft Lync Server 2013 提供以角色為基礎的存取控制 (RBAC) ，可讓您委派管理工作，同時維持高安全性標準。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="f5c4a-136">您可以使用 RBAC 遵循「最低許可權」的原則，讓使用者只會獲得其工作所需的系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="f5c4a-137">Lync Server 2013 引進的功能，可建立新的角色，也可修改現有角色的功能。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="f5c4a-138">如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃以角色為基礎的存取控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="f5c4a-139">網路位址轉譯 (NAT) </span><span class="sxs-lookup"><span data-stu-id="f5c4a-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="f5c4a-140">Lync Server 2013 不支援在 Edge Server 的內部介面上使用網路位址轉譯 (NAT) ，但它不支援將 Access Edge service、Web 會議 Edge service 和 A/V Edge service 的外部介面放在路由器或防火牆後面，可對單一及調整式合併 Edge Server 拓撲執行網路位址轉譯 (NAT) 。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="f5c4a-141">硬體負載平衡器背後的多部 Edge Server 無法使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="f5c4a-142">如果有多部 Edge Server 在其外部介面上使用 NAT，則需要網域名稱系統 (DNS) 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="f5c4a-143">反過來，使用 DNS 負載平衡可讓您減少 Edge Server 集區中每一 Edge Server 的公用 IP 位址數目。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="f5c4a-144">如需詳細資訊，請參閱[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5c4a-145">如果您與具有 Microsoft Office 通訊伺服器2007部署的企業同盟，且您需要在您的企業和同盟企業之間使用音訊/視頻，則埠需求將會是部署的舊版 Edge Server 的需求。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="f5c4a-146">例如，必須針對這兩種企業開啟這些舊版本所需的埠範圍，直到同盟合作夥伴將其 Edge Server 升級至 Lync Server 2013 為止。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="f5c4a-147">在這個階段，您可以根據新設定來檢查和縮短埠需求。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="f5c4a-148">簡化 Edge Server 的憑證</span><span class="sxs-lookup"><span data-stu-id="f5c4a-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="f5c4a-149">部署嚮導可自動將主體名稱填入 (SNs) 和主體替代名稱 (SANs) ，以減少包含不必要的可能不安全專案的可能性。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="f5c4a-150">可信賴的計算安全性開發生命週期 (SDL) </span><span class="sxs-lookup"><span data-stu-id="f5c4a-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="f5c4a-151">Lync Server 2013 的設計和開發符合 Microsoft 可信賴的計算安全性開發生命週期 (SDL) ，如所述 <https://go.microsoft.com/fwlink/?linkid=68761> 。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <https://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="f5c4a-152">**以設計**     為可信建立更安全的整合通訊系統的第一步是設計威脅模型，並在設計時測試每項功能。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="f5c4a-153">此外，Microsoft 會在設計行為以外執行測試，以找出意外產品行為所產生的安全性弱點。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="f5c4a-154">編碼程式和作法內建了多種安全性相關的增強功能。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="f5c4a-155">組建時間工具會在將程式碼存回最終產品之前，偵測緩衝區溢位及其他潛在安全性威脅。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="f5c4a-156">當然，不可能針對所有未知的安全性威脅進行設計。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="f5c4a-157">任何系統都不能保證完整的安全性。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-157">No system can guarantee complete security.</span></span> <span data-ttu-id="f5c4a-158">不過，由於產品開發採用來自「開始」的安全性設計原則，所以 Lync Server 2013 採用業界標準安全性技術作為其架構的基礎部分。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="f5c4a-159">**預設**     為可信依預設，Lync Server 2013 中的網路通訊都會加密。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="f5c4a-160">由於所有伺服器都使用憑證及 Kerberos 驗證、TLS、安全 Real-Time 傳輸通訊協定 (SRTP) 和其他業界標準加密技術，包括128位的進階加密標準 (AES) 加密，實際上所有的 Lync Server 資料都會在網路上受到保護。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="f5c4a-161">此外，以角色為基礎的存取控制可讓您部署執行 Lync Server 2013 的伺服器，如此一來，每個伺服器角色都只執行服務，而且只會有與這些服務相關的許可權，這些都適用于伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="f5c4a-162">**信任的部署**    所有的 Lync Server 2013 檔都包含最佳作法和建議，可協助您決定及設定部署的最佳安全性層級，並評估啟用非預設選項的安全性風險。</span><span class="sxs-lookup"><span data-stu-id="f5c4a-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

