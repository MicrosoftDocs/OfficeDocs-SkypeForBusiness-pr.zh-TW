---
title: Lync Server 2013：設定外部 Edge 介面的憑證
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
ms.openlocfilehash: c1c836191c19eeadd915d0263c89b52289f60fe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="f8681-102">針對 Lync Server 2013 設定外部 Edge 介面的憑證</span><span class="sxs-lookup"><span data-stu-id="f8681-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8681-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f8681-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f8681-104">當您執行證書嚮導時，請確定您使用的帳戶是群組的成員，而該群組已獲指派您要使用之憑證範本類型的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="f8681-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="f8681-105">根據預設，Lync 伺服器憑證要求會使用 Web 服務器憑證範本。</span><span class="sxs-lookup"><span data-stu-id="f8681-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="f8681-106">如果您使用的帳戶是 RTCUniversalServerAdmins 群組的成員，以使用此範本來申請憑證，請確認該群組已獲指派使用該範本所需的 [註冊] 許可權。</span><span class="sxs-lookup"><span data-stu-id="f8681-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="f8681-107">每個 Edge 伺服器在周邊網路與網際網路之間的介面上，都需要一個公用憑證，而證書的受領人備用名稱必須包含 [存取邊緣服務] 和 [Web 會議 Edge 服務] 的外部名稱，完全合格的功能變數名稱（Fqdn）。</span><span class="sxs-lookup"><span data-stu-id="f8681-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="f8681-108">如需有關此和其他證書需求的詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取證書需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f8681-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="f8681-109">若要在公用憑證授權單位（Ca）清單中提供符合整合通訊憑證特定需求的憑證，並與 Microsoft 取得合作，以確保他們能使用 Lync Server 2013 憑證嚮導，請參閱 Microsoft 知識庫文章929395：「Exchange Server 和通訊伺服器的整合通訊憑證合作夥伴」 [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)。</span><span class="sxs-lookup"><span data-stu-id="f8681-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="f8681-110">在外部介面上設定憑證</span><span class="sxs-lookup"><span data-stu-id="f8681-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="f8681-111">若要在網站的外部邊緣介面上設定憑證，請使用本節中的程式來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f8681-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="f8681-112">針對 Edge 伺服器的外部介面建立證書申請。</span><span class="sxs-lookup"><span data-stu-id="f8681-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="f8681-113">向您的公用 CA 提交申請。</span><span class="sxs-lookup"><span data-stu-id="f8681-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="f8681-114">匯入每個 Edge 伺服器外部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="f8681-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="f8681-115">指派每個 Edge 伺服器外部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="f8681-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="f8681-116">如果您的部署包含多個邊緣伺服器，請匯出憑證及其私密金鑰，然後將它複製到其他邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8681-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="f8681-117">然後，針對每個邊緣伺服器將其匯入，然後依前面所述將它指派給它。</span><span class="sxs-lookup"><span data-stu-id="f8681-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="f8681-118">針對每個邊緣伺服器重複此程式。</span><span class="sxs-lookup"><span data-stu-id="f8681-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="f8681-119">您可以直接從公用憑證授權單位（CA）要求公用證書（例如從公用 CA 的網站）。</span><span class="sxs-lookup"><span data-stu-id="f8681-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="f8681-120">本節中的程式會針對大多數憑證工作使用憑證嚮導。</span><span class="sxs-lookup"><span data-stu-id="f8681-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="f8681-121">如果您選擇直接從公用 CA 申請憑證，您將需要修改每個程式，以要求、傳輸及匯入憑證，也可以匯入憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="f8681-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="f8681-122">當您從外部 CA 申請憑證時，提供的認證必須具備從該 CA 要求憑證的許可權。</span><span class="sxs-lookup"><span data-stu-id="f8681-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="f8681-123">每個 CA 都有一個安全原則，可定義哪些認證（也就是特定的使用者和群組名稱）可要求、頒發、管理或讀取證書。</span><span class="sxs-lookup"><span data-stu-id="f8681-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="f8681-124">如果您決定使用憑證 Microsoft 管理主控台（MMC）匯入憑證連結和憑證，您必須將其匯入到電腦的憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="f8681-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="f8681-125">如果您將它們匯入到 [使用者] 或 [服務] 憑證存放區，則在 Lync Server 2013 憑證嚮導中將無法使用該憑證指派。</span><span class="sxs-lookup"><span data-stu-id="f8681-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="f8681-126">建立邊緣伺服器外部介面的憑證要求</span><span class="sxs-lookup"><span data-stu-id="f8681-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="f8681-127">在 Edge 伺服器的 [部署嚮導] 中，在 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**再次執行**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8681-128">如果您的組織想要支援與 AOL 的公用立即訊息（IM）連線，您就無法使用 Lync Server 部署嚮導來要求認證。</span><span class="sxs-lookup"><span data-stu-id="f8681-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="f8681-129">請改為在本主題稍後的 [建立 Edge 伺服器外部介面的憑證要求，以支援公用 IM 連線] 程式中執行步驟。</span><span class="sxs-lookup"><span data-stu-id="f8681-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="f8681-130">如果您有多個 Edge 伺服器位於某個池中的一個位置，您可以在任何一台邊緣伺服器上執行 Lync Server 2013 憑證嚮導。</span><span class="sxs-lookup"><span data-stu-id="f8681-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="f8681-131">在 [**可用的憑證**工作] 頁面上，按一下 [**建立新的憑證要求**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="f8681-132">在 [**憑證要求**] 頁面上，按一下 [**外部邊緣憑證**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="f8681-133">在 [**延遲] 或 [立即要求**] 頁面上，選取 [**立即準備要求，但稍後傳送**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f8681-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="f8681-134">在 [**憑證要求**檔案] 頁面上，輸入要儲存申請之檔案的完整路徑和檔案名（例如，c：\\cert\_外部\_edge）。</span><span class="sxs-lookup"><span data-stu-id="f8681-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="f8681-135">若要使用預設 Web 文件範本以外的範本，請在 [**指定備用憑證範本**] 頁面上，選取 [**針對所選的憑證授權單位使用替代憑證範本**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f8681-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="f8681-136">在 [**名稱及安全性設定**] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f8681-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="f8681-137">在 [**易記名稱**] 中，輸入憑證的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="f8681-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="f8681-138">在 [**位長**] 中，指定位長（通常是預設值**2048**）。</span><span class="sxs-lookup"><span data-stu-id="f8681-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="f8681-139">確認已選取 [將**憑證私人金鑰標示為可匯出**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f8681-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="f8681-140">在 [**組織資訊**] 頁面上，輸入組織的名稱和組織單位（例如，部門或部門）。</span><span class="sxs-lookup"><span data-stu-id="f8681-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="f8681-141">在 [**地理資訊**] 頁面上，指定位置資訊。</span><span class="sxs-lookup"><span data-stu-id="f8681-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="f8681-142">在 [ **Subject 名稱/主旨替換名稱**] 頁面上，會顯示要由嚮導自動填入的資訊。</span><span class="sxs-lookup"><span data-stu-id="f8681-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="f8681-143">如果需要額外的消費者替換名稱，請在接下來的兩個步驟中加以指定。</span><span class="sxs-lookup"><span data-stu-id="f8681-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="f8681-144">在 [**受領人替代名稱（san）** ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\> [主題替換名稱] 清單中的專案。</span><span class="sxs-lookup"><span data-stu-id="f8681-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="f8681-145">在 [**設定其他消費者替換名稱**] 頁面上，指定任何所需的其他消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="f8681-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="f8681-146">在 [**要求摘要**] 頁面上，查看要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="f8681-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="f8681-147">在命令完成執行之後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f8681-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="f8681-148">若要查看憑證申請的記錄，請按一下 [**查看記錄**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="f8681-149">若要完成證書申請，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="f8681-150">在 [**憑證要求**檔案] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f8681-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="f8681-151">若要查看產生的憑證簽署要求（CSR）檔案，請按一下 [View] （**查看**）。</span><span class="sxs-lookup"><span data-stu-id="f8681-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="f8681-152">若要關閉嚮導，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="f8681-153">將輸出檔案複製到您可以將其提交至公用 CA 的位置。</span><span class="sxs-lookup"><span data-stu-id="f8681-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="f8681-154">建立邊緣伺服器外部介面的憑證要求，以支援與 AOL 的公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f8681-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="f8681-155">當 CA 提供所需的範本時，請從 Edge 伺服器使用下列 Windows PowerShell Cmdlet，以要求認證：</span><span class="sxs-lookup"><span data-stu-id="f8681-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="f8681-156">在 Lync Server 2013 中提供之範本的預設憑證名稱是 Web 服務器。</span><span class="sxs-lookup"><span data-stu-id="f8681-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="f8681-157">如果您需要\<使用不同\>于預設範本的範本，請只指定範本名稱。</span><span class="sxs-lookup"><span data-stu-id="f8681-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8681-158">如果您的組織想要支援與 AOL 的公用 IM 連線，您必須使用 Windows PowerShell，而不是憑證嚮導，以要求將憑證指派給存取邊緣服務的外部邊緣。</span><span class="sxs-lookup"><span data-stu-id="f8681-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="f8681-159">這是因為 [認證嚮導] 用來要求憑證的 Lync Server 2013 Web Server 範本不支援用戶端 EKU 設定。</span><span class="sxs-lookup"><span data-stu-id="f8681-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="f8681-160">在使用 Windows PowerShell 建立憑證前，CA 管理員必須建立並部署支援用戶端 EKU 的新範本。</span><span class="sxs-lookup"><span data-stu-id="f8681-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="f8681-161">將申請提交至公用憑證授權單位</span><span class="sxs-lookup"><span data-stu-id="f8681-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="f8681-162">開啟輸出檔案。</span><span class="sxs-lookup"><span data-stu-id="f8681-162">Open the output file.</span></span>

2.  <span data-ttu-id="f8681-163">複製並貼上憑證簽署要求（CSR）的內容。</span><span class="sxs-lookup"><span data-stu-id="f8681-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="f8681-164">如果出現提示，請指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="f8681-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="f8681-165">**Microsoft**作為伺服器平臺。</span><span class="sxs-lookup"><span data-stu-id="f8681-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="f8681-166">[ **IIS** ] 做為版本。</span><span class="sxs-lookup"><span data-stu-id="f8681-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="f8681-167">[ **Web 服務器**] 做為使用類型。</span><span class="sxs-lookup"><span data-stu-id="f8681-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="f8681-168">[ **PKCS7** ] 做為回應格式。</span><span class="sxs-lookup"><span data-stu-id="f8681-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="f8681-169">公用 CA 驗證您的資訊後，您會收到一封電子郵件訊息，其中包含您的憑證所需的文字。</span><span class="sxs-lookup"><span data-stu-id="f8681-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="f8681-170">從電子郵件訊息中複製文字，並將內容儲存在本機電腦上的文字檔（.txt）中。</span><span class="sxs-lookup"><span data-stu-id="f8681-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="f8681-171">若要匯入邊緣伺服器外部介面的憑證</span><span class="sxs-lookup"><span data-stu-id="f8681-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="f8681-172">以系統管理員群組的成員身分登入您建立證書申請的同一個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8681-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="f8681-173">在 [部署嚮導] 的 [**部署邊緣伺服器**] 頁面上，在 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**再次執行**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="f8681-174">在 [**可用的憑證**工作] 頁面上，按一下 [**從 p7b、pfx 或 .Cer 檔案匯入憑證**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="f8681-175">在 [匯**入憑證**] 頁面上，按一下 **[流覽]** ，找出並選取您針對 Edge 伺服器外部介面所要求的憑證（或者，您也可以輸入完整路徑和檔案名）。</span><span class="sxs-lookup"><span data-stu-id="f8681-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="f8681-176">如果憑證包含私密金鑰，請選取 [**憑證檔案包含憑證的專用金鑰**]，然後輸入私密金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="f8681-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="f8681-177">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-177">Click **Next**.</span></span>

5.  <span data-ttu-id="f8681-178">在 [匯**入憑證摘要**] 頁面上，查看摘要，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="f8681-179">在**執行命令**時，請查看匯入的結果，按一下 [**視需要查看記錄**]，然後按一下 **[完成]** 以完成證書匯入。</span><span class="sxs-lookup"><span data-stu-id="f8681-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="f8681-180">如果您正在設定 Edge 伺服器池，請依照本主題稍後的「在池中匯出證書及邊緣伺服器的私密金鑰」程式中所述的私密金鑰，匯出憑證及其私人金鑰。</span><span class="sxs-lookup"><span data-stu-id="f8681-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="f8681-181">將匯出的憑證檔案複製到其他邊緣伺服器，然後將其匯入到每個 Edge 伺服器的電腦存放區。</span><span class="sxs-lookup"><span data-stu-id="f8681-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="f8681-182">在池中使用 Edge 伺服器的私人金鑰匯出憑證</span><span class="sxs-lookup"><span data-stu-id="f8681-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="f8681-183">以系統管理員群組的成員身分登入您匯入憑證的相同邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8681-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="f8681-184">按一下 [**開始**]，按一下 [**執行**]，然後輸入 [ **MMC**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="f8681-185">在 Microsoft 管理主控台（MMC）主控台中，按一下 [檔案]，**然後按一下 [\*\*\*\*新增/移除管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="f8681-186">在 [**新增或移除管理單元**] 中，按一下 [**憑證**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="f8681-187">在 [**憑證**] 對話方塊中，選取 [**電腦帳戶**]，然後按 **[下一步]**，選取 [**本機電腦（執行此主控台的電腦）** **]，再**按一下 **[完成]** ，然後按一下 **[確定]** 以完成 MMC 主控台的設定。</span><span class="sxs-lookup"><span data-stu-id="f8681-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="f8681-188">按兩下 **[憑證（本機電腦）** ] 展開憑證存放區，按兩下 [**個人**]，然後按兩下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f8681-189">如果在本機電腦的 [憑證個人] 存放區中沒有任何憑證，就表示沒有與所匯入的憑證相關聯的私用金鑰。</span><span class="sxs-lookup"><span data-stu-id="f8681-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="f8681-190">查看要求和匯入步驟。</span><span class="sxs-lookup"><span data-stu-id="f8681-190">Review the request and import steps.</span></span> <span data-ttu-id="f8681-191">如果問題持續發生，請與您的憑證授權單位系統管理員或提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="f8681-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="f8681-192">在**本機電腦的 [認證個人] 商店**中，以滑鼠右鍵按一下您要匯出的憑證，按一下 [**所有**工作]，然後按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="f8681-193">在證書匯出嚮導中，按一下 **[下一步]**，選取 **[是，匯出私密金鑰**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8681-194">如果選取 [<STRONG>是]，則無法使用 [匯出私密金鑰]</STRONG> ，不會將與此憑證相關的私密金鑰標示為 [匯出]。</span><span class="sxs-lookup"><span data-stu-id="f8681-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="f8681-195">您將需要再次要求證書，確保在您繼續匯出之前，已將憑證標示為允許匯出該私用金鑰。</span><span class="sxs-lookup"><span data-stu-id="f8681-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="f8681-196">請與您的憑證授權單位系統管理員或提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="f8681-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="f8681-197">在 [匯出檔案格式] 對話方塊中，選取 [**個人資訊\#交換– PKCS 12 （。PFX）** ，然後選取下列專案：</span><span class="sxs-lookup"><span data-stu-id="f8681-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="f8681-198">如果可能的話，請在憑證路徑中包含所有憑證</span><span class="sxs-lookup"><span data-stu-id="f8681-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="f8681-199">匯出所有延伸屬性</span><span class="sxs-lookup"><span data-stu-id="f8681-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="f8681-200">從 Edge 伺服器匯出憑證時，請不要選取<STRONG>[如果匯出成功，則刪除金鑰</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="f8681-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="f8681-201">選取此選項時，系統會要求您將憑證和私密金鑰匯入此 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8681-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="f8681-202">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-202">Click **Next**.</span></span>

11. <span data-ttu-id="f8681-203">輸入私人金鑰的密碼，再輸入一次密碼以進行確認，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="f8681-204">針對匯出的憑證輸入路徑和檔案名，並使用 .pfx 副檔名。</span><span class="sxs-lookup"><span data-stu-id="f8681-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="f8681-205">路徑必須可由池中的所有其他邊緣伺服器存取，或可透過卸除式媒體（例如 USB 快閃記憶體磁片磁碟機）傳輸。</span><span class="sxs-lookup"><span data-stu-id="f8681-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="f8681-206">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-206">Click **Next**.</span></span>

13. <span data-ttu-id="f8681-207">在**完成證書匯出嚮導**中查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="f8681-208">在 [成功匯出] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="f8681-209">依照本主題先前的 [匯入 Edge 伺服器外部介面的憑證] 程式中所述的步驟，將匯出的憑證檔案匯入到其他邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8681-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="f8681-210">指派邊緣伺服器外部介面的憑證</span><span class="sxs-lookup"><span data-stu-id="f8681-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="f8681-211">在每個 Edge 伺服器的 [部署嚮導] 中，在 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**再次執行**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="f8681-212">在 [**可用的憑證**工作] 頁面上，按一下 [**指派現有的憑證**]。</span><span class="sxs-lookup"><span data-stu-id="f8681-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="f8681-213">在 [**憑證指派**] 頁面上，按一下 [**外部邊緣憑證**]，然後選取 [**高級證書使用**情況] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f8681-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="f8681-214">在 [**高級證書使用**情況] 頁面上，選取所有核取方塊以指派所有使用方式的憑證。</span><span class="sxs-lookup"><span data-stu-id="f8681-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="f8681-215">在 [**憑證存放區**] 頁面上，選取您針對 Edge 伺服器的外部介面所要求和匯入的公用憑證。</span><span class="sxs-lookup"><span data-stu-id="f8681-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8681-216">如果您要求和匯入的憑證不在清單中，其中一種問題就是確認證書的受領人名稱和主旨替換名稱符合憑證的所有需求，而且如果您手動匯入證書與憑證鏈，而不是使用上述程式，而是證書位於正確的憑證存放區（電腦憑證存放區，而不是使用者或服務證書儲存區）。</span><span class="sxs-lookup"><span data-stu-id="f8681-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="f8681-217">在 [**憑證指派摘要**] 頁面上，查看您的設定，然後按一下 **[下一步]** ，指派憑證。</span><span class="sxs-lookup"><span data-stu-id="f8681-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="f8681-218">在 [嚮導完成] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f8681-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="f8681-219">使用此程式指派邊緣憑證之後，請在每個伺服器上開啟 [憑證] 管理單元、展開 **[憑證（本機電腦）**]、[**個人**]、[**憑證**]，然後在 [詳細資料] 窗格中，確認已列出該憑證。</span><span class="sxs-lookup"><span data-stu-id="f8681-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="f8681-220">如果您的部署包含多個邊緣伺服器，請針對每個邊緣伺服器重複執行此程式。</span><span class="sxs-lookup"><span data-stu-id="f8681-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

