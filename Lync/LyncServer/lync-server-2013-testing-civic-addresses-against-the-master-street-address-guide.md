---
title: 對照主要街道位址指南測試市政位址
description: 對照主要街道位址指南來測試市政位址。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16e0d721b70e3db175b2d23ddee6f59d13a13c4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560699"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="dbd48-103">對照 Lync Server 2013 中的主要街道位址指南來測試市政位址</span><span class="sxs-lookup"><span data-stu-id="dbd48-103">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbd48-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="dbd48-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbd48-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="dbd48-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dbd48-106">每日</span><span class="sxs-lookup"><span data-stu-id="dbd48-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd48-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="dbd48-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dbd48-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbd48-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd48-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="dbd48-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dbd48-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="dbd48-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dbd48-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsRegistration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="dbd48-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="dbd48-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dbd48-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dbd48-113">描述</span><span class="sxs-lookup"><span data-stu-id="dbd48-113">Description</span></span>

<span data-ttu-id="dbd48-114">Test-CsLisCivicAddress Cmdlet 是用來確認新增至您的位置資訊服務 (.LIS) 資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="dbd48-114">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="dbd48-115">此 Cmdlet 的運作方式是比較位置與主要街道通訊指南中所找到的位置 (MSAG) 屬於您的 E9-1-1 網路路由提供者。</span><span class="sxs-lookup"><span data-stu-id="dbd48-115">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="dbd48-116">如果您沒有網路路由傳送者，或無法連線提供者，您的測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="dbd48-116">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="dbd48-117">如果您將選用參數 UpdateValidationStatus 新增至您的命令，則每個透過測試的位址都會將對應的 MSAGValid 資料庫屬性設定為 True。</span><span class="sxs-lookup"><span data-stu-id="dbd48-117">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dbd48-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="dbd48-118">Running the test</span></span>

<span data-ttu-id="dbd48-119">Test-CsLisCivicAddress Cmdlet 可用來測試個別位址或測試多個位址。</span><span class="sxs-lookup"><span data-stu-id="dbd48-119">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="dbd48-120">例如，此命令會測試位於 Redmond，WA 中的單一位址：</span><span class="sxs-lookup"><span data-stu-id="dbd48-120">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="dbd48-121">相比之下，此命令會測試所有在 IIS 資料庫中的位址：</span><span class="sxs-lookup"><span data-stu-id="dbd48-121">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="dbd48-122">如需詳細資訊，請參閱 [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="dbd48-122">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dbd48-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="dbd48-123">Determining success or failure</span></span>

<span data-ttu-id="dbd48-124">Test-CsLisCivicAddress 會傳回提供之位址的成功或失敗報告。</span><span class="sxs-lookup"><span data-stu-id="dbd48-124">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="dbd48-125">如果找不到位址，或無法連絡服務提供者，則位址測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="dbd48-125">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dbd48-126">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="dbd48-126">Reasons why the test might have failed</span></span>

<span data-ttu-id="dbd48-127">以下是一些 Test-CsLisCivicAddress 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="dbd48-127">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="dbd48-128">.LIS 服務提供者可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="dbd48-128">The LIS service provider might not be available.</span></span> <span data-ttu-id="dbd48-129">您可以執行 Get-CsLisConfiguration Cmdlet，以取得您的 .LIS 服務提供者的 URL：</span><span class="sxs-lookup"><span data-stu-id="dbd48-129">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="dbd48-130">然後，您可以 ping 該 URL 以驗證服務提供者是否可供使用。</span><span class="sxs-lookup"><span data-stu-id="dbd48-130">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

