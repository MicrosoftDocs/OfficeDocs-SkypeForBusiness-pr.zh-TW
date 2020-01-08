---
title: Lync Server 2013：針對自動探索設定憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="6e9c8-102">在 Lync Server 2013 中設定自動探索的憑證</span><span class="sxs-lookup"><span data-stu-id="6e9c8-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e9c8-103">_**主題上次修改日期：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="6e9c8-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="6e9c8-104">您的主管池、前端伺服器池及反向 proxy 的憑證需要額外的消費者替換名稱專案來支援與 Lync 用戶端的安全連線。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e9c8-105">您可以使用<STRONG>CsCertificate</STRONG> Cmdlet 來查看目前指派的憑證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="6e9c8-106">不過，預設的視圖會截斷憑證的屬性，而不會顯示 SubjectAlternativeNames 屬性中的所有值。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="6e9c8-107">您可以使用<STRONG>CsCertificate</STRONG> 、 <STRONG>Request</STRONG>CsCertificate 和<STRONG>設定 CsCertificate</STRONG> Cmdlet 來查看部分資訊，並要求並指派證書。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="6e9c8-108">不過，如果您不確定目前憑證上的 subject 替換名稱（SAN）屬性，就不是最佳的使用方法。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="6e9c8-109">若要查看憑證及所有屬性成員，建議您使用<EM>Microsoft 管理主控台（MMC）</EM>中的 [憑證] 管理單元，或使用 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="6e9c8-110">在 Lync Server 部署嚮導中，您可以使用 [憑證] 嚮導來查看憑證屬性。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="6e9c8-111">使用 Lync Server 管理命令介面和<EM>Microsoft 管理主控台（MMC）</EM>來查看、要求及指派憑證的程式在下列程式中詳細說明。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="6e9c8-112">若要使用 Lync Server 部署嚮導，請參閱這裡的詳細資料：如果您已部署選用控制器或控制器池：<A href="lync-server-2013-configure-certificates-for-the-director.md">在 Lync Server 2013 中設定控制器的憑證</A>。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="6e9c8-113">若是前端伺服器或前端池，請參閱這裡的詳細資料：<A href="lync-server-2013-configure-certificates-for-servers.md">在 Lync Server 2013 中設定伺服器的憑證</A>。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="6e9c8-114">此程式中的初始步驟是準備步驟，以指導您瞭解目前證書所扮演的角色。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="6e9c8-115">根據預設，證書將沒有 lyncdiscover。&lt;sipdomain&gt;或 lyncdiscoverinternal。&lt;內部功能變數名稱&gt;專案，除非您先前已安裝過行動服務，或事先已準備好您的憑證。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="6e9c8-116">此程式會使用範例 SIP 功能變數名稱 "contoso.com" 和範例內部功能變數名稱 "contoso.net"。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="6e9c8-117">Lync Server 2013 和 Lync Server 2010 的預設憑證設定是使用單一憑證（名為「預設」）做為預設值（除了 web 服務以外的所有用途）、WebServicesExternal 和 WebServicesInternal。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="6e9c8-118">選擇性設定是針對每個用途使用個別的憑證。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="6e9c8-119">您可以使用 Lync Server 管理命令介面和 Windows PowerShell Cmdlet，或使用 Lync Server 部署嚮導中的 [憑證] 嚮導來管理憑證。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="6e9c8-120">使用 Lync Server 管理命令介面將憑證更新為新的消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="6e9c8-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="6e9c8-121">使用具有本機系統管理員許可權和許可權的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="6e9c8-122">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6e9c8-123">找出已指派給伺服器的憑證和使用的類型。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="6e9c8-124">您必須在下一個步驟中指定此資訊，才能指派已更新的憑證。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="6e9c8-125">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="6e9c8-126">查看上一個步驟的輸出，查看是否已指派單一憑證給多個用途，或是否指派給每個使用不同的憑證。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="6e9c8-127">查看 Use 參數，以瞭解如何使用憑證。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="6e9c8-128">比較所顯示之憑證的指紋參數，以查看相同的憑證是否有多個用途。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="6e9c8-129">更新證書。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-129">Update the certificate.</span></span> <span data-ttu-id="6e9c8-130">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="6e9c8-131">例如，如果**CsCertificate** Cmdlet 顯示使用預設值的憑證，另一種是使用 WebServicesInternal，而另一個是使用 WebServicesExternal，而另一個使用，則在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="6e9c8-132">**重要事項：**</span><span class="sxs-lookup"><span data-stu-id="6e9c8-132">**Important:**</span></span>
    
    <span data-ttu-id="6e9c8-133">如果每次使用都指派了個別的憑證（每個憑證的指紋值不一樣），請務必不要執行**CsCertificate** Cmdlet 與多種類型。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="6e9c8-134">在這種情況下，請針對每個用途分別執行**CsCertificate** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="6e9c8-135">例如：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="6e9c8-136">若要查看憑證，請按一下 [**開始**]，然後按一下 [**執行 ...**]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="6e9c8-137">輸入 MMC 以開啟 Microsoft 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="6e9c8-138">在 MMC 功能表中，選取 [檔案 **]，選取**[**新增/移除管理單元 ...**]，選取 [憑證]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="6e9c8-139">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-139">Click **Add**.</span></span> <span data-ttu-id="6e9c8-140">出現提示時，請選取 [**電腦帳戶**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="6e9c8-141">如果憑證位於這台電腦上，請選取 [**本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="6e9c8-142">如果憑證位於其他電腦上，請選取 [**另一台電腦**]，輸入電腦的完整功能變數名稱，或按一下 [在**輸入要選取的物件名稱**] 中的 **[流覽]** ，輸入電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="6e9c8-143">按一下 [**檢查名稱**]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-143">Click **Check Names**.</span></span> <span data-ttu-id="6e9c8-144">解析電腦名稱稱時，它會加上底線。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="6e9c8-145">按一下 **[確定]**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="6e9c8-146">按一下 **[確定]** ，確認選取範圍，然後關閉 [**新增或移除管理單元**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6e9c8-147">如果證書沒有顯示在主控台中，請確定您沒有選取 [使用者或服務]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="6e9c8-148">您必須選取 [電腦]，否則您將無法找到 probper 憑證。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="6e9c8-149">若要查看憑證的屬性，請展開 [**憑證**]，展開 [**個人**]，然後選取 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="6e9c8-150">選取要查看的憑證，以滑鼠右鍵按一下憑證，然後選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="6e9c8-151">在 [**憑證**] 視圖中，選取 [**詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="6e9c8-152">您可以從這裡選取 [ **subject** ]，然後選取 [指派的受領人名稱及相關聯的屬性] 來選取證書受領人名稱。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="6e9c8-153">若要查看指派的主題替換名稱，請選取 [ **Subject 替換名稱**]。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="6e9c8-154">隨即會顯示所有指派的主體替換名稱。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="6e9c8-155">根據預設，在屬性中找到的 [subject 替換名稱] 是「 **DNS 名稱**」。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="6e9c8-156">您應該會看到下列成員（無論是 DNS 主機（A 或 IPv6 AAAA）記錄中所代表的，都應該是完全限定功能變數名稱：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="6e9c8-157">此池的 [池名稱]，如果這不是 [池]，則則是單一伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="6e9c8-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="6e9c8-158">證書指派的伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="6e9c8-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="6e9c8-159">簡單的 URL 記錄，通常符合和撥入</span><span class="sxs-lookup"><span data-stu-id="6e9c8-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="6e9c8-160">Web 服務內部和 Web 服務外部名稱（例如 webpool01.contoso.net、webpool01.contoso.com），根據拓撲建立器和跨 ridden Web 服務選擇中的選擇進行。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="6e9c8-161">如果已指定，則 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="6e9c8-162">最後一個專案是您最感興趣的專案–如果有 lyncdiscover 和 lyncdiscoverinternal 的 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="6e9c8-163">有了這些資訊之後，您就可以關閉證書視圖和 MMC。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="6e9c8-164">如果自動探索服務，即 lyncdiscover。\>網功能變數名稱稱\>和 lyncdiscoverinternal。\<功能變數名稱\> （根據這是外部或內部憑證）缺少消費者備用名稱，且您針對預設、WebServicesInternal 和 WebServiceExternal 類型使用單一預設憑證，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="6e9c8-165">在 Lync Server Management Shell 命令列提示中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="6e9c8-166">如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="6e9c8-167">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="6e9c8-168">當您使用 DomainName 參數時，您必須為 lyncdiscoverinternal 和 lyncdiscover 記錄定義 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="6e9c8-169">例如：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="6e9c8-170">若要指派憑證，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="6e9c8-171">其中，"Thumbprint" 是新頒發的憑證所顯示的指紋。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="6e9c8-172">如果針對預設、WebServicesInternal 和 WebServicesExternal 使用不同的憑證時，缺少內部自動探索消費者備用名稱，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="6e9c8-173">在 Lync Server Management Shell 命令列提示中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="6e9c8-174">如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="6e9c8-175">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="6e9c8-176">當您使用 DomainName 參數時，必須針對 SIP 網域 FQDN 使用適當的首碼。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="6e9c8-177">例如：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="6e9c8-178">如果缺少外部自動探索消費者替換名稱，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="6e9c8-179">如果您有多個 SIP 網域，則無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="6e9c8-180">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="6e9c8-181">當您使用 DomainName 參數時，必須針對 SIP 網域 FQDN 使用適當的首碼。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="6e9c8-182">例如：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="6e9c8-183">若要指派個別的憑證類型，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="6e9c8-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="6e9c8-184">其中，"Thumbprint" 是顯示新頒發的個別憑證的指紋。</span><span class="sxs-lookup"><span data-stu-id="6e9c8-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

