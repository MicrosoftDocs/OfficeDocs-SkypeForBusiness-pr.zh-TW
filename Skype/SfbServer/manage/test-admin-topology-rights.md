---
title: 在商務用 Skype Server 中測試系統管理員拓撲許可權
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如何在商務用 Skype Server 中測試拓撲許可權
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832843"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="42b4b-103">在商務用 Skype Server 中測試系統管理員拓撲許可權</span><span class="sxs-lookup"><span data-stu-id="42b4b-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="42b4b-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="42b4b-104">Verification schedule</span></span>|<span data-ttu-id="42b4b-105">初次進行商務用 Skype Server 部署之後。</span><span class="sxs-lookup"><span data-stu-id="42b4b-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="42b4b-106">在發生許可權相關的問題時，視需要進行。</span><span class="sxs-lookup"><span data-stu-id="42b4b-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="42b4b-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="42b4b-107">Testing tool</span></span>|<span data-ttu-id="42b4b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42b4b-108">Windows PowerShell</span></span>|
|<span data-ttu-id="42b4b-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="42b4b-109">Permissions required</span></span>|<span data-ttu-id="42b4b-110">使用商務用 Skype Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="42b4b-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="42b4b-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsSetupPermission Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="42b4b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="42b4b-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="42b4b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="42b4b-113">Get-CsAdminRole \| Where-Object {$ _。Cmdlet-符合 "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="42b4b-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="42b4b-114">描述</span><span class="sxs-lookup"><span data-stu-id="42b4b-114">Description</span></span>

<span data-ttu-id="42b4b-115">根據預設，只有網域管理員可以啟用商務用 Skype 伺服器拓撲，並對商務用 Skype 伺服器基礎結構進行大型變更。</span><span class="sxs-lookup"><span data-stu-id="42b4b-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="42b4b-116">只要您的網域管理員和商務用 Skype 伺服器管理員都是相同的，這就不是問題。</span><span class="sxs-lookup"><span data-stu-id="42b4b-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="42b4b-117">在許多組織中，商務用 Skype 伺服器管理員不會保留整個網域的系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="42b4b-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="42b4b-118">根據預設，這表示這些系統管理員 (定義為 RTCUniversalServerAdmins 群組的成員) 無法進行商務用 Skype 伺服器拓撲變更。</span><span class="sxs-lookup"><span data-stu-id="42b4b-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="42b4b-119">若要授與 RTCUniversalServerAdmins 群組的成員進行拓撲變更，您必須使用 [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) Cmdlet 指派必要的 Active Directory 許可權。</span><span class="sxs-lookup"><span data-stu-id="42b4b-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="42b4b-120">Test-CsSetupPermission Cmdlet 會驗證安裝商務用 Skype 伺服器或其其中一個元件所需的必要許可權是否已在指定的 Active Directory 容器上進行設定。</span><span class="sxs-lookup"><span data-stu-id="42b4b-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="42b4b-121">若未指派許可權，您可以執行 Grant-CsSetupPermission 指令程式，給 RTCUniversalServerAdmins 群組的成員提供安裝及啟用商務用 Skype 伺服器的權利。</span><span class="sxs-lookup"><span data-stu-id="42b4b-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="42b4b-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="42b4b-122">Running the test</span></span>

<span data-ttu-id="42b4b-123">若要判斷是否為 Active Directory 容器指派安裝程式許可權，請致電 Test-CsSetupPermission Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="42b4b-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="42b4b-124">指定要檢查之容器的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="42b4b-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="42b4b-125">例如，此命令會驗證容器 ou = CsServers，dc = litwareinc，dc = com 的設定許可權：</span><span class="sxs-lookup"><span data-stu-id="42b4b-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="42b4b-126">如需詳細資訊，請參閱 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="42b4b-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="42b4b-127">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="42b4b-127">Determining success or failure</span></span>

<span data-ttu-id="42b4b-128">如果 Test-CsSetupPermission 判斷已經在 Active Directory 容器上設定必要的許可權，則 Cmdlet 會傳回值 True：</span><span class="sxs-lookup"><span data-stu-id="42b4b-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="42b4b-129">是</span><span class="sxs-lookup"><span data-stu-id="42b4b-129">True</span></span> 

<span data-ttu-id="42b4b-130">如果未設定許可權，Test-CsSetupPermission 會傳回值 False。</span><span class="sxs-lookup"><span data-stu-id="42b4b-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="42b4b-131">請注意，此值通常會包含在許多警告訊息中。</span><span class="sxs-lookup"><span data-stu-id="42b4b-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="42b4b-132">例如：</span><span class="sxs-lookup"><span data-stu-id="42b4b-132">For example:</span></span>

<span data-ttu-id="42b4b-133">警告：存取控制專案 (ACE) atl-cs-001\RTCUniversalServerAdmins;供ExtendedRight;全全1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="42b4b-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="42b4b-134">警告：物件 "CN = 電腦，DC = litwareinc，DC=com" 的存取控制專案 (Ace) 尚未就緒。</span><span class="sxs-lookup"><span data-stu-id="42b4b-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="42b4b-135">False</span><span class="sxs-lookup"><span data-stu-id="42b4b-135">False</span></span> 

<span data-ttu-id="42b4b-136">警告： "Test-CsSetupPermission" 處理已完成，但有警告。</span><span class="sxs-lookup"><span data-stu-id="42b4b-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="42b4b-137">在此執行期間，記錄了 "2" 個警告。</span><span class="sxs-lookup"><span data-stu-id="42b4b-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="42b4b-138">警告：在 "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" 可以找到詳細的結果。</span><span class="sxs-lookup"><span data-stu-id="42b4b-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="42b4b-139">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="42b4b-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="42b4b-140">雖然很少例外，但如果 Test-CsSetupPermission 失敗通常表示未指派指定之 Active Directory 容器的設定許可權。</span><span class="sxs-lookup"><span data-stu-id="42b4b-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="42b4b-141">您可以使用 Grant-CsSetupPermission Cmdlet 指派這些許可權。</span><span class="sxs-lookup"><span data-stu-id="42b4b-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="42b4b-142">例如，此命令會授與網域 litwareinc.com 中電腦容器的設定許可權：</span><span class="sxs-lookup"><span data-stu-id="42b4b-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="42b4b-143">如需詳細資訊，請參閱 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="42b4b-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
