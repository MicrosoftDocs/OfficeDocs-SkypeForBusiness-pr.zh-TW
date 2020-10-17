---
title: 要求和設定反向 HTTP proxy 的憑證
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
ms.openlocfilehash: 7651e3da61e5ca197d36ca59ad8216af4c0188af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511980"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="b5551-102">在 Lync Server 2013 中要求和設定反向 HTTP proxy 的憑證</span><span class="sxs-lookup"><span data-stu-id="b5551-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5551-103">_**主題上次修改日期：** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="b5551-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="b5551-104">在對執行 Microsoft Lync Server 2013 的內部伺服器發出伺服器憑證的 CA 基礎結構上，，您必須在執行 Microsoft Forefront 威脅管理閘道2010或 IIS ARR 的伺服器上，安裝根憑證授權單位 (CA) 憑證。</span><span class="sxs-lookup"><span data-stu-id="b5551-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="b5551-p101">您也必須在反向 Proxy 伺服器上安裝公用 Web 伺服器憑證。此憑證的主體替代名稱應該包含已啟用遠端存取的使用者所在之每個集區的已發行外部完整網域名稱 (FQDN)，以及要在該 Edge 基礎結構內使用之所有 Director 或 Director 集區的 FQDN。主體替代名稱也必須包含會議簡單 URL、撥入簡單 URL，以及 (如果您要部署行動應用程式，並且計劃要使用自動探索) 外部自動探索服務 URL，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="b5551-p101">You also must install a public web server certificate on your reverse proxy server. This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure. The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="b5551-108">值</span><span class="sxs-lookup"><span data-stu-id="b5551-108">Value</span></span></th>
<th><span data-ttu-id="b5551-109">範例</span><span class="sxs-lookup"><span data-stu-id="b5551-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5551-110">主體名稱</span><span class="sxs-lookup"><span data-stu-id="b5551-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="b5551-111">集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="b5551-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="b5551-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5551-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5551-113">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="b5551-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="b5551-114">集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="b5551-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="b5551-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5551-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="b5551-116">主體名稱也必須出現在主體替代名稱中。</span><span class="sxs-lookup"><span data-stu-id="b5551-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5551-117">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="b5551-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="b5551-118">在部署 Director 時 (選用 Director Web 服務) </span><span class="sxs-lookup"><span data-stu-id="b5551-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="b5551-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5551-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5551-120">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="b5551-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="b5551-121">會議簡單 URL</span><span class="sxs-lookup"><span data-stu-id="b5551-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="b5551-p102">所有會議簡單 URL 都必須出現在主體替代名稱中。每個 SIP 網域都至少必須有一個作用中的會議簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="b5551-p102">All meeting simple URLs must be in the subject alternative name. Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="b5551-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5551-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5551-125">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="b5551-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="b5551-126">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="b5551-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="b5551-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5551-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5551-128">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="b5551-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="b5551-129">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="b5551-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="b5551-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5551-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5551-131">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="b5551-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="b5551-132">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="b5551-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b5551-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5551-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="b5551-134">如果您也是使用 Microsoft Exchange Server，您也需要為 Exchange 自動探索和 web 服務 URLs 設定反向 proxy 規則。</span><span class="sxs-lookup"><span data-stu-id="b5551-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="b5551-135">如果您的內部部署包含多個 Standard Edition Server 或前端集區，則您必須為每個外部 Web 伺服陣列 FQDN 設定 Web 發行規則，且需要針對其中每個 FQDN 各有一個憑證和網頁接聽程式，否則，您就必須取得憑證 (其主體替代名稱包含所有集區使用的名稱)、將憑證指派給網頁接聽程式，然後在多個 Web 發行規則之間共用憑證。</span><span class="sxs-lookup"><span data-stu-id="b5551-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="b5551-136">建立憑證要求</span><span class="sxs-lookup"><span data-stu-id="b5551-136">Create a Certificate Request</span></span>

<span data-ttu-id="b5551-137">在反向 proxy 上建立憑證要求。</span><span class="sxs-lookup"><span data-stu-id="b5551-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="b5551-138">您可以在另一部電腦上建立要求，但是必須使用私密金鑰匯出簽署的憑證，並在從公用憑證授權單位單位收到該憑證後，再將其匯入到反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="b5551-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b5551-139"> (CSR) 的憑證要求或憑證簽署要求 (CA) 以驗證要求的電腦的公開金鑰，並對信任的公用憑證授權單位單位要求。</span><span class="sxs-lookup"><span data-stu-id="b5551-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="b5551-140">當憑證產生時，即會建立公開金鑰和私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="b5551-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="b5551-141">只會共用和簽署公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="b5551-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="b5551-142">顧名思義，公開金鑰可供任何公開要求使用。</span><span class="sxs-lookup"><span data-stu-id="b5551-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="b5551-143">公開金鑰可供用戶端、伺服器及其他要求者使用，以安全地交換資訊和驗證電腦的身分識別。</span><span class="sxs-lookup"><span data-stu-id="b5551-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="b5551-144">私密金鑰是保持安全的，而且只由建立金鑰組的電腦使用，用來解密以其公開金鑰加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="b5551-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="b5551-145">私密金鑰可用於其他用途。</span><span class="sxs-lookup"><span data-stu-id="b5551-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="b5551-146">針對反向 proxy 目的，資料加密是主要用途。</span><span class="sxs-lookup"><span data-stu-id="b5551-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="b5551-147">Secondarily，憑證機碼層級的憑證驗證是另一個用途，而且只限于要求申請者具有電腦公開金鑰的驗證，或您具有公開金鑰的電腦實際上是其所宣告的電腦。</span><span class="sxs-lookup"><span data-stu-id="b5551-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="b5551-148">如果您同時規劃 Edge Server 憑證和反向 proxy 憑證，您應該注意到這兩種憑證需求具有極大的相似性。</span><span class="sxs-lookup"><span data-stu-id="b5551-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="b5551-149">當您設定和要求 Edge Server 憑證時，請結合 Edge Server 與反向 proxy 主體的替代名稱。</span><span class="sxs-lookup"><span data-stu-id="b5551-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="b5551-150">如果您匯出憑證和私密金鑰，並將匯出的檔案複製到反向 proxy，然後匯入憑證/金鑰組，並在即將進行的程式中將其指派給，您可以對反向 proxy 使用相同的憑證。</span><span class="sxs-lookup"><span data-stu-id="b5551-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="b5551-151">請參閱 lync server 2013 中的 edge server Plan Edge server Plan 的憑證需求 &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A>和 lync server 2013 中的反向 proxy<A href="lync-server-2013-certificate-summary-reverse-proxy.md">憑證摘要-反向</A>proxy。</span><span class="sxs-lookup"><span data-stu-id="b5551-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="b5551-152">請務必使用可匯出的私密金鑰來建立憑證。</span><span class="sxs-lookup"><span data-stu-id="b5551-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="b5551-153">您可以使用可匯出的私密金鑰建立憑證和憑證要求，以用於集區的 Edge Server，因此這是一般作法，而在 Edge Server 的 Lync Server 部署嚮導中的憑證嚮導可讓您設定 <STRONG>私密金鑰可匯出</STRONG> 的標誌。</span><span class="sxs-lookup"><span data-stu-id="b5551-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="b5551-154">當您從公用憑證授權單位發回憑證要求後，就會匯出憑證和私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="b5551-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="b5551-155">如需如何使用私密金鑰建立及匯出憑證的詳細資訊，請參閱本 <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">2013</A> 主題中的「使用集區中 Edge server 的私密金鑰來匯出憑證」一節中的 [匯出憑證]。</span><span class="sxs-lookup"><span data-stu-id="b5551-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="b5551-156">憑證的副檔名應該是 <STRONG>.pfx</STRONG>的類型。</span><span class="sxs-lookup"><span data-stu-id="b5551-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="b5551-157">若要在將指派憑證和私密金鑰的電腦上產生憑證簽署要求，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b5551-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="b5551-158">**建立憑證簽署要求**</span><span class="sxs-lookup"><span data-stu-id="b5551-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="b5551-159">開啟 Microsoft Management Console (MMC) 並新增 [憑證] 嵌入式管理單元，然後選取 [ **電腦**]，然後展開 [ **個人**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="b5551-160">如需如何在 Microsoft Management Console (MMC) 中建立憑證主控台的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) 。</span><span class="sxs-lookup"><span data-stu-id="b5551-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="b5551-161">以滑鼠右鍵按一下 [ **憑證**]，按一下 [ **所有**工作]，按一下 [ **高級作業**]，按一下 [ **建立自訂要求**]</span><span class="sxs-lookup"><span data-stu-id="b5551-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="b5551-162">在 [ **憑證註冊** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b5551-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="b5551-163">在 [**自訂要求**] 底下的 [**選取憑證註冊原則**] 頁面上，選取 [**繼續，不含註冊原則**]</span><span class="sxs-lookup"><span data-stu-id="b5551-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="b5551-164">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b5551-164">Click **Next**.</span></span>

5.  <span data-ttu-id="b5551-165">在 [ **自訂要求** ] 頁面上，針對 **範本** 選取 [ \*\* (沒有範本) 舊版金鑰\*\*]。</span><span class="sxs-lookup"><span data-stu-id="b5551-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="b5551-166">除非您的憑證提供者其他方式使用，否則請保留**取消勾選預設的分機**號碼，並在**PKCS \# 10**上選取**要求格式**。</span><span class="sxs-lookup"><span data-stu-id="b5551-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="b5551-167">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b5551-167">Click **Next**.</span></span>

6.  <span data-ttu-id="b5551-168">在 [ **憑證資訊** ] 頁面上，按一下 [ **詳細資料**]，然後按一下 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="b5551-169">在 [**憑證屬性**] 頁面上的 [**好記名稱**] 欄位中，輸入此**憑證的名稱**。</span><span class="sxs-lookup"><span data-stu-id="b5551-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="b5551-170">（選用）在 [ **描述** ] 欄位中輸入描述。</span><span class="sxs-lookup"><span data-stu-id="b5551-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="b5551-171">「好記名稱」和「描述」通常是由系統管理員用來識別憑證用途，例如 **Lync Server 的反向 Proxy 監聽器**。</span><span class="sxs-lookup"><span data-stu-id="b5551-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="b5551-172">選取 [**主旨**] 索引標籤。在 [**類型**的**主體名稱**] 底下，選取 [主體名稱] 類型的 [**一般名稱**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="b5551-173">針對 **值**輸入您將用於反向 proxy 的主體名稱，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="b5551-174">在本主題的表格中所提供的範例中，主體名稱是 webext.contoso.com，並會輸入至 [主旨名稱] 的 [值] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="b5551-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="b5551-175">在 [**替代名稱**] 下的 [主旨] 索引標籤上，從下拉式清單中**選取 [** **DNS** **]。**</span><span class="sxs-lookup"><span data-stu-id="b5551-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="b5551-176">針對憑證上所需的每個已定義的主體替代名稱，輸入完整的功能變數名稱，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="b5551-177">例如，在資料表中有三個主體替代名稱、meet.contoso.com、dialin.contoso.com 及 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b5551-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="b5551-178">在 [ **值** ] 欄位中，輸入 meet.contoso.com，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="b5551-179">針對您需要定義的每個主體替代名稱重複此名稱。</span><span class="sxs-lookup"><span data-stu-id="b5551-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="b5551-180">在 [ **憑證屬性** ] 頁面上，按一下 [ **副檔名** ] 索引標籤。在此頁面上，您會定義 **金鑰用法** 中的加密金鑰用途，以及 \*\*延伸金鑰使用 (應用程式原則) \*\*中的延伸金鑰用法。</span><span class="sxs-lookup"><span data-stu-id="b5551-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="b5551-181">按一下 [ **金鑰使用** ] 箭頭以顯示 **可用的選項**。</span><span class="sxs-lookup"><span data-stu-id="b5551-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="b5551-182">在 [可用選項] 底下，按一下 [ **數位簽章**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="b5551-183">按一下 [ **金鑰解碼**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="b5551-184">如果未選取 [ **將這些按鍵用法** 設定為關鍵的核取方塊] 核取方塊，請選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b5551-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="b5551-185">按一下 [ \*\*擴充金鑰用法] (應用程式原則) \*\* 箭號以顯示 **可用的選項**。</span><span class="sxs-lookup"><span data-stu-id="b5551-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="b5551-186">在 [可用選項] 底下，按一下 [ **伺服器驗證**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="b5551-187">按一下 [ **用戶端驗證**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="b5551-188">如果已勾選 [ **將擴充金鑰使用** 方式設定為重要的] 核取方塊，請取消選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b5551-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="b5551-189">不是必須檢查的 [主要使用狀況] 核取方塊 () 您必須確定未勾選 [擴充金鑰使用狀況] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b5551-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="b5551-190">在 [ **憑證屬性** ] 頁面上，按一下 [ **私密金鑰** ] 索引標籤。按一下 [ **按鍵選項** ] 箭頭。</span><span class="sxs-lookup"><span data-stu-id="b5551-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="b5551-191">針對 **金鑰大小**，從下拉式功能表中選取 [ **2048** ]。</span><span class="sxs-lookup"><span data-stu-id="b5551-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="b5551-192">若要在此憑證所針對的反向 proxy 以外的電腦上產生此金鑰組和 CSR，請選取 [ **讓私密金鑰可匯出**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="b5551-194">安全性附注：</span><span class="sxs-lookup"><span data-stu-id="b5551-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="b5551-195">當您在伺服器陣列中有一個以上的反向 proxy 時，如果您要將憑證和私密金鑰複製到伺服器陣列中的每一部電腦，則通常會建議選取 [ <strong>讓私密金鑰可匯出</strong> ]。</span><span class="sxs-lookup"><span data-stu-id="b5551-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="b5551-196">如果您確實允許可匯出的私密金鑰，您必須特別小心憑證和其產生所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="b5551-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="b5551-197">私密金鑰（如已遭破壞）將會使憑證無法使用，而且可能會將電腦或電腦公開給外部存取和其他安全性弱點。</span><span class="sxs-lookup"><span data-stu-id="b5551-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="b5551-198">在 [ **私密金鑰** ] 索引標籤上，按一下 [ **Key type** ] 箭頭。</span><span class="sxs-lookup"><span data-stu-id="b5551-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="b5551-199">選取 [ **Exchange** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="b5551-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="b5551-200">按一下 **[確定]** 儲存您已設定的 **憑證屬性** 。</span><span class="sxs-lookup"><span data-stu-id="b5551-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="b5551-201">在 [ **憑證註冊** ] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b5551-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="b5551-202">在 [ **您要用來儲存離線要求的位置** ] 頁面上，系統會提示您 **輸入檔案名，以及儲存** 憑證簽署要求的 **檔案格式** 。</span><span class="sxs-lookup"><span data-stu-id="b5551-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="b5551-203">**在 [檔案名專案]** 欄位中，輸入要求的路徑和檔案名，或按一下 **[流覽]** 以選取檔案的位置，然後輸入要求的檔案名。</span><span class="sxs-lookup"><span data-stu-id="b5551-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="b5551-204">針對 **檔案格式**，按一下 [ **基底 64** ] 或 [ **二進位**]。</span><span class="sxs-lookup"><span data-stu-id="b5551-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="b5551-205">選取 [ **基本 64** ]，除非您的憑證的廠商未另行指示。</span><span class="sxs-lookup"><span data-stu-id="b5551-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="b5551-206">找到您在上一個步驟中儲存的要求檔案。</span><span class="sxs-lookup"><span data-stu-id="b5551-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="b5551-207">提交至您的公用憑證授權單位單位。</span><span class="sxs-lookup"><span data-stu-id="b5551-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b5551-208">Microsoft 已識別出符合整合通訊目的需求的公用 Ca。</span><span class="sxs-lookup"><span data-stu-id="b5551-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="b5551-209">下列知識文庫文章中會維護清單。</span><span class="sxs-lookup"><span data-stu-id="b5551-209">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

