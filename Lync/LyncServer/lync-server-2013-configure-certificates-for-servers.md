---
title: Lync Server 2013：設定伺服器的憑證
description: Lync Server 2013：設定伺服器的憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fab2f55f25ed3a289dd2d51b080374b3844029c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578109"
---
# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="4d873-103">在 Lync Server 2013 中設定伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="4d873-103">Configure certificates for servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d873-104">_**主題上次修改日期：** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="4d873-104">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="4d873-105">若要順利完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入，或是委派正確的許可權。</span><span class="sxs-lookup"><span data-stu-id="4d873-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="4d873-106">如需有關委派許可權的詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="4d873-106">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="4d873-107">根據您的組織以及對要求憑證的需求，您可能需要其他群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="4d873-107">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="4d873-108">請向負責管理公開金鑰基礎結構 (PKI) 憑證授權單位 (CA) 的部門洽詢相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4d873-108">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d873-109">Lync Server 2013 包含對 SHA-2 套件的支援 (SHA-2 對執行 Windows 7、Windows Server 512 R2、Windows Server 2008、windows Vista 或 Windows XP 作業系統的用戶端，除了 Lync Phone Edition 之外，針對來自執行 Windows 7、Windows Server 2008 R2、windows Server、windows Vista 或 Windows XP 作業系統的用戶端，使用摘要雜湊及簽署演算法的摘要 384 256 224 的長度) 的</span><span class="sxs-lookup"><span data-stu-id="4d873-109">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="4d873-110">若要使用 SHA-2 套件來支援外部存取，外部憑證是由公用 CA 所發出，也可以使用相同位長度的摘要來發出憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-110">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="4d873-111">您可以選擇哪些雜湊摘要和簽署演算法取決於用戶端和將使用憑證的伺服器，以及用戶端和伺服器要與其通訊的其他電腦和裝置，也必須瞭解如何使用憑證中所用的演算法。</span><span class="sxs-lookup"><span data-stu-id="4d873-111">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="4d873-112">如需作業系統和某些用戶端應用程式中支援摘要長度的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A> 。</span><span class="sxs-lookup"><span data-stu-id="4d873-112">For information on which digest lengths are supported in the operating system and some client applications, see<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="4d873-113">每個 Standard Edition server 或前端伺服器最多需要四個憑證： oAuthTokenIssuer 憑證、預設憑證、網頁內部憑證和網頁外部憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-113">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="4d873-114">不過，您可以使用適當的主體替代名稱專案以及 oAuthTokenIssuer 憑證要求並指派單一預設憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-114">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="4d873-115">如需憑證需求的詳細資訊，請參閱 [Lync Server 2013 中內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="4d873-115">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="4d873-116">如需有關要求、指派及安裝 oAuthTokenIssuer 憑證的詳細資訊，請參閱 [管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式的 Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="4d873-116">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="4d873-117">使用下列程式可要求、指派及安裝 Standard Edition server 或前端伺服器憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-117">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="4d873-118">針對每一部前端伺服器重複此程式。</span><span class="sxs-lookup"><span data-stu-id="4d873-118">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4d873-119">下列程式說明如何從組織部署的內部 enterprise PKI 設定憑證，並以離線要求處理。</span><span class="sxs-lookup"><span data-stu-id="4d873-119">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="4d873-120">如需從公用 CA 取得憑證的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 內部伺服器的憑證需求</A> 。</span><span class="sxs-lookup"><span data-stu-id="4d873-120">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="4d873-121">此外，此程式也說明如何在設定前端伺服器期間要求、指派及安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-121">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="4d873-122">如果您事先要求憑證，如本部署檔的 [ <A href="lync-server-2013-request-certificates-in-advance-optional.md">要求憑證中 (選用 2013) </A> ] 區段所述，或是您未使用組織中部署的內部企業 PKI 來取得憑證，您必須視需要修改此程式。</span><span class="sxs-lookup"><span data-stu-id="4d873-122">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="4d873-123">若要為前端伺服器設定憑證</span><span class="sxs-lookup"><span data-stu-id="4d873-123">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="4d873-124">在 [Lync Server 部署嚮導] 中，按一下 [**步驟3：要求、安裝或指派憑證**] 旁邊的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="4d873-124">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="4d873-125">在 **[憑證精靈]** 頁面中，按一下 **[要求]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-125">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="4d873-126">在 **[憑證要求]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-126">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="4d873-127">在 [**延遲或立即要求**] 頁面上，按一下 **[下一步]**，可接受預設**立即將要求傳送到線上憑證授權單位**單位選項。</span><span class="sxs-lookup"><span data-stu-id="4d873-127">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**.</span></span> <span data-ttu-id="4d873-128">如果您選取此選項，則必須使用具有自動線上註冊的內部 CA。</span><span class="sxs-lookup"><span data-stu-id="4d873-128">The internal CA with automatic online enrollment must be available if you select this option.</span></span> <span data-ttu-id="4d873-129">如果您選擇延遲要求的選項，系統會提示您輸入名稱和位置，以儲存憑證要求檔案。</span><span class="sxs-lookup"><span data-stu-id="4d873-129">If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file.</span></span> <span data-ttu-id="4d873-130">憑證要求必須由組織內的 CA 或公用 CA 所呈現及處理。</span><span class="sxs-lookup"><span data-stu-id="4d873-130">The certificate request must be presented and processed by a CA either inside your organization, or by a public CA.</span></span> <span data-ttu-id="4d873-131">接著，您將需要匯入憑證回應，並將它指派給適當的憑證角色。</span><span class="sxs-lookup"><span data-stu-id="4d873-131">You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="4d873-132">在 [ \*\*選擇憑證授權單位單位 (CA) \*\* ] 頁面上，選取 [ **從環境中偵測到的清單選取 CA** ] 選項，然後從清單中的 Active DIRECTORY 網域服務) CA 註冊，以選取已知 (。</span><span class="sxs-lookup"><span data-stu-id="4d873-132">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="4d873-133">或者，選取 [ **指定另一個憑證授權單位** 單位] 選項，然後在方塊中輸入另一個 CA 的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-133">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="4d873-134">在 [ **憑證授權單位單位帳戶** ] 頁面上，系統會提示您輸入認證要求並處理 CA 的憑證要求。</span><span class="sxs-lookup"><span data-stu-id="4d873-134">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="4d873-135">您應該已確定使用者名稱和密碼是否需要預先要求憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-135">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="4d873-136">您的 CA 管理員會有必要的資訊，而且可能需要在此步驟中協助您。</span><span class="sxs-lookup"><span data-stu-id="4d873-136">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="4d873-137">如果您需要提供替代認證，請選取 [核取方塊]，在文字方塊中提供使用者名稱和密碼，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-137">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="4d873-138">在 [ **指定替代的憑證範本** ] 頁面上，若要使用預設 Web 服務器範本，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-138">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d873-139">如果您的組織已建立用作預設網頁伺服器 CA 範本的替代範本，請選取核取方塊，然後輸入備用範本的名稱。</span><span class="sxs-lookup"><span data-stu-id="4d873-139">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template.</span></span> <span data-ttu-id="4d873-140">您將需要 CA 管理員所定義的範本名稱。</span><span class="sxs-lookup"><span data-stu-id="4d873-140">You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="4d873-141">在 [ **名稱和安全性設定** ] 頁面上，指定可讓您識別憑證和用途的 **易記名稱** 。</span><span class="sxs-lookup"><span data-stu-id="4d873-141">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="4d873-142">如果保留空白，則會自動產生名稱。</span><span class="sxs-lookup"><span data-stu-id="4d873-142">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="4d873-143">設定機碼的 **位長度** ，或接受預設值2048位。</span><span class="sxs-lookup"><span data-stu-id="4d873-143">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="4d873-144">選取 [將 **憑證的私密金鑰標記為可匯出** ] 如果您決定要將憑證和私密金鑰移動或複製到其他系統，請按一下 [ **下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-144">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d873-145">Lync Server 2013 具有可匯出私密金鑰的最低需求。</span><span class="sxs-lookup"><span data-stu-id="4d873-145">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="4d873-146">其中一個地方是在集區中的 Edge Server 上，媒體轉送驗證服務使用憑證的副本，而不是集區中每個實例的個別憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-146">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="4d873-147">在 [ **組織資訊** ] 頁面上，選擇提供組織資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-147">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="4d873-148">在 [ **地理資訊** ] 頁面上，選擇提供地理資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-148">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="4d873-149">在 [ **主體名稱/主體替代名稱** ] 頁面上，複查將要新增的主體替代名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-149">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="4d873-150">在 [ **SIP 網域設定** ] 頁面上，選取 [ **sip 網域**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-150">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="4d873-151">在 [ **設定其他主體替代名稱** ] 頁面上，新增任何其他必要的主體別名，包括未來其他 SIP 網域可能需要的主體替代名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-151">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="4d873-152">在 [ **憑證要求摘要** ] 頁面上，複查摘要中的資訊。</span><span class="sxs-lookup"><span data-stu-id="4d873-152">On the **Certificate Request Summary** page, review the information in the summary.</span></span> <span data-ttu-id="4d873-153">如果資訊正確，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-153">If the information is correct, click **Next**.</span></span> <span data-ttu-id="4d873-154">如果您需要更正或修改設定，請按一下 [ **回到** 正確的頁面]，以進行更正或修改。</span><span class="sxs-lookup"><span data-stu-id="4d873-154">If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="4d873-155">在 **[執行命令]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-155">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="4d873-156">在 [ **線上憑證要求狀態** ] 頁面上，複查傳回的資訊。</span><span class="sxs-lookup"><span data-stu-id="4d873-156">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="4d873-157">您應注意，已簽發憑證並將其安裝至本機憑證儲存區。</span><span class="sxs-lookup"><span data-stu-id="4d873-157">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="4d873-158">若報告為已簽發並已安裝，但無效，請確定伺服器的根信任 CA 存放區中已安裝 CA 的根憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-158">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="4d873-159">請參閱您的 CA 檔，瞭解如何取得信任的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-159">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="4d873-160">如果您需要查看已檢索的憑證，請按一下 [ **查看憑證詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="4d873-160">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="4d873-161">依預設，會檢查 **指派憑證至 Lync Server 憑證使用** 情況的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4d873-161">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="4d873-162">若要手動指派憑證，請清除核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-162">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="4d873-163">如果您已清除 [ **將憑證指派給舊版的 Lync Server 憑證使用** 情況] 核取方塊，將會出現 [ **憑證指派** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4d873-163">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="4d873-164">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-164">Click **Next**.</span></span>

18. <span data-ttu-id="4d873-165">在 [ **憑證存放區** ] 頁面上，選取您要求的憑證。</span><span class="sxs-lookup"><span data-stu-id="4d873-165">On the **Certificate Store** page, select the certificate that you requested.</span></span> <span data-ttu-id="4d873-166">如果您想要查看憑證，請按一下 [ **查看憑證詳細資料**]，然後按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="4d873-166">If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d873-167">如果 [ <STRONG>線上憑證要求狀態</STRONG> ] 頁面報告憑證有問題，例如憑證無效，則查看實際憑證可以協助解決問題。</span><span class="sxs-lookup"><span data-stu-id="4d873-167">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="4d873-168">兩個可能造成憑證無法使用的特定問題，都是先前提及的遺失信任的根 CA 憑證，以及與憑證相關聯的遺失私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="4d873-168">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="4d873-169">請參閱 CA 檔，以解決這兩個問題。</span><span class="sxs-lookup"><span data-stu-id="4d873-169">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="4d873-170">在 [ **憑證指派摘要** ] 頁面上，複查所呈現的資訊，確定這是應該指派的憑證，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-170">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="4d873-171">在 [ **執行命令** ] 頁面上，複查命令的輸出。</span><span class="sxs-lookup"><span data-stu-id="4d873-171">On the **Executing Commands** page, review the output of the command.</span></span> <span data-ttu-id="4d873-172">如果您想要複查指派程式，或是發出錯誤或警告，請按一下 [ **View Log** ]。</span><span class="sxs-lookup"><span data-stu-id="4d873-172">Click **View Log** if you want to review the assignment process or if there was an error or warning issued.</span></span> <span data-ttu-id="4d873-173">完成審閱後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4d873-173">When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="4d873-174">在 [ **憑證] 嚮導** 頁面上，確認憑證的 **狀態** 為「已指派」，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4d873-174">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d873-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4d873-175">See Also</span></span>


[<span data-ttu-id="4d873-176">Lync Server 2013 的憑證基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="4d873-176">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

