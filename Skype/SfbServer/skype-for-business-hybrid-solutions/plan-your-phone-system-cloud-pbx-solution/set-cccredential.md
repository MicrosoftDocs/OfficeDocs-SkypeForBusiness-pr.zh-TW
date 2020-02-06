---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: CcCredential Cmdlet 會設定目前商務用 Skype 雲端連接器版本部署的認證。
ms.openlocfilehash: b7620a6d76415e4e2a49ea9bd628d1e1cba7f4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824207"
---
# <a name="set-cccredential"></a><span data-ttu-id="9d895-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="9d895-103">Set-CcCredential</span></span>
 
<span data-ttu-id="9d895-104">CcCredential Cmdlet 會設定目前商務用 Skype 雲端連接器版本部署的認證。</span><span class="sxs-lookup"><span data-stu-id="9d895-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="9d895-105">使用雲端連接器版本2.0 和更新版本時，此 Cmdlet 也可以設定虛擬機器管理員和網域管理員的帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="9d895-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="9d895-106">範例</span><span class="sxs-lookup"><span data-stu-id="9d895-106">Examples</span></span>
<span data-ttu-id="9d895-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9d895-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="9d895-108">範例 1</span><span class="sxs-lookup"><span data-stu-id="9d895-108">Example 1</span></span>

<span data-ttu-id="9d895-109">下列範例會指定租使用者管理員的帳戶名稱和密碼：</span><span class="sxs-lookup"><span data-stu-id="9d895-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="9d895-110">詳細描述</span><span class="sxs-lookup"><span data-stu-id="9d895-110">Detailed Description</span></span>
<span data-ttu-id="9d895-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9d895-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="9d895-112">CcCredential Cmdlet 會為租使用者管理員設定帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="9d895-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="9d895-113">在2.0 之前的版本中，此系統管理員必須是 Office 365 全域管理員。</span><span class="sxs-lookup"><span data-stu-id="9d895-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="9d895-114">雲端連接器使用這個帳戶來取得配置資訊、設定設定參數，以及將裝置狀態更新為 Office 365 租使用者設定。</span><span class="sxs-lookup"><span data-stu-id="9d895-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="9d895-115">在發行2.0 及更新版本中，您也可以使用這個 Cmdlet 來更新 VmAdmin 和 DomainAdmin 帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="9d895-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9d895-116">參數</span><span class="sxs-lookup"><span data-stu-id="9d895-116">Parameters</span></span>
<span data-ttu-id="9d895-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9d895-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="9d895-118">**參數**</span><span class="sxs-lookup"><span data-stu-id="9d895-118">**Parameter**</span></span>|<span data-ttu-id="9d895-119">**必要**</span><span class="sxs-lookup"><span data-stu-id="9d895-119">**Required**</span></span>|<span data-ttu-id="9d895-120">**類型**</span><span class="sxs-lookup"><span data-stu-id="9d895-120">**Type**</span></span>|<span data-ttu-id="9d895-121">**說明**</span><span class="sxs-lookup"><span data-stu-id="9d895-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9d895-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="9d895-122">AccountType</span></span> <br/> | <span data-ttu-id="9d895-123">必要</span><span class="sxs-lookup"><span data-stu-id="9d895-123">Required</span></span> <br/> |<span data-ttu-id="9d895-124">System.String</span><span class="sxs-lookup"><span data-stu-id="9d895-124">System.String</span></span>  <br/> | <span data-ttu-id="9d895-125">參數值必須是 "TenantAdmin"、"VmAdmin" 或 "DomainAdmin"。</span><span class="sxs-lookup"><span data-stu-id="9d895-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9d895-126">輸入類型</span><span class="sxs-lookup"><span data-stu-id="9d895-126">Input Types</span></span>
<span data-ttu-id="9d895-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9d895-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="9d895-128">無。</span><span class="sxs-lookup"><span data-stu-id="9d895-128">None.</span></span> <span data-ttu-id="9d895-129">CcCredential Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="9d895-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9d895-130">傳回類型</span><span class="sxs-lookup"><span data-stu-id="9d895-130">Return Types</span></span>
<span data-ttu-id="9d895-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9d895-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="9d895-132">無</span><span class="sxs-lookup"><span data-stu-id="9d895-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d895-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9d895-133">See also</span></span>
<span data-ttu-id="9d895-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9d895-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="9d895-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="9d895-135">Get-CcCredential</span></span>](get-cccredential.md)
  

