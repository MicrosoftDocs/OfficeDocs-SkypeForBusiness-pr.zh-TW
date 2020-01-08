---
title: Lync Server 2013：設定伺服器憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a0e239074b4f6d4638214fad41ff8ba18078fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="7f72f-102">在 Lync Server 2013 中設定伺服器憑證</span><span class="sxs-lookup"><span data-stu-id="7f72f-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f72f-103">_**主題上次修改日期：** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="7f72f-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="7f72f-104">若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入，或是委派正確的許可權。</span><span class="sxs-lookup"><span data-stu-id="7f72f-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="7f72f-105">如需委派許可權的詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="7f72f-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="7f72f-106">根據您的組織和申請憑證的需求而定，您可能需要其他群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="7f72f-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="7f72f-107">參閱管理公開金鑰基礎結構（PKI）憑證授權單位（CA）的群組。</span><span class="sxs-lookup"><span data-stu-id="7f72f-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f72f-108">Lync Server 2013 包含對 SHA-1 套件的支援（SHA-1 是針對執行 Windows 7、Windows Server 512 R2、Windows Server 2008、Windows Vista 等用戶端的連線之摘要雜湊與簽名演算法的摘要長度，使用224、256、384或2008位）除了 Lync Phone Edition 之外，還有 Windows XP 作業系統。</span><span class="sxs-lookup"><span data-stu-id="7f72f-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="7f72f-109">若要使用 SHA-1 套件支援外部存取，外部憑證是由公用 CA 所頒發，也可以使用相同的位長度摘要來頒發憑證。</span><span class="sxs-lookup"><span data-stu-id="7f72f-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="7f72f-110">所選的雜湊摘要與簽章演算法取決於用戶端和要使用憑證的伺服器，以及用戶端與伺服器要與其通訊的其他電腦和裝置，也必須知道如何使用本文中所使用的演算法。憑證.</span><span class="sxs-lookup"><span data-stu-id="7f72f-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="7f72f-111">如需有關作業系統及一些用戶端應用程式支援哪些摘要長度的詳細資訊，<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>請參閱。</span><span class="sxs-lookup"><span data-stu-id="7f72f-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="7f72f-112">每個標準版伺服器或前端伺服器最多需要四個憑證： oAuthTokenIssuer 憑證、預設憑證、網頁內部憑證及網頁外部憑證。</span><span class="sxs-lookup"><span data-stu-id="7f72f-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="7f72f-113">不過，您可以使用適當的消費者替換名稱專案及 oAuthTokenIssuer 憑證來要求並指派單一預設憑證。</span><span class="sxs-lookup"><span data-stu-id="7f72f-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="7f72f-114">如需證書需求的詳細資訊，請參閱[Lync Server 2013 內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="7f72f-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="7f72f-115">如需有關要求、指派及安裝 oAuthTokenIssuer 憑證的詳細資料，請參閱[在 Lync server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="7f72f-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="7f72f-116">使用下列程式來要求、指派及安裝標準版 server 或前端伺服器憑證。</span><span class="sxs-lookup"><span data-stu-id="7f72f-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="7f72f-117">針對每個前端伺服器重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="7f72f-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f72f-118">下列程式說明如何從貴組織部署的內部企業 PKI 及離線要求處理來設定證書。</span><span class="sxs-lookup"><span data-stu-id="7f72f-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="7f72f-119">如需從公用 CA 取得憑證的相關資訊，請參閱規劃檔中的<A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 內部伺服器的憑證需求</A>。</span><span class="sxs-lookup"><span data-stu-id="7f72f-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="7f72f-120">此外，此程式也說明如何在設定前端伺服器期間要求、指派及安裝證書。</span><span class="sxs-lookup"><span data-stu-id="7f72f-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="7f72f-121">如果您提前要求證書，請參閱此部署檔的<A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 的 [提前申請憑證（選擇性）</A> ] 區段中所述，或者您不是使用貴組織中部署的內部企業 PKI 來取得憑證，您必須視情況修改此程式。</span><span class="sxs-lookup"><span data-stu-id="7f72f-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="7f72f-122">若要設定前端伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="7f72f-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="7f72f-123">在 Lync Server 部署嚮導中，按一下**步驟3： [要求]、[安裝或指派憑證**] 旁的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="7f72f-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="7f72f-124">在 [**憑證] 嚮導**頁面上，按一下 [**要求**]。</span><span class="sxs-lookup"><span data-stu-id="7f72f-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="7f72f-125">在 [**憑證要求**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="7f72f-126">在 [**延遲] 或 [立即要求**] 頁面上，您可以按一下 **[下一步]**，接受預設將**要求立即傳送給線上憑證授權單位**選項。</span><span class="sxs-lookup"><span data-stu-id="7f72f-126">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**.</span></span> <span data-ttu-id="7f72f-127">如果您選取此選項，則必須提供含自動線上註冊的內部 CA。</span><span class="sxs-lookup"><span data-stu-id="7f72f-127">The internal CA with automatic online enrollment must be available if you select this option.</span></span> <span data-ttu-id="7f72f-128">如果您選擇延遲要求的選項，系統會提示您輸入名稱和位置來儲存證書申請檔案。</span><span class="sxs-lookup"><span data-stu-id="7f72f-128">If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file.</span></span> <span data-ttu-id="7f72f-129">證書申請必須由您組織內的 CA 或公用 CA 出示並處理。</span><span class="sxs-lookup"><span data-stu-id="7f72f-129">The certificate request must be presented and processed by a CA either inside your organization, or by a public CA.</span></span> <span data-ttu-id="7f72f-130">接著您必須匯入憑證回應，然後將它指派給適當的憑證角色。</span><span class="sxs-lookup"><span data-stu-id="7f72f-130">You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="7f72f-131">在 [**選擇憑證授權單位（CA）** ] 頁面上，選取 [**從您的環境中偵測到的清單中選取 CA** ] 選項，然後從清單中選取 [已知] （透過 Active DIRECTORY 網域服務） CA 中的 [註冊]。</span><span class="sxs-lookup"><span data-stu-id="7f72f-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="7f72f-132">或者，選取 [**指定另一個憑證授權單位**] 選項，在方塊中輸入另一個 CA 的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="7f72f-133">在 [**憑證授權單位帳戶**] 頁面上，系統會提示您輸入認證，以要求並處理 CA 的證書申請。</span><span class="sxs-lookup"><span data-stu-id="7f72f-133">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="7f72f-134">您應該已確定是否需要使用者名稱和密碼才能提前申請憑證。</span><span class="sxs-lookup"><span data-stu-id="7f72f-134">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="7f72f-135">您的 CA 管理員將會提供必要的資訊，而且可能必須在這個步驟中協助您。</span><span class="sxs-lookup"><span data-stu-id="7f72f-135">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="7f72f-136">如果您需要提供備用認證，請選取核取方塊，在文字方塊中提供使用者名稱和密碼，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-136">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="7f72f-137">若要使用預設的 Web 服務器範本，請在 [**指定備用憑證範本**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f72f-138">如果您的組織已建立範本供您用來代替預設的 Web 服務器 CA 範本，請選取核取方塊，然後輸入備用範本的名稱。</span><span class="sxs-lookup"><span data-stu-id="7f72f-138">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template.</span></span> <span data-ttu-id="7f72f-139">您將需要由 CA 管理員所定義的範本名稱。</span><span class="sxs-lookup"><span data-stu-id="7f72f-139">You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="7f72f-140">在 [**名稱及安全性設定**] 頁面上，指定可讓您識別憑證和用途的**易記名稱**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="7f72f-141">如果您將它留白，系統會自動產生名稱。</span><span class="sxs-lookup"><span data-stu-id="7f72f-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="7f72f-142">設定金鑰的**位長**，或接受預設值2048位。</span><span class="sxs-lookup"><span data-stu-id="7f72f-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="7f72f-143">如果您認為需要將憑證和私人金鑰移動或複製到其他系統，請選取 [將**證書的私密金鑰標示為可匯出**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f72f-144">Lync Server 2013 對於可匯出的私密金鑰的需求最低。</span><span class="sxs-lookup"><span data-stu-id="7f72f-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="7f72f-145">其中一個位置是位於某個池中的邊緣伺服器上，媒體轉送驗證服務會使用憑證複本，而不是在池中每個實例的個別憑證。</span><span class="sxs-lookup"><span data-stu-id="7f72f-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="7f72f-146">在 [**組織資訊**] 頁面上，選擇 [提供組織資訊]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="7f72f-147">在 [**地理資訊**] 頁面上，選擇提供地理資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="7f72f-148">在 [**受領人名稱/主旨替換名稱**] 頁面上，查看將新增的 [subject 替換名稱]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="7f72f-149">在 [ **SIP 網域設定**] 頁面上，選取**SIP 網域**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="7f72f-150">在 [**設定其他消費者替換名稱**] 頁面上，新增任何其他必要的消費者替換名稱，包括將來其他 SIP 網域可能需要的任何其他主題，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="7f72f-151">在 [**憑證要求摘要**] 頁面上，查看 [摘要] 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="7f72f-151">On the **Certificate Request Summary** page, review the information in the summary.</span></span> <span data-ttu-id="7f72f-152">如果資訊正確無誤，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-152">If the information is correct, click **Next**.</span></span> <span data-ttu-id="7f72f-153">如果您需要修正或修改設定，請按一下 [**返回**至正確的頁面]，以進行修正或修改。</span><span class="sxs-lookup"><span data-stu-id="7f72f-153">If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="7f72f-154">在 [**執行命令**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="7f72f-155">在 [**線上憑證要求狀態**] 頁面上，查看傳回的資訊。</span><span class="sxs-lookup"><span data-stu-id="7f72f-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="7f72f-156">您應該注意到證書已頒發並安裝到本機憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="7f72f-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="7f72f-157">如果報告為已發出且已安裝，但無效，請確定 CA 根憑證已安裝在伺服器的根信任 CA 存放區中。</span><span class="sxs-lookup"><span data-stu-id="7f72f-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="7f72f-158">請參閱您的 CA 檔，瞭解如何檢索受信任的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="7f72f-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="7f72f-159">如果您需要查看檢索到的憑證，請按一下 [**查看憑證詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="7f72f-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="7f72f-160">根據預設，會選取 [**指派憑證至 Lync Server 證書使用**方式] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7f72f-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="7f72f-161">如果您想要手動指派憑證，請清除該核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="7f72f-162">如果您在前一頁清除 [**指派憑證至 Lync Server 證書使用**情況] 的核取方塊，就會顯示 [**憑證指派**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7f72f-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="7f72f-163">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-163">Click **Next**.</span></span>

18. <span data-ttu-id="7f72f-164">在 [**憑證存放區**] 頁面上，選取您要求的憑證。</span><span class="sxs-lookup"><span data-stu-id="7f72f-164">On the **Certificate Store** page, select the certificate that you requested.</span></span> <span data-ttu-id="7f72f-165">如果您想要查看憑證，請按一下 [**查看憑證詳細資料**]，然後按一下 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="7f72f-165">If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f72f-166">如果<STRONG>線上憑證要求狀態</STRONG>頁面報告了憑證的問題（例如憑證無效），請查看實際的憑證以協助解決問題。</span><span class="sxs-lookup"><span data-stu-id="7f72f-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="7f72f-167">可能導致憑證無法有效的兩個特定問題，就是先前提及的遺失根信任 CA 憑證，以及與憑證相關的遺失私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="7f72f-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="7f72f-168">請參閱您的 CA 檔以解決這兩個問題。</span><span class="sxs-lookup"><span data-stu-id="7f72f-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="7f72f-169">在 [**憑證指派摘要**] 頁面上，查看所提供的資訊，以確認這是應該指派的憑證，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="7f72f-170">在 [**執行命令**] 頁面上，檢查命令的輸出。</span><span class="sxs-lookup"><span data-stu-id="7f72f-170">On the **Executing Commands** page, review the output of the command.</span></span> <span data-ttu-id="7f72f-171">如果您想要查看作業程式，或是否已發出錯誤或警告，請按一下 [**查看記錄**]。</span><span class="sxs-lookup"><span data-stu-id="7f72f-171">Click **View Log** if you want to review the assignment process or if there was an error or warning issued.</span></span> <span data-ttu-id="7f72f-172">完成審閱後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="7f72f-172">When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="7f72f-173">在 [**憑證] 嚮導**頁面上，確認憑證的**狀態**為「已指派」，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="7f72f-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f72f-174">請參閱</span><span class="sxs-lookup"><span data-stu-id="7f72f-174">See Also</span></span>


[<span data-ttu-id="7f72f-175">Lync Server 2013 的憑證基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="7f72f-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

