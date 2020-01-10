---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: '[還原 Cc-認證] Cmdlet 會還原目前商務用 Skype 雲端連接器版本部署的所有認證。'
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003243"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="57551-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="57551-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="57551-104">[還原 Cc-認證] Cmdlet 會還原目前商務用 Skype 雲端連接器版本部署的所有認證。</span><span class="sxs-lookup"><span data-stu-id="57551-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="57551-105">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 2.1。</span><span class="sxs-lookup"><span data-stu-id="57551-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="57551-106">詳細描述</span><span class="sxs-lookup"><span data-stu-id="57551-106">Detailed Description</span></span>

<span data-ttu-id="57551-107">Restore-CcCredentials Cmdlet 會清除所有認證，並提示您重新輸入目前商務用 Skype 雲端連接器部署所使用的所有認證。</span><span class="sxs-lookup"><span data-stu-id="57551-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="57551-108">參數</span><span class="sxs-lookup"><span data-stu-id="57551-108">Parameters</span></span>

<span data-ttu-id="57551-109">無</span><span class="sxs-lookup"><span data-stu-id="57551-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="57551-110">輸入類型</span><span class="sxs-lookup"><span data-stu-id="57551-110">Input Types</span></span>

<span data-ttu-id="57551-111">無。</span><span class="sxs-lookup"><span data-stu-id="57551-111">None.</span></span> <span data-ttu-id="57551-112">Restore-CcCredentials Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="57551-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="57551-113">傳回類型</span><span class="sxs-lookup"><span data-stu-id="57551-113">Return Types</span></span>

<span data-ttu-id="57551-114">無。</span><span class="sxs-lookup"><span data-stu-id="57551-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="57551-115">範例</span><span class="sxs-lookup"><span data-stu-id="57551-115">Example</span></span>

<span data-ttu-id="57551-116">下列範例會還原目前雲端連接器部署的所有認證：</span><span class="sxs-lookup"><span data-stu-id="57551-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="57551-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="57551-117">See also</span></span>

[<span data-ttu-id="57551-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="57551-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="57551-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="57551-119">Set-CcCredential</span></span>](set-cccredential.md)
  

