---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile Cmdlet 會在 [商務用 Skype 雲端連接器版本] 的 [網站共用目錄] 下，移除 [CA] 資料夾中的 [憑證授權單位服務] 備份檔案。
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824289"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="5ed9c-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="5ed9c-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="5ed9c-104">CcCertificationAuthorityFile Cmdlet 會在 [商務用 Skype 雲端連接器版本]&lt;的 [&gt;網站共用目錄] 下，移除 CA 資料夾中的 [SiteRootDirectory \CA\SfB CCE Root. p12]。</span><span class="sxs-lookup"><span data-stu-id="5ed9c-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="5ed9c-105">參數</span><span class="sxs-lookup"><span data-stu-id="5ed9c-105">Parameters</span></span>

<span data-ttu-id="5ed9c-106">無</span><span class="sxs-lookup"><span data-stu-id="5ed9c-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5ed9c-107">範例</span><span class="sxs-lookup"><span data-stu-id="5ed9c-107">Examples</span></span>
<span data-ttu-id="5ed9c-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5ed9c-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5ed9c-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="5ed9c-109">Example 1</span></span>

<span data-ttu-id="5ed9c-110">下列範例會移除 [&lt;SITEROOTDIRECTORY&gt;\CA\SfB CCE 根目錄. p12] 在 [網站共用目錄] 下的 [CA] 資料夾中的 [憑證授權單位服務] 備份檔案：</span><span class="sxs-lookup"><span data-stu-id="5ed9c-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="5ed9c-111">輸入類型</span><span class="sxs-lookup"><span data-stu-id="5ed9c-111">Input Types</span></span>
<span data-ttu-id="5ed9c-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ed9c-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5ed9c-113">無。</span><span class="sxs-lookup"><span data-stu-id="5ed9c-113">None.</span></span> <span data-ttu-id="5ed9c-114">CcCertificationAuthorityFile Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="5ed9c-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5ed9c-115">傳回類型</span><span class="sxs-lookup"><span data-stu-id="5ed9c-115">Return Types</span></span>
<span data-ttu-id="5ed9c-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ed9c-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5ed9c-117">無</span><span class="sxs-lookup"><span data-stu-id="5ed9c-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ed9c-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ed9c-118">See also</span></span>
<span data-ttu-id="5ed9c-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5ed9c-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="5ed9c-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="5ed9c-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

