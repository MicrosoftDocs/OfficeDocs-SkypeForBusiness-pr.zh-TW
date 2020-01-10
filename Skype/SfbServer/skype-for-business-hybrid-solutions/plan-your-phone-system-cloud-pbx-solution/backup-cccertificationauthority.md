---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: CcCertificationAuthority Cmdlet 會將商務用 Skype 雲端連接器 Edition 認證機構服務備份到檔案，並將其儲存到 [網站共用目錄] 下的 [CA] 資料夾。
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003023"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="0e4d6-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="0e4d6-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="0e4d6-104">CcCertificationAuthority Cmdlet 會將商務用 Skype 雲端連接器 Edition 認證機構服務備份到檔案，並將其儲存到 [網站共用目錄] 下的 [CA] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="0e4d6-105">參數</span><span class="sxs-lookup"><span data-stu-id="0e4d6-105">Parameters</span></span>

<span data-ttu-id="0e4d6-106">無</span><span class="sxs-lookup"><span data-stu-id="0e4d6-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="0e4d6-107">範例</span><span class="sxs-lookup"><span data-stu-id="0e4d6-107">Examples</span></span>
<span data-ttu-id="0e4d6-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4d6-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="0e4d6-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="0e4d6-109">Example 1</span></span>

<span data-ttu-id="0e4d6-110">下列範例會將憑證授權單位服務備份到檔案，並將它儲存到 [網站共用目錄] 下的 CA 資料夾：</span><span class="sxs-lookup"><span data-stu-id="0e4d6-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="0e4d6-111">詳細描述</span><span class="sxs-lookup"><span data-stu-id="0e4d6-111">Detailed Description</span></span>
<span data-ttu-id="0e4d6-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4d6-112"></span></span>

<span data-ttu-id="0e4d6-113">如果您打算在發生災難時以相同的憑證重新部署雲端連接器裝置，或如果您想要將裝置移至新的硬體，則可以使用憑證授權單位備份。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="0e4d6-114">該命令會將雲端連接器憑證授權單位服務的複本從 AD Server 儲存至「\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12」。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="0e4d6-115">輸入類型</span><span class="sxs-lookup"><span data-stu-id="0e4d6-115">Input Types</span></span>
<span data-ttu-id="0e4d6-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4d6-116"></span></span>

<span data-ttu-id="0e4d6-117">無。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-117">None.</span></span> <span data-ttu-id="0e4d6-118">CcCertificationAuthority Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="0e4d6-118">The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0e4d6-119">傳回類型</span><span class="sxs-lookup"><span data-stu-id="0e4d6-119">Return Types</span></span>
<span data-ttu-id="0e4d6-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4d6-120"></span></span>

<span data-ttu-id="0e4d6-121">無</span><span class="sxs-lookup"><span data-stu-id="0e4d6-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e4d6-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0e4d6-122">See also</span></span>
<span data-ttu-id="0e4d6-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0e4d6-123"></span></span>

[<span data-ttu-id="0e4d6-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="0e4d6-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

