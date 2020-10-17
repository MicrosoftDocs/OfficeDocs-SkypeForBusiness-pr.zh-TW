---
title: Lync Server 2013：在 IIS 虛擬目錄上確認或設定驗證和憑證
description: Lync Server 2013：在 IIS 虛擬目錄上確認或設定驗證和憑證。
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
ms.openlocfilehash: 5e4d583eda7f0c7fb32b51dd5df6eb48af9b20d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560209"
---
# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="e23a4-103">在 Lync Server 2013 中驗證或設定 IIS 虛擬目錄上的驗證和憑證</span><span class="sxs-lookup"><span data-stu-id="e23a4-103">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e23a4-104">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="e23a4-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="e23a4-105">使用下列程式來設定網際網路資訊服務上的憑證 (IIS) 虛擬目錄，或確認已正確設定憑證。</span><span class="sxs-lookup"><span data-stu-id="e23a4-105">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="e23a4-106">在內部 Lync 伺服器集區中執行 IIS 的每一部伺服器及選用的 Director 或 Director 集區伺服器上，執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="e23a4-106">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e23a4-107">下列程式會定義一種程式，用以要求結合使用的憑證，以用於所有用途的 Lync Server、內部網站和 IIS 中的外部網站。</span><span class="sxs-lookup"><span data-stu-id="e23a4-107">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="e23a4-108">Lync Server 2010 引進一組 Lync Server Management Shell &nbsp; Windows PowerShell Cmdlet，以用於管理憑證要求、匯入和工作分派的速成目的。</span><span class="sxs-lookup"><span data-stu-id="e23a4-108">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="e23a4-109">程序中假設有內部部署的憑證授權單位 (CA) 可處理要求。</span><span class="sxs-lookup"><span data-stu-id="e23a4-109">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="e23a4-110">如果您出於 Lync Server 目的使用公用憑證，或您的 CA 需要離線要求，請參閱本主題中的詳細語法，以取得-Output 參數的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e23a4-110">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="e23a4-111"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="e23a4-111"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e23a4-112">設定 IIS 虛擬目錄上的驗證及憑證</span><span class="sxs-lookup"><span data-stu-id="e23a4-112">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e23a4-113">若要順利完成下列，您必須登入 (前端伺服器或已安裝 web 服務之 Director) 的電腦，以及本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="e23a4-113">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="e23a4-114">對於將向其要求憑證的憑證授權單位，您必須擁有該憑證授權單位的「讀取」\*\*\*\* 和「註冊」\*\*\*\* 權限。</span><span class="sxs-lookup"><span data-stu-id="e23a4-114">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="e23a4-115">如果將設定並傳送離線憑證要求，則不需要對憑證授權單位的權限。</span><span class="sxs-lookup"><span data-stu-id="e23a4-115">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="e23a4-116">按一下 **[開始]**，選取 **[所有程式]**、**[系統管理工具]**，然後按一下 **[Internet Information Services (IIS) 管理員]**。</span><span class="sxs-lookup"><span data-stu-id="e23a4-116">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="e23a4-p104">在 **[Internet Information Services (IIS) 管理員]** 中，選取 **[伺服器名稱]**。在 **[功能檢視]** 中，選取 **[伺服器憑證]**，按右鍵並選取 **[開啟功能]**。</span><span class="sxs-lookup"><span data-stu-id="e23a4-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e23a4-p105">在 [伺服器憑證功能檢視] 中，如果有憑證指派給伺服器，將會在此顯示。如果有憑證符合 IIS 中 External Web Site 的要求，可以重複使用該憑證。要檢視憑證，在憑證按右鍵並選取 <STRONG>[檢視...]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e23a4-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="e23a4-122">在您要求憑證的前端伺服器或 Director 上，依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e23a4-122">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="e23a4-123">在 Lync Server 管理命令介面中，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e23a4-123">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="e23a4-p106">輸出為目前在伺服器上電腦個人憑證存放區中的憑證清單。請注意：在組合憑證中 (亦即預設 Web 服務內部及 Web 服務外部使用相同的憑證)，「使用」屬性會填入 Default, WebServicesInternal 及 WebServicesExternal。每個「使用」類型也會有相同的「指紋」屬性。以下範例顯示 Get-CsCertificate 的輸出範例：</span><span class="sxs-lookup"><span data-stu-id="e23a4-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="e23a4-128">![目前 scert 狀態的 Get-CsCertificate 資訊](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "目前 scert 狀態的 Get-CsCertificate 資訊")</span><span class="sxs-lookup"><span data-stu-id="e23a4-128">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="e23a4-129">在 Lync Server 管理命令介面中，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e23a4-129">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="e23a4-130">完整命令將類似下列範例：</span><span class="sxs-lookup"><span data-stu-id="e23a4-130">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e23a4-p107">依預設，Request-CsCertificate 會在主體名稱中填入伺服器或集區名稱，並且在主體替代名稱的項目中填入伺服器 FQDN、集區 FQDN、簡單 URL FQDN 以及內部與外部 Web 服務 FQDN。這是透過參考部署中的拓撲文件。如果缺少某個值，而且指定了–Verbose 參數，將會通知您別名的計算值與實際值不同，但不會告知缺少哪些值，不過會提供您 Cmdlet 參考的整個計算值。可使用輸出中的計算別名字串，重新要求會包含所有值的新憑證。</span><span class="sxs-lookup"><span data-stu-id="e23a4-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="e23a4-136">![使用 Request-CsCertifica 從 cert 要求輸出](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "使用 Request-CsCertifica 從 cert 要求輸出")</span><span class="sxs-lookup"><span data-stu-id="e23a4-136">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="e23a4-137">在 Lync Server 管理命令介面中，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e23a4-137">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="e23a4-138">完整命令將類似下列範例：</span><span class="sxs-lookup"><span data-stu-id="e23a4-138">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="e23a4-139">Set-CsCertificate Cmdlet 的輸出會顯示相同的憑證 (以憑證指紋識別) 已指派給 Default, WebServicesExternal 及 WebServicesInternal 使用。</span><span class="sxs-lookup"><span data-stu-id="e23a4-139">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="e23a4-140">![從 IIS 上的 Set-CsCertificate 輸出 WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "從 IIS 上的 Set-CsCertificate 輸出 WebExt")</span><span class="sxs-lookup"><span data-stu-id="e23a4-140">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e23a4-141">確認或設定 IIS 虛擬目錄的驗證與憑證</span><span class="sxs-lookup"><span data-stu-id="e23a4-141">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e23a4-142">按一下 **[開始]**，選取 **[所有程式]**、[系統管理工具]\*\*\*\*，然後按一下 **[Internet Information Services (IIS) 管理員]**。</span><span class="sxs-lookup"><span data-stu-id="e23a4-142">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="e23a4-143">在 [ **Internet Information Services (IIS) 管理員**] 中，展開 [ **ServerName**]，然後展開 [ **網站**]。</span><span class="sxs-lookup"><span data-stu-id="e23a4-143">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="e23a4-144">用滑鼠右鍵按一下 **[Lync Server External Web Site]**，然後按一下 **[編輯繫結]**。</span><span class="sxs-lookup"><span data-stu-id="e23a4-144">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="e23a4-145">確認 https 關聯至連接埠 4443，然後按一下 **[https]**。</span><span class="sxs-lookup"><span data-stu-id="e23a4-145">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="e23a4-146">選取 HTTPS 專案，按一下 [ **編輯**]，然後確認 Lync Server WebServicesExternalCertificate 已系結至此通訊協定。</span><span class="sxs-lookup"><span data-stu-id="e23a4-146">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="e23a4-147">與來自 Set-CsCertificate Cmdlet 的指紋比較，確認預期的憑證已正確與 HTTPS 繫結關聯。</span><span class="sxs-lookup"><span data-stu-id="e23a4-147">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e23a4-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e23a4-148">See Also</span></span>


[<span data-ttu-id="e23a4-149">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e23a4-149">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="e23a4-150">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e23a4-150">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

