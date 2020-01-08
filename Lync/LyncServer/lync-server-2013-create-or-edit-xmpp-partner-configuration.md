---
title: Lync Server 2013：建立或編輯 XMPP 夥伴設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488fa84a3f24133c6ebcde4467cacdbdcffe7ff8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="baedb-102">在 Lync Server 2013 中建立或編輯 XMPP 夥伴設定</span><span class="sxs-lookup"><span data-stu-id="baedb-102">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baedb-103">_**主題上次修改日期：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="baedb-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="baedb-104">Microsoft Lync Server 2013 整合了 Edge 伺服器上的可擴展訊息和目前狀態通訊協定（XMPP） proxy，以及前端伺服器或頂層端池中的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="baedb-104">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="baedb-105">若要允許來自其他 XMPP 部署的連線，您必須在 Lync Server [控制台] 中設定 XMPP。</span><span class="sxs-lookup"><span data-stu-id="baedb-105">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="baedb-106">您可以設定 XMPP 網域的設定。</span><span class="sxs-lookup"><span data-stu-id="baedb-106">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="baedb-107">若要建立新的合作夥伴關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="baedb-107">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="baedb-108">若要建立新的聯盟合作夥伴或編輯現有的配置</span><span class="sxs-lookup"><span data-stu-id="baedb-108">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="baedb-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="baedb-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="baedb-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="baedb-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="baedb-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="baedb-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="baedb-112">在左側導覽列中，按一下 [**同盟及外部存取**]，然後按一下 [ **XMPP 聯盟夥伴**]。</span><span class="sxs-lookup"><span data-stu-id="baedb-112">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="baedb-113">若要建立新的設定，請按一下 [**新增**]</span><span class="sxs-lookup"><span data-stu-id="baedb-113">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="baedb-114">若要編輯現有的設定，請選取設定，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="baedb-114">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="baedb-115">若要建立或編輯**XMPP 聯盟夥伴**的設定，您可以定義下列設定：</span><span class="sxs-lookup"><span data-stu-id="baedb-115">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="baedb-116">**主要網域**（必要）。</span><span class="sxs-lookup"><span data-stu-id="baedb-116">**Primary domain** (Required).</span></span> <span data-ttu-id="baedb-117">[主要網域] 是 XMPP 合作夥伴的基底網域。</span><span class="sxs-lookup"><span data-stu-id="baedb-117">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="baedb-118">例如，您可以輸入 XMPP 夥伴功能變數名稱的**fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="baedb-118">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="baedb-119">這是必要的專案。</span><span class="sxs-lookup"><span data-stu-id="baedb-119">This is a required entry.</span></span>

8.  <span data-ttu-id="baedb-120">[**描述**]。</span><span class="sxs-lookup"><span data-stu-id="baedb-120">**Description**.</span></span> <span data-ttu-id="baedb-121">描述針對此特定設定的備忘稿或其他識別資訊。</span><span class="sxs-lookup"><span data-stu-id="baedb-121">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="baedb-122">這個專案是選用的。</span><span class="sxs-lookup"><span data-stu-id="baedb-122">This entry is optional.</span></span>

9.  <span data-ttu-id="baedb-123">**其他網域**。</span><span class="sxs-lookup"><span data-stu-id="baedb-123">**Additional domains**.</span></span> <span data-ttu-id="baedb-124">其他網域是您 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。</span><span class="sxs-lookup"><span data-stu-id="baedb-124">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="baedb-125">例如，如果主要網域是**fabrikam.com**，則您會列出位於 [fabrikam.com] 下的所有其他網域，您會透過 XMPP 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="baedb-125">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="baedb-126">例如，您可能會在 [fabrikam .com 的主要 XMPP 網域] 下輸入公司 XMPP 網域的**corp.fabrikam.com**和**IT.FABRIKAM.COM** ，以及 XMPP domain 的資訊技術。</span><span class="sxs-lookup"><span data-stu-id="baedb-126">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="baedb-127">**合作夥伴類型**。</span><span class="sxs-lookup"><span data-stu-id="baedb-127">**Partner type**.</span></span> <span data-ttu-id="baedb-128">「**合作夥伴類型**」是必要的設定，可讓您選取下拉式功能表中的三個選項。</span><span class="sxs-lookup"><span data-stu-id="baedb-128">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="baedb-129">您必須選擇下列其中一項，以描述並強制加入您可以新增的連絡人。</span><span class="sxs-lookup"><span data-stu-id="baedb-129">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="baedb-130">您可以選取 [寄件者]：</span><span class="sxs-lookup"><span data-stu-id="baedb-130">You can select from:</span></span>
    
      - <span data-ttu-id="baedb-131">\*\*\*\* 同盟。</span><span class="sxs-lookup"><span data-stu-id="baedb-131">**Federated**.</span></span> <span data-ttu-id="baedb-132">**聯盟**夥伴類型是 Lync Server 或 Office 通訊伺服器 2007 R2 合作夥伴部署之間的信任連線。</span><span class="sxs-lookup"><span data-stu-id="baedb-132">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="baedb-133">**公用驗證**。</span><span class="sxs-lookup"><span data-stu-id="baedb-133">**Public verified**.</span></span> <span data-ttu-id="baedb-134">**公用驗證**合作夥伴是指由提供者驗證之部署的連絡人，可以新增至使用者的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="baedb-134">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="baedb-135">您可以從 Lync 使用者傳送邀請，或者 Lync 使用者可以接受來自合作夥伴連絡人的邀請。</span><span class="sxs-lookup"><span data-stu-id="baedb-135">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="baedb-136">**公用未驗證**。</span><span class="sxs-lookup"><span data-stu-id="baedb-136">**Public unverified**.</span></span> <span data-ttu-id="baedb-137">**公用未驗證**的關聯表示兩個部署之間沒有已建立且可驗證的狀態。</span><span class="sxs-lookup"><span data-stu-id="baedb-137">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="baedb-138">Lync 使用者必須邀請該連絡人的未驗證連絡人，才能將 Lync 使用者新增至他的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="baedb-138">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="baedb-139">例如，Google GTalk 不是與 Lync Server 相關的公用驗證 XMPP 服務。</span><span class="sxs-lookup"><span data-stu-id="baedb-139">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="baedb-140">除非有明確的邀請從 Lync 使用者傳送，否則 GTalk 使用者將無法將 Lync 使用者新增為連絡人。</span><span class="sxs-lookup"><span data-stu-id="baedb-140">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="baedb-141">資料流程協商和安全方法傳輸層安全性（TLS）及軟體驗證與安全性層（SASL）的注意事項：</span><span class="sxs-lookup"><span data-stu-id="baedb-141">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="baedb-142">**XMPP 標準基礎**（XSF）和**網際網路工程工作組**（IETF）定義一組用來使用及管理 TLS 用戶端憑證、TLS 伺服器憑證及 SASL 機制的規則和標準。</span><span class="sxs-lookup"><span data-stu-id="baedb-142">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism.</span></span> <span data-ttu-id="baedb-143">使用 TLS 和 SASL 是保護 XMPP 資料流程所需的程式。</span><span class="sxs-lookup"><span data-stu-id="baedb-143">Using TLS and SASL is the required process for securing the XMPP stream.</span></span> <span data-ttu-id="baedb-144">從 XMPP 標準檔**XEP-0178**，「指定建議的通訊協定流程，以使用包含 PKIX 憑證的 SASL 外部機制，尤其是當 XMPP 服務指出 TLS 是強制協商時。」</span><span class="sxs-lookup"><span data-stu-id="baedb-144">From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.”</span></span> <span data-ttu-id="baedb-145">PKIX （如 XSF 檔所述），指的是公開金鑰基礎結構（也稱為 PKI）。</span><span class="sxs-lookup"><span data-stu-id="baedb-145">PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="baedb-146">如需 XMPP 需求的詳細資訊，請參閱 XSF 檔 XEP-0178。</span><span class="sxs-lookup"><span data-stu-id="baedb-146">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="baedb-147">如需詳細資訊，請參閱「XEP-0178：使用 SASL 外部與憑證的最佳做法」。</span><span class="sxs-lookup"><span data-stu-id="baedb-147">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="baedb-148">請參閱 IETF 檔「可擴展訊息和目前狀態通訊協定（XMPP）：核心」、5.0 區段、STARTTLS <http://tools.ietf.org/html/rfc6120>協商。</span><span class="sxs-lookup"><span data-stu-id="baedb-148">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <http://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="baedb-149">**TLS 協商**。</span><span class="sxs-lookup"><span data-stu-id="baedb-149">**TLS Negotiation**.</span></span> <span data-ttu-id="baedb-150">定義 TLS 協商規則。</span><span class="sxs-lookup"><span data-stu-id="baedb-150">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="baedb-151">XMPP 服務可能需要 TLS，可以進行 TLS 選用，或定義不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="baedb-151">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="baedb-152">選擇 [選用] 可將需求留給 XMPP 服務，以進行強制性的協商決策。</span><span class="sxs-lookup"><span data-stu-id="baedb-152">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="baedb-153">若要查看所有可能的設定和詳細資料，以瞭解 SASL、TLS 及回撥的協商，包括不合法和已知的錯誤配置-請參閱[Lync Server 2013 中 XMPP 聯盟夥伴的協商設定](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="baedb-153">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="baedb-154">**必要**。</span><span class="sxs-lookup"><span data-stu-id="baedb-154">**Required**.</span></span> <span data-ttu-id="baedb-155">XMPP 服務需要 TLS 協商。</span><span class="sxs-lookup"><span data-stu-id="baedb-155">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="baedb-156">**選用**。</span><span class="sxs-lookup"><span data-stu-id="baedb-156">**Optional**.</span></span> <span data-ttu-id="baedb-157">XMPP 服務指出 TLS 是強制性的協商式。</span><span class="sxs-lookup"><span data-stu-id="baedb-157">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="baedb-158">**不支援**。</span><span class="sxs-lookup"><span data-stu-id="baedb-158">**Not Supported**.</span></span> <span data-ttu-id="baedb-159">XMPP 服務不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="baedb-159">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="baedb-160">**SASL 協商**。</span><span class="sxs-lookup"><span data-stu-id="baedb-160">**SASL negotiation**.</span></span> <span data-ttu-id="baedb-161">定義 SASL 協商規則。</span><span class="sxs-lookup"><span data-stu-id="baedb-161">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="baedb-162">XMPP 服務可能需要 SASL、可進行 SASL 選擇，或定義不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="baedb-162">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="baedb-163">選擇 [選用] 可將需求留給合作夥伴 XMPP 服務，以進行強制性的協商決策。</span><span class="sxs-lookup"><span data-stu-id="baedb-163">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="baedb-164">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="baedb-164">SASL requires TLS.</span></span> <span data-ttu-id="baedb-165">若要使用 SASL，TLS 必須是必要的或選擇性的。</span><span class="sxs-lookup"><span data-stu-id="baedb-165">To use SASL, TLS must either be required or optional.</span></span> <span data-ttu-id="baedb-166">將 SASL 定義為 [必要] 或 [選擇性] 的任何設定，都必須有 TLS 支援。</span><span class="sxs-lookup"><span data-stu-id="baedb-166">Any configuration that defines SASL as either required or optional must have TLS support.</span></span> <span data-ttu-id="baedb-167">按一下 [ <STRONG>Commit</STRONG> ] （提交）以儲存變更時，如果您未將 TLS 設定為 [必要] 或 [選擇性]，系統會在 SASL 必須提供 tls 支援，且不會儲存您所做的變更。</span><span class="sxs-lookup"><span data-stu-id="baedb-167">When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved.</span></span> <span data-ttu-id="baedb-168">若要解決錯誤，請將 TLS 設定為 [<STRONG>必要</STRONG>] 或 [<STRONG>選擇性</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="baedb-168">To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>.</span></span> <span data-ttu-id="baedb-169">如果您選用了 SASL，且無法進行 TLS 協商支援，則您必須將 SASL 協商設定為 [<STRONG>不支援</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="baedb-169">If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>.</span></span> <span data-ttu-id="baedb-170">確認 XMPP 服務必須針對 TLS 和 SASL 進行哪些適當的協商資料流程，否則就會發生服務中斷。</span><span class="sxs-lookup"><span data-stu-id="baedb-170">Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="baedb-171">**必要**。</span><span class="sxs-lookup"><span data-stu-id="baedb-171">**Required**.</span></span> <span data-ttu-id="baedb-172">XMPP 服務需要 SASL 協商。</span><span class="sxs-lookup"><span data-stu-id="baedb-172">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="baedb-173">**選用**。</span><span class="sxs-lookup"><span data-stu-id="baedb-173">**Optional**.</span></span> <span data-ttu-id="baedb-174">XMPP 服務指出 SASL 是必須協商的。</span><span class="sxs-lookup"><span data-stu-id="baedb-174">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="baedb-175">**不支援**。</span><span class="sxs-lookup"><span data-stu-id="baedb-175">**Not Supported**.</span></span> <span data-ttu-id="baedb-176">XMPP 服務不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="baedb-176">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="baedb-177">**回撥（協商**）。</span><span class="sxs-lookup"><span data-stu-id="baedb-177">**Dialback negotiation**.</span></span> <span data-ttu-id="baedb-178">回撥的協商是由檔 XEP 中的 XSF 所定義 **-220：伺服器回撥** <http://xmpp.org/extensions/xep-0220.html>。</span><span class="sxs-lookup"><span data-stu-id="baedb-178">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="baedb-179">伺服器回撥程式會使用網域名稱系統（DNS）和權威性伺服器來驗證要求來自有效的 XMPP 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="baedb-179">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="baedb-180">若要這樣做，始發伺服器會使用產生的回撥金鑰來建立特定類型的郵件，並在 DNS 中尋找接收伺服器。</span><span class="sxs-lookup"><span data-stu-id="baedb-180">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="baedb-181">始發伺服器會將 XML 資料流程中的金鑰傳送到產生的 DNS 查詢（大概是接收伺服器）。</span><span class="sxs-lookup"><span data-stu-id="baedb-181">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="baedb-182">當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="baedb-182">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="baedb-183">權威性伺服器驗證金鑰是否有效或無效。</span><span class="sxs-lookup"><span data-stu-id="baedb-183">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="baedb-184">如果無效，接收伺服器就不會回應始發伺服器。</span><span class="sxs-lookup"><span data-stu-id="baedb-184">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="baedb-185">如果金鑰有效，接收伺服器會通知始發伺服器：身分識別和金鑰有效，且可以開始交談。</span><span class="sxs-lookup"><span data-stu-id="baedb-185">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="baedb-186">對於**回撥協商**，有兩種有效的狀態：</span><span class="sxs-lookup"><span data-stu-id="baedb-186">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="baedb-187">**True**。</span><span class="sxs-lookup"><span data-stu-id="baedb-187">**True**.</span></span> <span data-ttu-id="baedb-188">如果應從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥的協商</span><span class="sxs-lookup"><span data-stu-id="baedb-188">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="baedb-189">**False**。</span><span class="sxs-lookup"><span data-stu-id="baedb-189">**False**.</span></span> <span data-ttu-id="baedb-190">XMPP 伺服器未設定為使用回撥協商，如果應該從始發伺服器接收要求，則會被忽略</span><span class="sxs-lookup"><span data-stu-id="baedb-190">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

