---
title: 要求以及設定反向 HTTP proxy 的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 830d9d48e68142cf32f14d428fb48e3ab20afaca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="78035-102">要求以及設定反向 HTTP proxy Lync Server 2013 中的憑證</span><span class="sxs-lookup"><span data-stu-id="78035-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78035-103">_**上次修改主題：** 2014年-02-14_</span><span class="sxs-lookup"><span data-stu-id="78035-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="78035-104">您必須執行 Microsoft Forefront Threat Management Gateway 2010 或 IIS ARR 到執行 Microsoft Lync 的內部伺服器發出伺服器憑證的 CA 基礎結構的伺服器上安裝根憑證授權單位 (CA) 憑證Server 2013。</span><span class="sxs-lookup"><span data-stu-id="78035-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="78035-p101">您也必須在反向 Proxy 伺服器上安裝公用 Web 伺服器憑證。此憑證的主體替代名稱應該包含已啟用遠端存取的使用者所在之每個集區的已發行外部完整網域名稱 (FQDN)，以及要在該 Edge 基礎結構內使用之所有 Director 或 Director 集區的 FQDN。主體替代名稱也必須包含會議簡單 URL、撥入簡單 URL，以及 (如果您要部署行動應用程式，並且計劃要使用自動探索) 外部自動探索服務 URL，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="78035-p101">You also must install a public web server certificate on your reverse proxy server. This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure. The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="78035-108">值</span><span class="sxs-lookup"><span data-stu-id="78035-108">Value</span></span></th>
<th><span data-ttu-id="78035-109">範例</span><span class="sxs-lookup"><span data-stu-id="78035-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78035-110">主體名稱</span><span class="sxs-lookup"><span data-stu-id="78035-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="78035-111">集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="78035-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="78035-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78035-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78035-113">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="78035-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="78035-114">集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="78035-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="78035-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78035-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="78035-116">主體名稱也必須出現在主體替代名稱中。</span><span class="sxs-lookup"><span data-stu-id="78035-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78035-117">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="78035-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="78035-118">選用 Director Web 服務 （如果部署 Director）</span><span class="sxs-lookup"><span data-stu-id="78035-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="78035-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78035-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78035-120">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="78035-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="78035-121">會議簡單 URL</span><span class="sxs-lookup"><span data-stu-id="78035-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="78035-p102">所有會議簡單 URL 都必須出現在主體替代名稱中。每個 SIP 網域都至少必須有一個作用中的會議簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="78035-p102">All meeting simple URLs must be in the subject alternative name. Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="78035-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78035-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78035-125">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="78035-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="78035-126">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="78035-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="78035-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78035-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78035-128">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="78035-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="78035-129">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="78035-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="78035-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78035-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78035-131">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="78035-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="78035-132">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="78035-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="78035-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78035-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="78035-134">如果您同時使用 Microsoft Exchange Server 您也必須設定 Exchange 自動探索和 web 服務 url 的反向 proxy 規則。</span><span class="sxs-lookup"><span data-stu-id="78035-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="78035-135">如果您的內部部署包含多個 Standard Edition Server 或前端集區，則您必須為每個外部 Web 伺服陣列 FQDN 設定 Web 發行規則，且需要針對其中每個 FQDN 各有一個憑證和網頁接聽程式，否則，您就必須取得憑證 (其主體替代名稱包含所有集區使用的名稱)、將憑證指派給網頁接聽程式，然後在多個 Web 發行規則之間共用憑證。</span><span class="sxs-lookup"><span data-stu-id="78035-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="78035-136">建立憑證要求</span><span class="sxs-lookup"><span data-stu-id="78035-136">Create a Certificate Request</span></span>

<span data-ttu-id="78035-137">您的反向 proxy 上建立憑證要求。</span><span class="sxs-lookup"><span data-stu-id="78035-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="78035-138">在另一部電腦上建立要求，但您必須使用私密金鑰匯出的簽署的憑證並匯入反向 proxy，一旦您有來自公用憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="78035-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="78035-139">憑證要求或憑證簽署要求 (CSR) 是以驗證並登入要求的電腦公開金鑰受信任的公用憑證授權單位 (CA) 的要求。</span><span class="sxs-lookup"><span data-stu-id="78035-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="78035-140">產生憑證時，會建立公開金鑰及私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="78035-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="78035-141">僅限公開金鑰共用且帶正負號。</span><span class="sxs-lookup"><span data-stu-id="78035-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="78035-142">顧名思義，公開金鑰是提供給任何公用的要求。</span><span class="sxs-lookup"><span data-stu-id="78035-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="78035-143">公開金鑰是供用戶端、 伺服器和其他需要安全地交換資訊，並驗證電腦的身分識別的要求。</span><span class="sxs-lookup"><span data-stu-id="78035-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="78035-144">私密金鑰會保持安全，並只能由建立來解密郵件以其公開金鑰加密金鑰組的電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="78035-145">私密金鑰可以用於其他用途。</span><span class="sxs-lookup"><span data-stu-id="78035-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="78035-146">反向 proxy 的目的，資料編密是主要的使用。</span><span class="sxs-lookup"><span data-stu-id="78035-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="78035-147">再，憑證重要層級的憑證驗證是另一種用法，且只限於驗證已要求者電腦的公開金鑰，或您有公開金鑰的電腦是實際其所宣稱的電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="78035-148">如果您規劃您的 Edge Server 憑證和反向 proxy 憑證在同一時間時，您應該注意到已有極大的兩個憑證需求之間的相似性。</span><span class="sxs-lookup"><span data-stu-id="78035-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="78035-149">當您設定，並要求您的 Edge Server 憑證時，合併 Edge Server 和反向 proxy 的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="78035-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="78035-150">如果您匯出憑證與私密金鑰和將匯出的檔案複製到反向 proxy 然後匯入的憑證/金鑰組並將其指派視即將來臨的程序，您可以使用您的反向 proxy 的相同的憑證。</span><span class="sxs-lookup"><span data-stu-id="78035-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="78035-151">Edge Server 的憑證需求，請參閱&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Lync Server 2013 中的 Edge Server 憑證計劃</A>及反向 proxy<A href="lync-server-2013-certificate-summary-reverse-proxy.md">憑證摘要-Lync Server 2013 中的反向 proxy</A>。</span><span class="sxs-lookup"><span data-stu-id="78035-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="78035-152">請確定您建立具可匯出的私密金鑰的憑證。</span><span class="sxs-lookup"><span data-stu-id="78035-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="78035-153">建立具可匯出的私密金鑰的憑證與憑證要求才區的 Edge Server，因此這是標準的作法是，並在 Edge Server 的 [Lync Server 部署精靈的 [憑證] 精靈可讓您設定<STRONG>進行可匯出的私密金鑰</STRONG>的旗標。</span><span class="sxs-lookup"><span data-stu-id="78035-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="78035-154">一旦您從公用憑證授權單位取回收到憑證要求，您將會匯出憑證與私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="78035-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="78035-155">主題中的<A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 的外部 edge 介面的憑證設定</A>如需如何建立並匯出憑證與私密金鑰的詳細資訊，請參閱 「 若要匯出憑證與私密金鑰的集區中的 Edge Server 」 一節。</span><span class="sxs-lookup"><span data-stu-id="78035-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="78035-156">類型<STRONG>.pfx</STRONG>應該是憑證的擴充。</span><span class="sxs-lookup"><span data-stu-id="78035-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="78035-157">若要產生的憑證簽署要求，其中會指派的憑證及私密金鑰的電腦上，您執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="78035-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="78035-158">**建立的憑證簽署要求**</span><span class="sxs-lookup"><span data-stu-id="78035-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="78035-159">開啟 Microsoft Management Console (MMC)，並新增憑證嵌入式管理單元中，選取 [**電腦**]，然後依序展開 [**個人**。</span><span class="sxs-lookup"><span data-stu-id="78035-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="78035-160">如需如何建立憑證] 主控台中的 [Microsoft Management Console (MMC) 的詳細資訊，請參閱[http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)。</span><span class="sxs-lookup"><span data-stu-id="78035-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="78035-161">**憑證**上按一下滑鼠右鍵，按一下 [**所有工作**，按一下都 [**進階作業**，按一下都 [**建立自訂要求**。</span><span class="sxs-lookup"><span data-stu-id="78035-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="78035-162">在**憑證註冊**頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="78035-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="78035-163">在 [**自訂要求\*\*\*\*選取憑證註冊原則**] 頁面上，選取 [**沒有註冊原則繼續**。</span><span class="sxs-lookup"><span data-stu-id="78035-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="78035-164">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78035-164">Click **Next**.</span></span>

5.  <span data-ttu-id="78035-165">在 [**自訂要求**] 頁面上的**範本**選取 **（沒有範本） 傳統金鑰**。</span><span class="sxs-lookup"><span data-stu-id="78035-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="78035-166">除非另有指示您的憑證提供者，將保留**抑制預設延伸**未勾選和**要求格式**的選取範圍上**PKCS \#10**。</span><span class="sxs-lookup"><span data-stu-id="78035-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="78035-167">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78035-167">Click **Next**.</span></span>

6.  <span data-ttu-id="78035-168">在 [**認證資訊**] 頁面上，按一下 [**詳細資料**，然後按 [**屬性**。</span><span class="sxs-lookup"><span data-stu-id="78035-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="78035-169">在 [**易記名稱**] 欄位中的 [**一般**] 索引標籤上的**憑證內容**] 頁面上，輸入此憑證的名稱。</span><span class="sxs-lookup"><span data-stu-id="78035-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="78035-170">（選用） 在 [**描述**] 欄位中輸入描述。</span><span class="sxs-lookup"><span data-stu-id="78035-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="78035-171">易記的名稱和描述是通常用於由系統管理員識別憑證用途為何，例如 [ **Lync Server 的反向 Proxy 接聽程式**。</span><span class="sxs-lookup"><span data-stu-id="78035-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="78035-172">選取 [**主旨**] 索引標籤。**類型**的**主體名稱**] 下選取 [主旨名稱類型的**一般名稱**。</span><span class="sxs-lookup"><span data-stu-id="78035-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="78035-173">**值**中，輸入將用於反向 proxy，然後按一下 [**新增**的主體名稱。</span><span class="sxs-lookup"><span data-stu-id="78035-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="78035-174">在本主題中的表格中所提供的範例，在主體名稱是 webext.contoso.com，而要輸入到主體名稱的 [值] 欄位。</span><span class="sxs-lookup"><span data-stu-id="78035-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="78035-175">**替代名稱**下的 [**主旨**] 索引標籤中，選取 [ **DNS**從下拉式清單向下的**類型**。</span><span class="sxs-lookup"><span data-stu-id="78035-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="78035-176">每個已定義的主體替代名稱，您需要在憑證上，輸入完整的網域名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="78035-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="78035-177">例如，在資料表中有三個主體替代名稱、 meet.contoso.com、 dialin.contoso.com 和 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="78035-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="78035-178">在 [**值**] 欄位中的 [類型 meet.contoso.com，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="78035-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="78035-179">重複針對每個您要定義的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="78035-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="78035-180">在**憑證內容**頁面上，按一下 [**延伸**] 索引標籤。在此頁面上，您將**金鑰使用方法**和延伸的金鑰使用**延伸**的機碼使用量 （應用程式原則]） 中定義的密碼編譯的主要目的。</span><span class="sxs-lookup"><span data-stu-id="78035-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="78035-181">按一下 [**機碼流量**箭號，以顯示**可用的選項**。</span><span class="sxs-lookup"><span data-stu-id="78035-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="78035-182">[可用的選項] 下按一下 [**數位簽章**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="78035-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="78035-183">按一下 [**金鑰加密**，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="78035-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="78035-184">如果未選取**進行重大這些金鑰使用方式**的核取方塊，選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="78035-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="78035-185">按一下 [**延伸金鑰使用方法 （應用程式原則）** 箭號，以顯示**可用的選項**。</span><span class="sxs-lookup"><span data-stu-id="78035-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="78035-186">[可用的選項] 下按一下 [**伺服器驗證**，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="78035-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="78035-187">按一下 [**用戶端驗證**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="78035-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="78035-188">如果會檢查**進行擴充金鑰使用方式重要**核取方塊，取消選取該核取方塊。</span><span class="sxs-lookup"><span data-stu-id="78035-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="78035-189">相反金鑰使用方式] 核取方塊 （其必須檢查） 您必須確定已不存延伸金鑰使用方式] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="78035-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="78035-190">在 [**憑證內容**] 頁面上，按一下 [**私密金鑰**] 索引標籤按一下 [**金鑰選項**] 箭號。</span><span class="sxs-lookup"><span data-stu-id="78035-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="78035-191">若是**金鑰大小**，請選取 [ **2048年**從下拉式清單向下。</span><span class="sxs-lookup"><span data-stu-id="78035-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="78035-192">如果您要產生此金鑰組和 CSR，供此憑證的反向 proxy 以外的電腦上，選取 [設定**成可匯出的私密金鑰**。</span><span class="sxs-lookup"><span data-stu-id="78035-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="78035-194">安全性附註：</span><span class="sxs-lookup"><span data-stu-id="78035-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="78035-195">當您將有一個以上的反向 proxy 伺服器陣列中，因為您會將憑證與私密金鑰複製到伺服器陣列中每一部機器通常建議您選取 [<strong>讓可匯出的私密金鑰</strong>。</span><span class="sxs-lookup"><span data-stu-id="78035-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="78035-196">如果您不要允許可匯出的私密金鑰，您必須小心憑證與它產生的電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="78035-197">私密金鑰]，如果危害，將會轉譯憑證沒有用，以及可能會公開外部存取及其他安全性弱點的電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="78035-198">**私密金鑰**索引標籤上，按一下 [**索引鍵類型**箭號。</span><span class="sxs-lookup"><span data-stu-id="78035-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="78035-199">選取 [ **Exchange** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="78035-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="78035-200">按一下 **[確定]** 以儲存您已設定**憑證內容**]。</span><span class="sxs-lookup"><span data-stu-id="78035-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="78035-201">在**憑證註冊**頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="78035-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="78035-202">在**您要在其中儲存離線要求？** ] 頁面上，系統會提示您輸入**檔案名稱**和**檔案格式**儲存的憑證簽署要求。</span><span class="sxs-lookup"><span data-stu-id="78035-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="78035-203">在 [**檔案名稱**項目] 欄位中，輸入路徑和檔名的要求，或按一下 [**瀏覽**至選取的檔案的位置，然後輸入要求的檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="78035-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="78035-204">**檔案格式**，請按一下**Base 64** ] 或 [**二進位**。</span><span class="sxs-lookup"><span data-stu-id="78035-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="78035-205">除非您另有指示，否則廠商針對您的憑證，請選取 [ **Base 64** ]。</span><span class="sxs-lookup"><span data-stu-id="78035-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="78035-206">找出您在上一個步驟中儲存的要求檔案。</span><span class="sxs-lookup"><span data-stu-id="78035-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="78035-207">送出至您的公用憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="78035-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="78035-208">Microsoft 已識別公用 Ca 符合整合通訊用途的需求。</span><span class="sxs-lookup"><span data-stu-id="78035-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="78035-209">清單會維護下列知識庫文章中。</span><span class="sxs-lookup"><span data-stu-id="78035-209">A list is maintained in the following knowledge base article.</span></span> <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

