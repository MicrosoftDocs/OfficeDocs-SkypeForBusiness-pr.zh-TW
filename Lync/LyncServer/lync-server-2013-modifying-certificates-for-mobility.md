---
title: Lync Server 2013：修改行動的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b10ea662d055812b9fccaa730a936033aaea077c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515160"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="44264-102">在 Lync Server 2013 中修改行動憑證</span><span class="sxs-lookup"><span data-stu-id="44264-102">Modifying certificates for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44264-103">_**主題上次修改日期：** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="44264-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="44264-104">為了支援 Lync 環境與行動用戶端之間的安全連線，您的 Director 集區、前端集區和反向 proxy 的安全通訊端層 (SSL) 憑證必須使用其他的主體替代名稱來更新， (SAN) 專案。</span><span class="sxs-lookup"><span data-stu-id="44264-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="44264-105">如果您需要深入瞭解行動之憑證需求的詳細資訊，請參閱在 [Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)中的憑證需求一節，但基本上您必須使用包含的其他 SAN 專案從憑證授權單位單位取得新憑證，然後再使用本文的步驟來新增這些憑證。</span><span class="sxs-lookup"><span data-stu-id="44264-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="44264-106">當然，您開始之前，最好知道您的憑證已有哪些主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="44264-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="44264-107">如果您不確定已設定的內容，有許多方法可供您尋找。[！附注] 當您執行 **Get-CsCertificate** 及其他 PowerShell 命令以查看此資訊時， (在預設會) 透過此逐步進行的資料將會被截斷，所以您可能不會看到所有需要的屬性。</span><span class="sxs-lookup"><span data-stu-id="44264-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="44264-108">為了取得良好的憑證及其所有內容，您可以移至 Microsoft Management Console (MMC) 並載入 [憑證] 嵌入式管理單元， (我們也會逐步進行) ，您也可以只存回 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="44264-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="44264-109">如以上所述，下列步驟會逐步引導您使用 Lync Server 管理命令介面和 MMC 更新憑證。</span><span class="sxs-lookup"><span data-stu-id="44264-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="44264-110">如果您想要改為在 Lync Server 部署嚮導中使用憑證嚮導，請參閱設定 director 或 Director 集區的 [Lync server 2013 中的 director 憑證](lync-server-2013-configure-certificates-for-the-director.md) （如果您設定了一個 (您可能沒有) ）。</span><span class="sxs-lookup"><span data-stu-id="44264-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="44264-111">若為前端伺服器或前端集區，您會想要 [在 Lync server 2013 中查看 [設定伺服器的憑證](lync-server-2013-configure-certificates-for-servers.md)]。</span><span class="sxs-lookup"><span data-stu-id="44264-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="44264-112">您需要記住的最後一件事是，您的 Lync Server 2013 環境中可能有單一預設憑證，也可能會有預設 (的個別憑證，也就是 web 服務) 、WebServicesExternal 及 WebServicesInternal 的所有內容。</span><span class="sxs-lookup"><span data-stu-id="44264-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="44264-113">不管您的設定為何，這些步驟都應協助您執行。</span><span class="sxs-lookup"><span data-stu-id="44264-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="44264-114">使用 Lync Server 管理命令介面來更新具有新主體替代名稱的憑證</span><span class="sxs-lookup"><span data-stu-id="44264-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="44264-115">您必須使用具有本機系統管理員許可權的帳戶登入 Lync Server 2013 伺服器。</span><span class="sxs-lookup"><span data-stu-id="44264-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="44264-116">此外，如果您正在執行步驟12和之後的 PowerShell **Request-CsCertificate** ，該帳戶必須具有指定的憑證授權單位 (CA) 的許可權。</span><span class="sxs-lookup"><span data-stu-id="44264-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="44264-117">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="44264-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="44264-118">在您可以指派更新的憑證之前，您需要瞭解已指派給伺服器的憑證和使用類型。</span><span class="sxs-lookup"><span data-stu-id="44264-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="44264-119">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="44264-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="44264-120">請複查上一個步驟的輸出，以查看是否已指派單一憑證進行多種使用，或是否指派不同的憑證供每次使用。</span><span class="sxs-lookup"><span data-stu-id="44264-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="44264-121">請查看使用參數，以找出使用憑證的方式。</span><span class="sxs-lookup"><span data-stu-id="44264-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="44264-122">針對所顯示的憑證比較 Thumbprint 參數，看看相同的憑證是否有多個用途。</span><span class="sxs-lookup"><span data-stu-id="44264-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="44264-123">請留意指紋參數。</span><span class="sxs-lookup"><span data-stu-id="44264-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="44264-124">更新憑證。</span><span class="sxs-lookup"><span data-stu-id="44264-124">Update the certificate.</span></span> <span data-ttu-id="44264-125">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="44264-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="44264-126">例如，如果 **Get-CsCertificate** Cmdlet 顯示使用 Default 的憑證，另一個使用 WebServicesInternal 的憑證，另一個使用 WebServicesExternal 的指紋值，在命令列中，您應該輸入：</span><span class="sxs-lookup"><span data-stu-id="44264-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="44264-127">**重要事項：**</span><span class="sxs-lookup"><span data-stu-id="44264-127">**Important:**</span></span>
    
    <span data-ttu-id="44264-128">如果為每次使用指派個別的憑證 (因此，您上述檢查的指紋值因每個憑證) 而不同，因此您 **不** 需要以多種類型執行 **Set-CsCertificate** Cmdlet，如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="44264-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="44264-129">在此情況下，要為每個用途個別執行 **Set-CsCertificate** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="44264-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="44264-130">例如：</span><span class="sxs-lookup"><span data-stu-id="44264-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="44264-131">若要查看憑證 (或憑證) ，請按一下 [ **開始**]，然後按一下 [ **執行 ...**]。</span><span class="sxs-lookup"><span data-stu-id="44264-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="44264-132">鍵入 MMC 以開啟 Microsoft Management Console。</span><span class="sxs-lookup"><span data-stu-id="44264-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="44264-133">從 MMC 功能表中，依序選取 **[檔案]**、**[新增/移除嵌入式管理單元…]** 和 [憑證]。</span><span class="sxs-lookup"><span data-stu-id="44264-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="44264-134">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="44264-134">Click **Add**.</span></span> <span data-ttu-id="44264-135">出現提示時，選取 **[電腦帳戶]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="44264-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="44264-136">如果這是憑證所在的伺服器，請選取 [ **本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="44264-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="44264-137">如果憑證位於另一部電腦上，則應該選取**另一**部電腦，然後您可以輸入電腦的完整功能變數名稱，或按一下 [在**輸入要選取的物件名稱**] 中的 **[流覽]** ，然後輸入電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="44264-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="44264-138">按一下 **[檢查名稱]**。</span><span class="sxs-lookup"><span data-stu-id="44264-138">Click **Check Names**.</span></span> <span data-ttu-id="44264-139">當電腦的名稱解析時，它會加上底線。</span><span class="sxs-lookup"><span data-stu-id="44264-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="44264-140">依序按一下 **[確定]** 和 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="44264-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="44264-141">按一下 **[確定]** 以認可選取項目，然後關閉 **[新增/移除嵌入式管理單元]** 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="44264-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="44264-p113">如果要檢視憑證的屬性，依序展開 **[憑證]** 和 **[個人]**，然後選取 **[憑證]**。選取要檢視的憑證，用滑鼠右鍵按一下憑證，然後選取 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="44264-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="44264-p114">在 **[憑證]** 檢視中，選取 **[詳細資料]**。您可以在此處選取 **[主體]** 來選取憑證主體名稱，隨即顯示指派的主體名稱和相關屬性。</span><span class="sxs-lookup"><span data-stu-id="44264-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="44264-146">若要查看指派的主體替代名稱，請選取 [ **主體替代名稱**]。</span><span class="sxs-lookup"><span data-stu-id="44264-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="44264-147">所有指派的主體替代名稱會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="44264-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="44264-148">此處找到的主體替代名稱預設為「 **DNS 名稱** 」類型。</span><span class="sxs-lookup"><span data-stu-id="44264-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="44264-149">若 IPv6 AAAA) 記錄，您應該會看到下列成員 (所有應該是的功能變數名稱（如 DNS 主機中所述） (A 或（如果有的話）：</span><span class="sxs-lookup"><span data-stu-id="44264-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="44264-150">此集區的集區名稱，如果這不是集區，則為單一伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="44264-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="44264-151">被指派憑證的伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="44264-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="44264-152">簡單 URL 記錄，通常為 meet 和 dialin</span><span class="sxs-lookup"><span data-stu-id="44264-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="44264-153">Web 服務的內部及 Web 服務外部名稱 (例如，webpool01.contoso.net、webpool01.contoso.com) ，其依據拓撲產生器和透過 ridden Web 服務選取範圍內的選擇。</span><span class="sxs-lookup"><span data-stu-id="44264-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="44264-154">如果已指派，則 lyncdiscover。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="44264-154">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="44264-155">和 lyncdiscoverinternal。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="44264-155">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="44264-156">記錄。</span><span class="sxs-lookup"><span data-stu-id="44264-156">records.</span></span>
    
    <span data-ttu-id="44264-157">最後一個專案是您最感興趣的專案–如果有 lyncdiscover 和 lyncdiscoverinternal SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="44264-157">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="44264-158">如果您有多個要檢查的憑證，請重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="44264-158">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="44264-159">取得此資訊之後，即可關閉憑證檢視和 MMC。</span><span class="sxs-lookup"><span data-stu-id="44264-159">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="44264-160">如果自動探索服務主體替代名稱遺漏，而您對 Default、WebServicesInternal 和 WebServiceExternal 類型使用單一 Default 憑證，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="44264-160">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="44264-161">在 Lync Server 管理命令介面命令列提示字元處，輸入：</span><span class="sxs-lookup"><span data-stu-id="44264-161">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="44264-162">如果您有許多 SIP 網域，您就無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="44264-162">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="44264-163">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="44264-163">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="44264-164">當您使用 DomainName 參數時，您必須定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="44264-164">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="44264-165">例如：</span><span class="sxs-lookup"><span data-stu-id="44264-165">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="44264-166">如果要指派憑證，請鍵入：</span><span class="sxs-lookup"><span data-stu-id="44264-166">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="44264-167">其中 “Thumbprint” 代表對新發行的憑證顯示的指紋。</span><span class="sxs-lookup"><span data-stu-id="44264-167">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="44264-168">若為 Default、WebServicesInternal 和 WebServicesExternal 使用個別憑證時遺失內部自動探索 SAN，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="44264-168">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="44264-169">在 Lync Server 管理命令介面命令列提示字元處，輸入：</span><span class="sxs-lookup"><span data-stu-id="44264-169">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="44264-170">如果您有許多 SIP 網域，您就無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="44264-170">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="44264-171">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="44264-171">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="44264-172">當您使用 DomainName 參數時，您必須為 SIP 網域 FQDN 使用適當的首碼。</span><span class="sxs-lookup"><span data-stu-id="44264-172">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="44264-173">例如：</span><span class="sxs-lookup"><span data-stu-id="44264-173">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="44264-174">針對遺漏的外部自動探索主體替代名稱，在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="44264-174">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="44264-175">如果您有許多 SIP 網域，您就無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="44264-175">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="44264-176">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="44264-176">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="44264-177">當您使用 DomainName 參數時，您必須為 SIP 網域 FQDN 使用適當的首碼。</span><span class="sxs-lookup"><span data-stu-id="44264-177">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="44264-178">例如：</span><span class="sxs-lookup"><span data-stu-id="44264-178">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="44264-179">如果要指派個別憑證類型，請鍵入：</span><span class="sxs-lookup"><span data-stu-id="44264-179">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="44264-180">其中 “Thumbprint” 代表對新發行的個別憑證顯示的指紋。</span><span class="sxs-lookup"><span data-stu-id="44264-180">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="44264-181">請注意，只有在執行步驟12和13的帳戶有權存取具有適當許可權的憑證授權單位單位時，才應執行步驟12和13。</span><span class="sxs-lookup"><span data-stu-id="44264-181">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="44264-182">如果您無法使用具有這些許可權的帳戶登入，或是您為憑證使用 public 或 remote 憑證授權，則您必須透過 Lync Server 部署嚮導要求他們，在本文頂端已深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="44264-182">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

