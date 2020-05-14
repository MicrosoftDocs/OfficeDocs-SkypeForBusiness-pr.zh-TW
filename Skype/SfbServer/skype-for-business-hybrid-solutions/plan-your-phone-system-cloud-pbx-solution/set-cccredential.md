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
description: CcCredential Cmdlet 會設定目前商務用 Skype Connector Edition 部署的認證。
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221567"
---
# <a name="set-cccredential"></a><span data-ttu-id="735ba-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="735ba-103">Set-CcCredential</span></span>
 
<span data-ttu-id="735ba-104">CcCredential Cmdlet 會設定目前商務用 Skype Connector Edition 部署的認證。</span><span class="sxs-lookup"><span data-stu-id="735ba-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="735ba-105">使用雲端連接器版本2.0 和更新版本時，此 Cmdlet 也可以為虛擬機器管理員和網域管理員設定帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="735ba-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="735ba-106">範例</span><span class="sxs-lookup"><span data-stu-id="735ba-106">Examples</span></span>
<span data-ttu-id="735ba-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="735ba-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="735ba-108">範例 1</span><span class="sxs-lookup"><span data-stu-id="735ba-108">Example 1</span></span>

<span data-ttu-id="735ba-109">下列範例會指定租使用者管理員的帳戶名稱和密碼：</span><span class="sxs-lookup"><span data-stu-id="735ba-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="735ba-110">詳細描述</span><span class="sxs-lookup"><span data-stu-id="735ba-110">Detailed Description</span></span>
<span data-ttu-id="735ba-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="735ba-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="735ba-112">CcCredential Cmdlet 會為承租人管理員設定帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="735ba-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="735ba-113">在2.0 之前的版本中，此管理員必須是全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="735ba-113">For releases prior to 2.0, this administrator must be a Global Administrator.</span></span> <span data-ttu-id="735ba-114">雲端連接器會使用此帳戶來取得設定資訊、設定設定參數，並將裝置狀態更新為 Microsoft 365 或 Office 365 組織設定。</span><span class="sxs-lookup"><span data-stu-id="735ba-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="735ba-115">使用版本2.0 和更新版本時，您也可以使用此 Cmdlet 來更新 VmAdmin 及 DomainAdmin 帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="735ba-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="735ba-116">參數</span><span class="sxs-lookup"><span data-stu-id="735ba-116">Parameters</span></span>
<span data-ttu-id="735ba-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="735ba-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="735ba-118">**參數**</span><span class="sxs-lookup"><span data-stu-id="735ba-118">**Parameter**</span></span>|<span data-ttu-id="735ba-119">**Required**</span><span class="sxs-lookup"><span data-stu-id="735ba-119">**Required**</span></span>|<span data-ttu-id="735ba-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="735ba-120">**Type**</span></span>|<span data-ttu-id="735ba-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="735ba-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="735ba-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="735ba-122">AccountType</span></span> <br/> | <span data-ttu-id="735ba-123">必要</span><span class="sxs-lookup"><span data-stu-id="735ba-123">Required</span></span> <br/> |<span data-ttu-id="735ba-124">System.String</span><span class="sxs-lookup"><span data-stu-id="735ba-124">System.String</span></span>  <br/> | <span data-ttu-id="735ba-125">參數值必須是 "TenantAdmin"、"VmAdmin" 或 "DomainAdmin"。</span><span class="sxs-lookup"><span data-stu-id="735ba-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="735ba-126">輸入類型</span><span class="sxs-lookup"><span data-stu-id="735ba-126">Input Types</span></span>
<span data-ttu-id="735ba-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="735ba-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="735ba-128">無。</span><span class="sxs-lookup"><span data-stu-id="735ba-128">None.</span></span> <span data-ttu-id="735ba-129">CcCredential 指令程式不接受管線傳送的輸入。</span><span class="sxs-lookup"><span data-stu-id="735ba-129">The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="735ba-130">傳回類型</span><span class="sxs-lookup"><span data-stu-id="735ba-130">Return Types</span></span>
<span data-ttu-id="735ba-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="735ba-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="735ba-132">無</span><span class="sxs-lookup"><span data-stu-id="735ba-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="735ba-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="735ba-133">See also</span></span>
<span data-ttu-id="735ba-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="735ba-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="735ba-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="735ba-135">Get-CcCredential</span></span>](get-cccredential.md)
  

