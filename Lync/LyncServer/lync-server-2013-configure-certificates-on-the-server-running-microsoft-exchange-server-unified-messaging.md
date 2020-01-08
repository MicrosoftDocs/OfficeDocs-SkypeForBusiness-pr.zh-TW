---
title: Lync Server 2013：在運行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="9228b-102">在運行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="9228b-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9228b-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="9228b-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="9228b-104">如果您已部署 Exchange 整合訊息（UM），請參閱規劃檔中的[Lync Server 2013 規劃 Exchange 整合訊息整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)，以及您想要為貴組織中的企業語音使用者提供 exchange um 功能，您可以使用下列程式來設定執行 Exchange um 之伺服器上的憑證。</span><span class="sxs-lookup"><span data-stu-id="9228b-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9228b-105">對於內部憑證，執行 Lync Server 2013 的伺服器以及執行 Microsoft Exchange 的伺服器都必須擁有互相信任的根信任頒發機構憑證。</span><span class="sxs-lookup"><span data-stu-id="9228b-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="9228b-106">只要伺服器已在其受信任的根授權憑證存放區中註冊認證機構的根憑證，憑證授權單位（CA）就可以是相同或不同的憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="9228b-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="9228b-107">Exchange 伺服器必須使用伺服器憑證進行設定，才能連線至 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="9228b-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="9228b-108">下載 Exchange 伺服器的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="9228b-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="9228b-109">安裝 Exchange 伺服器的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="9228b-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="9228b-110">確認 CA 位於 Exchange 伺服器的根信任 Ca 清單中。</span><span class="sxs-lookup"><span data-stu-id="9228b-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="9228b-111">建立 Exchange 伺服器的憑證要求並安裝證書。</span><span class="sxs-lookup"><span data-stu-id="9228b-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="9228b-112">指派 Exchange 伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="9228b-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="9228b-113">下載 CA 憑證</span><span class="sxs-lookup"><span data-stu-id="9228b-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="9228b-114">在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，輸入**發證 CA\>伺服器\</Certsrv 的 HTTP://名稱**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9228b-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="9228b-115">在 [**選取任務**] 底下，按一下 [**下載 CA 憑證、憑證鏈或 CRL**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="9228b-116">在 [**下載 Ca 憑證、憑證連結或 CRL**] 底下，選取 [**編碼方法至基本 64**]，然後按一下 [**下載 CA 憑證**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9228b-117">您也可以在此步驟指定可分辨編碼規則（DER）編碼。</span><span class="sxs-lookup"><span data-stu-id="9228b-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="9228b-118">如果您選取 [DER 編碼]，此程式的下一個步驟中和<STRONG>安裝 CA 憑證</STRONG>的步驟10中的檔案類型是. p7b （而不是 .cer）。</span><span class="sxs-lookup"><span data-stu-id="9228b-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="9228b-119">在 [檔案**下載**] 對話方塊中，按一下 [**儲存**]，然後將檔案儲存到伺服器上的硬碟。</span><span class="sxs-lookup"><span data-stu-id="9228b-119">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="9228b-120">（根據您在上一個步驟中選取的編碼，該檔案將會有 .cer 或. p7b 檔案副檔名。）</span><span class="sxs-lookup"><span data-stu-id="9228b-120">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="9228b-121">若要安裝 CA 憑證</span><span class="sxs-lookup"><span data-stu-id="9228b-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="9228b-122">在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，在 [**開啟**] 方塊中輸入**MMC** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9228b-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="9228b-123">**在 [檔案**] 功能表上，按一下 [**新增/移除管理單元**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="9228b-124">在 [**新增獨立的管理單元**] 方塊中，按一下 [**憑證**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="9228b-125">在 [**憑證管理單元**] 對話方塊中，按一下 [**電腦帳戶**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9228b-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="9228b-126">在 [**選取電腦**] 對話方塊中，確認已選取 [**本機電腦（執行此主控台的電腦）** ] 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9228b-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="9228b-127">按一下 [**關閉**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9228b-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="9228b-128">在主控台樹中，展開 [**憑證（本機電腦）**]，展開 [**信任的根憑證授權單位**]，然後按一下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="9228b-129">以滑鼠右鍵按一下 [**憑證**]，按一下 [**所有任務**]，然後按一下 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="9228b-130">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9228b-130">Click **Next**.</span></span>

10. <span data-ttu-id="9228b-131">按一下 **[流覽]** 找出檔案，然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-131">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="9228b-132">（檔案將會有 .cer 或. p7b 副檔名，視您在**下載 CA 憑證**的步驟3中所選取的編碼而定。</span><span class="sxs-lookup"><span data-stu-id="9228b-132">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="9228b-133">按一下 **[將所有憑證放入下列存放區**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="9228b-134">按一下 **[流覽]**，然後選取 [**信任的根憑證授權單位**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="9228b-135">按一下 **[下一步**] 驗證設定，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9228b-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="9228b-136">確認 CA 位於信任的根 Ca 清單中</span><span class="sxs-lookup"><span data-stu-id="9228b-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="9228b-137">在執行 Exchange UM 的伺服器上，在 MMC 中展開 **[憑證（本機電腦）**]，展開 [**信任的根憑證授權單位**]，然後按一下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="9228b-138">在 [詳細資料] 窗格中，確認您的 CA 位於信任的 Ca 清單中。</span><span class="sxs-lookup"><span data-stu-id="9228b-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="9228b-139">若要將 Exchange Server 2013 UM 設定為使用 Lync Server</span><span class="sxs-lookup"><span data-stu-id="9228b-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="9228b-140">如需詳細資訊，請參閱 Exchange Server 檔中的「整合與 Lync Server 的 Exchange [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)2013 UM」。</span><span class="sxs-lookup"><span data-stu-id="9228b-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="9228b-141">在 Exchange Server 2007 （SP1）上建立憑證要求並安裝證書</span><span class="sxs-lookup"><span data-stu-id="9228b-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="9228b-142">在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，輸入發證 CA 伺服器**\>/certsrv**的**HTTP://\<** 名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9228b-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="9228b-143">按一下 [**選取任務**] 底下的 [**要求憑證**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="9228b-144">在 [**要求證書**] 底下，按一下 [**高級證書要求**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="9228b-145">在 [**高級憑證要求**] 底下，按一下 [**建立並提交此 CA 的要求**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="9228b-146">在 [**高級證書申請**] 底下，選取 [ **Web 服務器**] 或 [其他設定為伺服器驗證的伺服器憑證範本]。</span><span class="sxs-lookup"><span data-stu-id="9228b-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="9228b-147">在 [**離線範本的識別資訊**] 底下的 [**名稱**] 方塊中，輸入 Exchange 伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="9228b-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9228b-148">您必須輸入 Exchange 伺服器的 FQDN，才能進行通訊。</span><span class="sxs-lookup"><span data-stu-id="9228b-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="9228b-149">在 [**金鑰選項**] 底下，按一下 [**將憑證儲存在本機電腦憑證存放區**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9228b-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="9228b-150">按一下網頁底部的 [Submit] （**提交**）按鈕。</span><span class="sxs-lookup"><span data-stu-id="9228b-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="9228b-151">在開啟要求確認的對話方塊中，按一下 **[是**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="9228b-152">在 [頒發的憑證] 頁面上的 [**頒發的憑證**] 底下，按一下 [**安裝此憑證**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="9228b-153">在開啟要求確認的對話方塊中，按一下 **[是**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="9228b-154">確認出現「您的新憑證已成功安裝」訊息。</span><span class="sxs-lookup"><span data-stu-id="9228b-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="9228b-155">在 Exchange Server 2010 上建立憑證</span><span class="sxs-lookup"><span data-stu-id="9228b-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="9228b-156">以適當的使用者權利登入執行 Exchange UM 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9228b-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="9228b-157">如需詳細資訊，請參閱「用戶端[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)存取許可權」。</span><span class="sxs-lookup"><span data-stu-id="9228b-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="9228b-158">請參閱下列程式來建立證書：</span><span class="sxs-lookup"><span data-stu-id="9228b-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="9228b-159">「建立新的 Exchange 憑證」[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="9228b-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="9228b-160">「匯入 Exchange 憑證」[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="9228b-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9228b-161">針對證書<STRONG>受領人名稱</STRONG>，您必須輸入 Exchange 伺服器的 FQDN，才能使用通訊。</span><span class="sxs-lookup"><span data-stu-id="9228b-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="9228b-162">在 Exchange Server 2007 （SP1）上指派憑證</span><span class="sxs-lookup"><span data-stu-id="9228b-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="9228b-163">在執行 Exchange UM 的伺服器上，開啟 [MMC]。</span><span class="sxs-lookup"><span data-stu-id="9228b-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="9228b-164">在主控台樹中，展開 [**個人**]，然後按一下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="9228b-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="9228b-165">在 [詳細資料] 窗格中，確認已顯示 [個人憑證]。</span><span class="sxs-lookup"><span data-stu-id="9228b-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="9228b-166">按兩下憑證以閱讀其詳細資料，並確認它是有效的。</span><span class="sxs-lookup"><span data-stu-id="9228b-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9228b-167">認證可能需要幾分鐘的時間，才會顯示為有效。</span><span class="sxs-lookup"><span data-stu-id="9228b-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="9228b-168">重新開機 Microsoft Exchange 整合訊息服務。</span><span class="sxs-lookup"><span data-stu-id="9228b-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9228b-169">運行 Exchange Server 2007 SP1 整合通訊的伺服器會自動檢索正確的憑證。</span><span class="sxs-lookup"><span data-stu-id="9228b-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="9228b-170">開啟 [事件檢視器] 並尋找事件 ID 1112，該事件會指定伺服器執行 Exchange Server 2007 SP1 之統一通訊已檢索的憑證。</span><span class="sxs-lookup"><span data-stu-id="9228b-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="9228b-171">在 Exchange Server 2010 上指派憑證</span><span class="sxs-lookup"><span data-stu-id="9228b-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="9228b-172">以適當的使用者權利登入執行 Exchange UM 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9228b-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="9228b-173">如需詳細資訊，請參閱「用戶端[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)存取許可權」。</span><span class="sxs-lookup"><span data-stu-id="9228b-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="9228b-174">如需指派證書的程式，請參閱「指派服務給證書」 [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)。</span><span class="sxs-lookup"><span data-stu-id="9228b-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

