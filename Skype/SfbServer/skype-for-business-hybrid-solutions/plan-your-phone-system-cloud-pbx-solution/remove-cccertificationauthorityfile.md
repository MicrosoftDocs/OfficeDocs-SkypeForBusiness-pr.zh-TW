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
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile Cmdlet 會在 [商務用 Skype 雲端連接器版本] 的 [網站共用目錄] 下，移除 [CA] 資料夾中的 [憑證授權單位服務] 備份檔案。
ms.openlocfilehash: d7036633eaf092130fc6e4acaebda39d04ff17df
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003293"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="8207b-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="8207b-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="8207b-104">CcCertificationAuthorityFile Cmdlet 會在 [商務用 Skype 雲端連接器版本]&lt;的 [&gt;網站共用目錄] 下，移除 CA 資料夾中的 [SiteRootDirectory \CA\SfB CCE Root. p12]。</span><span class="sxs-lookup"><span data-stu-id="8207b-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="8207b-105">參數</span><span class="sxs-lookup"><span data-stu-id="8207b-105">Parameters</span></span>

<span data-ttu-id="8207b-106">無</span><span class="sxs-lookup"><span data-stu-id="8207b-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8207b-107">範例</span><span class="sxs-lookup"><span data-stu-id="8207b-107">Examples</span></span>
<span data-ttu-id="8207b-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8207b-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="8207b-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="8207b-109">Example 1</span></span>

<span data-ttu-id="8207b-110">下列範例會移除 [&lt;SITEROOTDIRECTORY&gt;\CA\SfB CCE 根目錄. p12] 在 [網站共用目錄] 下的 [CA] 資料夾中的 [憑證授權單位服務] 備份檔案：</span><span class="sxs-lookup"><span data-stu-id="8207b-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="8207b-111">輸入類型</span><span class="sxs-lookup"><span data-stu-id="8207b-111">Input Types</span></span>
<span data-ttu-id="8207b-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8207b-112"></span></span>

<span data-ttu-id="8207b-113">無。</span><span class="sxs-lookup"><span data-stu-id="8207b-113">None.</span></span> <span data-ttu-id="8207b-114">CcCertificationAuthorityFile Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="8207b-114">The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8207b-115">傳回類型</span><span class="sxs-lookup"><span data-stu-id="8207b-115">Return Types</span></span>
<span data-ttu-id="8207b-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8207b-116"></span></span>

<span data-ttu-id="8207b-117">無</span><span class="sxs-lookup"><span data-stu-id="8207b-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8207b-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8207b-118">See also</span></span>
<span data-ttu-id="8207b-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8207b-119"></span></span>

[<span data-ttu-id="8207b-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="8207b-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

