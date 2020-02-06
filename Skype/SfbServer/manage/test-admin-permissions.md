---
title: 在商務用 Skype Server 中測試系統管理員許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如何在商務用 Skype Server 中測試系統管理員許可權
ms.openlocfilehash: 97db574803b575d484240e7339d56603ae5432da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817184"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="35457-103">在商務用 Skype Server 中測試系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="35457-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="35457-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="35457-104">Verification schedule</span></span>|<span data-ttu-id="35457-105">開始進行商務用 Skype Server 部署之後。</span><span class="sxs-lookup"><span data-stu-id="35457-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="35457-106">如有許可權相關問題，請視需要進行。</span><span class="sxs-lookup"><span data-stu-id="35457-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="35457-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="35457-107">Testing tool</span></span>|<span data-ttu-id="35457-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35457-108">Windows PowerShell</span></span>|
|<span data-ttu-id="35457-109">需要許可權</span><span class="sxs-lookup"><span data-stu-id="35457-109">Permissions required</span></span>|<span data-ttu-id="35457-110">使用商務用 Skype Server Management Shell 在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="35457-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="35457-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsOUPermission Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="35457-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="35457-112">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="35457-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="35457-113">CsAdminRole \|物件 {$ _。Cmdlet-符合 "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="35457-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="35457-114">說明</span><span class="sxs-lookup"><span data-stu-id="35457-114">Description</span></span>

<span data-ttu-id="35457-115">當您安裝商務用 Skype Server 時，由安裝程式執行的其中一個工作，會為 RTCUniversalUserAdmins 群組提供管理使用者、電腦、連絡人、應用程式連絡人及 InetOrg 所需的 Active Directory 許可權。人員.</span><span class="sxs-lookup"><span data-stu-id="35457-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="35457-116">如果您已在 Active Directory 中停用許可權繼承，安裝程式將無法指派這些許可權。</span><span class="sxs-lookup"><span data-stu-id="35457-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="35457-117">因此，RTCUniversalUserAdmins 群組的成員將無法管理商務用 Skype Server 實體。</span><span class="sxs-lookup"><span data-stu-id="35457-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="35457-118">只有網域系統管理員可以使用這些管理許可權。</span><span class="sxs-lookup"><span data-stu-id="35457-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="35457-119">CsOUPermission Cmdlet 會驗證管理使用者、電腦及其他物件所需的許可權是否已在 Active Directory 容器上設定。</span><span class="sxs-lookup"><span data-stu-id="35457-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="35457-120">如果未設定這些許可權，您可以執行[授與 CsOUPermission Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)來解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="35457-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="35457-121">請注意，授與 CsOUPermission 只能將許可權指派給 RTCUniversalUserAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="35457-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="35457-122">您無法使用此 Cmdlet 來授與任何使用者或群組的許可權。</span><span class="sxs-lookup"><span data-stu-id="35457-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="35457-123">如果您想要讓不同的使用者或群組擁有使用者管理許可權，您應該將該使用者（或群組）新增至 [RTCUniversalUserAdmins] 群組。</span><span class="sxs-lookup"><span data-stu-id="35457-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="35457-124">執行測試</span><span class="sxs-lookup"><span data-stu-id="35457-124">Running the test</span></span>

<span data-ttu-id="35457-125">若要確認管理許可權是在容器上設定，請執行 Test CsOUPermission Cmdlet，後面接著該容器的辨識名稱，以及您要驗證的許可權類型。</span><span class="sxs-lookup"><span data-stu-id="35457-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="35457-126">例如，這個命令會檢查是否在 OU ou = 雷蒙德、dc = litwareinc、dc = com 中設定使用者許可權：</span><span class="sxs-lookup"><span data-stu-id="35457-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="35457-127">若要使用單一命令驗證多個許可權，請用引號括住每個許可權類型，然後使用逗號分隔這些類型。</span><span class="sxs-lookup"><span data-stu-id="35457-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="35457-128">例如，下列一個命令會驗證使用者、電腦和連絡人許可權：</span><span class="sxs-lookup"><span data-stu-id="35457-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="35457-129">如需詳細資訊，請參閱[Test CsOUPermission Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)的說明主題。</span><span class="sxs-lookup"><span data-stu-id="35457-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="35457-130">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="35457-130">Determining success or failure</span></span>

<span data-ttu-id="35457-131">如果已設定所需的許可權，則 CsOUPermission 會傳回單字回應：</span><span class="sxs-lookup"><span data-stu-id="35457-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="35457-132">滿足</span><span class="sxs-lookup"><span data-stu-id="35457-132">True</span></span>

<span data-ttu-id="35457-133">如果沒有設定所需的許可權，測試 CsOUPermission 就會傳回值 False。</span><span class="sxs-lookup"><span data-stu-id="35457-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="35457-134">您可能需要搜尋時間來尋找這個值。</span><span class="sxs-lookup"><span data-stu-id="35457-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="35457-135">它通常會內嵌在幾個伴隨的警告中。</span><span class="sxs-lookup"><span data-stu-id="35457-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="35457-136">例如：</span><span class="sxs-lookup"><span data-stu-id="35457-136">For example:</span></span>

<span data-ttu-id="35457-137">警告：存取控制專案（ACE） atl-cs-001\RTCUniversalUserReadOnlyGroup;允許ReadProperty;ContainerInherit;子類bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="35457-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="35457-138">警告：物件「OU = 北美、DC = atl-cs-001\DC = litwareinc、DC = com」上的存取控制專案（Ace）尚未就緒。</span><span class="sxs-lookup"><span data-stu-id="35457-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="35457-139">虛假</span><span class="sxs-lookup"><span data-stu-id="35457-139">False</span></span> 

<span data-ttu-id="35457-140">警告：「Test CsOUPermission」處理已完成，但出現警告。</span><span class="sxs-lookup"><span data-stu-id="35457-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="35457-141">此執行期間錄製了 "2" 個警告。</span><span class="sxs-lookup"><span data-stu-id="35457-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="35457-142">警告：您可以在「C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html」找到詳細的結果。</span><span class="sxs-lookup"><span data-stu-id="35457-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="35457-143">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="35457-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="35457-144">如果測試 CsOUPermission 失敗，通常表示指定的許可權尚未指派給 RTCUniversalUserAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="35457-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="35457-145">您可以使用 Grant CsOUPermission Cmdlet 來解決這個問題，並指派所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="35457-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="35457-146">例如，這個命令會將使用者、連絡人及 inetOrgPersons 的 OU 許可權提供給 RTCUniversalUserAdmins 群組：</span><span class="sxs-lookup"><span data-stu-id="35457-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="35457-147">如需詳細資訊，請參閱[Test CsOUPermission Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)的說明主題。</span><span class="sxs-lookup"><span data-stu-id="35457-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
