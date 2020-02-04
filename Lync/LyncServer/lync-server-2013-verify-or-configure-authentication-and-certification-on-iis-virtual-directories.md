---
title: Lync Server 2013：在 IIS 虛擬目錄上確認或設定驗證和憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="e58e0-102">在 Lync Server 2013 中的 IIS 虛擬目錄上確認或設定驗證和憑證</span><span class="sxs-lookup"><span data-stu-id="e58e0-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e58e0-103">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="e58e0-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="e58e0-104">使用下列程式在您的網際網路資訊服務（IIS）虛擬目錄上設定憑證，或驗證憑證已正確設定。</span><span class="sxs-lookup"><span data-stu-id="e58e0-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="e58e0-105">針對您內部 Lync 伺服器池中的每個執行 IIS 的伺服器，以及選用的控制器或控制器池伺服器，執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="e58e0-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e58e0-106">下列程式定義一個程式，以要求在 IIS 中針對所有用途的 Lync Server、內部網站和外部網站，提出所用的合併憑證。</span><span class="sxs-lookup"><span data-stu-id="e58e0-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="e58e0-107">Lync Server 2010 引進了一組 Lync Server 管理命令&nbsp;介面（Windows PowerShell Cmdlet），以管理憑證要求、匯入及作業的快速用途。</span><span class="sxs-lookup"><span data-stu-id="e58e0-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="e58e0-108">此程式假設有一個內部部署的認證機構（CA），可處理該要求。</span><span class="sxs-lookup"><span data-stu-id="e58e0-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="e58e0-109">如果您使用的是適用于 Lync Server 的公用憑證，或您的 CA 需要離線要求，請參閱本主題中的詳細語法，以取得有關– Output 參數的資訊。</span><span class="sxs-lookup"><span data-stu-id="e58e0-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="e58e0-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">要求-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="e58e0-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e58e0-111">在 IIS 虛擬目錄上設定驗證與憑證</span><span class="sxs-lookup"><span data-stu-id="e58e0-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e58e0-112">若要成功完成下列作業，您必須登入已安裝 web 服務的電腦（前端伺服器或控制器），而且是本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="e58e0-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="e58e0-113">如果憑證授權單位是貴組織的憑證授權單位，您必須在您要從其申請證書的憑證授權單位上擁有 [**讀取**] 和 [**註冊**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="e58e0-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="e58e0-114">如果您要設定並傳送離線證書要求，則不需要擁有憑證授權單位的許可權。</span><span class="sxs-lookup"><span data-stu-id="e58e0-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="e58e0-115">按一下 [**開始**]，選取 [**所有程式**]，選取 [**管理工具**]，然後按一下 **[網際網路資訊服務（IIS）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="e58e0-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="e58e0-116">在 **[網際網路資訊服務（IIS）管理員**] 中，選取 [**伺服器名稱**]。</span><span class="sxs-lookup"><span data-stu-id="e58e0-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="e58e0-117">在 [**功能] 視圖**中，選取 [**伺服器憑證**]，按一下滑鼠右鍵，然後選取 [**開啟功能**]。</span><span class="sxs-lookup"><span data-stu-id="e58e0-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e58e0-118">在 [伺服器憑證功能] 視圖中，如果有指派給伺服器的憑證，就會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="e58e0-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="e58e0-119">如果有與 IIS 中外部網站需求相符的憑證，您可以重新使用該憑證。</span><span class="sxs-lookup"><span data-stu-id="e58e0-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="e58e0-120">若要查看憑證，請以滑鼠右鍵按一下憑證，然後選取 [<STRONG>查看 ...]。</STRONG></span><span class="sxs-lookup"><span data-stu-id="e58e0-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="e58e0-121">在您要求憑證的前端伺服器或主管中，按一下 [**開始**]，選取 [**所有程式**]，選取 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server Management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="e58e0-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="e58e0-122">在 Lync Server 管理命令介面中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="e58e0-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="e58e0-123">[輸出] 是電腦個人憑證存放區中目前在伺服器上的憑證清單。</span><span class="sxs-lookup"><span data-stu-id="e58e0-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="e58e0-124">請注意，在結合的憑證（也就是預設、web 服務內部和 web 服務外部使用相同的憑證）中，您會看到 Use 屬性會以預設、WebServicesInternal 和 WebServicesExternal 來填入。</span><span class="sxs-lookup"><span data-stu-id="e58e0-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="e58e0-125">此外，每個使用類型的 Thumbprint 屬性都是相同的。</span><span class="sxs-lookup"><span data-stu-id="e58e0-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="e58e0-126">以下範例顯示 CsCertificate 的輸出範例：</span><span class="sxs-lookup"><span data-stu-id="e58e0-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="e58e0-127">![目前 scert 狀態的 Get-CsCertificate 資訊](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "目前 scert 狀態的 Get-CsCertificate 資訊")</span><span class="sxs-lookup"><span data-stu-id="e58e0-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="e58e0-128">在 Lync Server 管理命令介面中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="e58e0-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="e58e0-129">會出現完整命令的位置，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="e58e0-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e58e0-130">根據預設，Request CsCertificate 會使用伺服器或池名稱填入 subject 名稱，並以伺服器 FQDN、池 FQDN、簡單的 URL Fqdn 以及內部和外部 web 服務 Fqdn 來填入 subject 替換名稱中的專案。</span><span class="sxs-lookup"><span data-stu-id="e58e0-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="e58e0-131">它會透過參照您部署中的 [拓撲] 檔來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="e58e0-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="e58e0-132">如果缺少值，而且您已指定– Verbose 參數，系統會通知您替換名稱的計算值與實際值不一樣，但不會通知您缺少哪些值。</span><span class="sxs-lookup"><span data-stu-id="e58e0-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="e58e0-133">它會為您提供 Cmdlet 所參照的整個計算值。</span><span class="sxs-lookup"><span data-stu-id="e58e0-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="e58e0-134">在輸出中使用計算出的替換名稱字串，重新要求將包含所有值的新憑證。</span><span class="sxs-lookup"><span data-stu-id="e58e0-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="e58e0-135">![使用 Request-CsCertifica 從 cert 要求輸出](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "使用 Request-CsCertifica 從 cert 要求輸出")</span><span class="sxs-lookup"><span data-stu-id="e58e0-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="e58e0-136">在 Lync Server 管理命令介面中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="e58e0-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="e58e0-137">會出現完整命令的位置，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="e58e0-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="e58e0-138">CsCertificate Cmdlet 的輸出會顯示相同的憑證（由憑證指紋所識別）會指派給預設、WebServicesExternal 和 WebServicesInternal 用法。</span><span class="sxs-lookup"><span data-stu-id="e58e0-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="e58e0-139">![IIS WebExt 之 Set-CsCertificate 的輸出](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt 之 Set-CsCertificate 的輸出")</span><span class="sxs-lookup"><span data-stu-id="e58e0-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e58e0-140">在 IIS 虛擬目錄上驗證或設定驗證與憑證</span><span class="sxs-lookup"><span data-stu-id="e58e0-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e58e0-141">按一下 [**開始**]，選取 [**所有程式**]，選取 [**管理工具**]，然後按一下 **[網際網路資訊服務（IIS）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="e58e0-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="e58e0-142">在 **[網際網路資訊服務（IIS）管理員**] 中，展開 [**伺服器名稱**]，然後展開 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="e58e0-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="e58e0-143">以滑鼠右鍵按一下 [ **Lync Server 外部**網站]，然後按一下 [**編輯**系結]</span><span class="sxs-lookup"><span data-stu-id="e58e0-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="e58e0-144">確認 HTTPs 與埠4443相關聯，然後按一下 [ **HTTPs**]。</span><span class="sxs-lookup"><span data-stu-id="e58e0-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="e58e0-145">選取 HTTPS 專案，按一下 [**編輯**]，然後確認 [Lync Server WebServicesExternalCertificate] 已系結至此通訊協定。</span><span class="sxs-lookup"><span data-stu-id="e58e0-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="e58e0-146">比較指紋與 CsCertificate Cmdlet，以確保預期的憑證與 HTTPS 系結正確關聯。</span><span class="sxs-lookup"><span data-stu-id="e58e0-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e58e0-147">請參閱</span><span class="sxs-lookup"><span data-stu-id="e58e0-147">See Also</span></span>


[<span data-ttu-id="e58e0-148">CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e58e0-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="e58e0-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e58e0-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

