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
ms.openlocfilehash: 82c7cec94a65a35f4f5141950c4691fec0b28706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="d4ac2-102">在 Lync Server 2013 上設定 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="d4ac2-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4ac2-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d4ac2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d4ac2-104">當您針對可擴展訊息和目前狀態通訊協定（XMPP）同盟合作夥伴支援策略時，這些原則會套用至 XMPP 聯盟網域的使用者，但不會套用至會話初始通訊協定（SIP）立即訊息（IM）服務提供者的使用者（例如，Windows Live）或 SIP 聯盟網域。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="d4ac2-105">您可以針對每個 XMPP 聯盟網域設定 XMPP 聯盟夥伴，以允許使用者新增連絡人並與之通訊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="d4ac2-106">當原則就緒之後，其他的工作包括設定 XMPP 閘道憑證、部署 Lync Server 2013 XMPP 閘道，以及最終更新 XMPP 閘道的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="d4ac2-107">在 Lync Server 2013 Edge 伺服器上設定 XMPP 閘道憑證</span><span class="sxs-lookup"><span data-stu-id="d4ac2-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="d4ac2-108">在 Edge 伺服器的 [部署嚮導] 中，在 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**再次執行**]。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d4ac2-109">如果您是第一次部署邊緣伺服器，您會看到 [執行]，而不是再次執行。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="d4ac2-110">在 [**可用的憑證**工作] 頁面上，按一下 [**建立新的憑證要求**]。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="d4ac2-111">在 [**憑證要求**] 頁面上，按一下 [**外部邊緣憑證**]。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="d4ac2-112">在 [**延遲] 或 [立即要求**] 頁面上，選取 [**立即準備要求，但稍後傳送**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="d4ac2-113">在 [**憑證要求**檔案] 頁面上，輸入要儲存申請之檔案的完整路徑和檔案名（例如，c：\\cert\_外部\_edge）。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="d4ac2-114">若要使用預設 Web 文件範本以外的範本，請在 [**指定備用憑證範本**] 頁面上，選取 [**針對所選的憑證授權單位使用替代憑證範本**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="d4ac2-115">在 [**名稱及安全性設定**] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4ac2-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="d4ac2-116">在 [**易記名稱**] 中，輸入憑證的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="d4ac2-117">在 [**位長**] 中，指定位長（通常是預設值2048）。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="d4ac2-118">確認已選取 [將**憑證私人金鑰標示為可匯出**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="d4ac2-119">在 [**組織資訊**] 頁面上，輸入組織的名稱和組織單位（例如，部門或部門）。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="d4ac2-120">在 [**地理資訊**] 頁面上，指定位置資訊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="d4ac2-121">在 [ **Subject 名稱/主旨替換名稱**] 頁面上，會顯示要由嚮導自動填入的資訊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-121">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="d4ac2-122">如果需要額外的消費者替換名稱，請在接下來的兩個步驟中加以指定。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-122">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="d4ac2-123">在 [**受領人替代名稱（san）** ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\> [主題替換名稱] 清單中的專案。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="d4ac2-124">在 [**設定其他消費者替換名稱**] 頁面上，指定任何所需的其他消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d4ac2-125">如果已安裝 XMPP proxy，預設會在 SAN 專案中填入功能變數名稱（例如 [contoso.com]）。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-125">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="d4ac2-126">如果您需要更多專案，請在此步驟中加以新增。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-126">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="d4ac2-127">在 [**要求摘要**] 頁面上，查看要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="d4ac2-128">在命令完成執行之後，您可以**查看記錄**，或按一下 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="d4ac2-129">在 [**憑證要求**檔案] 頁面上，您可以按一下 [查看] 或 [結束證書] 嚮導來查看產生的憑證簽署要求（CSR）檔案，方法是按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="d4ac2-130">複製要求檔案並提交至您的公用憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="d4ac2-131">接收、匯入及指派公用憑證之後，您必須停止並重新啟動 Edge 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-131">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="d4ac2-132">您可以在 Lync Server 管理主控台中輸入以下專案來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="d4ac2-132">You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="d4ac2-133">設定新的 Lync Server 2013 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="d4ac2-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="d4ac2-134">開啟 [Lync Server 控制台]。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="d4ac2-135">在左側導覽列中，按一下 [**同盟及外部存取**]，然後按一下 [ **XMPP 聯盟夥伴**]。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="d4ac2-136">若要建立新的設定，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="d4ac2-137">定義下列設定：</span><span class="sxs-lookup"><span data-stu-id="d4ac2-137">Define the following settings:</span></span>

5.  <span data-ttu-id="d4ac2-138">**主要網域**    （必要）。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="d4ac2-139">[主要網域] 是 XMPP 合作夥伴的基底網域。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="d4ac2-140">例如，您可以輸入 XMPP 夥伴功能變數名稱的**fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="d4ac2-141">這是必要的專案。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-141">This is a required entry.</span></span>

6.  <span data-ttu-id="d4ac2-142">**描述**   針對此特定設定的備忘稿或其他識別資訊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="d4ac2-143">這個專案是選用的。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-143">This entry is optional.</span></span>

7.  <span data-ttu-id="d4ac2-144">**其他網域**   其他網域是您 XMPP 夥伴網域中的網域，應包含在允許的 XMPP 通訊中。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="d4ac2-145">例如，如果主要網域是**fabrikam.com**，則您會列出位於 [fabrikam.com] 下的所有其他網域，您會透過 XMPP 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="d4ac2-146">**合作夥伴類型**   「**合作夥伴類型**是必要的設定。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="d4ac2-147">您必須選擇下列其中一項，以描述並強制加入您可以新增的連絡人。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="d4ac2-148">您可以選取 [寄件者]：</span><span class="sxs-lookup"><span data-stu-id="d4ac2-148">You can select from:</span></span>
    
      - <span data-ttu-id="d4ac2-149">\*\*\*\* 同盟同盟**夥伴類型**代表 Lync Server 部署與 XMPP 合作夥伴之間的高信任等級。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="d4ac2-150">我們建議使用此合作夥伴類型，以便與同一企業內的 XMPP 伺服器進行聯盟，或有已建立的業務關係。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="d4ac2-151">XMPP 聯盟夥伴中的連絡人可以：</span><span class="sxs-lookup"><span data-stu-id="d4ac2-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="d4ac2-152">新增 Lync 連絡人並查看其目前狀態（不需要 Lync 使用者的快速授權）。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="d4ac2-153">無論 Lync 使用者是否已將立即訊息新增到連絡人清單中，都可以傳送立即訊息給 Lync 連絡人。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="d4ac2-154">查看 Lync 使用者的狀態筆記。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="d4ac2-155">**公用驗證** **公用**XMPP 提供者是信任的公用提供者，可驗證其使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="d4ac2-156">在公開驗證的網路中 XMPP 連絡人可以新增 Lync 連絡人並查看其目前狀態，並在沒有 Lync 使用者的授權的情況下，傳送立即訊息給他們。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="d4ac2-157">在公開驗證的網路中 XMPP 連絡人，不會看到 Lync 使用者的狀態筆記。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="d4ac2-158">建議不要使用此設定。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="d4ac2-159">**公用驗證**公用的未**驗證**合作夥伴是不受信任的公用 XMPP 提供者，以驗證其使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-159">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="d4ac2-160">除非 Lync 使用者已從連絡人清單中新增授權，否則，在公用未驗證的網路上 XMPP 使用者無法與 Lync 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-160">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="d4ac2-161">XMPP 公用未驗證網路上的使用者永遠不會看到 Lync 使用者的狀態筆記。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-161">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="d4ac2-162">對於任何具有公用 XMPP 提供者的同盟（例如 Google 通話），建議使用此設定。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-162">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="d4ac2-163">**連線類型：** 定義各種規則與回撥設定。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="d4ac2-164">**Tls 協商**   會定義 TLS 協商規則。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="d4ac2-165">XMPP 服務可能需要 TLS，可以進行 TLS 選用，或定義不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="d4ac2-166">選擇 [選用] 可將需求留給 XMPP 服務，以進行強制性的協商決策。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="d4ac2-167">若要查看所有可能的設定和詳細資料，以瞭解 SASL、TLS 及回撥，包括不合法和已知的錯誤配置-請參閱[Lync Server 2013 中 XMPP 聯盟夥伴的協商設定。](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="d4ac2-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="d4ac2-168">**必要**   ： XMPP 服務需要 TLS 協商。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="d4ac2-169">**選擇性**   ： XMPP 服務指出 TLS 是必須協商的。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="d4ac2-170">**不支援**   XMPP 服務不支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="d4ac2-171">**Sasl 協商**   會定義 SASL 協商規則。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="d4ac2-172">XMPP 服務可能需要 SASL、可進行 SASL 選擇，或定義不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="d4ac2-173">選擇 [選用] 可將需求留給合作夥伴 XMPP 服務，以進行強制性的協商決策。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="d4ac2-174">**必要需要**   SASL 協商的 XMPP 服務。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="d4ac2-175">**選擇性**   ： XMPP 服務指出 SASL 是必須協商的。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="d4ac2-176">**不支援**   XMPP 服務不支援 SASL。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="d4ac2-177">**支援伺服器回撥回協商**支援伺服器回撥的協商程式會使用網域名稱系統（DNS）和權威性伺服器來驗證要求來自有效的 XMPP 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="d4ac2-178">若要這樣做，始發伺服器會使用產生的回撥金鑰來建立特定類型的郵件，並在 DNS 中尋找接收伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="d4ac2-179">始發伺服器會將 XML 資料流程中的金鑰傳送到產生的 DNS 查詢（大概是接收伺服器）。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="d4ac2-180">當您在 XML 資料流程上收到金鑰時，接收伺服器不會回應始發伺服器，但會將金鑰傳送至已知的授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="d4ac2-181">權威性伺服器驗證金鑰是否有效或無效。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="d4ac2-182">如果無效，接收伺服器就不會回應始發伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="d4ac2-183">如果金鑰有效，接收伺服器會通知始發伺服器：身分識別和金鑰有效，且可以開始交談。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="d4ac2-184">對於**回撥協商**，有兩種有效的狀態：</span><span class="sxs-lookup"><span data-stu-id="d4ac2-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="d4ac2-185">**True**   如果應從始發伺服器接收要求，則將 XMPP 伺服器設定為使用回撥協商。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="d4ac2-186">**False**   未將 XMPP 伺服器設定為使用回撥協商，而且如果應該從始發伺服器接收要求，則會被忽略。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="d4ac2-187">按一下 [**認可**]，儲存您對網站或使用者原則所做的變更。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="d4ac2-188">更新 Lync Server 2013 XMPP 閘道的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="d4ac2-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="d4ac2-189">若要為 XMPP 同盟設定 DNS，您可以將下列 SRV 記錄新增到您的\_外部 DNS： XMPP-伺服器。\_tcp。\<[功能變數名稱] SRV 記錄會解析為邊緣伺服器的存取邊緣 FQDN，埠值為\> 5269。</span><span class="sxs-lookup"><span data-stu-id="d4ac2-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

