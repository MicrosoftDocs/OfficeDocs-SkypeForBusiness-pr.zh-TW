---
title: Lync Server 2013：檢查 Lync Server 2013 伺服器憑證
description: Lync Server 2013：請檢查 Lync Server 2013 伺服器憑證。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543589"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="1c3cc-103">檢查 Lync Server 2013 伺服器憑證</span><span class="sxs-lookup"><span data-stu-id="1c3cc-103">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c3cc-104">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="1c3cc-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c3cc-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="1c3cc-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1c3cc-106">每月</span><span class="sxs-lookup"><span data-stu-id="1c3cc-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c3cc-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="1c3cc-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1c3cc-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c3cc-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c3cc-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="1c3cc-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1c3cc-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1c3cc-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Get-CsCertificate Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="1c3cc-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1c3cc-113">描述</span><span class="sxs-lookup"><span data-stu-id="1c3cc-113">Description</span></span>

<span data-ttu-id="1c3cc-114">Get-CsCertificate Cmdlet 可讓您檢索每一部 Lync Server 憑證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-114">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="1c3cc-115">這一點特別重要，因為憑證具有內建的到期日。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-115">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="1c3cc-116">例如，私下發行的憑證通常會在12個月後到期。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-116">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="1c3cc-117">如果任何 Lync Server 憑證到期，則在續訂或取代憑證之前，您會失去伴隨的功能。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-117">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1c3cc-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="1c3cc-118">Running the test</span></span>

<span data-ttu-id="1c3cc-119">若要傳回每個 Lync Server 憑證的詳細資訊，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-119">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="1c3cc-120">或者，您可以根據到期日來篩選傳回憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-120">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="1c3cc-121">例如，此命令會將傳回的資料限制在2014年6月1日後到期 (無法使用的憑證) ：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-121">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="1c3cc-122">如需詳細資訊，請參閱 Get-CsCertificate Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-122">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="1c3cc-123">請注意，雖然 Test-CsCertificateConfiguration Cmdlet 存在，但對系統管理員而言並不十分實用。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-123">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="1c3cc-124"> (相反地，該 Cmdlet 主要是由憑證嚮導使用。 ) 雖然 Cmdlet 能夠運作，但它傳回的資訊的價值最低，如下列輸出範例所示：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-124">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="1c3cc-125">指紋使用</span><span class="sxs-lookup"><span data-stu-id="1c3cc-125">Thumbprint Use</span></span>

<span data-ttu-id="1c3cc-126">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="1c3cc-126">\---------- ---</span></span>

<span data-ttu-id="1c3cc-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 預設值</span><span class="sxs-lookup"><span data-stu-id="1c3cc-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="1c3cc-128">檢查輸出</span><span class="sxs-lookup"><span data-stu-id="1c3cc-128">Reviewing the output</span></span>

<span data-ttu-id="1c3cc-129">Get-CsCertificate Cmdlet 會針對每個 Lync Server 憑證傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-129">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="1c3cc-130">發行者： CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="1c3cc-130">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="1c3cc-131">NotAfter： 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="1c3cc-131">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="1c3cc-132">NotBefore： 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="1c3cc-132">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="1c3cc-133">SerialNumber：611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="1c3cc-133">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="1c3cc-134">Subject： CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1c3cc-134">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="1c3cc-135">AlternativeNames： {sip.fabrikam.com、LYNC-SE.fabrikam.com、</span><span class="sxs-lookup"><span data-stu-id="1c3cc-135">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="1c3cc-136">meet.fabrikam.com，admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1c3cc-136">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="1c3cc-137">指紋： A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="1c3cc-137">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="1c3cc-138">使用：預設值</span><span class="sxs-lookup"><span data-stu-id="1c3cc-138">Use : Default</span></span>

<span data-ttu-id="1c3cc-139">一般來說，與 Lync Server 憑證有關的主要問題包括日期和時間，例如當憑證生效時 (NotBefore) 或到期時 (NotAfter) 。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-139">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="1c3cc-140">因為這些日期和時間很重要，您可能想要將傳回的資料限制為憑證使用、憑證序號碼和憑證到期日等資訊。然後，您可以快速查看所有憑證和到期的時間。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-140">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="1c3cc-141">若只要傳回該資訊，請使用命令和如下所示的選項：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-141">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="1c3cc-142">該命令會傳回與下列類似的資料，並以到期日的順序排序憑證：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-142">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="1c3cc-143">使用 SerialNumber NotAfter</span><span class="sxs-lookup"><span data-stu-id="1c3cc-143">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="1c3cc-144">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="1c3cc-144">\--- ------------ --------</span></span>

<span data-ttu-id="1c3cc-145">預設 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="1c3cc-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="1c3cc-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="1c3cc-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="1c3cc-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="1c3cc-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="1c3cc-148">如果您有憑證問題，您可能想要查看為憑證設定的 AlternativeNames。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-148">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="1c3cc-149">乍一看，似乎是問題。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-149">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="1c3cc-150">根據預設，根據主控台視窗的大小而定，Get-CsCertificate 可能無法顯示所有的名稱：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-150">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="1c3cc-151">AlternativeNames： {sip.fabrikam.com、LYNC.fabrikam.com、</span><span class="sxs-lookup"><span data-stu-id="1c3cc-151">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="1c3cc-152">meet.fabrikam.com，fabrika。</span><span class="sxs-lookup"><span data-stu-id="1c3cc-152">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="1c3cc-153">若要查看指派給憑證的所有替代名稱，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-153">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="1c3cc-154">應該在憑證上顯示所有替代名稱：</span><span class="sxs-lookup"><span data-stu-id="1c3cc-154">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="1c3cc-155">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1c3cc-155">sip.fabrikam.com</span></span>

<span data-ttu-id="1c3cc-156">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1c3cc-156">LYNC.fabrikam.com</span></span>

<span data-ttu-id="1c3cc-157">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1c3cc-157">meet.fabrikam.com</span></span>

<span data-ttu-id="1c3cc-158">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1c3cc-158">admin.fabrikam.com</span></span>

<span data-ttu-id="1c3cc-159">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1c3cc-159">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="1c3cc-160">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="1c3cc-160">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c3cc-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1c3cc-161">See Also</span></span>


[<span data-ttu-id="1c3cc-162">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="1c3cc-162">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

