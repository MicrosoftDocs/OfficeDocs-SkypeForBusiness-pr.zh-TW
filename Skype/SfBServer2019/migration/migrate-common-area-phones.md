---
title: 移轉公共區域電話
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 公共區域電話為最常在共用工作區或公共區域 (例如大廳、廚房或工廠) 的 IP 電話。 一般區域電話不需要連線到電腦，就能供應商務用 Skype Server 整合通訊（UC）功能。 將部署遷移至商務用 Skype Server 2019 之後，您還必須遷移與舊版通用區域電話相關聯的連絡人物件。 使用商務用 Skype Server 管理命令介面您會先取得與舊版公用區域電話相關聯的所有連絡人物件，然後將這些物件移至商務用 Skype Server 2019 集區。
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752705"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="588c6-106">移轉公共區域電話</span><span class="sxs-lookup"><span data-stu-id="588c6-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="588c6-107">公共區域電話為最常在共用工作區或公共區域 (例如大廳、廚房或工廠) 的 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="588c6-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="588c6-108">一般區域電話不需要連線到電腦，就能供應商務用 Skype Server 整合通訊（UC）功能。</span><span class="sxs-lookup"><span data-stu-id="588c6-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="588c6-109">將部署遷移至商務用 Skype Server 2019 之後，您還必須遷移與舊版通用區域電話相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="588c6-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="588c6-110">使用商務用 Skype Server 管理命令介面，您會先取得與舊版公用區域電話相關聯的所有連絡人物件，然後將這些物件移至商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="588c6-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="588c6-111">移轉公共區域電話</span><span class="sxs-lookup"><span data-stu-id="588c6-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="588c6-112">從商務用 Skype Server 2019 前端伺服器，開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="588c6-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="588c6-113">從命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="588c6-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="588c6-114">若要確認已將所有連絡人物件移至商務用 Skype Server 2019 集區，請從商務用 Skype Server 管理命令介面輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="588c6-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="588c6-115">確認所有連絡人物件現在已與商務用 Skype Server 2019 集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="588c6-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

