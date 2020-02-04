---
title: Lync Server 2013：設定內部邊緣介面的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6e462bdc629308493799c857ecb6b2434dc268
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="04952-102">在 Lync Server 2013 中設定內部邊緣介面的憑證</span><span class="sxs-lookup"><span data-stu-id="04952-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04952-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="04952-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="04952-104">當您執行證書嚮導時，請確定您使用的帳戶是群組的成員，而該群組已獲指派您要使用之憑證範本類型的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="04952-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="04952-105">根據預設，Lync Server 2013 證書要求會使用 Web 服務器憑證範本。</span><span class="sxs-lookup"><span data-stu-id="04952-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="04952-106">如果您使用的帳戶是 RTCUniversalServerAdmins 群組的成員，以使用此範本來申請憑證，請確認該群組已獲指派使用該範本所需的 [註冊] 許可權。</span><span class="sxs-lookup"><span data-stu-id="04952-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="04952-107">每個 Edge 伺服器的內部介面都需要單一憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="04952-108">內部介面的憑證可以由內部企業憑證授權單位（CA）或公用 CA 所頒發。</span><span class="sxs-lookup"><span data-stu-id="04952-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="04952-109">如果您的組織已部署內部 CA，您可以使用內部 CA 頒發內部介面的憑證，以節省使用公用憑證的費用。</span><span class="sxs-lookup"><span data-stu-id="04952-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="04952-110">您可以使用內部 Windows Server 2008 CA 或 Windows Server 2008 R2 CA 來建立這些憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="04952-111">如需有關此和其他證書需求的詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取證書需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="04952-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="04952-112">若要在網站的內部邊緣介面上設定憑證，請使用本節中的程式來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="04952-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="04952-113">將內部介面的 CA 認證鏈下載到每個 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="04952-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="04952-114">在每個 Edge 伺服器上匯入內部介面的 CA 認證鏈。</span><span class="sxs-lookup"><span data-stu-id="04952-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="04952-115">在一台邊緣伺服器（稱為第一台邊緣伺服器）上建立內部介面的憑證要求。</span><span class="sxs-lookup"><span data-stu-id="04952-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="04952-116">匯入第一台邊緣伺服器上的內部介面憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="04952-117">匯入此網站的其他邊緣伺服器（或部署在此負載平衡器之後）中的憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="04952-118">指派每個邊緣伺服器的內部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="04952-119">如果您有一個以上的網站有邊緣伺服器（也就是多網站邊緣拓朴），或是部署在不同負載平衡器之後的個別邊緣伺服器集，您必須針對每個有 Edge 伺服器的網站，以及每一組邊緣伺服器執行下列步驟。部署在不同的負載平衡器後。</span><span class="sxs-lookup"><span data-stu-id="04952-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04952-120">本節中的程式步驟是依據使用 Windows Server&nbsp;2008 CA、windows server&nbsp;2008&nbsp;R2 ca、Windows server 2012 CA 或 Windows server 2012 R2 Ca 來建立每個 Edge 伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="04952-121">如需任何其他 CA 的逐步指導方針，請參閱該 CA 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="04952-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="04952-122">根據預設，所有經過驗證的使用者都有適當的使用者許可權來申請證書。</span><span class="sxs-lookup"><span data-stu-id="04952-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="04952-123">本節中的程式是以邊緣伺服器部署程式的一部分在 Edge 伺服器上建立憑證要求的基礎。</span><span class="sxs-lookup"><span data-stu-id="04952-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="04952-124">您可以使用前端伺服器來建立證書申請。</span><span class="sxs-lookup"><span data-stu-id="04952-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="04952-125">您可以這樣做，在開始部署邊緣伺服器前，在規劃和部署程式的初期完成證書申請。</span><span class="sxs-lookup"><span data-stu-id="04952-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="04952-126">若要這樣做，您必須確保您要求的憑證是使用可匯出的私密金鑰來定義。</span><span class="sxs-lookup"><span data-stu-id="04952-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="04952-127">本節中的程式說明如何針對憑證使用 .cer 和. p7b 檔案。</span><span class="sxs-lookup"><span data-stu-id="04952-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="04952-128">如果您使用不同的檔案類型，請視情況修改這些程式。</span><span class="sxs-lookup"><span data-stu-id="04952-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="04952-129">使用 certsrv 網站下載內部介面的 CA 認證鏈</span><span class="sxs-lookup"><span data-stu-id="04952-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="04952-130">以系統**管理員**群組成員的身分登入內部網路（也就是 Edge 伺服器）中的 Lync server 2013 伺服器。</span><span class="sxs-lookup"><span data-stu-id="04952-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="04952-131">按一下 [**開始**]，按一下 [**執行**]，然後輸入下列命令，在命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="04952-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="04952-132">例如：</span><span class="sxs-lookup"><span data-stu-id="04952-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04952-133">如果您使用的是 Windows Server 2008 或 Windows Server 2008 R2 enterprise CA，您必須使用 HTTPs，而不是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="04952-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="04952-134">在發證 CA 的 certsrv 網頁上的 [**選取工作**] 底下，按一下 [**下載 CA 憑證、憑證連結或 CRL**]。</span><span class="sxs-lookup"><span data-stu-id="04952-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="04952-135">在 [**下載 Ca 憑證、憑證連結或 CRL**] 底下，按一下 [**下載 ca 憑證連結**]。</span><span class="sxs-lookup"><span data-stu-id="04952-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="04952-136">在 [檔案**下載**] 對話方塊中，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="04952-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="04952-137">將. p7b 檔案儲存到伺服器上的硬碟，然後將它複製到每個 Edge 伺服器的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="04952-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04952-138">. P7b 檔案包含憑證路徑中所有的憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="04952-139">若要查看憑證路徑，請開啟伺服器憑證，然後按一下憑證路徑。</span><span class="sxs-lookup"><span data-stu-id="04952-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="04952-140">使用 MMC 匯出內部介面的 CA 憑證鏈</span><span class="sxs-lookup"><span data-stu-id="04952-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="04952-141">您可以使用 Microsoft 管理主控台（MMC），從任何加入網域的電腦匯出 CA 根憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="04952-142">按一下 [**開始**]，按一下 [**執行**]，然後輸入 [ **MMC**]。</span><span class="sxs-lookup"><span data-stu-id="04952-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="04952-143">在 MMC 主控台中，按一下 [檔案 **]，然後按一下 [\*\*\*\*新增/移除**]。</span><span class="sxs-lookup"><span data-stu-id="04952-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="04952-144">從 [**新增或移除管理單元**] 對話方塊清單中，選取 [**憑證**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="04952-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="04952-145">出現提示時，請選取 [**電腦帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="04952-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="04952-146">在 [**選取電腦**] 對話方塊中，選取 [**本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="04952-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="04952-147">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="04952-147">Click **Finish**.</span></span> <span data-ttu-id="04952-148">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04952-148">Click **OK**.</span></span>

4.  <span data-ttu-id="04952-149">展開 **[憑證（本機電腦）**]。</span><span class="sxs-lookup"><span data-stu-id="04952-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="04952-150">展開 [**受信任的根憑證授權單位**]，選取 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="04952-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="04952-151">按一下您的 CA 所頒發的根憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="04952-152">以滑鼠右鍵按一下憑證，選取 [**所有任務**]，選取 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="04952-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="04952-153">[**證書匯出] 嚮導**隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="04952-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="04952-154">在 [**證書匯出嚮導]** 中，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="04952-155">在 [**匯出檔案格式**] 對話方塊中，選取要匯出的格式。</span><span class="sxs-lookup"><span data-stu-id="04952-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="04952-156">我們建議將**加密訊息語法標準– PKCS \#7 憑證（。P7B）**。</span><span class="sxs-lookup"><span data-stu-id="04952-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="04952-157">如果您選取**加密郵件語法標準-PKCS \#7 憑證（。P7B）**，請選取 [**如果可能的話，包括憑證路徑中的所有憑證**] 核取方塊，以匯出憑證連結，包括根 ca 憑證及任何中間 ca 憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="04952-158">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-158">Click **Next**.</span></span>

8.  <span data-ttu-id="04952-159">在 [檔案名] 專案的 [**要匯出**的檔案] 對話方塊中，輸入匯出憑證的路徑和檔案名（預設副檔名為. p7b）。</span><span class="sxs-lookup"><span data-stu-id="04952-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="04952-160">您也可以按一下 **[流覽]**，找出要將匯出的憑證放入其中的目錄，並提供匯出憑證的名稱。</span><span class="sxs-lookup"><span data-stu-id="04952-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="04952-161">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="04952-161">Click **Save**.</span></span> <span data-ttu-id="04952-162">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-162">Click **Next**.</span></span>

9.  <span data-ttu-id="04952-163">查看動作摘要，然後按一下 **[完成]** 以完成憑證的匯出。</span><span class="sxs-lookup"><span data-stu-id="04952-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="04952-164">按一下 **[確定]** 以確認匯出成功。</span><span class="sxs-lookup"><span data-stu-id="04952-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="04952-165">若要匯入內部介面的 CA 認證鏈</span><span class="sxs-lookup"><span data-stu-id="04952-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="04952-166">在每個邊緣伺服器上，按一下 [**開始**]，按一下 [**執行**]，在 [**開啟**] 方塊中輸入**MMC** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="04952-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="04952-167">**在 [檔案**] 功能表上，按一下 [**新增/移除管理單元**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="04952-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="04952-168">在 [**新增獨立的管理單元**] 方塊中，按一下 [**憑證**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="04952-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="04952-169">在 [**憑證管理單元**] 對話方塊中，按一下 [**電腦帳戶**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="04952-170">在 [**選取電腦**] 對話方塊中，確認已選取 [**本機電腦（執行此主控台的電腦）** ] 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="04952-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="04952-171">按一下 [**關閉**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="04952-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="04952-172">在主控台樹中，展開 [**憑證（本機電腦）**]，以滑鼠右鍵按一下 [**受信任的根憑證授權單位**]，指向 [**所有任務**]，然後按一下 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="04952-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="04952-173">在嚮導的 [**要匯入**的檔案] 中，指定憑證的檔案名（也就是您在下載上述程式中內部介面的 CA 憑證鏈時所指定的名稱）。</span><span class="sxs-lookup"><span data-stu-id="04952-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="04952-174">在每個 Edge 伺服器上重複此程式。</span><span class="sxs-lookup"><span data-stu-id="04952-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="04952-175">建立內部介面的憑證要求</span><span class="sxs-lookup"><span data-stu-id="04952-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="04952-176">在其中一個邊緣伺服器上，啟動 [部署嚮導]，然後在**步驟3： [要求**]、[安裝] 或 [指派憑證] 旁，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="04952-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04952-177">如果您有多個 Edge 伺服器位於某個池中的一個位置，您可以在任何一台邊緣伺服器上執行憑證嚮導。</span><span class="sxs-lookup"><span data-stu-id="04952-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="04952-178">第一次執行步驟3之後，該按鈕會變更為 [<STRONG>再次執行</STRONG>]，而綠色的核取記號表示任務成功完成，直到所有需要的憑證都已要求、已安裝並指派為止。</span><span class="sxs-lookup"><span data-stu-id="04952-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="04952-179">在 [**可用的憑證**工作] 頁面上，按一下 [**建立新的憑證要求**]。</span><span class="sxs-lookup"><span data-stu-id="04952-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="04952-180">在 [**憑證要求**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="04952-181">在 [**延遲] 或 [立即要求**] 頁面上，按一下 **[立即準備要求]，但稍後再傳送**。</span><span class="sxs-lookup"><span data-stu-id="04952-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="04952-182">在 [**憑證要求**檔案] 頁面上，輸入要儲存申請的完整路徑和檔案名（例如， **c：\\cert\_內部\_邊緣. cer**）。</span><span class="sxs-lookup"><span data-stu-id="04952-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="04952-183">若要使用預設 Web 文件範本以外的範本，請在 [**指定備用憑證範本**] 頁面上，選取 [**針對所選憑證授權單位使用替代憑證範本**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04952-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="04952-184">在 [**名稱及安全性設定**] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="04952-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="04952-185">在 [**易記名稱**] 中，輸入憑證的顯示名稱（例如，內部邊緣）。</span><span class="sxs-lookup"><span data-stu-id="04952-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="04952-186">在 [**位長**] 中，指定位長（通常是預設值**2048**）。</span><span class="sxs-lookup"><span data-stu-id="04952-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="04952-187">較高的位長會提供更多安全性，但對速度有負面影響。</span><span class="sxs-lookup"><span data-stu-id="04952-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="04952-188">如果憑證必須是可匯出的，請選取 [將**證書私密金鑰標示為可匯出**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04952-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="04952-189">在 [**組織資訊**] 頁面上，輸入組織的名稱和組織單位（OU）（例如，部門或部門）。</span><span class="sxs-lookup"><span data-stu-id="04952-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="04952-190">在 [**地理資訊**] 頁面上，指定位置資訊。</span><span class="sxs-lookup"><span data-stu-id="04952-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="04952-191">在 [ **Subject 名稱/主旨替換名稱**] 頁面上，會顯示要由嚮導自動填入的資訊。</span><span class="sxs-lookup"><span data-stu-id="04952-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="04952-192">在 [**設定其他消費者替換名稱**] 頁面上，指定任何所需的其他消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="04952-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="04952-193">在 [**要求摘要**] 頁面上，檢查要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="04952-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="04952-194">在命令完成之後，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="04952-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="04952-195">若要查看憑證申請的記錄，請按一下 [**查看記錄**]。</span><span class="sxs-lookup"><span data-stu-id="04952-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="04952-196">若要完成證書申請，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="04952-197">在 [**憑證要求**檔案] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="04952-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="04952-198">若要查看產生的憑證簽署要求（CSR）檔案，請按一下 [View] （**查看**）。</span><span class="sxs-lookup"><span data-stu-id="04952-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="04952-199">若要關閉嚮導，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="04952-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="04952-200">將此檔案提交給您的 CA （依電子郵件或貴組織針對您的企業 CA 所支援的其他方法），當您收到回應檔案時，請將新憑證複製到此電腦，以供匯入。</span><span class="sxs-lookup"><span data-stu-id="04952-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="04952-201">匯入內部介面的憑證</span><span class="sxs-lookup"><span data-stu-id="04952-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="04952-202">登入您以本機管理員群組成員的身分建立證書申請的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="04952-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="04952-203">在 [部署嚮導] 的 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**再次執行**]。</span><span class="sxs-lookup"><span data-stu-id="04952-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="04952-204">第一次執行步驟3之後，該按鈕會變更為**再次執行**，但綠色的核取記號（表示工作成功完成）不會顯示，直到所有需要的憑證都已要求、已安裝並指派為止。</span><span class="sxs-lookup"><span data-stu-id="04952-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="04952-205">在 [**可用的憑證**工作] 頁面上，按一下 [**從 a 匯入憑證]。P7b、.pfx 或 .cer**檔案。</span><span class="sxs-lookup"><span data-stu-id="04952-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="04952-206">在 [匯**入憑證**] 頁面上，輸入您針對此 Edge 伺服器的內部介面所要求及收到之憑證的完整路徑和檔案名（或按一下 **[流覽]** 以找出並選取該檔案）。</span><span class="sxs-lookup"><span data-stu-id="04952-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="04952-207">如果您要匯入擁有私密金鑰之憑證的其他成員的憑證，請選取 [憑證檔案**包含 certifcate 的私人金鑰**] 核取方塊，然後指定密碼。</span><span class="sxs-lookup"><span data-stu-id="04952-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="04952-208">在池中使用 Edge 伺服器的私人金鑰匯出憑證</span><span class="sxs-lookup"><span data-stu-id="04952-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="04952-209">以系統管理員群組的成員身分登入您匯入憑證的相同邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="04952-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="04952-210">按一下 [**開始**]，按一下 [**執行**]，然後輸入 [ **MMC**]。</span><span class="sxs-lookup"><span data-stu-id="04952-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="04952-211">從 MMC 主控台，按一下 [檔案 **]，然後按一下 [\*\*\*\*新增/移除管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="04952-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="04952-212">從 [新增或移除管理單元] 頁面上，按一下 [**憑證**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="04952-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="04952-213">在 [憑證] 管理單元中，選取 [**電腦帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="04952-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="04952-214">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-214">Click **Next**.</span></span> <span data-ttu-id="04952-215">在 [選取電腦] 中，選取 **[本機電腦：] （此主機正在執行的電腦）**。</span><span class="sxs-lookup"><span data-stu-id="04952-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="04952-216">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="04952-216">Click **Finish**.</span></span> <span data-ttu-id="04952-217">按一下 **[確定]** 以完成 MMC 主控台的設定。</span><span class="sxs-lookup"><span data-stu-id="04952-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="04952-218">按兩下 **[憑證（本機電腦）** ]，展開證書存放區。</span><span class="sxs-lookup"><span data-stu-id="04952-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="04952-219">按兩下 [**個人**]，然後按兩下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="04952-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="04952-220">如果在本機電腦的 [憑證個人] 存放區中沒有任何憑證，就表示沒有與所匯入的憑證相關聯的私用金鑰。</span><span class="sxs-lookup"><span data-stu-id="04952-220">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="04952-221">查看要求和匯入步驟。</span><span class="sxs-lookup"><span data-stu-id="04952-221">Review the request and import steps.</span></span> <span data-ttu-id="04952-222">如果問題持續發生，請與您的憑證授權單位系統管理員或提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="04952-222">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="04952-223">在本機電腦的 [認證個人] 商店中，以滑鼠右鍵按一下您要匯出的憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="04952-224">按一下 [**所有任務**]，然後按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="04952-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="04952-225">在 [證書匯出嚮導] 中，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="04952-226">選取 **[是，匯出私人金鑰]**。</span><span class="sxs-lookup"><span data-stu-id="04952-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="04952-227">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04952-228">如果選取 [<STRONG>是]，則無法使用 [匯出私密金鑰]</STRONG> ，不會將與此憑證相關的私密金鑰標示為 [匯出]。</span><span class="sxs-lookup"><span data-stu-id="04952-228">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="04952-229">您將需要再次要求證書，確保在您繼續匯出之前，已將憑證標示為允許匯出該私用金鑰。</span><span class="sxs-lookup"><span data-stu-id="04952-229">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="04952-230">請與您的憑證授權單位系統管理員或提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="04952-230">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="04952-231">在 [匯出檔案格式] 對話方塊中，選取 [**個人資訊\#交換– PKCS 12 （。PFX）** ，然後選取下列專案：</span><span class="sxs-lookup"><span data-stu-id="04952-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="04952-232">如果可能的話，請在憑證路徑中包含所有憑證</span><span class="sxs-lookup"><span data-stu-id="04952-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="04952-233">匯出所有延伸屬性</span><span class="sxs-lookup"><span data-stu-id="04952-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="04952-234">從 Edge 伺服器匯出憑證時，請不要選取<STRONG>[如果匯出成功，則刪除金鑰</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="04952-234">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="04952-235">選取此選項時，系統會要求您將憑證和私密金鑰匯入此 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="04952-235">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="04952-236">請按 [下一步]\*\*\*\* 繼續。</span><span class="sxs-lookup"><span data-stu-id="04952-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="04952-237">如果您要指派密碼來保護私人金鑰，請輸入私密金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="04952-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="04952-238">重新輸入密碼以進行確認。</span><span class="sxs-lookup"><span data-stu-id="04952-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="04952-239">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-239">Click **Next**.</span></span>

11. <span data-ttu-id="04952-240">針對匯出的憑證輸入路徑和檔案名，並使用 .pfx 副檔名。</span><span class="sxs-lookup"><span data-stu-id="04952-240">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="04952-241">路徑必須可由池中的所有其他邊緣伺服器存取，或可透過卸除式媒體（例如 USB 快閃記憶體磁片磁碟機）傳輸。</span><span class="sxs-lookup"><span data-stu-id="04952-241">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="04952-242">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="04952-242">Click **Next**.</span></span>

12. <span data-ttu-id="04952-243">在 [完成證書匯出嚮導] 對話方塊中查看摘要資訊。</span><span class="sxs-lookup"><span data-stu-id="04952-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="04952-244">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="04952-244">Click **Finish**.</span></span>

13. <span data-ttu-id="04952-245">按一下 [成功匯出] 對話方塊中的 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="04952-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="04952-246">按照[針對 Lync Server 2013 程式的外部邊緣介面設定憑證](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md)中所述的步驟，將匯出的憑證檔案匯入到其他邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="04952-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="04952-247">在邊緣伺服器上指派內部憑證</span><span class="sxs-lookup"><span data-stu-id="04952-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="04952-248">在每個 Edge 伺服器的 [部署嚮導] 中，在 [**步驟3：要求、安裝或指派憑證**] 旁，按一下 [**再次執行**]。</span><span class="sxs-lookup"><span data-stu-id="04952-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="04952-249">在 [**可用的憑證**工作] 頁面上，按一下 [**指派現有的憑證**]。</span><span class="sxs-lookup"><span data-stu-id="04952-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="04952-250">在 [**憑證指派**] 頁面上，選取清單中的 [**邊緣內部**]。</span><span class="sxs-lookup"><span data-stu-id="04952-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="04952-251">在 [**憑證存放區**] 頁面上，選取您針對內部邊緣所匯入的憑證（從上一個程式）。</span><span class="sxs-lookup"><span data-stu-id="04952-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="04952-252">在 [**憑證指派摘要**] 頁面上，查看您的設定，然後按一下 **[下一步]** ，指派憑證。</span><span class="sxs-lookup"><span data-stu-id="04952-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="04952-253">在 [嚮導完成] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="04952-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="04952-254">使用此程式來指派內部邊緣證書之後，請在每個伺服器上開啟 [憑證] 管理單元、展開 **[憑證（本機電腦）**]、[**個人**]、[**憑證**]，然後在 [詳細資料] 窗格中，確認 [內部邊緣] 憑證已列出。</span><span class="sxs-lookup"><span data-stu-id="04952-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="04952-255">如果您的部署包含多個邊緣伺服器，請針對每個邊緣伺服器重複執行此程式。</span><span class="sxs-lookup"><span data-stu-id="04952-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

