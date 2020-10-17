---
title: 在 Lync Server 2013 上設定 XMPP 閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a2893d05230edbd261f7115a9be92bcd3275723
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503170"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="e0501-102">在 Lync Server 2013 上設定 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="e0501-102">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0501-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e0501-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e0501-104">當您設定支援可延伸訊息和目前狀態通訊協定 (XMPP) 同盟協力廠商的原則時，這些原則會套用至 XMPP 同盟網域的使用者，但不會套用至工作階段初始通訊協定 (SIP) 立即訊息 (IM) 服務提供者 (例如 Windows Live) 或 SIP 同盟網域的使用者。</span><span class="sxs-lookup"><span data-stu-id="e0501-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="e0501-105">您可以為每個 XMPP 同盟網域設定所需的 XMPP 同盟協力廠商，以讓使用者新增連絡人並與連絡人通訊。</span><span class="sxs-lookup"><span data-stu-id="e0501-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="e0501-106">當原則就緒後，其他工作會包括設定 XMPP 閘道憑證、部署 Lync Server 2013 XMPP 閘道，最後更新 XMPP 閘道的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="e0501-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="e0501-107">在 Lync Server 2013 Edge Server 上設定 XMPP 閘道憑證</span><span class="sxs-lookup"><span data-stu-id="e0501-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="e0501-108">在 Edge Server 的 [部署精靈] 中，按一下 [步驟 3: 要求、安裝或指派憑證]\*\*\*\* 旁邊的 [再執行一次]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0501-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e0501-109">如果是第一次部署 Edge Server，則會看到 [執行]，而不是 [再執行一次]。</span><span class="sxs-lookup"><span data-stu-id="e0501-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="e0501-110">在 **[可用憑證工作]** 頁面上，按一下 **[建立新憑證要求]**。</span><span class="sxs-lookup"><span data-stu-id="e0501-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="e0501-111">在 **[憑證要求]** 頁面上，按一下 **[外部邊緣憑證]**。</span><span class="sxs-lookup"><span data-stu-id="e0501-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="e0501-112">在 **[延遲或立即要求]** 頁面上，選取 **[立即準備此要求，但稍後再傳送]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e0501-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="e0501-113">在 [ **憑證要求** 檔案] 頁面上，輸入要儲存要求的檔案完整路徑和檔案名 (例如，c： \\ cert \_ 外部 \_ edge) 。</span><span class="sxs-lookup"><span data-stu-id="e0501-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="e0501-114">若要使用預設 WebServer 範本之外的其他範本，請在 **[指定其他憑證範本]** 頁面上，選取 **[將其他憑證範本用於所選的憑證授權單位]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e0501-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="e0501-115">在 **[名稱和安全性設定]** 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e0501-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="e0501-116">在 [易記名稱]\*\*\*\* 中，輸入憑證的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="e0501-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="e0501-117">在 [位元長度]\*\*\*\* 中，指定位元長度 (預設值通常是 2048)。</span><span class="sxs-lookup"><span data-stu-id="e0501-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="e0501-118">確認 [將憑證私密金鑰標示為可匯出]\*\*\*\* 核取方塊已經選取。</span><span class="sxs-lookup"><span data-stu-id="e0501-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="e0501-119">在 **[組織資訊]** 頁面上，輸入組織的名稱和組織單位 (例如部門)。</span><span class="sxs-lookup"><span data-stu-id="e0501-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="e0501-120">在 **[地理資訊]** 頁面上，指定位置資訊。</span><span class="sxs-lookup"><span data-stu-id="e0501-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="e0501-p102">在 **[主體名稱/主體別名]** 頁面上，會顯示精靈將自動填入的資訊。如果您還需要其他主體別名，請在後續兩個步驟中指定。</span><span class="sxs-lookup"><span data-stu-id="e0501-p102">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="e0501-123">在 [ \*\*主體別名 (SANs) \*\* ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="e0501-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="e0501-124">專案的主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="e0501-124">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="e0501-125">在 **[設定其他主體替代名稱]** 頁面上，指定任何需要的其他主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="e0501-125">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e0501-p104">如果已安裝 XMPP Proxy，則 SAN 項目中預設會填入網域名稱 (例如 contoso.com) 。如果您需要更多項目，請在此步驟中新增它們。</span><span class="sxs-lookup"><span data-stu-id="e0501-p104">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="e0501-128">在 **[要求摘要]** 頁面上，檢閱要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="e0501-128">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="e0501-129">當命令執行完畢之後，您可以 [檢視記錄檔]\*\*\*\*，或按 [下一步]\*\*\*\* 繼續。</span><span class="sxs-lookup"><span data-stu-id="e0501-129">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="e0501-130">在「憑證要求檔案」\*\*\*\* 頁面上，您可以按一下 [檢視] 檢視產生的憑證簽署要求 (CSR) 檔案，或按一下 [完成]\*\*\*\* 結束 [憑證精靈]。</span><span class="sxs-lookup"><span data-stu-id="e0501-130">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="e0501-131">複製要求檔案，並送出到您的公用憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="e0501-131">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="e0501-p105">接收、匯入並指派公用憑證之後，您必須停止並重新啟動 Edge Server 服務。作法是輸入 Lync Server 管理主控台：</span><span class="sxs-lookup"><span data-stu-id="e0501-p105">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="e0501-134">設定新的 Lync Server 2013 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="e0501-134">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="e0501-135">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="e0501-135">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="e0501-136">在左導覽列中，按一下 [同盟和外部存取]\*\*\*\*，然後按一下 [XMPP 同盟協力廠商]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0501-136">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="e0501-137">若要建立新組態，請按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0501-137">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="e0501-138">定義下列設定：</span><span class="sxs-lookup"><span data-stu-id="e0501-138">Define the following settings:</span></span>

5.  <span data-ttu-id="e0501-139">**主要網域**     (必要) 。</span><span class="sxs-lookup"><span data-stu-id="e0501-139">**Primary domain**    (Required).</span></span> <span data-ttu-id="e0501-140">主要網域為 XMPP 協力廠商的基本網域。</span><span class="sxs-lookup"><span data-stu-id="e0501-140">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="e0501-141">例如，您可以為 XMPP 協力廠商網域名稱輸入 **fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="e0501-141">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="e0501-142">此為必要項目。</span><span class="sxs-lookup"><span data-stu-id="e0501-142">This is a required entry.</span></span>

6.  <span data-ttu-id="e0501-143">**描述**    描述是針對此特定設定的附注或其他識別資訊。</span><span class="sxs-lookup"><span data-stu-id="e0501-143">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="e0501-144">此專案是選用專案。</span><span class="sxs-lookup"><span data-stu-id="e0501-144">This entry is optional.</span></span>

7.  <span data-ttu-id="e0501-145">**其他網域**    其他網域是 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。</span><span class="sxs-lookup"><span data-stu-id="e0501-145">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="e0501-146">例如，如果主域是 **fabrikam.com**，則您會列出位於 fabrikam.com 的所有其他網域，您會透過 XMPP 的方式來進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e0501-146">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="e0501-147">**合作夥伴類型**    **同伴類型**是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="e0501-147">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="e0501-148">您必須選擇下列其中一項來描述及強制執行哪些連絡人可以新增。</span><span class="sxs-lookup"><span data-stu-id="e0501-148">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="e0501-149">您可以從下列選取：</span><span class="sxs-lookup"><span data-stu-id="e0501-149">You can select from:</span></span>
    
      - <span data-ttu-id="e0501-150">**Federated**同盟同盟**夥伴類型**代表 Lync Server 部署與 XMPP 合作夥伴之間的高信任層級。</span><span class="sxs-lookup"><span data-stu-id="e0501-150">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="e0501-151">建議使用此夥伴類型，以與相同企業內的 XMPP 伺服器同盟，或已建立的業務關係。</span><span class="sxs-lookup"><span data-stu-id="e0501-151">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="e0501-152">同盟合作夥伴中的 XMPP 連絡人可以：</span><span class="sxs-lookup"><span data-stu-id="e0501-152">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="e0501-153">新增 Lync 連絡人並檢視其目前狀態，而不需要 Lync 使用者的明確授權。</span><span class="sxs-lookup"><span data-stu-id="e0501-153">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="e0501-154">不論 Lync 使用者是否將 Lync 連絡人新增至其連絡人清單，都可將立即訊息傳送給 Lync 連絡人。</span><span class="sxs-lookup"><span data-stu-id="e0501-154">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="e0501-155">查看 Lync 使用者的狀態記事。</span><span class="sxs-lookup"><span data-stu-id="e0501-155">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="e0501-156">**公用驗證**  **公用驗證**夥伴是一種公開的 XMPP 提供者，可供信任以驗證使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="e0501-156">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="e0501-157">XMPP 公用驗證網路中的連絡人可以新增 Lync 連絡人並查看其目前狀態，並傳送立即訊息給他們，但不需要 Lync 使用者的明確授權。</span><span class="sxs-lookup"><span data-stu-id="e0501-157">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="e0501-158">XMPP 公用驗證網路中的連絡人永遠不會看到 Lync 使用者的狀態筆記。</span><span class="sxs-lookup"><span data-stu-id="e0501-158">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="e0501-159">建議您不要使用此設定。</span><span class="sxs-lookup"><span data-stu-id="e0501-159">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="e0501-p112">**未公開驗證**：[未公開驗證]\*\*\*\* 協力廠商是無法確定其使用者身分識別之不受信任的公用 XMPP 提供者。除非 Lync 使用者將 [未公開驗證] 網路上的 XMPP 使用者新增至連絡人清單，以明確授權 XMPP 使用者，否則 [未公開驗證] 網路上的 XMPP 使用者無法與 Lync 使用者通訊。 [未公開驗證] 網路上的 XMPP 連絡人無法查看 Lync 使用者的狀態記事。若要與 Google Talk 等公用 XMPP 提供者進行任何同盟，建議使用此設定。</span><span class="sxs-lookup"><span data-stu-id="e0501-p112">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.  XMPP users on public unverified networks never see Lync users’ status notes.  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="e0501-164">**連線類型**：定義各種規則及回撥設定。</span><span class="sxs-lookup"><span data-stu-id="e0501-164">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="e0501-165">**TLS 協商**    定義 TLS 協商規則。</span><span class="sxs-lookup"><span data-stu-id="e0501-165">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="e0501-166">XMPP 服務可以要求 TLS，也可以使用 tls 選用，或定義不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="e0501-166">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="e0501-167">選擇 [選用]，將需求留給 XMPP 服務，以強制進行必要的協商決策。</span><span class="sxs-lookup"><span data-stu-id="e0501-167">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="e0501-168">若要查看所有可能的設定和詳細資料以進行 SASL、TLS 和回撥，請參閱[Lync Server 2013 中的 XMPP](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)同盟協力廠商協商設定。</span><span class="sxs-lookup"><span data-stu-id="e0501-168">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="e0501-169">**必要**    XMPP 服務需要 TLS 協商。</span><span class="sxs-lookup"><span data-stu-id="e0501-169">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="e0501-170">**選用**    XMPP 服務表示 TLS 必須協商。</span><span class="sxs-lookup"><span data-stu-id="e0501-170">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="e0501-171">**不支援**    XMPP 服務不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="e0501-171">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="e0501-172">**SASL 協商**    定義 SASL 協商規則。</span><span class="sxs-lookup"><span data-stu-id="e0501-172">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="e0501-173">XMPP 服務可能需要 SASL，可以進行 SASL 選用，或者您定義的是不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="e0501-173">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="e0501-174">選擇 [選用]，將需求留給夥伴 XMPP 服務，以進行強制協商決策。</span><span class="sxs-lookup"><span data-stu-id="e0501-174">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="e0501-175">**必要**    XMPP 服務需要 SASL 協商。</span><span class="sxs-lookup"><span data-stu-id="e0501-175">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="e0501-176">**選用**    XMPP 服務指出必須對 SASL 進行協商。</span><span class="sxs-lookup"><span data-stu-id="e0501-176">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="e0501-177">**不支援**    XMPP 服務不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="e0501-177">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="e0501-178">**支援伺服器的回撥協商** 支援伺服器回撥協商程式會使用網域名稱系統 (DNS) 和授權伺服器以驗證要求來自有效的 XMPP 合作者。</span><span class="sxs-lookup"><span data-stu-id="e0501-178">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="e0501-179">為做到這一點，始發伺服器會使用產生的回撥機碼來建立特定類型的郵件，並在 DNS 中查閱接收伺服器。</span><span class="sxs-lookup"><span data-stu-id="e0501-179">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="e0501-180">原始伺服器會將 XML 資料流程中的金鑰傳送到所產生的 DNS 查詢（大概是接收伺服器）。</span><span class="sxs-lookup"><span data-stu-id="e0501-180">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="e0501-181">當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="e0501-181">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="e0501-182">授權伺服器會驗證機碼是否有效或無效。</span><span class="sxs-lookup"><span data-stu-id="e0501-182">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="e0501-183">如果無效，則接收伺服器不會回應始發伺服器。</span><span class="sxs-lookup"><span data-stu-id="e0501-183">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="e0501-184">若機碼是有效的，則接收伺服器會通知始發伺服器身分識別和金鑰是有效的，交談可以開始。</span><span class="sxs-lookup"><span data-stu-id="e0501-184">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="e0501-185">**回撥交涉**具備兩種有效狀態：</span><span class="sxs-lookup"><span data-stu-id="e0501-185">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="e0501-186">**True**    如果應該從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥協商。</span><span class="sxs-lookup"><span data-stu-id="e0501-186">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="e0501-187">**False**    XMPP server 並未設定為使用回撥協商，而且若應該從始發伺服器接收要求，則會被忽略。</span><span class="sxs-lookup"><span data-stu-id="e0501-187">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="e0501-188">按一下 [認可]\*\*\*\* 以儲存對網站或使用者原則的變更。</span><span class="sxs-lookup"><span data-stu-id="e0501-188">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="e0501-189">更新 Lync Server 2013 XMPP 閘道的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="e0501-189">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="e0501-190">若要設定 DNS 以進行 XMPP 同盟，您可以將下列 SRV 記錄新增至您的外部 DNS： \_ XMPP-server。 \_Tcp。\<domain name\></span><span class="sxs-lookup"><span data-stu-id="e0501-190">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="e0501-191">SRV 記錄會解析為 Edge server 的 Access Edge FQDN，埠值為5269。</span><span class="sxs-lookup"><span data-stu-id="e0501-191">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

