---
title: 在商務用 Skype Server 中測試管理員拓朴許可權
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
description: 如何在商務用 Skype Server 中測試拓撲許可權
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817309"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="54b94-103">在商務用 Skype Server 中測試管理員拓朴許可權</span><span class="sxs-lookup"><span data-stu-id="54b94-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="54b94-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="54b94-104">Verification schedule</span></span>|<span data-ttu-id="54b94-105">開始進行商務用 Skype Server 部署之後。</span><span class="sxs-lookup"><span data-stu-id="54b94-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="54b94-106">如有許可權相關問題，請視需要進行。</span><span class="sxs-lookup"><span data-stu-id="54b94-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="54b94-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="54b94-107">Testing tool</span></span>|<span data-ttu-id="54b94-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54b94-108">Windows PowerShell</span></span>|
|<span data-ttu-id="54b94-109">需要許可權</span><span class="sxs-lookup"><span data-stu-id="54b94-109">Permissions required</span></span>|<span data-ttu-id="54b94-110">使用商務用 Skype Server Management Shell 在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="54b94-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="54b94-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsSetupPermission Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="54b94-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="54b94-112">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="54b94-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="54b94-113">CsAdminRole \|物件 {$ _。Cmdlet-符合 "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="54b94-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="54b94-114">說明</span><span class="sxs-lookup"><span data-stu-id="54b94-114">Description</span></span>

<span data-ttu-id="54b94-115">根據預設，只有網域系統管理員可以啟用商務用 Skype 伺服器拓撲，並對商務用 Skype 伺服器基礎結構進行較大的變更。</span><span class="sxs-lookup"><span data-stu-id="54b94-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="54b94-116">只要您的網域管理員與您的商務用 Skype Server 管理員都是相同的，就不會發生問題。</span><span class="sxs-lookup"><span data-stu-id="54b94-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="54b94-117">在許多組織中，商務用 Skype Server 系統管理員不會在整個網域中保留系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="54b94-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="54b94-118">根據預設，這表示這些系統管理員（定義為 RTCUniversalServerAdmins 群組的成員）無法進行商務用 Skype Server 拓撲的變更。</span><span class="sxs-lookup"><span data-stu-id="54b94-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="54b94-119">若要賦予 RTCUniversalServerAdmins 群組的成員對拓撲進行變更的權利，您必須使用[Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) Cmdlet 來指派所需的 Active Directory 許可權。</span><span class="sxs-lookup"><span data-stu-id="54b94-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="54b94-120">CsSetupPermission Cmdlet 會驗證安裝商務用 Skype Server 或其中一個元件所需的許可權是否已在指定的 Active Directory 容器上設定。</span><span class="sxs-lookup"><span data-stu-id="54b94-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="54b94-121">如果沒有指派許可權，您可以執行授與 CsSetupPermission Cmdlet，將 RTCUniversalServerAdmins 群組的成員授與安裝及啟用商務用 Skype Server 的權利。</span><span class="sxs-lookup"><span data-stu-id="54b94-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="54b94-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="54b94-122">Running the test</span></span>

<span data-ttu-id="54b94-123">若要判斷是否已指派 Active Directory 容器的設定許可權，請呼叫 CsSetupPermission Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54b94-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="54b94-124">指定要檢查之容器的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="54b94-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="54b94-125">例如，這個命令會驗證容器 ou = CsServers、dc = litwareinc、dc = com 的設定許可權：</span><span class="sxs-lookup"><span data-stu-id="54b94-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="54b94-126">如需詳細資訊，請參閱[Test CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="54b94-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="54b94-127">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="54b94-127">Determining success or failure</span></span>

<span data-ttu-id="54b94-128">如果測試 CsSetupPermission 決定已在 Active Directory 容器上設定所需的許可權，則 Cmdlet 會傳回值 True：</span><span class="sxs-lookup"><span data-stu-id="54b94-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="54b94-129">滿足</span><span class="sxs-lookup"><span data-stu-id="54b94-129">True</span></span> 

<span data-ttu-id="54b94-130">如果沒有設定許可權，測試 CsSetupPermission 會傳回值 False。</span><span class="sxs-lookup"><span data-stu-id="54b94-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="54b94-131">請注意，這個值通常會括在許多警告訊息中。</span><span class="sxs-lookup"><span data-stu-id="54b94-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="54b94-132">例如：</span><span class="sxs-lookup"><span data-stu-id="54b94-132">For example:</span></span>

<span data-ttu-id="54b94-133">警告：存取控制專案（ACE） atl-cs-001\RTCUniversalServerAdmins;允許ExtendedRight;所有所有1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="54b94-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="54b94-134">警告：物件「CN = 電腦、DC = litwareinc、DC = com」上的存取控制專案（Ace）尚未就緒。</span><span class="sxs-lookup"><span data-stu-id="54b94-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="54b94-135">虛假</span><span class="sxs-lookup"><span data-stu-id="54b94-135">False</span></span> 

<span data-ttu-id="54b94-136">警告：「Test CsSetupPermission」處理已完成，但出現警告。</span><span class="sxs-lookup"><span data-stu-id="54b94-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="54b94-137">此執行期間錄製了 "2" 個警告。</span><span class="sxs-lookup"><span data-stu-id="54b94-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="54b94-138">警告：您可以在「C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html」找到詳細的結果。</span><span class="sxs-lookup"><span data-stu-id="54b94-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="54b94-139">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="54b94-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="54b94-140">雖然不常見的例外狀況，但如果測試 CsSetupPermission 失敗，通常表示沒有為指定的 Active Directory 容器指派設定許可權。</span><span class="sxs-lookup"><span data-stu-id="54b94-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="54b94-141">您可以使用 Grant CsSetupPermission Cmdlet 來指派這些許可權。</span><span class="sxs-lookup"><span data-stu-id="54b94-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="54b94-142">例如，這個命令會在網域 litwareinc.com 中授與電腦容器的設定許可權：</span><span class="sxs-lookup"><span data-stu-id="54b94-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="54b94-143">如需詳細資訊，請參閱[Test CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="54b94-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
