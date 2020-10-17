---
title: Lync Server 2013：設定內部 edge 介面的憑證
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
ms.openlocfilehash: f8f8c5c41eba828cb6514ba6963167d708ed203d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509890"
---
# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="5d72e-102">在 Lync Server 2013 中設定內部 edge 介面的憑證</span><span class="sxs-lookup"><span data-stu-id="5d72e-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d72e-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="5d72e-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5d72e-104">當您執行 [憑證精靈] 時，請確定您用來登入的帳戶，是具有您要使用之憑證範本類型適當權限的群組成員。</span><span class="sxs-lookup"><span data-stu-id="5d72e-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="5d72e-105">根據預設，Lync Server 2013 憑證要求會使用網頁伺服器憑證範本。</span><span class="sxs-lookup"><span data-stu-id="5d72e-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="5d72e-106">如果您要以 RTCUniversalServerAdmins 群組成員的帳戶使用此範本來要求憑證，請確定群組具有使用該範本所需的註冊權限。</span><span class="sxs-lookup"><span data-stu-id="5d72e-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="5d72e-107">在每一部 Edge Server 的內部介面上都需要一個憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="5d72e-108">內部企業憑證授權單位單位 (CA) 或公用 CA，可發出內部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="5d72e-109">如果您的組織已部署內部 CA，您可以使用內部 CA 發出內部介面的憑證，以節省使用公用憑證的費用。</span><span class="sxs-lookup"><span data-stu-id="5d72e-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="5d72e-110">您可以使用內部 Windows Server 2008 CA 或 Windows Server 2008 R2 CA 來建立這些憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="5d72e-111">如需此和其他憑證需求的詳細資訊，請參閱 [Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="5d72e-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="5d72e-112">若要在網站的內部 edge 介面上設定憑證，請使用本節中的程式執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="5d72e-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="5d72e-113">將內部介面的 CA 憑證鏈下載至每一部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="5d72e-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="5d72e-114">在每一部 Edge Server 上匯入內部介面的 CA 憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="5d72e-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="5d72e-115">在一部 Edge Server 上建立內部介面的憑證要求，稱為第一部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="5d72e-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="5d72e-116">在第一部 Edge Server 上匯入內部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="5d72e-117">在此網站上的其他 Edge Server 上匯入憑證 (或部署于此負載平衡器) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="5d72e-118">為每一部 Edge Server 的內部介面指派憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="5d72e-119">如果您有多個具有 Edge Server 的網站 (也就是說，多網站 edge 拓撲) 或個別的一組 Edge Server 部署在不同的負載平衡器之後，您必須針對每個具有 Edge Server 的網站，以及在不同負載平衡器之後部署的每一組 Edge Server 執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="5d72e-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d72e-120">本節中程式的步驟是根據使用 Windows Server &nbsp; 2008 CA、Windows server &nbsp; 2008 &nbsp; R2 Ca、WINDOWS server 2012 Ca 或 Windows SERVER 2012 R2 ca，為每個 Edge Server 建立憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="5d72e-121">如需其他 CA 的逐步指引，請參閱該 CA 的檔。</span><span class="sxs-lookup"><span data-stu-id="5d72e-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="5d72e-122">根據預設，所有經過驗證的使用者都有適當的使用者權限可要求憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="5d72e-123">本節中的程式是根據 Edge Server 部署程式的一部分，在 Edge Server 上建立憑證要求。</span><span class="sxs-lookup"><span data-stu-id="5d72e-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="5d72e-124">您可以使用前端伺服器建立憑證要求。</span><span class="sxs-lookup"><span data-stu-id="5d72e-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="5d72e-125">在您開始部署 Edge Server 之前，您可以執行這項作業，儘早完成憑證要求的規劃與部署程式。</span><span class="sxs-lookup"><span data-stu-id="5d72e-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="5d72e-126">若要這麼做，您必須確定您要求的憑證是使用可匯出的私密金鑰所定義。</span><span class="sxs-lookup"><span data-stu-id="5d72e-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="5d72e-127">本節中的程式說明如何使用 .cer 和憑證的 p7b 檔案。</span><span class="sxs-lookup"><span data-stu-id="5d72e-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="5d72e-128">如果您使用另一種類型的檔案，請視需要修改這些程式。</span><span class="sxs-lookup"><span data-stu-id="5d72e-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="5d72e-129">使用 certsrv 網站下載內部介面的 CA 憑證鏈</span><span class="sxs-lookup"><span data-stu-id="5d72e-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="5d72e-130">以系統 **管理員** 群組成員的身分，登入內部網路 (中的 Lync server 2013 伺服器，而非 Edge server) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="5d72e-131">按一下 [ **開始**]，按一下 [ **執行**]，然後輸入下列命令，在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5d72e-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="5d72e-132">例如：</span><span class="sxs-lookup"><span data-stu-id="5d72e-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d72e-133">如果您使用的是 Windows Server 2008 或 Windows Server 2008 R2 enterprise CA，您必須使用 HTTPs，而不是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="5d72e-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="5d72e-134">在發證 CA 的 certsrv 網頁上，按一下 [ **選取任務**] 底下的 [ **下載 CA 憑證、憑證鏈或 CRL**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="5d72e-135">在 [ **下載 Ca 憑證、憑證鏈或 CRL**] 底下，按一下 [ **下載 ca 憑證鏈**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="5d72e-136">在 **[檔案下載]** 對話方塊中，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="5d72e-137">將. p7b 檔案儲存至伺服器的硬碟磁碟機上，然後將它複製到每一部 Edge Server 上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="5d72e-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d72e-138">P7b 檔案包含憑證路徑中的所有憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="5d72e-139">若要查看憑證路徑，請開啟伺服器憑證，然後按一下憑證路徑。</span><span class="sxs-lookup"><span data-stu-id="5d72e-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="5d72e-140">若要使用 MMC 匯出內部介面的 CA 憑證鏈</span><span class="sxs-lookup"><span data-stu-id="5d72e-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="5d72e-141">您可以使用 Microsoft Management Console (MMC) ，從任何已加入網域的機器匯出 CA 根憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="5d72e-142">按一下 [ **開始**]，按一下 [ **執行**]，然後輸入 **MMC**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="5d72e-143">在 MMC 主控台 **中，按一下**[檔案]，然後按一下 [ **新增/移除**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="5d72e-144">從 [ **新增或移除嵌入式管理單元** ] 對話方塊清單中，選取 [ **憑證**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="5d72e-145">出現提示時，請選取 [ **電腦帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="5d72e-146">在 [ **選取電腦** ] 對話方塊中，選取 [ **本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="5d72e-147">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-147">Click **Finish**.</span></span> <span data-ttu-id="5d72e-148">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d72e-148">Click **OK**.</span></span>

4.  <span data-ttu-id="5d72e-149">展開 [ \*\*憑證 (本機電腦]) \*\*。</span><span class="sxs-lookup"><span data-stu-id="5d72e-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="5d72e-150">展開 **[信任的根憑證授權**單位]，然後選取 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="5d72e-151">按一下您的 CA 所簽發的根憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="5d72e-152">以滑鼠右鍵按一下憑證，選取 [ **所有**工作]，然後選取 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="5d72e-153">隨即會開啟 [ **憑證匯出] 嚮導** 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="5d72e-154">在 [憑證匯出精靈]\*\*\*\* 中，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d72e-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="5d72e-155">在 [ **匯出檔案格式** ] 對話方塊中，選取要匯出的格式。</span><span class="sxs-lookup"><span data-stu-id="5d72e-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="5d72e-156">建議您將 \*\*加密郵件語法標準– PKCS \# 7 憑證 (。P7B) \*\*。</span><span class="sxs-lookup"><span data-stu-id="5d72e-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="5d72e-157">如果您選取 \*\*密碼編譯郵件語法 Standard – PKCS \# 7 憑證 (。P7B) \*\*，選取 [ **如果可能的話，包含憑證路徑中的所有憑證** ] 核取方塊，以匯出憑證鏈，包括根 ca 憑證和任何中間 ca 憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="5d72e-158">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-158">Click **Next**.</span></span>

8.  <span data-ttu-id="5d72e-159">在 [檔案名] 專案中的 [ **要匯出** 的檔案] 對話方塊中，輸入路徑和檔案名 (預設副檔名為已匯出憑證的 p7b) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="5d72e-160">（選用）按一下 **[流覽]**，尋找要將匯出的憑證放入其中的目錄，並提供匯出憑證的名稱。</span><span class="sxs-lookup"><span data-stu-id="5d72e-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="5d72e-161">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-161">Click **Save**.</span></span> <span data-ttu-id="5d72e-162">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-162">Click **Next**.</span></span>

9.  <span data-ttu-id="5d72e-163">複查動作摘要，然後按一下 **[完成]** 完成憑證的匯出。</span><span class="sxs-lookup"><span data-stu-id="5d72e-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="5d72e-164">按一下 **[確定]** 確認成功的匯出。</span><span class="sxs-lookup"><span data-stu-id="5d72e-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="5d72e-165">若要匯入內部介面的 CA 憑證鏈</span><span class="sxs-lookup"><span data-stu-id="5d72e-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="5d72e-166">在每一部 Edge Server 上，按一下 [**開始**]，按一下 [**執行**]，然後在 [**開啟**] 方塊中輸入**MMC** ，然後按一下 **[確定]**，以開啟 Microsoft Management Console (MMC) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="5d72e-167">在 **[檔案]** 功能表中，按一下 **[新增/移除嵌入式管理單元]**，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="5d72e-168">在 **[新增獨立嵌入式管理單元]** 方塊中，按一下 **[憑證]**，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="5d72e-169">在 **[憑證嵌入式管理單元]** 對話方塊中，按一下 **[電腦帳戶]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="5d72e-170">在 **[選擇電腦]** 對話方塊中，確定 **[本機電腦: (執行這個主控台的電腦)]** 核取方塊已經選取，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="5d72e-171">按一下 **[關閉]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="5d72e-172">在主控台樹中，依序展開 [ \*\*憑證 (本機電腦]) \*\*中，以滑鼠右鍵按一下 **[信任的根憑證授權**單位]，指向 [ **所有**工作]，然後按一下 [匯 **入**]</span><span class="sxs-lookup"><span data-stu-id="5d72e-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="5d72e-173">在嚮導的 [ **要匯入**的檔案] 中，指定憑證 (的檔案名，也就是當您為先前程式中的內部介面下載 CA 憑證鏈) 時所指定的名稱。</span><span class="sxs-lookup"><span data-stu-id="5d72e-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="5d72e-174">在每一部 Edge Server 上重複此程式。</span><span class="sxs-lookup"><span data-stu-id="5d72e-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="5d72e-175">若要為內部介面建立憑證要求</span><span class="sxs-lookup"><span data-stu-id="5d72e-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="5d72e-176">在其中一部 Edge Server 上，啟動 [部署嚮導]，然後在 [ **步驟3：要求、安裝或指派憑證**] 旁邊，按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d72e-177">如果您在集區中的一個位置有多部 Edge Server，則可以在任何一部 Edge Server 上執行憑證嚮導。</span><span class="sxs-lookup"><span data-stu-id="5d72e-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="5d72e-178">在您第一次執行步驟3之後，按鈕將變更為 [ <STRONG>再執行</STRONG>一次]，直到要求、安裝並指派所有需要憑證之後，才會顯示一個綠色核取記號，表示成功完成任務。</span><span class="sxs-lookup"><span data-stu-id="5d72e-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="5d72e-179">在 **[可用憑證工作]** 頁面上，按一下 **[建立新憑證要求]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="5d72e-180">在 **[憑證要求]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="5d72e-181">在 [ **延遲或立即要求** ] 頁面上，按一下 **[立即準備此要求，但稍後再傳送**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="5d72e-182">在 [ **憑證要求** 檔案] 頁面上，輸入要儲存要求的完整路徑和檔案名 (例如， **c： \\ cert \_ internal \_ edge .cer**) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="5d72e-183">在 [ **指定替代的憑證範本** ] 頁面上，若要使用預設 WebServer 範本以外的範本，請選取 [對 **選取的憑證授權單位單位使用其他憑證範本** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5d72e-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="5d72e-184">在 **[名稱和安全性設定]** 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5d72e-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="5d72e-185">在 [ **易記名稱**] 中，輸入憑證 (的顯示名稱，例如，[內部 Edge]) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="5d72e-186">在 **[位元長度]** 中，指定位元長度 (預設值通常是 **2048**)。</span><span class="sxs-lookup"><span data-stu-id="5d72e-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5d72e-187">較高的位長度可提供更高的安全性，但是對速度有負面影響。</span><span class="sxs-lookup"><span data-stu-id="5d72e-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="5d72e-188">若憑證必須可匯出，請選取 [將 **憑證私密金鑰標示為可匯出** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5d72e-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="5d72e-189">在 [ **組織資訊** ] 頁面上，輸入組織的名稱和組織單位 (OU)  (例如，[部門] 或 [部門]) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="5d72e-190">在 **[地理資訊]** 頁面上，指定位置資訊。</span><span class="sxs-lookup"><span data-stu-id="5d72e-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="5d72e-191">在 **[主體名稱/主體別名]** 頁面上，會顯示精靈將自動填入的資訊。</span><span class="sxs-lookup"><span data-stu-id="5d72e-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="5d72e-192">在 **[設定其他主體替代名稱]** 頁面上，指定任何需要的其他主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="5d72e-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="5d72e-193">在 [ **要求摘要** ] 頁面上，複查將要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="5d72e-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="5d72e-194">命令完成之後，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5d72e-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="5d72e-195">若要檢視憑證要求記錄檔，按一下 **[檢視記錄檔]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="5d72e-196">若要完成憑證要求，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="5d72e-197">在 **[憑證要求檔案]** 頁面上，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5d72e-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="5d72e-198">若要檢視產生的憑證簽署要求 (CSR) 檔案，按一下 **[檢視]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="5d72e-199">按一下 **[完成]**，關閉精靈。</span><span class="sxs-lookup"><span data-stu-id="5d72e-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="5d72e-200">請將此檔案提交給您的 CA (您的企業 CA 所支援的電子郵件或其他方法) ，而且當您收到回應檔案時，請將新憑證複製到這部電腦，使其可供匯入。</span><span class="sxs-lookup"><span data-stu-id="5d72e-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="5d72e-201">若要匯入內部介面的憑證</span><span class="sxs-lookup"><span data-stu-id="5d72e-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="5d72e-202">以本機系統管理員群組成員的身分，登入建立憑證要求的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="5d72e-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="5d72e-203">在 [部署嚮導] 中，按一下 [ **步驟3：要求、安裝或指派憑證**] 旁邊的 [ **再執行一次**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="5d72e-204">在您第一次執行步驟3之後，按鈕將變更為 [ **再執行**一次]，但是綠色核取記號 (表示工作順利完成，除非要求、安裝並指派所有要求的憑證，否則不會顯示該任務) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="5d72e-205">在 [ **可用憑證** 工作] 頁面上，按一下 [匯 **入憑證自 a]。P7b、.pfx 或 .cer**檔案。</span><span class="sxs-lookup"><span data-stu-id="5d72e-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="5d72e-206">在 [匯 **入憑證** ] 頁面上，輸入您為此 Edge Server 的內部介面要求和接收之憑證的完整路徑和檔案名 (或按一下 **[流覽]** ，尋找並選取檔案) 。</span><span class="sxs-lookup"><span data-stu-id="5d72e-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="5d72e-207">若要匯入集區其他成員的憑證包含私密金鑰的憑證，請選取 [憑證檔案 **包含憑證的私密金鑰** ] 核取方塊，並指定密碼。</span><span class="sxs-lookup"><span data-stu-id="5d72e-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="5d72e-208">為集區中的 Edge Server 匯出包含私密金鑰的憑證</span><span class="sxs-lookup"><span data-stu-id="5d72e-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="5d72e-209">以 Administrators 群組成員身分登入剛才用來匯入憑證的同一部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="5d72e-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="5d72e-210">按一下 [開始]\*\*\*\*，按一下 [執行]\*\*\*\*，然後輸入 **MMC**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="5d72e-211">在 MMC 主控台中，按一下 [檔案 **]，然後**按一下 [ **新增/移除嵌入式管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="5d72e-212">在 [新增或移除嵌入式管理單元] 頁面上，按一下 [ **憑證**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="5d72e-213">在 [憑證嵌入式管理單元] 對話方塊中，選取 [ **電腦帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="5d72e-214">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-214">Click **Next**.</span></span> <span data-ttu-id="5d72e-215">在 [選取電腦] 中，選取 \*\*[本機電腦： (此主控台執行的電腦]) \*\*。</span><span class="sxs-lookup"><span data-stu-id="5d72e-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="5d72e-216">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-216">Click **Finish**.</span></span> <span data-ttu-id="5d72e-217">按一下 **[確定]** 完成 MMC 主控台的設定。</span><span class="sxs-lookup"><span data-stu-id="5d72e-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="5d72e-218">按兩下 [ \*\*憑證 (本機電腦]) \*\* 以展開憑證儲存區。</span><span class="sxs-lookup"><span data-stu-id="5d72e-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="5d72e-219">連按兩下 [ **個人**]，然後按兩下 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5d72e-p116">如果本機電腦的憑證個人存放區中沒有憑證，則匯入的憑證就沒有關聯的私密金鑰。請檢閱要求和匯入步驟。如果問題仍持續存在，請與您的憑證授權單位管理員或提供者連絡。</span><span class="sxs-lookup"><span data-stu-id="5d72e-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="5d72e-223">在本機電腦的 [憑證個人] 存放區中，以滑鼠右鍵按一下您要匯出的憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="5d72e-224">按一下 [ **所有**工作]，然後按一下 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="5d72e-225">在 [憑證匯出] 嚮導中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="5d72e-226">選取 **[是，匯出私密金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="5d72e-227">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d72e-p119">如果 [是，匯出私密金鑰]<STRONG></STRONG> 選項無法使用，則與該憑證關聯的私密金鑰就不會標示為可匯出。您需要重新申請憑證，確定憑證標示為允許匯出私密金鑰，才能繼續匯出。請與您的憑證授權單位管理員或提供者連絡。</span><span class="sxs-lookup"><span data-stu-id="5d72e-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="5d72e-231">在 [匯出檔案格式] 對話方塊中，選取 [ \*\*個人資訊交換– PKCS \# 12] (。PFX) \*\* 然後選取下列各項：</span><span class="sxs-lookup"><span data-stu-id="5d72e-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="5d72e-232">盡可能在憑證路徑中包含所有憑證</span><span class="sxs-lookup"><span data-stu-id="5d72e-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="5d72e-233">匯出所有延伸內容</span><span class="sxs-lookup"><span data-stu-id="5d72e-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="5d72e-p120">從 Edge Server 匯出憑證時，不要選取 [如果匯出成功即刪除私密金鑰]<STRONG></STRONG>。選取這個選項時，必須將憑證和私密金鑰匯入這個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="5d72e-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="5d72e-236">按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="5d72e-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="5d72e-237">如果您想要指派密碼來保護私密金鑰，請輸入私密金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="5d72e-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="5d72e-238">請重新輸入密碼以加以確認。</span><span class="sxs-lookup"><span data-stu-id="5d72e-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="5d72e-239">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-239">Click **Next**.</span></span>

11. <span data-ttu-id="5d72e-p122">輸入匯出憑證的路徑和檔案名稱，使用 .pfx 副檔名。路徑必須可供集區中的所有其他 Edge Server 存取，或是可透過卸除式媒體進行傳輸，例如 USB 快閃磁碟機。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d72e-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="5d72e-243">在 [完成憑證匯出嚮導] 對話方塊中查看摘要。</span><span class="sxs-lookup"><span data-stu-id="5d72e-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="5d72e-244">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-244">Click **Finish**.</span></span>

13. <span data-ttu-id="5d72e-245">在 [成功匯出] 對話方塊中，按一下 **[確定** ]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="5d72e-246">遵循為 [Lync Server 2013 程式設定外部 edge 介面的憑證](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) 中所述的步驟，將匯出的憑證檔案匯入其他 Edge server。</span><span class="sxs-lookup"><span data-stu-id="5d72e-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="5d72e-247">在 Edge Server 上指派內部憑證</span><span class="sxs-lookup"><span data-stu-id="5d72e-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="5d72e-248">在每一部 Edge Server 的 [部署嚮導] 中，按一下 [ **步驟3：要求、安裝或指派憑證**] 旁邊的 [ **再執行**一次]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="5d72e-249">在 **[可用憑證工作]** 頁面上，按一下 **[指派現有的憑證]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="5d72e-250">在 [ **憑證指派** ] 頁面上，選取清單中的 [ **Edge Internal** ]。</span><span class="sxs-lookup"><span data-stu-id="5d72e-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="5d72e-251">在 [ **憑證儲存區** ] 頁面上，選取您為內部 edge 匯入的憑證，以供先前程式)  (。</span><span class="sxs-lookup"><span data-stu-id="5d72e-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="5d72e-252">在 **[憑證指派摘要]** 頁面上，檢閱您的設定，然後按 **[下一步]** 指派憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="5d72e-253">在精靈完成頁面中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="5d72e-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="5d72e-254">使用此程式指派內部 edge 憑證之後，請在每個伺服器上開啟憑證嵌入式管理單元，展開 [ \*\*憑證 (本機電腦]) \*\*，展開 [ **個人**]，按一下 [ **憑證**]，然後在詳細資料窗格中列出內部 edge 憑證。</span><span class="sxs-lookup"><span data-stu-id="5d72e-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="5d72e-255">如果您的部署範圍包括多部 Edge Server，請為每部 Edge Server 重複這個程序。</span><span class="sxs-lookup"><span data-stu-id="5d72e-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

