---
title: 測試指派給網站之 Kerberos 帳戶的設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c096edc0267501bb17870a5c018e4b6b0c513422
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="ceaee-102">在 Lync Server 2013 中測試指派給網站之 Kerberos 帳戶的設定</span><span class="sxs-lookup"><span data-stu-id="ceaee-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceaee-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ceaee-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ceaee-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="ceaee-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ceaee-105">日常</span><span class="sxs-lookup"><span data-stu-id="ceaee-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ceaee-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="ceaee-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ceaee-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ceaee-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ceaee-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="ceaee-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ceaee-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ceaee-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ceaee-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsKerberosAccountAssignment Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ceaee-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="ceaee-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ceaee-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ceaee-112">說明</span><span class="sxs-lookup"><span data-stu-id="ceaee-112">Description</span></span>

<span data-ttu-id="ceaee-113">CsKerberosAccountAssignment Cmdlet 可讓您確認 Kerberos 帳戶是否與指定的網站產生關聯、該帳戶是否已正確設定，以及該帳戶是否如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="ceaee-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="ceaee-114">Kerberos 帳戶是電腦帳戶，可充當執行網際網路資訊伺服器（IIS）之網站中所有電腦的驗證原則。</span><span class="sxs-lookup"><span data-stu-id="ceaee-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="ceaee-115">因為這些帳戶使用 Kerberos 驗證通訊協定，所以帳戶稱為 Kerberos 帳戶，而新的驗證程式則稱為 Kerberos web 驗證。</span><span class="sxs-lookup"><span data-stu-id="ceaee-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="ceaee-116">這可讓您使用單一帳戶來管理所有 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ceaee-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="ceaee-117">如需詳細資訊，請參閱[Test CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="ceaee-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ceaee-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="ceaee-118">Running the Test</span></span>

<span data-ttu-id="ceaee-119">根據預設，測試 CsKerberosAccountAssignment 會在畫面上顯示極小的輸出。</span><span class="sxs-lookup"><span data-stu-id="ceaee-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="ceaee-120">相反地，由 Cmdlet 傳回的資訊會寫入 HTML 檔案。</span><span class="sxs-lookup"><span data-stu-id="ceaee-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="ceaee-121">因此，建議您在每次執行 Test CsKerberosAccountAssignment 時包含詳細參數和 Report 參數。</span><span class="sxs-lookup"><span data-stu-id="ceaee-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="ceaee-122">此詳細參數會在執行 Cmdlet 時，在螢幕上提供稍有更詳細的輸出。</span><span class="sxs-lookup"><span data-stu-id="ceaee-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="ceaee-123">Report 參數可讓您指定由 Test CsKerberosAccountAssignment 所產生之 HTML 檔案的檔案路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="ceaee-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="ceaee-124">如果您不包含報表參數，HTML 檔案將會自動儲存到 [使用者] 資料夾，並指定如下的名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f .html。</span><span class="sxs-lookup"><span data-stu-id="ceaee-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="ceaee-125">當您執行 Test CsKerberosAccountAssignment 時，您也必須指定網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="ceaee-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="ceaee-126">Kerberos 帳戶是在網站範圍內指派。</span><span class="sxs-lookup"><span data-stu-id="ceaee-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="ceaee-127">下列命令會執行 Test-CsKerberosAccountAssignment，並將輸出儲存到名為 C：\\Logs\\KerberosTest 的檔案中：</span><span class="sxs-lookup"><span data-stu-id="ceaee-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="ceaee-128">如需詳細資訊，請參閱[Test CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="ceaee-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ceaee-129">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="ceaee-129">Determining Success or Failure</span></span>

<span data-ttu-id="ceaee-130">Test CsKerberosAccountAssignment Cmdlet 不會傳回簡單的指示成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="ceaee-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="ceaee-131">相反地，您必須使用 Internet Explorer 來查看產生的 HTML 檔案。</span><span class="sxs-lookup"><span data-stu-id="ceaee-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ceaee-132">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="ceaee-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="ceaee-133">以下是測試 CsKerberosAccountAssignment 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="ceaee-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="ceaee-134">您可能指定了不正確的網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="ceaee-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="ceaee-135">若要返回有效網站身分識別的清單，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="ceaee-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="ceaee-136">網站身分識別通常如下所示：</span><span class="sxs-lookup"><span data-stu-id="ceaee-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="ceaee-137">網站：雷蒙德</span><span class="sxs-lookup"><span data-stu-id="ceaee-137">site:Redmond</span></span>

  - <span data-ttu-id="ceaee-138">指定的網站可能沒有指派給它的 Kerberos 帳戶。</span><span class="sxs-lookup"><span data-stu-id="ceaee-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="ceaee-139">您可以執行如下的命令來判斷 Kerberos 帳戶是否已指派給網站：</span><span class="sxs-lookup"><span data-stu-id="ceaee-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="ceaee-140">您的 Kerberos 帳戶可能有不正確密碼。</span><span class="sxs-lookup"><span data-stu-id="ceaee-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="ceaee-141">如果您在報表中收到下列錯誤訊息，您可能需要重設 Kerberos 帳戶密碼：</span><span class="sxs-lookup"><span data-stu-id="ceaee-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="ceaee-142">InvalidKerberosConfiguration： Kerberos 配置無效。</span><span class="sxs-lookup"><span data-stu-id="ceaee-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="ceaee-143">InvalidKerberosConfiguration： atl-cs001.litwareinc.com 上的 Kerberos 配置無效。</span><span class="sxs-lookup"><span data-stu-id="ceaee-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="ceaee-144">預期指派的帳戶是 litwareinc\\kerberostest。</span><span class="sxs-lookup"><span data-stu-id="ceaee-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="ceaee-145">確定帳戶未過期，且電腦上設定的密碼與帳戶的 Active Directory 密碼相符。</span><span class="sxs-lookup"><span data-stu-id="ceaee-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="ceaee-146">您可以使用[CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) Cmdlet 來設定密碼。</span><span class="sxs-lookup"><span data-stu-id="ceaee-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

