---
title: 要求以及設定反向 HTTP Proxy 的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffe1ce6a4b206b927b2fcdec4c02b905e01d5bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="68963-102">在 Lync Server 2013 中要求及設定反向 HTTP Proxy 的憑證</span><span class="sxs-lookup"><span data-stu-id="68963-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68963-103">_**主題上次修改日期：** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="68963-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="68963-104">您必須在執行 Microsoft Forefront 威脅管理閘道2010或 IIS ARR 的伺服器上，安裝根憑證授權單位（CA）憑證，以便將伺服器憑證頒發給執行 Microsoft Lync 的內部伺服器的 CA 基礎結構Server 2013。</span><span class="sxs-lookup"><span data-stu-id="68963-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="68963-105">您也必須在您的反向 proxy 伺服器上安裝公用 web 伺服器憑證。</span><span class="sxs-lookup"><span data-stu-id="68963-105">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="68963-106">這個憑證的消費者替換名稱應該包含已為使用者啟用遠端存取的每一個池的已發佈外部完整功能變數名稱（Fqdn），以及將在其中使用的所有控制器或控制器池的外部 Fqdn該 Edge 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="68963-106">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="68963-107">Subject 替換名稱也必須包含會議簡易 URL、撥入式簡易 URL，以及如果您要部署行動應用程式並規劃使用自動探索（如下表所示）的外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="68963-107">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="68963-108">值</span><span class="sxs-lookup"><span data-stu-id="68963-108">Value</span></span></th>
<th><span data-ttu-id="68963-109">範例</span><span class="sxs-lookup"><span data-stu-id="68963-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68963-110">消費者名稱</span><span class="sxs-lookup"><span data-stu-id="68963-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="68963-111">池 FQDN</span><span class="sxs-lookup"><span data-stu-id="68963-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="68963-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68963-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68963-113">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="68963-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68963-114">池 FQDN</span><span class="sxs-lookup"><span data-stu-id="68963-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="68963-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68963-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="68963-116">受領人名稱也必須存在於 subject 替換名稱中。</span><span class="sxs-lookup"><span data-stu-id="68963-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68963-117">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="68963-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68963-118">選用控制器 Web 服務（如果已部署 Director）</span><span class="sxs-lookup"><span data-stu-id="68963-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="68963-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68963-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68963-120">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="68963-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68963-121">[會議] 簡易 URL</span><span class="sxs-lookup"><span data-stu-id="68963-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="68963-122">所有會議的簡單 Url 都必須在 subject 替換名稱中。</span><span class="sxs-lookup"><span data-stu-id="68963-122">All meeting simple URLs must be in the subject alternative name.</span></span> <span data-ttu-id="68963-123">每個 SIP 網域都必須至少有一個作用中會議簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="68963-123">Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="68963-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68963-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68963-125">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="68963-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68963-126">電話撥入式簡易 URL</span><span class="sxs-lookup"><span data-stu-id="68963-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="68963-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68963-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68963-128">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="68963-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68963-129">Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="68963-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="68963-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68963-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68963-131">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="68963-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68963-132">外部自動探索服務 URL</span><span class="sxs-lookup"><span data-stu-id="68963-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="68963-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68963-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="68963-134">如果您也是使用 Microsoft Exchange Server，您也需要針對 Exchange 自動探索和 web 服務 Url 設定反向 proxy 規則。</span><span class="sxs-lookup"><span data-stu-id="68963-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="68963-135">如果您的內部部署是由多個標準版 server 或 [前端] 池組成，您必須針對每個外部網站伺服器陣列 FQDN 設定 web 發佈規則，或者您必須取得證書與 web 攔截器，或者您必須取得憑證其 subject 替換名稱包含所有池所使用的名稱，請將它指派給網頁監聽程式，並在多個 web 發佈規則之間共用。</span><span class="sxs-lookup"><span data-stu-id="68963-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="68963-136">建立憑證要求</span><span class="sxs-lookup"><span data-stu-id="68963-136">Create a Certificate Request</span></span>

<span data-ttu-id="68963-137">您在反向 proxy 上建立證書申請。</span><span class="sxs-lookup"><span data-stu-id="68963-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="68963-138">您在另一部電腦上建立要求，但是您必須先將簽署的憑證匯出為私密金鑰，然後再匯入到反向 proxy 之後，再從公用憑證授權單位收到。</span><span class="sxs-lookup"><span data-stu-id="68963-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="68963-139">證書申請或憑證簽署要求（CSR）是對受信任的公用憑證授權單位（CA）的要求，以驗證並簽署要求電腦的公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="68963-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="68963-140">當產生證書時，就會建立一個公開金鑰和一個私用的金鑰。</span><span class="sxs-lookup"><span data-stu-id="68963-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="68963-141">只有公開金鑰是共用和簽署的。</span><span class="sxs-lookup"><span data-stu-id="68963-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="68963-142">顧名思義，公開金鑰是提供給任何公開的要求。</span><span class="sxs-lookup"><span data-stu-id="68963-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="68963-143">公開金鑰供用戶端、伺服器和其他需要安全地交換資訊並驗證電腦身分識別的申請者使用。</span><span class="sxs-lookup"><span data-stu-id="68963-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="68963-144">私人金鑰會保持安全，而且只會由建立金鑰組的電腦使用，以解密以其公開金鑰加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="68963-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="68963-145">您可以使用私密金鑰來進行其他用途。</span><span class="sxs-lookup"><span data-stu-id="68963-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="68963-146">針對反向 proxy 目的，資料解碼是主要用途。</span><span class="sxs-lookup"><span data-stu-id="68963-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="68963-147">Secondarily，證書金鑰層級的憑證驗證是另一個用途，而且只限于驗證者擁有電腦的公開金鑰，或您擁有公開金鑰的電腦實際上是它所聲稱的電腦。</span><span class="sxs-lookup"><span data-stu-id="68963-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="68963-148">如果您同時規劃 Edge 伺服器憑證和您的反向 proxy 憑證，您應該注意到兩個憑證需求之間有很大的相似性。</span><span class="sxs-lookup"><span data-stu-id="68963-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="68963-149">當您設定並要求 Edge 伺服器憑證時，請結合邊緣伺服器與反向 proxy 消費者的替換名稱。</span><span class="sxs-lookup"><span data-stu-id="68963-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="68963-150">如果您匯出憑證和私密金鑰，然後將匯出的檔案複製到反向 proxy，然後匯入憑證/金鑰組，並視未來程式所需加以指派，就可以針對您的反向 proxy 使用相同的憑證。</span><span class="sxs-lookup"><span data-stu-id="68963-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="68963-151">請參閱 lync&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">server 2013 中 edge 伺服器方案</A>的邊緣伺服器方案的憑證需求，以及 [反向 proxy<A href="lync-server-2013-certificate-summary-reverse-proxy.md">憑證摘要-lync server 2013 中的反向</A>proxy]。</span><span class="sxs-lookup"><span data-stu-id="68963-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="68963-152">請確定您是使用可匯出的私密金鑰建立證書。</span><span class="sxs-lookup"><span data-stu-id="68963-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="68963-153">建立擁有可匯出私密金鑰的憑證和憑證要求，以供外邊緣伺服器使用時，這是一個正常做法，而在 Edge 伺服器的 Lync Server 部署嚮導中的 [憑證] 嚮導則可讓您設定 [<STRONG>製作私密金鑰可匯出</STRONG>] 標記。</span><span class="sxs-lookup"><span data-stu-id="68963-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="68963-154">當您從公用憑證授權單位收到證書要求之後，您將會匯出憑證和私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="68963-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="68963-155">如需如何使用私密金鑰建立及匯出您的憑證的詳細資訊，請參閱主題為<A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013 的外部邊緣介面設定</A>憑證中的「匯出證書，並在池中取得邊緣伺服器的私密金鑰」一節。</span><span class="sxs-lookup"><span data-stu-id="68963-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="68963-156">憑證的副檔名應為<STRONG>.pfx</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="68963-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="68963-157">若要在指派證書及私密金鑰的電腦上產生證書簽署要求，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="68963-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="68963-158">**建立憑證簽署要求**</span><span class="sxs-lookup"><span data-stu-id="68963-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="68963-159">開啟 Microsoft 管理主控台（MMC）並新增 [憑證] 管理單元，然後選取 [**電腦**]，然後展開 [**個人**]。</span><span class="sxs-lookup"><span data-stu-id="68963-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="68963-160">如需如何在 Microsoft 管理主控台（MMC）中建立憑證主控台的詳細資料，請[http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)參閱。</span><span class="sxs-lookup"><span data-stu-id="68963-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="68963-161">以滑鼠右鍵按一下 [**憑證**]，按一下 [**所有**工作]，按一下 [**高級作業**]，按一下 [**建立自訂要求**]</span><span class="sxs-lookup"><span data-stu-id="68963-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="68963-162">在 [**憑證註冊**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="68963-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="68963-163">在 [**選取憑證註冊原則**] 頁面的 [**自訂要求**] 底下，選取 [**不含註冊原則，繼續**]。</span><span class="sxs-lookup"><span data-stu-id="68963-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="68963-164">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="68963-164">Click **Next**.</span></span>

5.  <span data-ttu-id="68963-165">在 [**自訂要求**] 頁面上，針對**範本**選取 **[（無範本）舊版金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="68963-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="68963-166">除非您的憑證提供者有其他指示，否則請不要選取 [**取消選取預設擴充**]，以及在**PKCS \#10**上選取 [**要求格式**]。</span><span class="sxs-lookup"><span data-stu-id="68963-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="68963-167">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="68963-167">Click **Next**.</span></span>

6.  <span data-ttu-id="68963-168">在 [**憑證資訊**] 頁面上，按一下 [**詳細資料**]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="68963-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="68963-169">在 [**證書\*\*\*\*摘要**] 索引標籤上的 [**易記名稱**] 欄位中，輸入此憑證的名稱。</span><span class="sxs-lookup"><span data-stu-id="68963-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="68963-170">您也可以選擇在 [**描述**] 欄位中輸入描述。</span><span class="sxs-lookup"><span data-stu-id="68963-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="68963-171">系統管理員通常會使用易記名稱和描述來識別證書用途，例如**Lync Server 的反向 Proxy 監聽**程式。</span><span class="sxs-lookup"><span data-stu-id="68963-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="68963-172">選取 [**主語**] 索引標籤。在**類型**的 [主旨**名稱**] 底下，選取 [主旨名稱] 類型的 [**通用名稱**]。</span><span class="sxs-lookup"><span data-stu-id="68963-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="68963-173">針對 [**值**] 輸入您將用於反向 proxy 的主旨名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="68963-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="68963-174">在本主題中的資料表中所提供的範例中，subject 名稱是 webext.contoso.com，並會在主旨名稱的 [值] 欄位中輸入。</span><span class="sxs-lookup"><span data-stu-id="68963-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="68963-175">在 [ **Subject** ] 索引標籤的 [**替代名稱**] 底下，從下拉式清單中選取 [ **DNS** **]。**</span><span class="sxs-lookup"><span data-stu-id="68963-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="68963-176">針對您在憑證上所需的每個已定義的消費者替換名稱，輸入完整的功能變數名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="68963-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="68963-177">例如，在資料表中有三個使用中的主題替換名稱、meet.contoso.com、dialin.contoso.com 和 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="68963-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="68963-178">在 [**值**] 欄位中，輸入 meet.contoso.com，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="68963-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="68963-179">針對您需要定義的每個主體替換名稱，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="68963-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="68963-180">在 [**憑證屬性**] 頁面上，按一下 [**延伸**] 索引標籤。在此頁面上，您將在**金鑰用法**中定義加密金鑰的目的，以及**延伸金鑰用法（應用程式原則）** 中的延伸金鑰用法。</span><span class="sxs-lookup"><span data-stu-id="68963-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="68963-181">按一下 [**金鑰用法**] 箭號，以顯示**可用的選項**。</span><span class="sxs-lookup"><span data-stu-id="68963-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="68963-182">按一下 [可用選項] 底下的 [**數位簽章**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="68963-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="68963-183">按一下 [**金鑰解碼**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="68963-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="68963-184">如果未選取 [**將這些主要用法設為重要**] 核取方塊，請選取該核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68963-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="68963-185">按一下 [**擴展金鑰用法（應用程式原則）** ] 箭號，以顯示**可用的選項**。</span><span class="sxs-lookup"><span data-stu-id="68963-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="68963-186">按一下 [可用選項] 底下的 [**伺服器驗證**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="68963-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="68963-187">按一下 [**用戶端驗證**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="68963-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="68963-188">如果已選取 [**使延伸金鑰用法為關鍵性**] 核取方塊，請取消選取核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68963-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="68963-189">與 [金鑰用法] 核取方塊（必須核取）相反，您必須確定未選取 [延伸金鑰用法] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68963-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="68963-190">在 [**憑證屬性**] 頁面上，按一下 [**私人金鑰**] 索引標籤。按一下 [**金鑰選項**] 箭號。</span><span class="sxs-lookup"><span data-stu-id="68963-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="68963-191">針對**金鑰大小**，請從下拉式清單中選取 [ **2048** ]。</span><span class="sxs-lookup"><span data-stu-id="68963-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="68963-192">如果您要在並非此憑證所針對的相反代理伺服器以外的電腦上產生此金鑰組與 CSR，請選取 [**讓私人金鑰可匯出**]。</span><span class="sxs-lookup"><span data-stu-id="68963-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="68963-194">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="68963-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="68963-195">當您在伺服器陣列中有多個反向 proxy 時，通常會建議選取 [<strong>製作私密金鑰匯出</strong>]，因為您會將憑證和私密金鑰複製到伺服器陣列中的每個電腦。</span><span class="sxs-lookup"><span data-stu-id="68963-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="68963-196">如果您允許可匯出的私密金鑰，您就必須對憑證以及它產生的電腦格外小心。</span><span class="sxs-lookup"><span data-stu-id="68963-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="68963-197">如果密碼遭到破壞，私密金鑰會將 [無法使用] 轉譯成無法使用，而且可能會將電腦或電腦暴露在外部存取及其他安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="68963-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="68963-198">在 [**私人金鑰**] 索引標籤上，按一下 [**金鑰類型**] 箭號。</span><span class="sxs-lookup"><span data-stu-id="68963-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="68963-199">選取 [ **Exchange** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="68963-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="68963-200">按一下 **[確定]** 儲存已設定的**憑證屬性**。</span><span class="sxs-lookup"><span data-stu-id="68963-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="68963-201">在 [**憑證註冊**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="68963-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="68963-202">在 [**您要儲存離線要求的位置？** ] 頁面上，系統會提示您輸入**檔案名和\*\*\*\*檔案格式**，以儲存憑證簽署要求。</span><span class="sxs-lookup"><span data-stu-id="68963-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="68963-203">**在 [檔案名專案]** 欄位中，輸入要求的路徑和檔案名，或按一下 **[流覽]** 以選取檔案的位置，然後輸入要求的檔案名。</span><span class="sxs-lookup"><span data-stu-id="68963-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="68963-204">針對**檔案格式**，請按一下 [**基本 64** ] 或 [**二進位**]。</span><span class="sxs-lookup"><span data-stu-id="68963-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="68963-205">除非您向您的憑證提供給供應商的指示，否則請選取 [**基本 64** ]。</span><span class="sxs-lookup"><span data-stu-id="68963-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="68963-206">找出您在上一個步驟中儲存的要求檔案。</span><span class="sxs-lookup"><span data-stu-id="68963-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="68963-207">提交至您的公用憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="68963-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="68963-208">Microsoft 已識別符合整合通訊需求的公用 Ca。</span><span class="sxs-lookup"><span data-stu-id="68963-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="68963-209">下列知識庫文章中會保留清單。</span><span class="sxs-lookup"><span data-stu-id="68963-209">A list is maintained in the following knowledge base article.</span></span> <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

