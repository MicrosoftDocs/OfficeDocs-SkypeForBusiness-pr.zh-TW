---
title: Lync Server 2013： 核取 Lync Server 2013 伺服器憑證
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
ms.openlocfilehash: ebdbfdc4ed0f88d78fc78037a3522c73bd220270
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="41999-102">檢查 Lync Server 2013 伺服器憑證</span><span class="sxs-lookup"><span data-stu-id="41999-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41999-103">_**上次修改主題：** 2014年-11-01_</span><span class="sxs-lookup"><span data-stu-id="41999-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41999-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="41999-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="41999-105">每月</span><span class="sxs-lookup"><span data-stu-id="41999-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41999-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="41999-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="41999-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41999-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41999-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="41999-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="41999-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="41999-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="41999-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行 Get-cscertificate cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="41999-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="41999-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="41999-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="41999-112">描述</span><span class="sxs-lookup"><span data-stu-id="41999-112">Description</span></span>

<span data-ttu-id="41999-113">Get-cscertificate cmdlet 可讓您擷取每個 Lync 伺服器憑證的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="41999-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="41999-114">這是特別重要，因為憑證具有內建到期日期。</span><span class="sxs-lookup"><span data-stu-id="41999-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="41999-115">例如、 私下發出的憑證通常 12 個月後過期。</span><span class="sxs-lookup"><span data-stu-id="41999-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="41999-116">如果任何您 Lync Server 的憑證到期然後該憑證會更新或取代之前，您會失去隨附的功能。</span><span class="sxs-lookup"><span data-stu-id="41999-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="41999-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="41999-117">Running the test</span></span>

<span data-ttu-id="41999-118">若要傳回每個 Lync 伺服器的相關資訊的憑證只會執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="41999-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="41999-119">或者，您可以篩選傳回的憑證資訊會根據 [到期日。</span><span class="sxs-lookup"><span data-stu-id="41999-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="41999-120">例如，此命令傳回的資料限制為過期的憑證 （無法使用之後） 2014 年 6 月 1 日：</span><span class="sxs-lookup"><span data-stu-id="41999-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="41999-121">如需詳細資訊，請參閱 < Get-cscertificate cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="41999-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="41999-122">請注意，雖然 Test-cscertificateconfiguration 指令程式已存在，但它不是很有用給系統管理員。</span><span class="sxs-lookup"><span data-stu-id="41999-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="41999-123">（相反地，該 cmdlet 主要由使用 [憑證] 精靈。）雖然指令程式的運作方式，它會傳回的資訊是最小值，下列的輸出範例所示：</span><span class="sxs-lookup"><span data-stu-id="41999-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="41999-124">指紋使用</span><span class="sxs-lookup"><span data-stu-id="41999-124">Thumbprint Use</span></span>

<span data-ttu-id="41999-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="41999-125">\---------- ---</span></span>

<span data-ttu-id="41999-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 預設</span><span class="sxs-lookup"><span data-stu-id="41999-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="41999-127">檢閱輸出</span><span class="sxs-lookup"><span data-stu-id="41999-127">Reviewing the output</span></span>

<span data-ttu-id="41999-128">Get-cscertificate cmdlet 會傳回類似以下的每個 Lync 伺服器憑證資訊：</span><span class="sxs-lookup"><span data-stu-id="41999-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="41999-129">簽發者： CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="41999-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="41999-130">NotAfter: 2015/12/28/下午 3:35:41</span><span class="sxs-lookup"><span data-stu-id="41999-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="41999-131">NotBefore: 1/2/2014年下午 12:49:37</span><span class="sxs-lookup"><span data-stu-id="41999-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="41999-132">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="41999-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="41999-133">主旨： CN = LYNC SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41999-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="41999-134">AlternativeNames: {sip.fabrikam.com，LYNC SE.fabrikam.com，</span><span class="sxs-lookup"><span data-stu-id="41999-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="41999-135">meet.fabrikam.com，admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="41999-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="41999-136">指紋： A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="41999-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="41999-137">使用： 預設值</span><span class="sxs-lookup"><span data-stu-id="41999-137">Use : Default</span></span>

<span data-ttu-id="41999-138">一般而言，涉及 Lync Server 憑證熱門問題牽涉到日期和時間，例如憑證時才會生效 (NotBefore) 或到期 (NotAfter)。</span><span class="sxs-lookup"><span data-stu-id="41999-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="41999-139">因為這些日期和時間是非常重要，所以您可能想要限制資訊例如憑證使用、 憑證序號及憑證到期日，傳回的資料然後您可以快速檢閱所有憑證和時將會到期。</span><span class="sxs-lookup"><span data-stu-id="41999-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="41999-140">若要傳回只是該資訊，請使用與選項搭配命令所示：</span><span class="sxs-lookup"><span data-stu-id="41999-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="41999-141">該命令會傳回類似下列命令，以其到期日期的順序排序的憑證資料：</span><span class="sxs-lookup"><span data-stu-id="41999-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="41999-142">使用 SerialNumber NotAfter</span><span class="sxs-lookup"><span data-stu-id="41999-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="41999-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="41999-143">\--- ------------ --------</span></span>

<span data-ttu-id="41999-144">預設 611BB01200000000000C 2015/12/28 下午 3:35:41</span><span class="sxs-lookup"><span data-stu-id="41999-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="41999-145">WebServicesInteral 32980AA20BBB20000191 2016 02 月 15 日下午 2:16:12</span><span class="sxs-lookup"><span data-stu-id="41999-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="41999-146">WebServicesExternal 0451B012003872651A0C 2016 02 月 20 日上午 7:11:58</span><span class="sxs-lookup"><span data-stu-id="41999-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="41999-147">如果您有憑證問題，您可能想要檢閱憑證設定 AlternativeNames。</span><span class="sxs-lookup"><span data-stu-id="41999-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="41999-148">乍看之下，這就好像有問題。</span><span class="sxs-lookup"><span data-stu-id="41999-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="41999-149">依預設，並會根據您的主控台視窗的大小，Get-cscertificate 可能無法顯示所有名稱：</span><span class="sxs-lookup"><span data-stu-id="41999-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="41999-150">AlternativeNames: {sip.fabrikam.com，LYNC.fabrikam.com，</span><span class="sxs-lookup"><span data-stu-id="41999-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="41999-151">meet.fabrikam.com，admin.fabrika...}</span><span class="sxs-lookup"><span data-stu-id="41999-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="41999-152">若要查看所有另一個指派給憑證的名稱，請使用類似這樣的命令：</span><span class="sxs-lookup"><span data-stu-id="41999-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="41999-153">應會顯示您所有的替代名稱的憑證：</span><span class="sxs-lookup"><span data-stu-id="41999-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="41999-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41999-154">sip.fabrikam.com</span></span>

<span data-ttu-id="41999-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41999-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="41999-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41999-156">meet.fabrikam.com</span></span>

<span data-ttu-id="41999-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41999-157">admin.fabrikam.com</span></span>

<span data-ttu-id="41999-158">LYNC SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41999-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="41999-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="41999-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41999-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="41999-160">See Also</span></span>


[<span data-ttu-id="41999-161">Get-cscertificate</span><span class="sxs-lookup"><span data-stu-id="41999-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

