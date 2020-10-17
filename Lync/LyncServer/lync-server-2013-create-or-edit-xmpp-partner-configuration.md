---
title: Lync Server 2013：建立或編輯 XMPP 夥伴設定
description: Lync Server 2013：建立或編輯 XMPP partner configuration。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19289df1920287984f104bb1bdfa214d6f83f5cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553869"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a><span data-ttu-id="e2a6d-103">在 Lync Server 2013 中建立或編輯 XMPP partner configuration</span><span class="sxs-lookup"><span data-stu-id="e2a6d-103">Create or edit XMPP partner configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2a6d-104">_**主題上次修改日期：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="e2a6d-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="e2a6d-105">Microsoft Lync Server 2013 整合了 Edge Server 上的可延伸訊息和顯示狀態通訊協定 (XMPP) proxy，以及前端伺服器或前端集區上的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-105">Microsoft Lync Server 2013 integrates an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="e2a6d-106">若要允許來自其他 XMPP 部署的連線，您必須在 Lync Server 控制台中設定 XMPP。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-106">To allow connections from other XMPP deployments, you must configure XMPP in the Lync Server Control Panel.</span></span> <span data-ttu-id="e2a6d-107">您可以根據 XMPP 網域進行設定。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-107">You configure settings on an XMPP domain basis.</span></span> <span data-ttu-id="e2a6d-108">若要建立新的協力廠商關聯，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e2a6d-108">To create a new partner association, you do the following:</span></span>

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a><span data-ttu-id="e2a6d-109">若要建立新的同盟合作夥伴或編輯現有的設定</span><span class="sxs-lookup"><span data-stu-id="e2a6d-109">To create a new federated partner or edit an existing configuration</span></span>

1.  <span data-ttu-id="e2a6d-110">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2a6d-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2a6d-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2a6d-113">在左導覽列中，按一下 **[同盟和外部存取]**，然後按一下 **[XMPP 同盟協力廠商]**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-113">In the left navigation bar, click **Federation and External Access**, and then click **XMPP Federated Partners**.</span></span>

4.  <span data-ttu-id="e2a6d-114">若要建立新設定，按一下 **[新增]**</span><span class="sxs-lookup"><span data-stu-id="e2a6d-114">To create a new configuration, click **New**</span></span>

5.  <span data-ttu-id="e2a6d-115">若要編輯現有的設定，可選取該設定，然後按一下 **[編輯]**</span><span class="sxs-lookup"><span data-stu-id="e2a6d-115">To edit an existing configuration, select the configuration and click **Edit**</span></span>

6.  <span data-ttu-id="e2a6d-116">若要建立或編輯 **[XMPP 同盟協力廠商]** 的設定，您要定義下列設定：</span><span class="sxs-lookup"><span data-stu-id="e2a6d-116">To create or edit configurations for **XMPP Federated Partners**, you define the following settings:</span></span>

7.  <span data-ttu-id="e2a6d-117">**主要網域** (必要) 。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-117">**Primary domain** (Required).</span></span> <span data-ttu-id="e2a6d-118">主要網域為 XMPP 協力廠商的基本網域。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-118">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="e2a6d-119">例如，您可以為 XMPP 協力廠商網域名稱輸入 **fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-119">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="e2a6d-120">此為必要項目。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-120">This is a required entry.</span></span>

8.  <span data-ttu-id="e2a6d-121">**描述**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-121">**Description**.</span></span> <span data-ttu-id="e2a6d-122">描述是針對此特定設定的附注或其他識別資訊。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-122">The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="e2a6d-123">此專案是選用專案。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-123">This entry is optional.</span></span>

9.  <span data-ttu-id="e2a6d-124">**其他網域**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-124">**Additional domains**.</span></span> <span data-ttu-id="e2a6d-125">其他網域是 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-125">Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="e2a6d-126">例如，如果主域是 **fabrikam.com**，則您會列出位於 fabrikam.com 的所有其他網域，您會透過 XMPP 的方式來進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-126">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span> <span data-ttu-id="e2a6d-127">例如，您可以在 fabrikam .com 的主要 XMPP 網域中，輸入公司 XMPP 網域和資訊技術 XMPP 網域的 **corp.fabrikam.com** 和 **it.fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-127">For example, you might enter **corp.fabrikam.com** and **it.fabrikam.com** for the Corporate XMPP domain and the Information Technologies XMPP domain under fabrikam.com’s main XMPP domain.</span></span>

10. <span data-ttu-id="e2a6d-128">**合作夥伴類型**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-128">**Partner type**.</span></span> <span data-ttu-id="e2a6d-129">「 **合作夥伴類型** 」是必要的設定，可讓您選取下拉式功能表中的三個選項。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-129">The **Partner type** is a required setting and gives you a selection of three choices in a drop-down menu.</span></span> <span data-ttu-id="e2a6d-130">您必須選擇下列其中一項來描述及強制執行哪些連絡人可以新增。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-130">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="e2a6d-131">您可以從下列選取：</span><span class="sxs-lookup"><span data-stu-id="e2a6d-131">You can select from:</span></span>
    
      - <span data-ttu-id="e2a6d-132">**Federated**同盟。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-132">**Federated**.</span></span> <span data-ttu-id="e2a6d-133">同盟 **夥伴類型** 是 Lync Server 或 Office 通訊伺服器 2007 R2 協力廠商部署之間的信任連線。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-133">A **Federated** partner type is a trusted connection between a Lync Server or Office Communications Server 2007 R2 partner deployment.</span></span>
    
      - <span data-ttu-id="e2a6d-134">**公用驗證**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-134">**Public verified**.</span></span> <span data-ttu-id="e2a6d-135">**公用驗證**夥伴是指可將提供者所驗證之部署之一部分的連絡人新增至使用者的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-135">A **Public verified** partner is when contacts that are part of a deployment that are verified by the provider can be added to your user’s list of contacts.</span></span> <span data-ttu-id="e2a6d-136">可以從 Lync 使用者傳送邀請，或 Lync 使用者可以接受來自合作夥伴連絡人的邀請。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-136">Invites can be sent from the Lync user or the Lync user can accept invites from the partner contact.</span></span>
    
      - <span data-ttu-id="e2a6d-137">**公用未驗證**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-137">**Public unverified**.</span></span> <span data-ttu-id="e2a6d-138">公開的未 **驗證** 關聯性表示兩個部署之間沒有建立且可驗證的狀態。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-138">A **Public unverified** relationship implies that there is no established and verifiable status between the two deployments.</span></span> <span data-ttu-id="e2a6d-139">Lync 使用者必須邀請該連絡人的未驗證連絡人，才能將 Lync 使用者新增至其連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-139">A Lync user must invite the unverified contact for that contact to be able to add the Lync user to his contact list.</span></span> <span data-ttu-id="e2a6d-140">例如，Google GTalk 不是與 Lync Server 相關的公開驗證 XMPP 服務。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-140">For example, Google GTalk is not a public verified XMPP service as it relates to Lync Server.</span></span> <span data-ttu-id="e2a6d-141">除非有從 Lync 使用者傳送的明確邀請，否則 GTalk 使用者將無法將 Lync 使用者新增為連絡人。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-141">A GTalk user will not be able to add the Lync user as a contact unless there is an explicit invite sent from the Lync user.</span></span>

11. <span data-ttu-id="e2a6d-142">關於資料流交涉與安全性方法傳輸層安全性 (TLS) 和軟體驗證及安全性階層 (SASL) 的附註：</span><span class="sxs-lookup"><span data-stu-id="e2a6d-142">Notes on stream negotiation and the security methods Transport Layer Security (TLS) and Software Authentication and Security Layer (SASL):</span></span>
    
    <span data-ttu-id="e2a6d-p110">**XMPP Standards Foundation** (XSF) 和**網際網路工程任務推動小組** (IETF) 會定義一組使用與管理 TLS 用戶端憑證、TLS 伺服器憑證及 SASL 機制的規則與標準。使用 TLS 和 SASL 是保護 XMPP 資料流安全的必要程序。從 XMPP Standards 文件 **XEP-0178**，「指定建議使用的通訊協定流程，將 SASL EXTERNAL 機制與 PKIX 憑證搭配使用，特別是在 XMPP 服務指出 TLS 為強制交涉時。」PKIX (如 XSF 文件中所述) 是指公用金鑰基礎結構，亦稱為 PKI。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-p110">The **XMPP Standards Foundation** (XSF) and the **Internet Engineering Task Force** (IETF) define a set of rules and standards for using and managing TLS client certificates, TLS server certificates, and the SASL mechanism. Using TLS and SASL is the required process for securing the XMPP stream. From the XMPP Standards document **XEP-0178**, “specifies a recommended protocol flow for use of the SASL EXTERNAL mechanism with PKIX certificates, especially when an XMPP service indicates that TLS is mandatory-to-negotiate.” PKIX, as stated in the XSF documentation, refers to public key infrastructure, also known as PKI.</span></span>
    
    <span data-ttu-id="e2a6d-147">如需 XMPP 需求的詳細資訊，請參閱 XSF 檔 XEP-0178。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-147">Refer to the XSF document XEP-0178 for more details on the XMPP requirements.</span></span> <span data-ttu-id="e2a6d-148">如需詳細資訊，請參閱「XEP-0178：使用 SASL EXTERNAL with 憑證的最佳作法」。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-148">For details, refer to “XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates”.</span></span> <http://xmpp.org/extensions/xep-0178.html>
    
    <span data-ttu-id="e2a6d-149">請參閱 IETF 檔「可擴展郵件和顯示狀態通訊協定 (XMPP) ： Core」，5.0，STARTTLS 協商 <https://tools.ietf.org/html/rfc6120> 。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-149">Refer to the IETF document “Extensible Messaging and Presence Protocol (XMPP): Core“, Section 5.0, STARTTLS Negotiation <https://tools.ietf.org/html/rfc6120>.</span></span>
    
      - <span data-ttu-id="e2a6d-150">**TLS 協商**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-150">**TLS Negotiation**.</span></span> <span data-ttu-id="e2a6d-151">定義 TLS 協商規則。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-151">Defines the TLS negotiation rules.</span></span> <span data-ttu-id="e2a6d-152">XMPP 服務可以要求 TLS，也可以使用 tls 選用，或定義不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-152">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="e2a6d-153">選擇 [選用]，將需求留給 XMPP 服務，以強制進行必要的協商決策。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-153">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="e2a6d-154">若要查看所有可能的設定和詳細資料，以瞭解 SASL、TLS 和回撥的協商-包括沒有有效和已知的錯誤設定，請參閱 [Lync Server 2013 中的 XMPP](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)同盟協力廠商協商設定。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-154">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="e2a6d-155">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-155">**Required**.</span></span> <span data-ttu-id="e2a6d-156">XMPP 服務要求 TLS 交涉。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-156">The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="e2a6d-157">**選用**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-157">**Optional**.</span></span> <span data-ttu-id="e2a6d-158">XMPP 服務表示 TLS 為強制交涉。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-158">The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="e2a6d-159">**不支援**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-159">**Not Supported**.</span></span> <span data-ttu-id="e2a6d-160">XMPP 服務不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-160">The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="e2a6d-161">**SASL 協商**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-161">**SASL negotiation**.</span></span> <span data-ttu-id="e2a6d-162">定義 SASL 協商規則。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-162">Defines the SASL negotiation rules.</span></span> <span data-ttu-id="e2a6d-163">XMPP 服務可能需要 SASL，可以進行 SASL 選用，或者您定義的是不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-163">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="e2a6d-164">選擇 [選用]，將需求留給夥伴 XMPP 服務，以進行強制協商決策。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-164">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="e2a6d-p117">SASL 要求 TLS。若要使用 SASL，TLS 必須是必要項目或選用項目。任何將 SASL 定義為必要或選用的設定都必須受到 TLS 支援。按一下 <STRONG>[認可]</STRONG> 以儲存您的變更時，如果您尚未將 TLS 設定為必要或選用，系統將會警告您，SASL 必須受到 TLS 支援，而您的變更將不會儲存。若要解決此錯誤，請將 TLS 設定為 <STRONG>[必要]</STRONG> 或 <STRONG>[選用]</STRONG>。如果 SASL 的用法為選用且無法支援 TLS 交涉，則您必須將 SASL 交涉設定為 <STRONG>[不支援]</STRONG>。利用 XMPP 服務來確認適用於 TLS 和 SASL 的正確交涉資料流必須是何種類型，或者將會發生服務中斷。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-p117">SASL requires TLS. To use SASL, TLS must either be required or optional. Any configuration that defines SASL as either required or optional must have TLS support. When clicking <STRONG>Commit</STRONG> to save your changes, if you have not set TLS to required or optional, you will be warned that SASL must have TLS support and your changes are not saved. To resolve the error, set TLS to <STRONG>Required</STRONG> or <STRONG>Optional</STRONG>. If use of SASL is optional and TLS negotiation support is not possible, you must set SASL negotiation to <STRONG>Not Supported</STRONG>. Confirm with the XMPP service what the proper negotiation streams must be for TLS and SASL or service interruption will occur.</span></span>

        
        </div>
        
          - <span></span>  
            <span data-ttu-id="e2a6d-172">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-172">**Required**.</span></span> <span data-ttu-id="e2a6d-173">XMPP 服務要求 SASL 交涉。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-173">The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="e2a6d-174">**選用**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-174">**Optional**.</span></span> <span data-ttu-id="e2a6d-175">XMPP 服務表示 SASL 為強制交涉。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-175">The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="e2a6d-176">**不支援**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-176">**Not Supported**.</span></span> <span data-ttu-id="e2a6d-177">XMPP 服務不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-177">The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="e2a6d-178">**回撥協商**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-178">**Dialback negotiation**.</span></span> <span data-ttu-id="e2a6d-179">回撥協商是由檔 XEP 中的 XSF 所定義 **-220：伺服器回撥** <http://xmpp.org/extensions/xep-0220.html> 。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-179">Dialback negotiation is defined by the XSF in document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>.</span></span> <span data-ttu-id="e2a6d-180">伺服器回撥程式會使用網域名稱系統 (DNS) 和授權伺服器以驗證要求來自有效的 XMPP 合作者。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-180">The server dialback process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="e2a6d-181">為做到這一點，始發伺服器會使用產生的回撥機碼來建立特定類型的郵件，並在 DNS 中查閱接收伺服器。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-181">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="e2a6d-182">原始伺服器會將 XML 資料流程中的金鑰傳送到所產生的 DNS 查詢（大概是接收伺服器）。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-182">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="e2a6d-183">當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-183">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="e2a6d-184">授權伺服器會驗證機碼是否有效或無效。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-184">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="e2a6d-185">如果無效，則接收伺服器不會回應始發伺服器。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-185">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="e2a6d-186">若機碼是有效的，則接收伺服器會通知始發伺服器身分識別和金鑰是有效的，交談可以開始。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-186">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="e2a6d-187">**回撥交涉**具備兩種有效狀態：</span><span class="sxs-lookup"><span data-stu-id="e2a6d-187">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="e2a6d-188">**True**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-188">**True**.</span></span> <span data-ttu-id="e2a6d-189">如果應該從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥協商。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-189">The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server</span></span>
        
          - <span></span>  
            <span data-ttu-id="e2a6d-190">**False**。</span><span class="sxs-lookup"><span data-stu-id="e2a6d-190">**False**.</span></span> <span data-ttu-id="e2a6d-191">XMPP 伺服器並未設定為使用回撥交涉，而且，如果必須接收來自原始伺服器的要求，將會忽略此項</span><span class="sxs-lookup"><span data-stu-id="e2a6d-191">The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

