---
title: Lync Server 2013：修改行動憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bccb901f241089a21fd7428e28b005f46e157300
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="9a0f0-102">在 Lync Server 2013 中修改行動憑證</span><span class="sxs-lookup"><span data-stu-id="9a0f0-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a0f0-103">_**主題上次修改日期：** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="9a0f0-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="9a0f0-104">若要支援 Lync 環境與行動用戶端之間的安全連線，您的控制器池、前臺端池及反向 proxy 的安全通訊端層（SSL）憑證必須更新為其他消費者替換名稱（SAN）專案。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="9a0f0-105">如果您需要瞭解行動性證書需求的詳細資料，請參閱[Lync Server 2013 的行動技術需求](lync-server-2013-technical-requirements-for-mobility.md)中的 [認證需求] 區段，但基本而言，您必須使用隨附的其他 SAN 專案來取得憑證授權單位的新憑證，然後使用本文的步驟新增這些憑證。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="9a0f0-106">當然，在開始之前，通常最好知道您的憑證已有哪些消費者替代名稱。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="9a0f0-107">如果您不確定已設定的內容，有許多方法可讓您瞭解。雖然此選項是執行**CsCertificate**及其他 PowerShell 命令來查看此資訊（我們會在下方逐步引導），但是您可能不會看到您需要的所有屬性。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="9a0f0-108">若要充分瞭解憑證及其所有屬性，您可以移至 Microsoft 管理主控台（MMC）並載入 [憑證] 管理單元（我們也會逐步引導），或者您只需檢查 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="9a0f0-109">如前所述，下列步驟將逐步引導您使用 Lync Server 管理命令介面和 MMC 更新憑證。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="9a0f0-110">如果您想要改為在 Lync Server 部署嚮導中使用 [憑證] 嚮導，請改為在主管或主管伺服器的 [ [Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) ] 中，核取 [設定認證]。如果您已設定（您可能沒有的話）。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="9a0f0-111">對於前端伺服器或前端池，您會想要[在 Lync Server 2013 中查看伺服器的憑證](lync-server-2013-configure-certificates-for-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="9a0f0-112">需要記住的最後一點是，您可能會在 Lync Server 2013 環境中擁有單一預設憑證，或者您可能會有不同的預設憑證（除了 web 服務以外的所有專案）、WebServicesExternal 和 WebServicesInternal。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="9a0f0-113">無論您是哪一項設定，這些步驟都應該協助您解決。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="9a0f0-114">使用 Lync Server 管理命令介面將憑證更新為新的消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="9a0f0-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="9a0f0-115">您必須使用擁有本機系統管理員許可權和許可權的帳戶，登入 Lync Server 2013 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="9a0f0-116">此外，如果您在步驟12和之後的版本中執行 PowerShell**要求-CsCertificate** ，該帳戶必須擁有指定的憑證頒發機構（CA）的許可權。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="9a0f0-117">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9a0f0-118">您必須先瞭解已將哪些憑證指派給伺服器，以及使用哪種類型，才能指派更新的憑證。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="9a0f0-119">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="9a0f0-120">查看上一個步驟的輸出，以查看是否已將單一憑證指派給多個用途，或是否指派給每個使用不同的憑證。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="9a0f0-121">查看 Use 參數，以瞭解如何使用憑證。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="9a0f0-122">比較所顯示之憑證的指紋參數，以查看相同的憑證是否有多個用途。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="9a0f0-123">在指紋參數上留意您的注意。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="9a0f0-124">更新證書。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-124">Update the certificate.</span></span> <span data-ttu-id="9a0f0-125">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="9a0f0-126">例如，如果**CsCertificate** Cmdlet 顯示使用 [預設值] 的憑證，另一個是使用 WebServicesInternal，而另一個是使用 WebServicesExternal，而另一個則在命令列中有相同的指紋值，您應該輸入：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="9a0f0-127">**重要事項：**</span><span class="sxs-lookup"><span data-stu-id="9a0f0-127">**Important:**</span></span>
    
    <span data-ttu-id="9a0f0-128">如果每次使用都指派了個別的憑證（因此，您在上面所核取的指紋值對於每個憑證都不一樣），請務必**不要**執行**CsCertificate** Cmdlet 與多種類型，如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="9a0f0-129">在這種情況下，請針對每個用途分別執行**CsCertificate** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="9a0f0-130">例如：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="9a0f0-131">若要查看憑證（或憑證），請按一下 [**開始**]，然後按一下 [**執行 ...**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="9a0f0-132">輸入 MMC 以開啟 Microsoft 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="9a0f0-133">在 MMC 功能表中，選取 [檔案 **]，選取**[**新增/移除管理單元 ...**]，選取 [憑證]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="9a0f0-134">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-134">Click **Add**.</span></span> <span data-ttu-id="9a0f0-135">出現提示時，請選取 [**電腦帳戶**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="9a0f0-136">如果這是憑證所在的伺服器，請選取 [**本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="9a0f0-137">如果憑證位於另一部電腦上，您應該選取 [**另一台電腦**]，然後您可以輸入電腦的完整功能變數名稱，或按一下 [**流覽]** ，**輸入要選取的物件名稱**，然後輸入電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="9a0f0-138">按一下 [**檢查名稱**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-138">Click **Check Names**.</span></span> <span data-ttu-id="9a0f0-139">當電腦的名稱解析時，它會加上底線。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="9a0f0-140">按一下 **[確定]**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="9a0f0-141">按一下 **[確定]** ，確認選取範圍，然後關閉 [**新增或移除管理單元**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="9a0f0-142">若要查看憑證的屬性，請展開 [**憑證**]，展開 [**個人**]，然後選取 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="9a0f0-143">選取要查看的憑證，以滑鼠右鍵按一下憑證，然後選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="9a0f0-144">在 [**憑證**] 視圖中，選取 [**詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="9a0f0-145">您可以從這裡選取 [ **subject** ]，然後選取 [指派的受領人名稱及相關聯的屬性] 來選取證書受領人名稱。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="9a0f0-146">若要查看指派的主題替換名稱，請選取 [ **Subject 替換名稱**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="9a0f0-147">所有指派的主體替換名稱都會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="9a0f0-148">此處找到的使用中的 [主題替換名稱] 預設為 [類型**DNS 名稱**]。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="9a0f0-149">您應該會看到下列成員（無論是 DNS 主機（A 或 IPv6 AAAA）記錄中所代表的，都應該是完全限定功能變數名稱：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="9a0f0-150">此池的 [池名稱]，如果不是 [池]，則則是單一伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="9a0f0-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="9a0f0-151">證書指派的伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="9a0f0-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="9a0f0-152">簡單的 URL 記錄，通常符合和撥入</span><span class="sxs-lookup"><span data-stu-id="9a0f0-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="9a0f0-153">Web 服務內部和 Web 服務外部名稱（例如 webpool01.contoso.net、webpool01.contoso.com），根據拓撲建立器和跨 ridden Web 服務選擇中的選擇進行。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="9a0f0-154">如果已指定，則 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="9a0f0-155">最後一個專案是您最感興趣的專案–如果有 lyncdiscover 和 lyncdiscoverinternal 的 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="9a0f0-156">如果您有多個要檢查的憑證，請重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="9a0f0-157">有了這些資訊之後，您就可以關閉證書視圖和 MMC。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="9a0f0-158">如果找不到 [自動探索服務消費者] 替換名稱，且您針對預設、WebServicesInternal 和 WebServiceExternal 類型使用單一預設憑證，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="9a0f0-159">在 Lync Server Management Shell 命令列提示中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="9a0f0-160">如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="9a0f0-161">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="9a0f0-162">當您使用 DomainName 參數時，您必須為 lyncdiscoverinternal 和 lyncdiscover 記錄定義 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="9a0f0-163">例如：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="9a0f0-164">若要指派憑證，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="9a0f0-165">其中，"Thumbprint" 是新頒發的憑證所顯示的指紋。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="9a0f0-166">如果針對預設、WebServicesInternal 和 WebServicesExternal 使用不同的憑證，請執行下列動作，以取得缺少的內部自動探索 SAN：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="9a0f0-167">在 Lync Server Management Shell 命令列提示中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="9a0f0-168">如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="9a0f0-169">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="9a0f0-170">當您使用 DomainName 參數時，您必須為 SIP 網域 FQDN 使用適當的首碼。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="9a0f0-171">例如：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="9a0f0-172">如果缺少外部自動探索消費者替換名稱，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="9a0f0-173">如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="9a0f0-174">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="9a0f0-175">當您使用 DomainName 參數時，您必須為 SIP 網域 FQDN 使用適當的首碼。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="9a0f0-176">例如：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="9a0f0-177">若要指派個別的憑證類型，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="9a0f0-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="9a0f0-178">其中，"Thumbprint" 是顯示新頒發的個別憑證的指紋。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a0f0-179">請注意，只有執行步驟12和13的帳戶才能使用適當的許可權來存取憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="9a0f0-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="9a0f0-180">如果您無法以擁有這些許可權的帳戶登入，或者如果您使用的是您憑證的公用或遠端憑證授權單位，您必須透過 Lync Server 部署嚮導要求他們，這會在本文.</span><span class="sxs-lookup"><span data-stu-id="9a0f0-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

