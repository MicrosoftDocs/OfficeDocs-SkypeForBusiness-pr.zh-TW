---
title: Lync Server 2013：在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證
description: Lync Server 2013：在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a7d1e0aec3ec36723ee68c0a1dcd7f60050f9ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564399"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="ced66-103">在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="ced66-103">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ced66-104">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="ced66-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="ced66-105">如果您已部署 Exchange 整合通訊 (UM) （如規劃檔中的「 [在 Lync Server 2013 中規劃 exchange 整合通訊整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 」中所述），且您想要將 exchange um 功能提供給組織中的 Enterprise Voice 使用者，您可以使用下列程式在執行 Exchange um 的伺服器上設定憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-105">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ced66-106">針對內部憑證，執行 Lync Server 2013 的伺服器和執行 Microsoft Exchange 的伺服器必須具有相互信任的根信任授權憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-106">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="ced66-107">憑證授權單位單位 (CA) 可以相同或不同的憑證授權單位單位，只要伺服器在其受信任的根授權憑證存放區中註冊了憑證授權單位的根憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-107">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="ced66-108">必須將 Exchange 伺服器設定為使用伺服器憑證，才能連線至 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="ced66-108">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="ced66-109">下載 Exchange Server 的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-109">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="ced66-110">安裝 Exchange Server 的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-110">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="ced66-111">確認 CA 在 Exchange Server 的受信任的根 CA 清單中。</span><span class="sxs-lookup"><span data-stu-id="ced66-111">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="ced66-112">建立 Exchange Server 的憑證要求並安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-112">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="ced66-113">指派 Exchange Server 的憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-113">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="ced66-114">若要下載 CA 憑證</span><span class="sxs-lookup"><span data-stu-id="ced66-114">To download the CA certificate</span></span>

1.  <span data-ttu-id="ced66-115">在執行 Exchange UM 的伺服器上，按一下 [ **開始**]，按一下 [ **執行**]，輸入 **Http:// \<name of your Issuing CA Server\> /Certsrv**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-115">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="ced66-116">在 **[選取工作]** 下方，按一下 **[下載 CA 憑證、憑證鏈結或 CRL]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-116">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="ced66-117">在 [ **下載 Ca 憑證、憑證鏈或 CRL**] 底下，選取 [ **編碼方式為 64**]，然後按一下 [ **下載 CA 憑證**]。</span><span class="sxs-lookup"><span data-stu-id="ced66-117">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ced66-118">您也可以在此步驟 (DER) 編碼中指定可辨識的編碼規則。</span><span class="sxs-lookup"><span data-stu-id="ced66-118">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="ced66-119">如果您選取 DER 編碼，此程序下一個步驟中以及<STRONG>「若要安裝 CA 憑證」</STRONG>步驟 10 中的檔案類型會是 .p7b，而非 .cer。</span><span class="sxs-lookup"><span data-stu-id="ced66-119">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="ced66-p103">在 **[檔案下載]** 對話方塊中，按一下 **[儲存]**，然後將檔案儲存到伺服器的硬碟上 (視您在上一個步驟中選取的編碼而定，檔案的副檔名會是 .cer 或 .p7b)。</span><span class="sxs-lookup"><span data-stu-id="ced66-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="ced66-122">若要安裝 CA 憑證</span><span class="sxs-lookup"><span data-stu-id="ced66-122">To install the CA certificate</span></span>

1.  <span data-ttu-id="ced66-123">在執行 Exchange UM 的伺服器上，按一下 [**開始**]，按一下 [**執行**]，然後在 [**開啟**] 方塊中輸入**MMC** ，然後按一下 **[確定]**，以開啟 Microsoft Management Console (MMC) 。</span><span class="sxs-lookup"><span data-stu-id="ced66-123">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="ced66-124">在 **[檔案]** 功能表中，按一下 **[新增/移除嵌入式管理單元]**，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-124">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="ced66-125">在 **[新增獨立嵌入式管理單元]** 方塊中，按一下 **[憑證]**，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-125">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="ced66-126">在 **[憑證嵌入式管理單元]** 對話方塊中，按一下 **[電腦帳戶]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-126">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="ced66-127">在 [ **選取電腦** ] 對話方塊中，確認已選取 [ \*\*本機電腦： (執行此主控台的電腦) \*\* ] 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-127">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="ced66-128">按一下 **[關閉]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-128">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="ced66-129">在主控台樹狀目錄中，依序展開 **[憑證 (本機電腦)]** 和 **[信任的根憑證授權]**，然後按一下 **[憑證]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-129">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="ced66-130">以滑鼠右鍵按一下 **[憑證]**，按一下 **[所有工作]**，再按一下 **[匯入]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-130">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="ced66-131">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-131">Click **Next**.</span></span>

10. <span data-ttu-id="ced66-p104">按一下 **[瀏覽]**，找出檔案，然後按 **[下一步]** (視您在 **「若要下載 CA 憑證」** 步驟 3 中選取的編碼而定，檔案的副檔名會是 .cer 或 .p7b)。</span><span class="sxs-lookup"><span data-stu-id="ced66-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="ced66-134">按一下 **[將所有憑證放入以下的存放區]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-134">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="ced66-135">按一下 **[瀏覽]**，然後選取 **[受信任的根憑證授權單位]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-135">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="ced66-136">按 **[下一步]** 以驗證設定，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-136">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="ced66-137">若要確認 CA 是否在受信任的根 CA 清單中</span><span class="sxs-lookup"><span data-stu-id="ced66-137">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="ced66-138">在執行 Exchange UM 的伺服器上，于 MMC 中展開 [ \*\*憑證 (本機電腦]) \*\*中，展開 [ **受信任的根憑證授權**單位]，然後按一下 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="ced66-138">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="ced66-139">在詳細資料窗格中，確認您的 CA 位於受信任的 CA 清單上。</span><span class="sxs-lookup"><span data-stu-id="ced66-139">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="ced66-140">設定 Exchange Server 2013 UM 與 Lync Server</span><span class="sxs-lookup"><span data-stu-id="ced66-140">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="ced66-141">如需詳細資訊，請參閱 Exchange Server 檔中的「整合 Exchange 2013 UM 與 Lync Server」 [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) 。</span><span class="sxs-lookup"><span data-stu-id="ced66-141">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="ced66-142">若要在 Exchange Server 2007 (SP1) 上建立憑證要求及安裝憑證</span><span class="sxs-lookup"><span data-stu-id="ced66-142">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="ced66-143">在執行 Exchange UM 的伺服器上，按一下 [ **開始**]，按一下 [ **執行**]，輸入 **Http:// \<**name of your Issuing CA Server**\> /Certsrv**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-143">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<**name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="ced66-144">在 **[選取工作]** 下，按一下 **[要求憑證]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-144">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="ced66-145">在 **[要求憑證]** 下，按一下 **[進階憑證要求]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-145">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="ced66-146">在 **[進階憑證要求]** 下，按一下 **[建立並送出要求至此 CA]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-146">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="ced66-147">在 **[進階憑證要求]** 下，選取 **[Web 伺服器]** 或針對伺服器驗證設定的另一個伺服器憑證範本。</span><span class="sxs-lookup"><span data-stu-id="ced66-147">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="ced66-148">在 [ **離線範本識別資訊**] 底下的 [ **名稱** ] 方塊中，輸入 Exchange 伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="ced66-148">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ced66-149">您必須輸入 Exchange Server 的 FQDN，才能夠進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ced66-149">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="ced66-150">在 **[金鑰選項]** 下，按一下 **[將憑證存放在本機電腦憑證存放區]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ced66-150">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="ced66-151">按一下網頁下方的 **[送出]** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ced66-151">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="ced66-152">在開啟並要求確認的對話方塊中，按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-152">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="ced66-153">在 [已發出憑證] 頁面的 **[已發出憑證]** 下，按一下 **[安裝這個憑證]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-153">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="ced66-154">在開啟並要求確認的對話方塊中，按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-154">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="ced66-155">確認顯示「您的新憑證已經安裝成功」訊息。</span><span class="sxs-lookup"><span data-stu-id="ced66-155">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="ced66-156">若要在 Exchange Server 2010 上建立憑證</span><span class="sxs-lookup"><span data-stu-id="ced66-156">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="ced66-157">以適當的使用者權限登入執行 Exchange UM 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ced66-157">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="ced66-158">如需詳細資訊，請參閱的「用戶端存取許可權」 [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) 。</span><span class="sxs-lookup"><span data-stu-id="ced66-158">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="ced66-159">參閱下列程序以建立憑證：</span><span class="sxs-lookup"><span data-stu-id="ced66-159">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="ced66-160">「建立新的 Exchange 憑證」 [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="ced66-160">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="ced66-161">「匯入 Exchange 憑證」 [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="ced66-161">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ced66-162">對於憑證的 <STRONG>[主體名稱]</STRONG>，您必須輸入 Exchange Server 的 FQDN，才能夠進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ced66-162">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="ced66-163">若要在 Exchange Server 2007 (SP1) 上指派憑證</span><span class="sxs-lookup"><span data-stu-id="ced66-163">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="ced66-164">在執行 Exchange UM 的伺服器上，開啟 [MMC]。</span><span class="sxs-lookup"><span data-stu-id="ced66-164">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="ced66-165">在主控台樹狀目錄中，展開 **[個人]**，然後按一下 **[憑證]**。</span><span class="sxs-lookup"><span data-stu-id="ced66-165">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="ced66-166">在詳細資料窗格中，確認有顯示個人憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-166">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="ced66-167">按兩下憑證以閱讀其詳細資料，並確認其有效。</span><span class="sxs-lookup"><span data-stu-id="ced66-167">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ced66-168">可能需要幾分鐘，才會顯示憑證是有效的。</span><span class="sxs-lookup"><span data-stu-id="ced66-168">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="ced66-169">重新啟動 Microsoft Exchange Unified Messaging 服務。</span><span class="sxs-lookup"><span data-stu-id="ced66-169">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ced66-170">執行 Exchange Server 2007 SP1 Unified Messaging 的伺服器會自動擷取正確的憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-170">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="ced66-171">開啟 [事件檢視器] 並尋找事件識別碼 1112，此事件識別碼會指定執行 Exchange Server 2007 SP1 Unified Messaging 之伺服器所擷取的憑證。</span><span class="sxs-lookup"><span data-stu-id="ced66-171">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="ced66-172">若要在 Exchange Server 2010 上指派憑證</span><span class="sxs-lookup"><span data-stu-id="ced66-172">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="ced66-173">以適當的使用者權限登入執行 Exchange UM 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ced66-173">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="ced66-174">如需詳細資訊，請參閱的「用戶端存取許可權」 [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) 。</span><span class="sxs-lookup"><span data-stu-id="ced66-174">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="ced66-175">如需指派憑證的程式，請參閱的「將服務指派給憑證」 [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) 。</span><span class="sxs-lookup"><span data-stu-id="ced66-175">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

