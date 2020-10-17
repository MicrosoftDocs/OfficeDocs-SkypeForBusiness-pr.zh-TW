---
title: 在 Lync Server 2013 上設定 XMPP 閘道
description: 在 Lync Server 2013 上設定 XMPP 閘道。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78765237e737dea29d77230d6b0eecdb0348cb41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542949"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="0f8af-103">在 Lync Server 2013 上設定 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="0f8af-103">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f8af-104">_**主題上次修改日期：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="0f8af-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="0f8af-105">遷移 XMPP 閘道的最後步驟是設定 Lync Server 2013 Edge Server 的憑證，部署 Lync Server 2013 XMPP 閘道，並更新 XMPP 閘道的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="0f8af-105">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="0f8af-106">您應平行執行這些步驟，以將 XMPP 閘道的停機時間降至最低。</span><span class="sxs-lookup"><span data-stu-id="0f8af-106">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="0f8af-107">在執行這些步驟之前，必須先將所有使用者移至您的 Microsoft Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="0f8af-107">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="0f8af-108">在 survivable branch 裝置上的使用者不支援 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="0f8af-108">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="0f8af-109">這適用于查看顯示狀態資訊和交換 IM 郵件。</span><span class="sxs-lookup"><span data-stu-id="0f8af-109">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="0f8af-110">在 Lync Server 2013 Edge Server 上設定 XMPP 閘道憑證</span><span class="sxs-lookup"><span data-stu-id="0f8af-110">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="0f8af-111">在 Edge Server 的 [部署精靈] 中，按一下 [步驟 3: 要求、安裝或指派憑證]\*\*\*\* 旁邊的 [再執行一次]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f8af-111">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="0f8af-112">如果是第一次部署 Edge Server，則會看到 [執行]，而不是 [再執行一次]。</span><span class="sxs-lookup"><span data-stu-id="0f8af-112">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="0f8af-113">在 **[可用憑證工作]** 頁面上，按一下 **[建立新憑證要求]**。</span><span class="sxs-lookup"><span data-stu-id="0f8af-113">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="0f8af-114">在 **[憑證要求]** 頁面上，按一下 **[外部邊緣憑證]**。</span><span class="sxs-lookup"><span data-stu-id="0f8af-114">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="0f8af-115">在 **[延遲或立即要求]** 頁面上，選取 **[立即準備此要求，但稍後再傳送]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0f8af-115">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="0f8af-116">在 [ **憑證要求** 檔案] 頁面上，輸入要儲存要求的檔案完整路徑和檔案名 (例如，c： \\ cert \_ 外部 \_ edge) 。</span><span class="sxs-lookup"><span data-stu-id="0f8af-116">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="0f8af-117">若要使用預設 WebServer 範本之外的其他範本，請在 **[指定其他憑證範本]** 頁面上，選取 **[將其他憑證範本用於所選的憑證授權單位]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0f8af-117">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="0f8af-118">在 **[名稱和安全性設定]** 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0f8af-118">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="0f8af-119">在 [易記名稱]\*\*\*\* 中，輸入憑證的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="0f8af-119">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="0f8af-120">在 [位元長度]\*\*\*\* 中，指定位元長度 (預設值通常是 2048)。</span><span class="sxs-lookup"><span data-stu-id="0f8af-120">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="0f8af-121">確認 [將憑證私密金鑰標示為可匯出]\*\*\*\* 核取方塊已經選取。</span><span class="sxs-lookup"><span data-stu-id="0f8af-121">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="0f8af-122">在 **[組織資訊]** 頁面上，輸入組織的名稱和組織單位 (例如部門)。</span><span class="sxs-lookup"><span data-stu-id="0f8af-122">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="0f8af-123">在 **[地理資訊]** 頁面上，指定位置資訊。</span><span class="sxs-lookup"><span data-stu-id="0f8af-123">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="0f8af-p103">在 **[主體名稱/主體別名]** 頁面上，會顯示精靈將自動填入的資訊。如果您還需要其他主體別名，請在後續兩個步驟中指定。</span><span class="sxs-lookup"><span data-stu-id="0f8af-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="0f8af-126">在 [ \*\*主體別名 (SANs) \*\* ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0f8af-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="0f8af-127">專案的主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="0f8af-127">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="0f8af-128">在 **[設定其他主體替代名稱]** 頁面上，指定任何需要的其他主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="0f8af-128">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="0f8af-p105">如果已安裝 XMPP Proxy，則 SAN 項目中預設會填入網域名稱 (例如 contoso.com) 。如果您需要更多項目，請在此步驟中新增它們。</span><span class="sxs-lookup"><span data-stu-id="0f8af-p105">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="0f8af-131">在 **[要求摘要]** 頁面上，檢閱要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="0f8af-131">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="0f8af-132">命令執行完畢後，您可以 **查看記錄**檔，或按 [下一步] 繼續。</span><span class="sxs-lookup"><span data-stu-id="0f8af-132">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="0f8af-133">在 **[憑證要求檔案]** 頁面上，您可以按一下 **[檢視]** 來檢視所產生的憑證簽署要求 (CSR) 檔案，或者按一下 **[完成]** 以結束 [憑證精靈]。</span><span class="sxs-lookup"><span data-stu-id="0f8af-133">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="0f8af-134">複製要求檔案並提交公用憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="0f8af-134">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="0f8af-p106">接收、匯入並指派公用憑證之後，您必須停止並重新啟動 Edge Server 服務。作法是輸入 Lync Server 管理主控台：</span><span class="sxs-lookup"><span data-stu-id="0f8af-p106">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="0f8af-137">設定新的 Lync Server 2013 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="0f8af-137">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="0f8af-138">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="0f8af-138">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="0f8af-139">在左導覽列中，按一下 [同盟和外部存取]\*\*\*\*，然後按一下 [XMPP 同盟協力廠商]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f8af-139">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="0f8af-140">若要建立新組態，請按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f8af-140">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="0f8af-141">定義下列設定：</span><span class="sxs-lookup"><span data-stu-id="0f8af-141">Define the following settings:</span></span>

5.  <span data-ttu-id="0f8af-142">**主要網域**     (必要) 。</span><span class="sxs-lookup"><span data-stu-id="0f8af-142">**Primary domain**    (Required).</span></span> <span data-ttu-id="0f8af-143">主要網域為 XMPP 協力廠商的基本網域。</span><span class="sxs-lookup"><span data-stu-id="0f8af-143">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="0f8af-144">例如，您可以為 XMPP 協力廠商網域名稱輸入 **fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="0f8af-144">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="0f8af-145">此為必要項目。</span><span class="sxs-lookup"><span data-stu-id="0f8af-145">This is a required entry.</span></span>

6.  <span data-ttu-id="0f8af-146">**描述**    描述是針對此特定設定的附注或其他識別資訊。</span><span class="sxs-lookup"><span data-stu-id="0f8af-146">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="0f8af-147">此專案是選用專案。</span><span class="sxs-lookup"><span data-stu-id="0f8af-147">This entry is optional.</span></span>

7.  <span data-ttu-id="0f8af-148">**其他網域**    其他網域是 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。</span><span class="sxs-lookup"><span data-stu-id="0f8af-148">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="0f8af-149">例如，如果主域是 **fabrikam.com**，則您會列出位於 fabrikam.com 的所有其他網域，您會透過 XMPP 的方式來進行通訊。</span><span class="sxs-lookup"><span data-stu-id="0f8af-149">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="0f8af-150">**合作夥伴類型**    **同伴類型**是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="0f8af-150">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="0f8af-151">您必須選擇下列其中一項來描述及強制執行哪些連絡人可以新增。</span><span class="sxs-lookup"><span data-stu-id="0f8af-151">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="0f8af-152">您可以從下列選取：</span><span class="sxs-lookup"><span data-stu-id="0f8af-152">You can select from:</span></span>
    
      - <span data-ttu-id="0f8af-153">**Federated**同盟    同盟**夥伴類型**代表 Lync Server 部署與 XMPP 合作夥伴之間的高信任層級。</span><span class="sxs-lookup"><span data-stu-id="0f8af-153">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="0f8af-154">建議使用此夥伴類型，以與相同企業內的 XMPP 伺服器同盟，或已建立的業務關係。</span><span class="sxs-lookup"><span data-stu-id="0f8af-154">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="0f8af-155">同盟合作夥伴中的 XMPP 連絡人可以：</span><span class="sxs-lookup"><span data-stu-id="0f8af-155">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="0f8af-156">新增 Lync 連絡人並檢視其目前狀態，而不需要 Lync 使用者的明確授權。</span><span class="sxs-lookup"><span data-stu-id="0f8af-156">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="0f8af-157">不論 Lync 使用者是否將 Lync 連絡人新增至其連絡人清單，都可將立即訊息傳送給 Lync 連絡人。</span><span class="sxs-lookup"><span data-stu-id="0f8af-157">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="0f8af-158">查看 Lync 使用者的狀態記事。</span><span class="sxs-lookup"><span data-stu-id="0f8af-158">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="0f8af-159">**公用驗證**    **公用驗證**夥伴是一種公開的 XMPP 提供者，可供信任以驗證使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="0f8af-159">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="0f8af-160">XMPP 公用驗證網路中的連絡人可以新增 Lync 連絡人並查看其目前狀態，並傳送立即訊息給他們，但不需要 Lync 使用者的明確授權。</span><span class="sxs-lookup"><span data-stu-id="0f8af-160">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="0f8af-161">XMPP 公用驗證網路中的連絡人永遠不會看到 Lync 使用者的狀態筆記。</span><span class="sxs-lookup"><span data-stu-id="0f8af-161">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="0f8af-162">建議您不要使用此設定。</span><span class="sxs-lookup"><span data-stu-id="0f8af-162">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="0f8af-163">**公用未驗證**    **公用未驗證**夥伴是不受信任的公用 XMPP 提供者，以驗證其使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="0f8af-163">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="0f8af-164">XMPP 未驗證之網路上的使用者無法與 Lync 使用者通訊，除非 Lync 使用者已將其新增至連絡人清單以明確授權。</span><span class="sxs-lookup"><span data-stu-id="0f8af-164">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="0f8af-165">XMPP 公用未驗證網路上的使用者，永遠不會看到 Lync 使用者的狀態筆記。</span><span class="sxs-lookup"><span data-stu-id="0f8af-165">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="0f8af-166">對於任何使用 public XMPP 提供者（如 Google 談話）的同盟，建議使用此設定。</span><span class="sxs-lookup"><span data-stu-id="0f8af-166">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="0f8af-167">**連線類型**：定義各種規則及回撥設定。</span><span class="sxs-lookup"><span data-stu-id="0f8af-167">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="0f8af-168">**TLS 協商**    定義 TLS 協商規則。</span><span class="sxs-lookup"><span data-stu-id="0f8af-168">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="0f8af-169">XMPP 服務可以要求 TLS，也可以使用 tls 選用，或定義不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="0f8af-169">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="0f8af-170">選擇 [選用]，將需求留給 XMPP 服務，以強制進行必要的協商決策。</span><span class="sxs-lookup"><span data-stu-id="0f8af-170">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="0f8af-171">若要查看所有可能的設定和詳細資料，以瞭解 SASL、TLS 和回撥的協商-包括沒有有效和已知的錯誤設定，請參閱 [Lync Server 2013 中的 XMPP](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)同盟協力廠商協商設定。</span><span class="sxs-lookup"><span data-stu-id="0f8af-171">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="0f8af-172">**必要**    XMPP 服務需要 TLS 協商。</span><span class="sxs-lookup"><span data-stu-id="0f8af-172">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0f8af-173">**選用**    XMPP 服務表示 TLS 必須協商。</span><span class="sxs-lookup"><span data-stu-id="0f8af-173">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0f8af-174">**不支援**    XMPP 服務不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="0f8af-174">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="0f8af-175">**SASL 協商**    定義 SASL 協商規則。</span><span class="sxs-lookup"><span data-stu-id="0f8af-175">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="0f8af-176">XMPP 服務可能需要 SASL，可以進行 SASL 選用，或者您定義的是不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="0f8af-176">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="0f8af-177">選擇 [選用]，將需求留給夥伴 XMPP 服務，以進行強制協商決策。</span><span class="sxs-lookup"><span data-stu-id="0f8af-177">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0f8af-178">**必要**    XMPP 服務需要 SASL 協商。</span><span class="sxs-lookup"><span data-stu-id="0f8af-178">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0f8af-179">**選用**    XMPP 服務指出必須對 SASL 進行協商。</span><span class="sxs-lookup"><span data-stu-id="0f8af-179">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0f8af-180">**不支援**    XMPP 服務不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="0f8af-180">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="0f8af-181">**支援伺服器的回撥協商** 支援伺服器回撥協商程式會使用網域名稱系統 (DNS) 和授權伺服器以驗證要求來自有效的 XMPP 合作者。</span><span class="sxs-lookup"><span data-stu-id="0f8af-181">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="0f8af-182">為做到這一點，始發伺服器會使用產生的回撥機碼來建立特定類型的郵件，並在 DNS 中查閱接收伺服器。</span><span class="sxs-lookup"><span data-stu-id="0f8af-182">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="0f8af-183">原始伺服器會將 XML 資料流程中的金鑰傳送到所產生的 DNS 查詢（大概是接收伺服器）。</span><span class="sxs-lookup"><span data-stu-id="0f8af-183">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="0f8af-184">當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="0f8af-184">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="0f8af-185">授權伺服器會驗證機碼是否有效或無效。</span><span class="sxs-lookup"><span data-stu-id="0f8af-185">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="0f8af-186">如果無效，則接收伺服器不會回應始發伺服器。</span><span class="sxs-lookup"><span data-stu-id="0f8af-186">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="0f8af-187">若機碼是有效的，則接收伺服器會通知始發伺服器身分識別和金鑰是有效的，交談可以開始。</span><span class="sxs-lookup"><span data-stu-id="0f8af-187">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="0f8af-188">**回撥交涉**具備兩種有效狀態：</span><span class="sxs-lookup"><span data-stu-id="0f8af-188">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="0f8af-189">**True**    如果應該從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥協商。</span><span class="sxs-lookup"><span data-stu-id="0f8af-189">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="0f8af-190">**False**    XMPP server 並未設定為使用回撥協商，而且若應該從始發伺服器接收要求，則會被忽略。</span><span class="sxs-lookup"><span data-stu-id="0f8af-190">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="0f8af-191">按一下 [認可]\*\*\*\* 以儲存對網站或使用者原則的變更。</span><span class="sxs-lookup"><span data-stu-id="0f8af-191">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="0f8af-192">更新 Lync Server 2013 XMPP 閘道的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="0f8af-192">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="0f8af-193">若要設定 DNS 以進行 XMPP 同盟，您可以將下列 SRV 記錄新增至您的外部 DNS： \_ XMPP-server。 \_Tcp。\<domain name\></span><span class="sxs-lookup"><span data-stu-id="0f8af-193">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="0f8af-194">SRV 記錄會解析為 Edge server 的 Access Edge FQDN，埠值為5269。</span><span class="sxs-lookup"><span data-stu-id="0f8af-194">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

