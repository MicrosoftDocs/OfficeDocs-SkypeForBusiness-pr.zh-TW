---
title: Lync Server 2013：設定外部 edge 介面的憑證
description: Lync Server 2013：設定外部 edge 介面的憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeca6edf0a3b50ab5dcaf9ecdbaea931d7bdf947
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575409"
---
# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="2416b-103">為 Lync Server 2013 設定外部 edge 介面的憑證</span><span class="sxs-lookup"><span data-stu-id="2416b-103">Set up certificates for the external edge interface for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2416b-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2416b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2416b-105">當您執行 [憑證精靈] 時，請確定您用來登入的帳戶，是具有您要使用之憑證範本類型適當權限的群組成員。</span><span class="sxs-lookup"><span data-stu-id="2416b-105">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="2416b-106">根據預設，Lync Server 憑證要求會使用網頁伺服器憑證範本。</span><span class="sxs-lookup"><span data-stu-id="2416b-106">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="2416b-107">如果您要以 RTCUniversalServerAdmins 群組成員的帳戶使用此範本來要求憑證，請確定群組具有使用該範本所需的註冊權限。</span><span class="sxs-lookup"><span data-stu-id="2416b-107">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="2416b-108">每一台 Edge Server 都需要在周邊網路與網際網路之間的介面上放置一個公用憑證，而該憑證的主體替代名稱必須包含 Access Edge Service 的外部名稱與 Web Conferencing Edge Service 完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="2416b-108">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="2416b-109">如需此和其他憑證需求的詳細資訊，請參閱 [Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="2416b-109">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="2416b-110">如需公開憑證授權單位清單 (CAs) 提供符合整合通訊憑證之特定需求的憑證，並與 Microsoft 合作，以確保其與 Lync Server 2013 憑證嚮導搭配運作，請參閱 Microsoft 知識庫文章929395：「Exchange Server 和通訊伺服器的整合通訊憑證合作夥伴」，「at」 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。</span><span class="sxs-lookup"><span data-stu-id="2416b-110">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="2416b-111">設定外部介面的憑證</span><span class="sxs-lookup"><span data-stu-id="2416b-111">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="2416b-112">若要在網站上設定外部 Edge 介面的憑證，請使用本節所述步驟執行下列事項：</span><span class="sxs-lookup"><span data-stu-id="2416b-112">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="2416b-113">為 Edge Server 的外部介面建立憑證要求。</span><span class="sxs-lookup"><span data-stu-id="2416b-113">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="2416b-114">將要求送出給公用 CA。</span><span class="sxs-lookup"><span data-stu-id="2416b-114">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="2416b-115">匯入每一部 Edge Server 外部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="2416b-115">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="2416b-116">指派每一部 Edge Server 外部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="2416b-116">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="2416b-p102">如果您的部署範圍包括好幾部 Edge Server，請將憑證連同其私密金鑰一起匯出，然後將其複製到其他 Edge Server 上。接著，將其匯入到每一台 Edge Server 並如先前所述加以指定。在每一部 Edge Server 上重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="2416b-p102">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers. Then, for each Edge Server, import it and assign it as previously described. Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="2416b-p103">您可以從公用憑證授權單位 (CA) 直接要求公用憑證，例如從公用 CA 網站。本節所述步驟使用的憑證精靈適用於大多數憑證工作。如果您選擇從公用 CA 直接要求憑證，則您需要適當修改每個步驟以要求、傳輸與匯入憑證，同時匯入憑證鏈結。</span><span class="sxs-lookup"><span data-stu-id="2416b-p103">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA). The procedures in this section use the Certificate Wizard for most certificate tasks. If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="2416b-p104">當您從外部 CA 要求憑證時，附上的認證必須具備從該 CA 要求憑證的權限。每一家 CA 的安全性原則都會定義可以用來要求、發行、管理或讀取憑證的認證 (亦即，特定使用者與群組名稱)。</span><span class="sxs-lookup"><span data-stu-id="2416b-p104">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA. Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="2416b-125">如果您決定透過 Certificates Microsoft Management Console (MMC) 匯入憑證鏈結與憑證，則您必須將其匯入電腦的憑證存放庫。</span><span class="sxs-lookup"><span data-stu-id="2416b-125">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="2416b-126">如果您將其匯入使用者或服務證書存放區，該憑證將無法在 Lync Server 2013 憑證嚮導中使用指派。</span><span class="sxs-lookup"><span data-stu-id="2416b-126">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="2416b-127">若要為 Edge Server 的外部介面建立憑證要求</span><span class="sxs-lookup"><span data-stu-id="2416b-127">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="2416b-128">在 Edge Server 的 [部署精靈] 中，按一下 **[步驟 3:要求、安裝或指派憑證]** 旁邊的 **[再執行一次]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-128">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2416b-129">如果您的組織想要支援與 AOL 的公用立即訊息 (IM) 連線能力，您將無法使用 Lync Server 部署精靈要求憑證。</span><span class="sxs-lookup"><span data-stu-id="2416b-129">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="2416b-130">這時請執行本主題稍後「若要為 Edge Server 的外部介面建立憑證要求以支援對 AOL 的公用 IM 連線能力」中的步驟。</span><span class="sxs-lookup"><span data-stu-id="2416b-130">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="2416b-131">如果您在集區中的一個位置有多部 Edge server，則可以在任何一部 Edge server 上執行 Lync Server 2013 憑證嚮導。</span><span class="sxs-lookup"><span data-stu-id="2416b-131">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="2416b-132">在 **[可用憑證工作]** 頁面上，按一下 **[建立新憑證要求]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-132">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="2416b-133">在 **[憑證要求]** 頁面上，按一下 **[外部邊緣憑證]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-133">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="2416b-134">在 **[延遲或立即要求]** 頁面上，選取 **[立即準備此要求，但稍後再傳送]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2416b-134">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="2416b-135">在 [ **憑證要求** 檔案] 頁面上，輸入要儲存要求的檔案完整路徑和檔案名 (例如，c： \\ cert \_ 外部 \_ edge) 。</span><span class="sxs-lookup"><span data-stu-id="2416b-135">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="2416b-136">若要使用預設 WebServer 範本之外的其他範本，請在 **[指定其他憑證範本]** 頁面上，選取 **[將其他憑證範本用於所選的憑證授權單位]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2416b-136">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="2416b-137">在 **[名稱和安全性設定]** 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2416b-137">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="2416b-138">在 **[易記名稱]** 中，輸入憑證的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="2416b-138">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="2416b-139">在 **[位元長度]** 中，指定位元長度 (預設值通常是 **2048**)。</span><span class="sxs-lookup"><span data-stu-id="2416b-139">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="2416b-140">確認 **[將憑證私密金鑰標示為可匯出]** 核取方塊已經選取。</span><span class="sxs-lookup"><span data-stu-id="2416b-140">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="2416b-141">在 **[組織資訊]** 頁面上，輸入組織的名稱和組織單位 (例如部門)。</span><span class="sxs-lookup"><span data-stu-id="2416b-141">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="2416b-142">在 **[地理資訊]** 頁面上，指定位置資訊。</span><span class="sxs-lookup"><span data-stu-id="2416b-142">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="2416b-p107">在 **[主體名稱/主體別名]** 頁面上，會顯示精靈將自動填入的資訊。如果您還需要其他主體別名，請在後續兩個步驟中指定。</span><span class="sxs-lookup"><span data-stu-id="2416b-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="2416b-145">在 [ \*\*主體別名 (SANs) \*\* ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2416b-145">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="2416b-146">專案的主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="2416b-146">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="2416b-147">在 **[設定其他主體別名]** 頁面上，指定任何需要的其他主體別名。</span><span class="sxs-lookup"><span data-stu-id="2416b-147">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="2416b-148">在 **[要求摘要]** 頁面上，檢閱要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="2416b-148">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="2416b-149">當命令執行完畢之後，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2416b-149">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="2416b-150">若要檢視憑證要求記錄檔，按一下 **[檢視記錄檔]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-150">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="2416b-151">若要完成憑證要求，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-151">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="2416b-152">在 **[憑證要求檔案]** 頁面上，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2416b-152">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="2416b-153">若要檢視產生的憑證簽署要求 (CSR) 檔案，按一下 **[檢視]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-153">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="2416b-154">按一下 **[完成]**，關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="2416b-154">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="2416b-155">將輸出檔案複製到某個位置，您可以從這個位置將它送出到公用 CA。</span><span class="sxs-lookup"><span data-stu-id="2416b-155">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="2416b-156">若要為 Edge Server 的外部介面建立憑證要求以支援對 AOL 的公用 IM 連線能力</span><span class="sxs-lookup"><span data-stu-id="2416b-156">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="2416b-157">當 CA 可使用必要範本時，請從 Edge Server 使用下列 Windows PowerShell Cmdlet，以要求憑證：</span><span class="sxs-lookup"><span data-stu-id="2416b-157">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="2416b-158">Lync Server 2013 中提供之範本的預設憑證名稱是網頁伺服器。</span><span class="sxs-lookup"><span data-stu-id="2416b-158">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="2416b-159">只有在 \<template name\> 您需要使用不同于預設範本的範本時，才指定。</span><span class="sxs-lookup"><span data-stu-id="2416b-159">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2416b-160">如果您的組織想要支援與 AOL 的公用 IM 連線，您必須使用 Windows PowerShell，而不是使用憑證嚮導要求將憑證指派給 Access Edge service 的外部 edge。</span><span class="sxs-lookup"><span data-stu-id="2416b-160">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="2416b-161">這是因為憑證嚮導用來要求憑證的 Lync Server 2013 網頁伺服器範本不支援用戶端 EKU 設定。</span><span class="sxs-lookup"><span data-stu-id="2416b-161">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="2416b-162">在使用 Windows PowerShell 建立憑證之前，CA 管理員必須建立及部署支援用戶端 EKU 的新範本。</span><span class="sxs-lookup"><span data-stu-id="2416b-162">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="2416b-163">若要將要求送出到公用憑證授權單位</span><span class="sxs-lookup"><span data-stu-id="2416b-163">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="2416b-164">開啟輸出檔案。</span><span class="sxs-lookup"><span data-stu-id="2416b-164">Open the output file.</span></span>

2.  <span data-ttu-id="2416b-165">複製並貼上憑證簽署要求 (CSR) 的內容。</span><span class="sxs-lookup"><span data-stu-id="2416b-165">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="2416b-166">如果出現提示，請指定下列選項：</span><span class="sxs-lookup"><span data-stu-id="2416b-166">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="2416b-167">伺服器平台為 **[Microsoft]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-167">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="2416b-168">版本為 **[IIS]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-168">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="2416b-169">使用類型為 **[Web 伺服器]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-169">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="2416b-170">回應格式為 **PKCS7**。</span><span class="sxs-lookup"><span data-stu-id="2416b-170">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="2416b-171">在公用 CA 驗證您的資訊之後，您會收到一封電子郵件，其中包含憑證所需的文字。</span><span class="sxs-lookup"><span data-stu-id="2416b-171">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="2416b-172">複製此電子郵件的文字，並將內容儲存到本機電腦的文字檔 (.txt) 中。</span><span class="sxs-lookup"><span data-stu-id="2416b-172">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="2416b-173">若要匯入 Edge Server 外部介面的憑證</span><span class="sxs-lookup"><span data-stu-id="2416b-173">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="2416b-174">以 Administrators 群組成員身分登入方才用來建立憑證要求的同一部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="2416b-174">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="2416b-175">在 [部署精靈] 的 **[部署 Edge Server]** 頁面上，按一下 **[步驟 3：要求、安裝或指派憑證]** 旁邊的 **[再執行一次]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-175">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="2416b-176">在 **[可用憑證工作]** 頁面上，按一下 **[從 .p7b、pfx 或 .cer 檔案匯入憑證]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-176">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="2416b-p111">在 [匯入憑證]\*\*\*\* 頁面上，按一下 [瀏覽]\*\*\*\* 來尋找並選取您為 Edge Server 外部介面要求的憑證 (或者，您可以輸入完整路徑和檔案名稱)。如果憑證包含私密金鑰，請選取 [憑證檔案包含憑證的私密金鑰]\*\*\*\*，然後輸入私密金鑰的密碼。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-p111">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name). If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key. Click **Next**.</span></span>

5.  <span data-ttu-id="2416b-180">在 [匯入憑證摘要]\*\*\*\* 頁面中，檢閱摘要，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-180">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="2416b-181">在 [執行命令]\*\*\*\* 中，檢閱匯入結果，視需要按一下 [檢視記錄檔]\*\*\*\* 以取得更多資訊，然後按一下 [完成]\*\*\*\*，完成憑證的匯入。</span><span class="sxs-lookup"><span data-stu-id="2416b-181">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="2416b-p112">如果您正在設定 Edge Server 集區，請按照本主題後面的「為集區中的 Edge Server 匯出包含私密金鑰的憑證」程序，匯出憑證及其私密金鑰。請將匯出的憑證檔案複製到其他 Edge Server，然後將之匯出至每一部 Edge Server 上的電腦存放區。</span><span class="sxs-lookup"><span data-stu-id="2416b-p112">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic. Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="2416b-184">為集區中的 Edge Server 匯出包含私密金鑰的憑證</span><span class="sxs-lookup"><span data-stu-id="2416b-184">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="2416b-185">以 Administrators 群組成員身分登入剛才用來匯入憑證的同一部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="2416b-185">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="2416b-186">按一下 [開始]\*\*\*\*，按一下 [執行]\*\*\*\*，然後輸入 **MMC**。</span><span class="sxs-lookup"><span data-stu-id="2416b-186">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="2416b-187">在 Microsoft Management Console (MMC) 主控台，按一下 [檔案]\*\*\*\*，然後按一下 [新增/移除嵌入式管理單元]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-187">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="2416b-188">在 [新增或移除嵌入式管理單元]\*\*\*\* 中，按一下 [憑證]\*\*\*\*，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-188">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="2416b-189">在 [憑證]\*\*\*\* 對話方塊中，選取 [電腦帳戶]\*\*\*\*，按 [下一步]\*\*\*\*，在 [選取電腦]\*\*\*\* 中選取 [本機電腦: (執行這個主控台的電腦)]\*\*\*\*，按一下 [完成]\*\*\*\*，然後按一下 [確定]\*\*\*\*，完成 MMC 主控台的設定。</span><span class="sxs-lookup"><span data-stu-id="2416b-189">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="2416b-190">按兩下 [憑證 (本機電腦)]\*\*\*\*，展開憑證存放區，按兩下 [個人]\*\*\*\*，然後按兩下 [憑證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-190">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2416b-p113">如果本機電腦的憑證個人存放區中沒有憑證，則匯入的憑證就沒有關聯的私密金鑰。請檢閱要求和匯入步驟。如果問題仍持續存在，請與您的憑證授權單位管理員或提供者連絡。</span><span class="sxs-lookup"><span data-stu-id="2416b-p113">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="2416b-194">在 [本機電腦的憑證個人存放區]\*\*\*\* 中，在您匯出的憑證上按一下滑鼠右鍵，按一下 [所有工作]\*\*\*\*，然後按一下 [匯出]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-194">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="2416b-195">在憑證匯出精靈中，按 [下一步]\*\*\*\*，選取 [是，匯出私密金鑰]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-195">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2416b-p114">如果 [是，匯出私密金鑰]<STRONG></STRONG> 選項無法使用，則與該憑證關聯的私密金鑰就不會標示為可匯出。您需要重新申請憑證，確定憑證標示為允許匯出私密金鑰，才能繼續匯出。請與您的憑證授權單位管理員或提供者連絡。</span><span class="sxs-lookup"><span data-stu-id="2416b-p114">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="2416b-199">在 [匯出檔案格式] 對話方塊中，選取 [ \*\*個人資訊交換– PKCS \# 12] (。PFX) \*\* 然後選取下列各項：</span><span class="sxs-lookup"><span data-stu-id="2416b-199">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="2416b-200">盡可能在憑證路徑中包含所有憑證</span><span class="sxs-lookup"><span data-stu-id="2416b-200">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="2416b-201">匯出所有延伸內容</span><span class="sxs-lookup"><span data-stu-id="2416b-201">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="2416b-p115">從 Edge Server 匯出憑證時，不要選取 [如果匯出成功即刪除私密金鑰]<STRONG></STRONG>。選取這個選項時，必須將憑證和私密金鑰匯入這個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="2416b-p115">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="2416b-204">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-204">Click **Next**.</span></span>

11. <span data-ttu-id="2416b-205">輸入私密金鑰的密碼，再輸入一次密碼以進行確認，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-205">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="2416b-p116">輸入匯出憑證的路徑和檔案名稱，使用 .pfx 副檔名。路徑必須可供集區中的所有其他 Edge Server 存取，或是可透過卸除式媒體進行傳輸，例如 USB 快閃磁碟機。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-p116">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

13. <span data-ttu-id="2416b-209">檢閱 [完成憑證匯出精靈]\*\*\*\* 中的摘要，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-209">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="2416b-210">在 [成功匯出] 對話方塊中，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2416b-210">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="2416b-211">按照本主題中的「若要匯入 Edge Server 外部介面的憑證」程序步驟，將匯出的憑證檔匯入其他 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="2416b-211">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="2416b-212">若要指派 Edge Server 外部介面的憑證</span><span class="sxs-lookup"><span data-stu-id="2416b-212">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="2416b-213">在每一部 Edge Server 的 [部署嚮導] 中，按一下 [ **步驟3：要求、安裝或指派憑證**] 旁邊的 [ **再執行**一次]。</span><span class="sxs-lookup"><span data-stu-id="2416b-213">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="2416b-214">在 **[可用憑證工作]** 頁面上，按一下 **[指派現有的憑證]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-214">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="2416b-215">在 **[憑證指派]** 頁面上，按一下 **[外部邊緣憑證]** 並選取 **[進階憑證用途]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2416b-215">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="2416b-216">在 **[進階憑證用途]** 頁面上，選取所有核取方塊以將憑證指派給所有用途。</span><span class="sxs-lookup"><span data-stu-id="2416b-216">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="2416b-217">在 **[憑證存放區]** 頁面上，選取您為 Edge Server 外部介面要求與匯入的公用憑證。</span><span class="sxs-lookup"><span data-stu-id="2416b-217">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2416b-218">如果您所要求與匯入的憑證不在清單中，可用的疑難排解方法之一就是確認憑證的主體名稱與主體別名符合憑證的所有需求，同時，如果您是手動匯入憑證與憑證鏈結 (而非使用先前的步驟進行)，表示該憑證位於正確的憑證存放區 (電腦憑證存放區，而非使用者或服務憑證存放區)。</span><span class="sxs-lookup"><span data-stu-id="2416b-218">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="2416b-219">在 **[憑證指派摘要]** 頁面上，檢閱您的設定，然後按 **[下一步]** 指派憑證。</span><span class="sxs-lookup"><span data-stu-id="2416b-219">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="2416b-220">在精靈完成頁面中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="2416b-220">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="2416b-221">在使用以上步驟指派邊緣憑證之後，開啟每部伺服器上的「憑證」嵌入式管理單元，並依序展開 **[憑證 (本機電腦)]** 和 **[個人]**，接著按一下 **[憑證]**，然後確認在詳細資料窗格中有列出該憑證。</span><span class="sxs-lookup"><span data-stu-id="2416b-221">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="2416b-222">如果您的部署範圍包括多部 Edge Server，請為每部 Edge Server 重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="2416b-222">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

