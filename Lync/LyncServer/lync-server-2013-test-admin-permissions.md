---
title: Lync Server 2013：測試系統管理員許可權
description: Lync Server 2013：測試系統管理員許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e15be288ed31afe9303d91ce3e623d19822428
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568519"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="a7fa2-103">在 Lync Server 2013 中測試系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="a7fa2-103">Test admin permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7fa2-104">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="a7fa2-104">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7fa2-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="a7fa2-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a7fa2-106">初始 Lync Server 部署之後。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="a7fa2-107">在發生許可權相關的問題時，視需要進行。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7fa2-108">測試控管</span><span class="sxs-lookup"><span data-stu-id="a7fa2-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a7fa2-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7fa2-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7fa2-110">必要的權限</span><span class="sxs-lookup"><span data-stu-id="a7fa2-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a7fa2-111">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a7fa2-112">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsOUPermission Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="a7fa2-113">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a7fa2-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a7fa2-114">描述</span><span class="sxs-lookup"><span data-stu-id="a7fa2-114">Description</span></span>

<span data-ttu-id="a7fa2-115">當您安裝 Lync Server 2013 1 的安裝程式所執行的工作時，會讓 RTCUniversalUserAdmins 群組管理使用者、電腦、連絡人、應用程式連絡人及 InetOrg 人員所需的 Active Directory 許可權。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-115">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="a7fa2-116">如果您已在 Active Directory 中停用許可權繼承，安裝程式將無法指派這些許可權。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-116">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="a7fa2-117">因此，RTCUniversalUserAdmins 群組的成員將無法管理 Lync Server 實體。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="a7fa2-118">只有網域系統管理員可以使用這些管理許可權。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-118">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="a7fa2-119">Test-CsOUPermission Cmdlet 會驗證管理使用者、電腦及其他物件所需的必要許可權是否已在 Active Directory 容器上設定。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-119">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="a7fa2-120">若未設定這些許可權，您可以執行 [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) Cmdlet 來解決此問題。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="a7fa2-121">請注意，Grant-CsOUPermission 只能將許可權指派給 RTCUniversalUserAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="a7fa2-122">您無法使用此 Cmdlet 將許可權授與任意使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="a7fa2-123">若要讓不同的使用者或群組擁有使用者管理許可權，您應該將該使用者 (或群組) 新增至 RTCUniversalUserAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="a7fa2-124">如需有關 OU 許可權的詳細資訊，請參閱在 [Lync Server 2013 中的電腦、使用者或 InetOrgPerson 容器上，已停用許可權繼承](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-124">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a7fa2-125">執行測試</span><span class="sxs-lookup"><span data-stu-id="a7fa2-125">Running the test</span></span>

<span data-ttu-id="a7fa2-126">若要確認是否已在容器上設定管理許可權，請先執行 Test-CsOUPermission 指令程式，然後再執行容器的辨識名稱，以及您要驗證的許可權類型。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-126">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="a7fa2-127">例如，此命令會檢查是否已在 OU ou = Redmond，dc = litwareinc，dc = com 上設定使用者許可權：</span><span class="sxs-lookup"><span data-stu-id="a7fa2-127">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="a7fa2-128">若要使用單一命令來驗證多個許可權，請以引號括住每個許可權類型，然後使用逗號分隔這些類型。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-128">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="a7fa2-129">例如，下列命令會驗證使用者、電腦及連絡人許可權：</span><span class="sxs-lookup"><span data-stu-id="a7fa2-129">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="a7fa2-130">如需詳細資訊，請參閱 [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-130">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a7fa2-131">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="a7fa2-131">Determining success or failure</span></span>

<span data-ttu-id="a7fa2-132">如果已設定必要的許可權，則 Test-CsOUPermission 會傳回一個單字回應：</span><span class="sxs-lookup"><span data-stu-id="a7fa2-132">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="a7fa2-133">是</span><span class="sxs-lookup"><span data-stu-id="a7fa2-133">True</span></span>

<span data-ttu-id="a7fa2-134">如果未設定必要的許可權，則 Test-CsOUPermission 會傳回值 False。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-134">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="a7fa2-135">您可能需要搜尋一會兒，以找出此值。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-135">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="a7fa2-136">它通常會內嵌在數個伴隨的警告內。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-136">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="a7fa2-137">例如：</span><span class="sxs-lookup"><span data-stu-id="a7fa2-137">For example:</span></span>

<span data-ttu-id="a7fa2-138">警告： access control entry (ACE) atl-cs-001 \\ RTCUniversalUserReadOnlyGroup; allow;ReadProperty;ContainerInherit;其子bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="a7fa2-138">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="a7fa2-139">警告：物件 "OU = NorthAmerica，DC = atl-cs-001 \\ dc = litwareinc，DC=com" 的存取控制專案 (ace) 尚未就緒。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-139">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="a7fa2-140">False</span><span class="sxs-lookup"><span data-stu-id="a7fa2-140">False</span></span>

<span data-ttu-id="a7fa2-141">警告： "Test-CsOUPermission" 處理已完成，但有警告。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-141">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="a7fa2-142">在此執行期間，記錄了 "2" 個警告。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-142">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="a7fa2-143">警告：在 "C： \\ Users \\ Admin \\ AppData \\ Local \\ Temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" 上可以找到詳細的結果。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-143">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a7fa2-144">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="a7fa2-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="a7fa2-145">如果 Test-CsOUPermission 失敗，則通常表示指定的許可權尚未指派給 RTCUniversalUserAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-145">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="a7fa2-146">您可以使用 Grant-CsOUPermission Cmdlet 來解決此問題，並指派必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-146">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="a7fa2-147">例如，下列命令會將使用者、連絡人及 Inetorgperson 的 OU 許可權提供給 RTCUniversalUserAdmins 群組：</span><span class="sxs-lookup"><span data-stu-id="a7fa2-147">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="a7fa2-148">如需詳細資訊，請參閱 Grant-CsOUPermission Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="a7fa2-148">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

