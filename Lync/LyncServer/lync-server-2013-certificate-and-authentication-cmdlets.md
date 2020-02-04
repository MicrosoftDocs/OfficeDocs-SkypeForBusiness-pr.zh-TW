---
title: Lync Server 2013：憑證和驗證 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate and authentication cmdlets
ms:assetid: ebb51778-3558-49d2-8343-d83e7a731559
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415680(v=OCS.15)
ms:contentKeyID: 48185711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70fdd821dd80752875bab5d8981eed2347a0e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-and-authentication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="11b9e-102">Lync Server 2013 中的憑證和驗證 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="11b9e-102">Certificate and authentication cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11b9e-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="11b9e-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="11b9e-104">證書與驗證 Cmdlet 涵蓋各種不同的工作，包括伺服器和用戶端憑證的管理;管理使用者 Pin （個人識別碼）;同時管理 SIP 網域以及與網際網路資訊服務搭配使用的 Kerberos 帳戶。</span><span class="sxs-lookup"><span data-stu-id="11b9e-104">The certificate and authentication cmdlets cover a wide range of tasks, including the management of server and client certificates; the management of user PINs (personal identification numbers); and the management of both SIP domains and the Kerberos accounts used with Internet Information Services.</span></span>

<div>

## <a name="certificate-and-authentication-cmdlets"></a><span data-ttu-id="11b9e-105">憑證和驗證 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="11b9e-105">Certificate and Authentication Cmdlets</span></span>

<span data-ttu-id="11b9e-106">以下是直接與管理證書及驗證相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="11b9e-106">The following is a list of cmdlets that relate directly to managing certificates and authentication:</span></span>

<span data-ttu-id="11b9e-107">**憑證和驗證**</span><span class="sxs-lookup"><span data-stu-id="11b9e-107">**Certificates and Authentication**</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-108">[CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-108">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-109">[匯入-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-109">[Import-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-110">[移除-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-110">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-111">[要求-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-111">[Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-112">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-112">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-113">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-113">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-114">[CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-114">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-115">[吊銷-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-115">[Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-116">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-116">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-117">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-117">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-118">[解除鎖定-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-118">[Unlock-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-119">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-119">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-120">[新-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-120">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-121">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-121">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-122">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-122">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-123">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-123">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-124">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-124">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-125">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-125">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-126">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-126">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-127">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-127">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-128">[授與 CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-128">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-129">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-129">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-130">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-130">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-131">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-131">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-132">[CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-132">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-133">[New-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-133">[New-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-134">[移除-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-134">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-135">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-135">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="11b9e-136">[CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-136">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-137">[新-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-137">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-138">[移除-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-138">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="11b9e-139">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="11b9e-139">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11b9e-140">請參閱</span><span class="sxs-lookup"><span data-stu-id="11b9e-140">See Also</span></span>


[<span data-ttu-id="11b9e-141">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="11b9e-141">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

