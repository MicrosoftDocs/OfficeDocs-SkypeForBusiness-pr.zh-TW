---
title: Lync Server 2013：測試管理員拓撲許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3681a3328f0e1e659377947919bbfc782f1fea7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="367da-102">Lync Server 2013 中的測試管理員拓朴許可權</span><span class="sxs-lookup"><span data-stu-id="367da-102">Test admin topology rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="367da-103">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="367da-103">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="367da-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="367da-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="367da-105">初次進行 Lync Server 部署之後。</span><span class="sxs-lookup"><span data-stu-id="367da-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="367da-106">如有許可權相關問題，請視需要進行。</span><span class="sxs-lookup"><span data-stu-id="367da-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="367da-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="367da-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="367da-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="367da-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="367da-109">需要許可權</span><span class="sxs-lookup"><span data-stu-id="367da-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="367da-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="367da-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="367da-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsSetupPermission Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="367da-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="367da-112">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="367da-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="367da-113">說明</span><span class="sxs-lookup"><span data-stu-id="367da-113">Description</span></span>

<span data-ttu-id="367da-114">根據預設，只有網域系統管理員可以啟用 Lync Server 拓撲，並對 Lync Server 基礎結構進行較大的變更。</span><span class="sxs-lookup"><span data-stu-id="367da-114">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="367da-115">只要您的網域系統管理員和您的 Lync 伺服器管理員都是相同的，就不會發生問題。在許多組織中，Lync Server 系統管理員不會在整個網域中保留系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="367da-115">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="367da-116">根據預設，這表示這些系統管理員（定義為 RTCUniversalServerAdmins 群組的成員）無法進行 Lync Server 拓撲變更。</span><span class="sxs-lookup"><span data-stu-id="367da-116">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="367da-117">若要賦予 RTCUniversalServerAdmins 群組的成員對拓撲進行變更的權利，您必須使用[Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) Cmdlet 來指派所需的 Active Directory 許可權。</span><span class="sxs-lookup"><span data-stu-id="367da-117">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="367da-118">CsSetupPermission Cmdlet 會確認安裝 Lync Server 或其某個元件所需的許可權已在指定的 Active Directory 容器上設定。</span><span class="sxs-lookup"><span data-stu-id="367da-118">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="367da-119">如果沒有指派許可權，您可以執行授與 CsSetupPermission Cmdlet，將 RTCUniversalServerAdmins 群組的成員授與安裝和啟用 Lync Server 的權利。</span><span class="sxs-lookup"><span data-stu-id="367da-119">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="367da-120">如需由授與 CsSetupPermission 指派之許可權的詳細清單，請參閱博客文章<A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">授與授與授與授與授與 CsOUPermission</A>。</span><span class="sxs-lookup"><span data-stu-id="367da-120">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="367da-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="367da-121">Running the test</span></span>

<span data-ttu-id="367da-122">若要判斷是否已指派 Active Directory 容器的設定許可權，請呼叫 CsSetupPermission Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="367da-122">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="367da-123">指定要檢查之容器的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="367da-123">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="367da-124">例如，這個命令會驗證容器 ou = CsServers、dc = litwareinc、dc = com 的設定許可權：</span><span class="sxs-lookup"><span data-stu-id="367da-124">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="367da-125">如需詳細資訊，請參閱[Test CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="367da-125">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="367da-126">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="367da-126">Determining success or failure</span></span>

<span data-ttu-id="367da-127">如果測試 CsSetupPermission 決定已在 Active Directory 容器上設定所需的許可權，則 Cmdlet 會傳回值 True：</span><span class="sxs-lookup"><span data-stu-id="367da-127">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="367da-128">滿足</span><span class="sxs-lookup"><span data-stu-id="367da-128">True</span></span>

<span data-ttu-id="367da-129">如果沒有設定許可權，測試 CsSetupPermission 會傳回值 False。</span><span class="sxs-lookup"><span data-stu-id="367da-129">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="367da-130">請注意，這個值通常會括在許多警告訊息中。</span><span class="sxs-lookup"><span data-stu-id="367da-130">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="367da-131">例如：</span><span class="sxs-lookup"><span data-stu-id="367da-131">For example:</span></span>

<span data-ttu-id="367da-132">警告：存取控制專案（ACE） atl-cs-001\\RTCUniversalServerAdmins;允許ExtendedRight;所有所有1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="367da-132">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="367da-133">警告：物件「CN = 電腦、DC = litwareinc、DC = com」上的存取控制專案（Ace）尚未就緒。</span><span class="sxs-lookup"><span data-stu-id="367da-133">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="367da-134">虛假</span><span class="sxs-lookup"><span data-stu-id="367da-134">False</span></span>

<span data-ttu-id="367da-135">警告：「Test CsSetupPermission」處理已完成，但出現警告。</span><span class="sxs-lookup"><span data-stu-id="367da-135">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="367da-136">此執行期間錄製了 "2" 個警告。</span><span class="sxs-lookup"><span data-stu-id="367da-136">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="367da-137">警告：您\\可以在「C：使用者\\系統管理員\\AppData\\本機\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118 .html」中找到詳細的結果。</span><span class="sxs-lookup"><span data-stu-id="367da-137">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="367da-138">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="367da-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="367da-139">雖然不常見的例外狀況，但如果測試 CsSetupPermission 失敗，通常表示沒有為指定的 Active Directory 容器指派設定許可權。</span><span class="sxs-lookup"><span data-stu-id="367da-139">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="367da-140">您可以使用 Grant CsSetupPermission Cmdlet 來指派這些許可權。</span><span class="sxs-lookup"><span data-stu-id="367da-140">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="367da-141">例如，這個命令會在網域 litwareinc.com 中授與電腦容器的設定許可權：</span><span class="sxs-lookup"><span data-stu-id="367da-141">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="367da-142">如需詳細資訊，請參閱[Test CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="367da-142">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

