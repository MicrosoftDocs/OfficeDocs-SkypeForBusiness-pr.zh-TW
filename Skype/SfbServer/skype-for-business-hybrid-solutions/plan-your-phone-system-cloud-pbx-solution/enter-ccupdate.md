---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: CcUpdate Cmdlet 會將商務用 Skype 雲端連接器 Edition 主機伺服器加入維護模式, 以進行更新程式。 裝置會立即停止所有服務、結束任何正在進行的通話, 並拒絕任何新的呼叫。
ms.openlocfilehash: 3ff4c1543e3e882a7ccbaf0b9a216ce902a77c5f
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36193932"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="17f9a-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="17f9a-104">Enter-CcUpdate</span></span>

<span data-ttu-id="17f9a-105">CcUpdate Cmdlet 會將商務用 Skype 雲端連接器 Edition 主機伺服器加入維護模式, 以進行更新程式。</span><span class="sxs-lookup"><span data-stu-id="17f9a-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="17f9a-106">裝置會立即停止所有服務、結束任何正在進行的通話, 並拒絕任何新的呼叫。</span><span class="sxs-lookup"><span data-stu-id="17f9a-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="17f9a-107">參數</span><span class="sxs-lookup"><span data-stu-id="17f9a-107">Parameters</span></span>

<span data-ttu-id="17f9a-108">無</span><span class="sxs-lookup"><span data-stu-id="17f9a-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="17f9a-109">範例</span><span class="sxs-lookup"><span data-stu-id="17f9a-109">Examples</span></span>
<span data-ttu-id="17f9a-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="17f9a-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="17f9a-111">範例 1</span><span class="sxs-lookup"><span data-stu-id="17f9a-111">Example 1</span></span>

<span data-ttu-id="17f9a-112">下列範例會進入 [維護] 模式, 為更新程式準備裝置:</span><span class="sxs-lookup"><span data-stu-id="17f9a-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="17f9a-113">詳細描述</span><span class="sxs-lookup"><span data-stu-id="17f9a-113">Detailed Description</span></span>
<span data-ttu-id="17f9a-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="17f9a-114"></span></span>

<span data-ttu-id="17f9a-115">CcUpdate Cmdlet 會立即停止所有結束進行中通話的服務, 而裝置將拒絕任何新的呼叫, 傳送到其他生產裝置。</span><span class="sxs-lookup"><span data-stu-id="17f9a-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="17f9a-116">您必須確保剩餘的生產裝置擁有足夠的容量, 才能處理您準備更新之裝置的通話。</span><span class="sxs-lookup"><span data-stu-id="17f9a-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="17f9a-117">如果您的裝置已啟用自動更新 (例如, Microsoft 發行重要的熱修復程式), 維護模式就很有用。</span><span class="sxs-lookup"><span data-stu-id="17f9a-117">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix.</span></span> <span data-ttu-id="17f9a-118">如果您決定要關閉自動更新, 但是您會在一致的基礎上執行手動更新, 維護模式也很有用。</span><span class="sxs-lookup"><span data-stu-id="17f9a-118">Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="17f9a-119">安裝更新之後, 裝置可以執行 CcUpdate Cmdlet, 回到生產模式。</span><span class="sxs-lookup"><span data-stu-id="17f9a-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="17f9a-120">如果您決定手動更新雲端連接器裝置, 您必須在 Microsoft 發行下一個版本之後的60天內更新。</span><span class="sxs-lookup"><span data-stu-id="17f9a-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="17f9a-121">在發行新版本之後, Microsoft 支援舊版雲端連接器60天</span><span class="sxs-lookup"><span data-stu-id="17f9a-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="17f9a-122">輸入類型</span><span class="sxs-lookup"><span data-stu-id="17f9a-122">Input Types</span></span>
<span data-ttu-id="17f9a-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17f9a-123"></span></span>

<span data-ttu-id="17f9a-124">無。</span><span class="sxs-lookup"><span data-stu-id="17f9a-124">None.</span></span> <span data-ttu-id="17f9a-125">CCUpdate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="17f9a-125">The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="17f9a-126">傳回類型</span><span class="sxs-lookup"><span data-stu-id="17f9a-126">Return Types</span></span>
<span data-ttu-id="17f9a-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17f9a-127"></span></span>

<span data-ttu-id="17f9a-128">無</span><span class="sxs-lookup"><span data-stu-id="17f9a-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="17f9a-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17f9a-129">See also</span></span>
<span data-ttu-id="17f9a-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17f9a-130"></span></span>

[<span data-ttu-id="17f9a-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="17f9a-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

