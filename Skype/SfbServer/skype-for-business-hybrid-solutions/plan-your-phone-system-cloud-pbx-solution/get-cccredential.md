---
title: CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: CcCredential Cmdlet 會傳回目前商務用 Skype 雲端連接器版本部署的認證。
ms.openlocfilehash: 87dd3934767a4be7afb57889fd0641e8507fba13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190786"
---
# <a name="get-cccredential"></a><span data-ttu-id="2a677-103">CcCredential</span><span class="sxs-lookup"><span data-stu-id="2a677-103">Get-CcCredential</span></span>
 
<span data-ttu-id="2a677-104">CcCredential Cmdlet 會傳回目前商務用 Skype 雲端連接器版本部署的認證。</span><span class="sxs-lookup"><span data-stu-id="2a677-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="2a677-105">在版本2.0 及更新版本中, 您也可以使用-DisplayPassword 參數來顯示 TenantAdmin、DomainAdmin 和 VMAdmin 的密碼。</span><span class="sxs-lookup"><span data-stu-id="2a677-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="2a677-106">範例</span><span class="sxs-lookup"><span data-stu-id="2a677-106">Examples</span></span>
<span data-ttu-id="2a677-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2a677-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="2a677-108">範例 1</span><span class="sxs-lookup"><span data-stu-id="2a677-108">Example 1</span></span>

<span data-ttu-id="2a677-109">下列範例會傳回雲端連接器虛擬機器網域之網域管理員的認證:</span><span class="sxs-lookup"><span data-stu-id="2a677-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="2a677-110">詳細描述</span><span class="sxs-lookup"><span data-stu-id="2a677-110">Detailed Description</span></span>
<span data-ttu-id="2a677-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2a677-111"></span></span>

<span data-ttu-id="2a677-112">CcCredential Cmdlet 會傳回指定帳戶類型的認證資訊。</span><span class="sxs-lookup"><span data-stu-id="2a677-112">The Get-CcCredential cmdlet returns the credential information about the specified account type.</span></span> <span data-ttu-id="2a677-113">這些認證是由執行 CcAppliance 及安裝 CcAppliance Cmdlet 的管理員指定, 在部署目前的裝置時。</span><span class="sxs-lookup"><span data-stu-id="2a677-113">These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="2a677-114">CcCredential Cmdlet 會傳回系統. Management. PSCredential 物件的實例。</span><span class="sxs-lookup"><span data-stu-id="2a677-114">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span> <span data-ttu-id="2a677-115">傳回物件的 password 屬性是 SecureString。</span><span class="sxs-lookup"><span data-stu-id="2a677-115">The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="2a677-116">如果您想要取得網域管理員密碼的明文, 請確定密碼是由主機伺服器上的目前登入帳戶所輸入, 然後以系統管理員身分開啟 PowerShell 主機, 然後執行下列腳本:</span><span class="sxs-lookup"><span data-stu-id="2a677-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="2a677-117">參數</span><span class="sxs-lookup"><span data-stu-id="2a677-117">Parameters</span></span>
<span data-ttu-id="2a677-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2a677-118"></span></span>

|<span data-ttu-id="2a677-119">**參數**</span><span class="sxs-lookup"><span data-stu-id="2a677-119">**Parameter**</span></span>|<span data-ttu-id="2a677-120">**必要**</span><span class="sxs-lookup"><span data-stu-id="2a677-120">**Required**</span></span>|<span data-ttu-id="2a677-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="2a677-121">**Type**</span></span>|<span data-ttu-id="2a677-122">**說明**</span><span class="sxs-lookup"><span data-stu-id="2a677-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2a677-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="2a677-123">AccountType</span></span> <br/> |<span data-ttu-id="2a677-124">必要</span><span class="sxs-lookup"><span data-stu-id="2a677-124">Required</span></span>  <br/> | <span data-ttu-id="2a677-125">System.String</span><span class="sxs-lookup"><span data-stu-id="2a677-125">System.String</span></span> <br/> | <span data-ttu-id="2a677-126">AccountType 值可以是下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="2a677-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="2a677-127">VmAdmin: 雲端連接器虛擬機器的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="2a677-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="2a677-128">DomainAdmin: 雲端連接器虛擬機器網域的網域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="2a677-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="2a677-129">SafeModeAdmin: SafeModeAdmin 雲端連接器虛擬電腦網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="2a677-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="2a677-130">ExternalCert: 在 Edge 伺服器上安裝外部憑證的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2a677-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="2a677-131">TenantAdmin: O365 租使用者的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="2a677-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2a677-132">輸入類型</span><span class="sxs-lookup"><span data-stu-id="2a677-132">Input Types</span></span>
<span data-ttu-id="2a677-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a677-133"></span></span>

<span data-ttu-id="2a677-134">無。</span><span class="sxs-lookup"><span data-stu-id="2a677-134">None.</span></span> <span data-ttu-id="2a677-135">CcCredential Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="2a677-135">The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2a677-136">傳回類型</span><span class="sxs-lookup"><span data-stu-id="2a677-136">Return Types</span></span>
<span data-ttu-id="2a677-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a677-137"></span></span>

<span data-ttu-id="2a677-138">CcCredential Cmdlet 會傳回系統. Management. PSCredential 物件的實例。</span><span class="sxs-lookup"><span data-stu-id="2a677-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2a677-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2a677-139">See also</span></span>
<span data-ttu-id="2a677-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a677-140"></span></span>

[<span data-ttu-id="2a677-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="2a677-141">Set-CcCredential</span></span>](set-cccredential.md)
  

