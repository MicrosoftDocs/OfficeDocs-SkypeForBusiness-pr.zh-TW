---
title: Lync Server 2013：設定自動探索的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502110"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="2e80b-102">在 Lync Server 2013 中設定自動探索的憑證</span><span class="sxs-lookup"><span data-stu-id="2e80b-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e80b-103">_**主題上次修改日期：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="2e80b-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="2e80b-104">Director 集區、前端集區及反向 proxy 的憑證，都需要額外的主體替代名稱專案，以支援與 Lync 用戶端的安全連線。</span><span class="sxs-lookup"><span data-stu-id="2e80b-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e80b-105">您可以使用 <STRONG>Get-CsCertificate</STRONG> Cmdlet 來檢視目前指派的憑證相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2e80b-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="2e80b-106">然而，預設檢視會截斷憑證屬性，而且不會顯示 SubjectAlternativeNames 屬性中所有的值。</span><span class="sxs-lookup"><span data-stu-id="2e80b-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="2e80b-107">您可以使用 <STRONG>Get-CsCertificate</STRONG>、<STRONG>Request-</STRONG>CsCertificate 和 <STRONG>Set-CsCertificate</STRONG> Cmdlet 來檢視部分資訊，並要求及指派憑證。</span><span class="sxs-lookup"><span data-stu-id="2e80b-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="2e80b-108">不過，如果您不確定目前憑證上主體替代名稱 (SAN) 的屬性，這並不是最好的方法。</span><span class="sxs-lookup"><span data-stu-id="2e80b-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="2e80b-109">若要查看憑證和所有的屬性成員，建議使用 <EM>Microsoft Management Console (MMC) </EM> 中的 [憑證] 嵌入式管理單元，或使用 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="2e80b-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="2e80b-110">在 [Lync Server 部署嚮導] 中，您可以使用 [憑證] 嚮導來查看憑證屬性。</span><span class="sxs-lookup"><span data-stu-id="2e80b-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="2e80b-111">下列程式會詳細說明如何使用 Lync Server 管理命令介面和 <EM>Microsoft Management Console (MMC) </EM> 來查看、要求與指派憑證的程式。</span><span class="sxs-lookup"><span data-stu-id="2e80b-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="2e80b-112">若要使用 Lync Server 部署嚮導，請參閱此處的詳細資料：如果您已部署選用的 Director 或 Director 集區： <A href="lync-server-2013-configure-certificates-for-the-director.md">在 Lync Server 2013 中設定 director 的憑證</A>。</span><span class="sxs-lookup"><span data-stu-id="2e80b-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="2e80b-113">若為前端伺服器或前端集區，請參閱以下的詳細資料： <A href="lync-server-2013-configure-certificates-for-servers.md">在 Lync Server 2013 中為伺服器設定憑證</A>。</span><span class="sxs-lookup"><span data-stu-id="2e80b-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="2e80b-114">此程序中的最初步驟是準備步驟，引導您成為目前憑證扮演的角色。</span><span class="sxs-lookup"><span data-stu-id="2e80b-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="2e80b-115">根據預設，憑證不會有 lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain &gt; 或 lyncdiscoverinternal。 &lt;內部功能變數名稱 &gt; 專案，除非您先前已安裝行動服務，或是預先準備好您的憑證。</span><span class="sxs-lookup"><span data-stu-id="2e80b-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="2e80b-116">這個程序使用 SIP 網域名稱範例 ‘contoso.com’ 及內部網域名稱範例  ‘contoso.net’。</span><span class="sxs-lookup"><span data-stu-id="2e80b-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="2e80b-117">Lync Server 2013 和 Lync Server 2010 的預設憑證設定是使用名為 ' Default ) ' 的單一憑證 (，但 web 服務) 、WebServicesExternal 和 WebServicesInternal 以外的目的預設 (。</span><span class="sxs-lookup"><span data-stu-id="2e80b-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="2e80b-118">選用設定是針對每種用途使用不同的憑證。</span><span class="sxs-lookup"><span data-stu-id="2e80b-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="2e80b-119">您可以使用 Lync Server 管理命令介面和 Windows PowerShell Cmdlet 來管理憑證，或使用 Lync Server 部署嚮導中的憑證嚮導來管理憑證。</span><span class="sxs-lookup"><span data-stu-id="2e80b-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="2e80b-120">使用 Lync Server 管理命令介面來更新具有新主體替代名稱的憑證</span><span class="sxs-lookup"><span data-stu-id="2e80b-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="2e80b-121">使用具有本機系統管理員權限的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="2e80b-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="2e80b-122">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="2e80b-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2e80b-p104">找出哪些憑證已經指派給伺服器，以及使用類型為何。在下一個步驟中，您會需要此資訊來指派更新的憑證。請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="2e80b-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="2e80b-p105">查閱上一個步驟的輸出，看看是否有單一憑證指派至多個用途，或者是否為每個用途指派不同的憑證。查閱 Use 參數，以找出憑證的用法。針對所顯示的憑證比較 Thumbprint 參數，看看相同的憑證是否有多個用途。</span><span class="sxs-lookup"><span data-stu-id="2e80b-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="2e80b-p106">更新憑證。在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="2e80b-p106">Update the certificate. At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="2e80b-131">例如，如果 **Get-CsCertificate** Cmdlet 顯示一個含有 Use of Default 的憑證、一個含有 Use of WebServicesInternal 的憑證，以及一個含有 Use of WebServicesExternal 的憑證 , 而且它們全都有相同的憑證指紋值，請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="2e80b-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="2e80b-132">**重要事項：**</span><span class="sxs-lookup"><span data-stu-id="2e80b-132">**Important:**</span></span>
    
    <span data-ttu-id="2e80b-133">如果為每個用途指派不同的憑證 (每個憑證的憑證指紋值都不同)，則切勿以多種類型來執行 **Set-CsCertificate** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2e80b-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="2e80b-134">在此情況下，要為每個用途個別執行 **Set-CsCertificate** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2e80b-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="2e80b-135">例如：</span><span class="sxs-lookup"><span data-stu-id="2e80b-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="2e80b-p108">如果要檢視憑證，依序按一下 **[開始]** 和 **[執行…]**。鍵入 MMC 以開啟 Microsoft Management Console。</span><span class="sxs-lookup"><span data-stu-id="2e80b-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="2e80b-p109">從 MMC 功能表中，依序選取 **[檔案]**、**[新增/移除嵌入式管理單元…]** 和 [憑證]。按一下 **[新增]**。出現提示時，選取 **[電腦帳戶]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2e80b-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="2e80b-141">如果憑證位於這部電腦上，請選取 [ **本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="2e80b-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="2e80b-142">如果憑證位於另一台電腦上，則選取 **[另一台電腦]**，鍵入電腦的完整網域名稱或按一下 **[請輸入物件名稱來選取]** 中的 **[瀏覽]**，鍵入電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="2e80b-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="2e80b-143">按一下 **[檢查名稱]**。</span><span class="sxs-lookup"><span data-stu-id="2e80b-143">Click **Check Names**.</span></span> <span data-ttu-id="2e80b-144">解析出電腦的名稱之後，將會加上底線。</span><span class="sxs-lookup"><span data-stu-id="2e80b-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="2e80b-145">依序按一下 **[確定]** 和 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="2e80b-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="2e80b-146">按一下 **[確定]** 以認可選取項目，然後關閉 **[新增/移除嵌入式管理單元]** 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="2e80b-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2e80b-147">如果憑證未出現在主控台中，請確定您沒有選取 [使用者或服務]。</span><span class="sxs-lookup"><span data-stu-id="2e80b-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="2e80b-148">您必須選取 [電腦]，否則您將無法找到 probper 憑證。</span><span class="sxs-lookup"><span data-stu-id="2e80b-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="2e80b-p112">如果要檢視憑證的屬性，依序展開 **[憑證]** 和 **[個人]**，然後選取 **[憑證]**。選取要檢視的憑證，用滑鼠右鍵按一下憑證，然後選取 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="2e80b-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="2e80b-p113">在 **[憑證]** 檢視中，選取 **[詳細資料]**。您可以在此處選取 **[主體]** 來選取憑證主體名稱，隨即顯示指派的主體名稱和相關屬性。</span><span class="sxs-lookup"><span data-stu-id="2e80b-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="2e80b-153">若要查看指派的主體替代名稱，請選取 [ **主體替代名稱**]。</span><span class="sxs-lookup"><span data-stu-id="2e80b-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="2e80b-154">隨即會顯示所有指派的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="2e80b-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="2e80b-155">根據預設，在屬性中找到的主體替代名稱是「 **DNS 名稱** 」類型。</span><span class="sxs-lookup"><span data-stu-id="2e80b-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="2e80b-156">若 IPv6 AAAA) 記錄，您應該會看到下列成員 (所有應該是的功能變數名稱（如 DNS 主機中所述） (A 或（如果有的話）：</span><span class="sxs-lookup"><span data-stu-id="2e80b-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="2e80b-157">此集區的集區名稱，或單一伺服器名稱 (如果不是集區)</span><span class="sxs-lookup"><span data-stu-id="2e80b-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="2e80b-158">被指派憑證的伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="2e80b-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="2e80b-159">簡單 URL 記錄，通常為 meet 和 dialin</span><span class="sxs-lookup"><span data-stu-id="2e80b-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="2e80b-160">Web 服務的內部及 Web 服務外部名稱 (例如，webpool01.contoso.net、webpool01.contoso.com) ，其依據拓撲產生器和透過 ridden Web 服務選取範圍內的選擇。</span><span class="sxs-lookup"><span data-stu-id="2e80b-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="2e80b-161">如果已指派，則 lyncdiscover。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2e80b-161">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="2e80b-162">和 lyncdiscoverinternal。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2e80b-162">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="2e80b-163">記錄。</span><span class="sxs-lookup"><span data-stu-id="2e80b-163">records.</span></span>
    
    <span data-ttu-id="2e80b-164">最後一項是您最感興趣的 – 是否有 lyncdiscover 和 lyncdiscoverinternal SAN 項目。</span><span class="sxs-lookup"><span data-stu-id="2e80b-164">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="2e80b-165">取得此資訊之後，即可關閉憑證檢視和 MMC。</span><span class="sxs-lookup"><span data-stu-id="2e80b-165">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="2e80b-166">如果自動探索服務，表示 lyncdiscover。 \>功能變數名稱 \> 和 lyncdiscoverinternal。\<domain name\></span><span class="sxs-lookup"><span data-stu-id="2e80b-166">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\></span></span> <span data-ttu-id="2e80b-167"> (根據此為外部或內部憑證) 主體替代名稱缺失，且預設使用單一預設憑證、WebServicesInternal 和 WebServiceExternal 類型，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2e80b-167">(based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="2e80b-168">在 Lync Server 管理命令介面命令列提示字元處，輸入：</span><span class="sxs-lookup"><span data-stu-id="2e80b-168">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="2e80b-169">如果您有許多 SIP 網域，則無法使用新的 AllSipDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="2e80b-169">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="2e80b-170">相反地，您必須使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="2e80b-170">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="2e80b-171">當您使用 DomainName 參數時，必須定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2e80b-171">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="2e80b-172">例如：</span><span class="sxs-lookup"><span data-stu-id="2e80b-172">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="2e80b-173">如果要指派憑證，請鍵入：</span><span class="sxs-lookup"><span data-stu-id="2e80b-173">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="2e80b-174">其中 “Thumbprint” 代表對新發行的憑證顯示的指紋。</span><span class="sxs-lookup"><span data-stu-id="2e80b-174">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="2e80b-175">針對在對 Default、WebServicesInternal 和 WebServicesExternal 使用不同憑證時遺漏的內部自動探索主體替代名稱，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2e80b-175">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="2e80b-176">在 Lync Server 管理命令介面命令列提示字元處，輸入：</span><span class="sxs-lookup"><span data-stu-id="2e80b-176">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="2e80b-p118">如果您有許多 SIP 網域，則不能使用新的 AllSipDomain 參數，而必須使用 DomainName 參數。當您使用 DomainName 參數時，必須為 SIP 網域 FQDN 使用適當的字首。例如：</span><span class="sxs-lookup"><span data-stu-id="2e80b-p118">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="2e80b-181">針對遺漏的外部自動探索主體替代名稱，在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="2e80b-181">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="2e80b-p119">如果您有許多 SIP 網域，則不能使用新的 AllSipDomain 參數，而必須使用 DomainName 參數。當您使用 DomainName 參數時，必須為 SIP 網域 FQDN 使用適當的字首。例如：</span><span class="sxs-lookup"><span data-stu-id="2e80b-p119">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="2e80b-186">如果要指派個別憑證類型，請鍵入：</span><span class="sxs-lookup"><span data-stu-id="2e80b-186">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="2e80b-187">其中 “Thumbprint” 代表對新發行的個別憑證顯示的指紋。</span><span class="sxs-lookup"><span data-stu-id="2e80b-187">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

