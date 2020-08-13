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
ms.openlocfilehash: a608f84c3c302c503450bfe1c763aebacc269e96
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="30848-102">在 Lync Server 2013 中測試指派給網站之 Kerberos 帳戶的設定</span><span class="sxs-lookup"><span data-stu-id="30848-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30848-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="30848-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30848-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="30848-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="30848-105">每日</span><span class="sxs-lookup"><span data-stu-id="30848-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30848-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="30848-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="30848-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30848-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30848-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="30848-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="30848-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="30848-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="30848-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsKerberosAccountAssignment Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="30848-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="30848-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="30848-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="30848-112">描述</span><span class="sxs-lookup"><span data-stu-id="30848-112">Description</span></span>

<span data-ttu-id="30848-113">Test-CsKerberosAccountAssignment Cmdlet 可讓您驗證 Kerberos 帳戶是否與指定的網站相關聯、已正確設定此帳戶，以及該帳戶是否如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="30848-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="30848-114">Kerberos 帳戶是電腦帳戶，可充當執行 Internet information Server 之網站中所有電腦的驗證主體，)  (IIS。</span><span class="sxs-lookup"><span data-stu-id="30848-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="30848-115">因為這些帳戶使用 Kerberos 驗證通訊協定，所以帳戶稱為 Kerberos 帳戶，而新的驗證處理常式稱為 Kerberos web 驗證。</span><span class="sxs-lookup"><span data-stu-id="30848-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="30848-116">這可讓您使用單一帳戶管理所有 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="30848-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="30848-117">如需詳細資訊，請參閱[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="30848-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="30848-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="30848-118">Running the Test</span></span>

<span data-ttu-id="30848-119">根據預設，Test-CsKerberosAccountAssignment 會在螢幕上顯示非常少的輸出。</span><span class="sxs-lookup"><span data-stu-id="30848-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="30848-120">相反地，指令程式傳回的資訊會寫入至 HTML 檔案。</span><span class="sxs-lookup"><span data-stu-id="30848-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="30848-121">因此，建議您在每次執行 Test-CsKerberosAccountAssignment 時，加入 Verbose 參數和 Report 參數。</span><span class="sxs-lookup"><span data-stu-id="30848-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="30848-122">在執行 Cmdlet 時，Verbose 參數會在螢幕上稍有增加的輸出。</span><span class="sxs-lookup"><span data-stu-id="30848-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="30848-123">Report 參數可讓您指定 Test-CsKerberosAccountAssignment 所產生之 HTML 檔案的檔案路徑和檔案名。</span><span class="sxs-lookup"><span data-stu-id="30848-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="30848-124">如果不包含報表參數，HTML 檔案將會自動儲存至您的使用者資料夾，並指定如下名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f.html。</span><span class="sxs-lookup"><span data-stu-id="30848-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="30848-125">您也必須在執行 Test-CsKerberosAccountAssignment 時指定網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="30848-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="30848-126">在網站範圍指派 Kerberos 帳戶。</span><span class="sxs-lookup"><span data-stu-id="30848-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="30848-127">下列命令會執行 Test-CsKerberosAccountAssignment，並將輸出儲存至名為 C： Logs 的 \\ 檔案 \\KerberosTest.html：</span><span class="sxs-lookup"><span data-stu-id="30848-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="30848-128">如需詳細資訊，請參閱[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="30848-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="30848-129">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="30848-129">Determining Success or Failure</span></span>

<span data-ttu-id="30848-130">Test-CsKerberosAccountAssignment Cmdlet 不會傳回成功或失敗的簡單指示。</span><span class="sxs-lookup"><span data-stu-id="30848-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="30848-131">相反地，您必須使用 Internet Explorer 來查看產生的 HTML 檔案。</span><span class="sxs-lookup"><span data-stu-id="30848-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="30848-132">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="30848-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="30848-133">以下是一些 Test-CsKerberosAccountAssignment 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="30848-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="30848-134">您可能指定了錯誤的網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="30848-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="30848-135">若要傳回有效網站身分識別的清單，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="30848-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="30848-136">網站身分識別通常如下所示：</span><span class="sxs-lookup"><span data-stu-id="30848-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="30848-137">site： Redmond</span><span class="sxs-lookup"><span data-stu-id="30848-137">site:Redmond</span></span>

  - <span data-ttu-id="30848-138">指定的網站可能未指派 Kerberos 帳戶給它。</span><span class="sxs-lookup"><span data-stu-id="30848-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="30848-139">您可以執行類似如下的命令，判斷 Kerberos 帳戶是否已指派給網站：</span><span class="sxs-lookup"><span data-stu-id="30848-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="30848-140">您的 Kerberos 帳戶可能具有不正確密碼。</span><span class="sxs-lookup"><span data-stu-id="30848-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="30848-141">如果您在報告中收到下列錯誤訊息，您可能必須重設 Kerberos 帳戶密碼：</span><span class="sxs-lookup"><span data-stu-id="30848-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="30848-142">InvalidKerberosConfiguration： Kerberos 設定無效。</span><span class="sxs-lookup"><span data-stu-id="30848-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="30848-143">InvalidKerberosConfiguration： atl-cs001.litwareinc.com 上的 Kerberos 設定無效。</span><span class="sxs-lookup"><span data-stu-id="30848-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="30848-144">期望的指派帳戶為 litwareinc \\ kerberostest。</span><span class="sxs-lookup"><span data-stu-id="30848-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="30848-145">確定帳戶未到期，且電腦上所設定的密碼與帳戶的 Active Directory 密碼相符。</span><span class="sxs-lookup"><span data-stu-id="30848-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="30848-146">您可以使用[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) Cmdlet 來設定密碼。</span><span class="sxs-lookup"><span data-stu-id="30848-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

