---
title: Lync Server 2013：檢查 Lync Server 2013 伺服器憑證
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
ms.openlocfilehash: 4f5e8465ce7f0343bea96ee6f0613b8725d0e540
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502700"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="5ff53-102">檢查 Lync Server 2013 伺服器憑證</span><span class="sxs-lookup"><span data-stu-id="5ff53-102">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ff53-103">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="5ff53-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ff53-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="5ff53-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5ff53-105">每月</span><span class="sxs-lookup"><span data-stu-id="5ff53-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ff53-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="5ff53-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5ff53-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ff53-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ff53-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="5ff53-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5ff53-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5ff53-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5ff53-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Get-CsCertificate Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="5ff53-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="5ff53-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ff53-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5ff53-112">描述</span><span class="sxs-lookup"><span data-stu-id="5ff53-112">Description</span></span>

<span data-ttu-id="5ff53-113">Get-CsCertificate Cmdlet 可讓您檢索每一部 Lync Server 憑證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5ff53-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="5ff53-114">這一點特別重要，因為憑證具有內建的到期日。</span><span class="sxs-lookup"><span data-stu-id="5ff53-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="5ff53-115">例如，私下發行的憑證通常會在12個月後到期。</span><span class="sxs-lookup"><span data-stu-id="5ff53-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="5ff53-116">如果任何 Lync Server 憑證到期，則在續訂或取代憑證之前，您會失去伴隨的功能。</span><span class="sxs-lookup"><span data-stu-id="5ff53-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5ff53-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="5ff53-117">Running the test</span></span>

<span data-ttu-id="5ff53-118">若要傳回每個 Lync Server 憑證的詳細資訊，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5ff53-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="5ff53-119">或者，您可以根據到期日來篩選傳回憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="5ff53-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="5ff53-120">例如，此命令會將傳回的資料限制在2014年6月1日後到期 (無法使用的憑證) ：</span><span class="sxs-lookup"><span data-stu-id="5ff53-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="5ff53-121">如需詳細資訊，請參閱 Get-CsCertificate Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="5ff53-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="5ff53-122">請注意，雖然 Test-CsCertificateConfiguration Cmdlet 存在，但對系統管理員而言並不十分實用。</span><span class="sxs-lookup"><span data-stu-id="5ff53-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="5ff53-123"> (相反地，該 Cmdlet 主要是由憑證嚮導使用。 ) 雖然 Cmdlet 能夠運作，但它傳回的資訊的價值最低，如下列輸出範例所示：</span><span class="sxs-lookup"><span data-stu-id="5ff53-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="5ff53-124">指紋使用</span><span class="sxs-lookup"><span data-stu-id="5ff53-124">Thumbprint Use</span></span>

<span data-ttu-id="5ff53-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="5ff53-125">\---------- ---</span></span>

<span data-ttu-id="5ff53-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 預設值</span><span class="sxs-lookup"><span data-stu-id="5ff53-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="5ff53-127">檢查輸出</span><span class="sxs-lookup"><span data-stu-id="5ff53-127">Reviewing the output</span></span>

<span data-ttu-id="5ff53-128">Get-CsCertificate Cmdlet 會針對每個 Lync Server 憑證傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="5ff53-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="5ff53-129">發行者： CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="5ff53-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="5ff53-130">NotAfter： 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="5ff53-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="5ff53-131">NotBefore： 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="5ff53-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="5ff53-132">SerialNumber：611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="5ff53-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="5ff53-133">Subject： CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ff53-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="5ff53-134">AlternativeNames： {sip.fabrikam.com、LYNC-SE.fabrikam.com、</span><span class="sxs-lookup"><span data-stu-id="5ff53-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="5ff53-135">meet.fabrikam.com，admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ff53-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="5ff53-136">指紋： A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="5ff53-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="5ff53-137">使用：預設值</span><span class="sxs-lookup"><span data-stu-id="5ff53-137">Use : Default</span></span>

<span data-ttu-id="5ff53-138">一般來說，與 Lync Server 憑證有關的主要問題包括日期和時間，例如當憑證生效時 (NotBefore) 或到期時 (NotAfter) 。</span><span class="sxs-lookup"><span data-stu-id="5ff53-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="5ff53-139">因為這些日期和時間很重要，您可能想要將傳回的資料限制為憑證使用、憑證序號碼和憑證到期日等資訊。然後，您可以快速查看所有憑證和到期的時間。</span><span class="sxs-lookup"><span data-stu-id="5ff53-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="5ff53-140">若只要傳回該資訊，請使用命令和如下所示的選項：</span><span class="sxs-lookup"><span data-stu-id="5ff53-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="5ff53-141">該命令會傳回與下列類似的資料，並以到期日的順序排序憑證：</span><span class="sxs-lookup"><span data-stu-id="5ff53-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="5ff53-142">使用 SerialNumber NotAfter</span><span class="sxs-lookup"><span data-stu-id="5ff53-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="5ff53-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="5ff53-143">\--- ------------ --------</span></span>

<span data-ttu-id="5ff53-144">預設 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="5ff53-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="5ff53-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="5ff53-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="5ff53-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="5ff53-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="5ff53-147">如果您有憑證問題，您可能想要查看為憑證設定的 AlternativeNames。</span><span class="sxs-lookup"><span data-stu-id="5ff53-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="5ff53-148">乍一看，似乎是問題。</span><span class="sxs-lookup"><span data-stu-id="5ff53-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="5ff53-149">根據預設，根據主控台視窗的大小而定，Get-CsCertificate 可能無法顯示所有的名稱：</span><span class="sxs-lookup"><span data-stu-id="5ff53-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="5ff53-150">AlternativeNames： {sip.fabrikam.com、LYNC.fabrikam.com、</span><span class="sxs-lookup"><span data-stu-id="5ff53-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="5ff53-151">meet.fabrikam.com，fabrika。</span><span class="sxs-lookup"><span data-stu-id="5ff53-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="5ff53-152">若要查看指派給憑證的所有替代名稱，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="5ff53-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="5ff53-153">應該在憑證上顯示所有替代名稱：</span><span class="sxs-lookup"><span data-stu-id="5ff53-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="5ff53-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ff53-154">sip.fabrikam.com</span></span>

<span data-ttu-id="5ff53-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ff53-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="5ff53-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ff53-156">meet.fabrikam.com</span></span>

<span data-ttu-id="5ff53-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ff53-157">admin.fabrikam.com</span></span>

<span data-ttu-id="5ff53-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ff53-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="5ff53-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5ff53-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ff53-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ff53-160">See Also</span></span>


[<span data-ttu-id="5ff53-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="5ff53-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

