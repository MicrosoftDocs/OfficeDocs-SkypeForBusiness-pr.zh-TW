---
title: '商務用 Skype Server 2019 的虛擬化支援 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：瞭解商務用 Skype Server 2019 的虛擬化支援。
ms.openlocfilehash: b4524b1284a85e7ab372b415d45c2005f8212887
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755807"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="0aaff-103">商務用 Skype Server 2019 的虛擬化支援</span><span class="sxs-lookup"><span data-stu-id="0aaff-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="0aaff-104">虛擬化支援商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="0aaff-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="0aaff-105">支援虛擬化時，需要記住一些要點：</span><span class="sxs-lookup"><span data-stu-id="0aaff-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="0aaff-106">維護虛擬 CPU 與實體 CPU 的1:1 比率。</span><span class="sxs-lookup"><span data-stu-id="0aaff-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="0aaff-107">請勿移動來賓伺服器的運作方式。</span><span class="sxs-lookup"><span data-stu-id="0aaff-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="0aaff-108">不支援即時系統和虛擬機器的便攜性遷移。</span><span class="sxs-lookup"><span data-stu-id="0aaff-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="0aaff-109">停用所有主機上的超執行緒。</span><span class="sxs-lookup"><span data-stu-id="0aaff-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="0aaff-110">請勿在主伺服器上設定動態記憶體。</span><span class="sxs-lookup"><span data-stu-id="0aaff-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="0aaff-111">使用固定磁片或傳遞磁片（而非動態磁碟）。</span><span class="sxs-lookup"><span data-stu-id="0aaff-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="0aaff-112">針對虛擬來賓所需的虛擬機器監控程式，允許超過6-10% 的負載。</span><span class="sxs-lookup"><span data-stu-id="0aaff-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="0aaff-113">支援的虛擬機器監控程式</span><span class="sxs-lookup"><span data-stu-id="0aaff-113">Supported hypervisors</span></span>

<span data-ttu-id="0aaff-114">Windows Server 2016 和 Windows Server 2019 支援 SfB Server 2019。</span><span class="sxs-lookup"><span data-stu-id="0aaff-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="0aaff-115">針對協力廠商虛擬機器管理器，您需要已超過伺服器虛擬化驗證方案（SVVP）測試（適用于相關作業系統）的虛擬機器監控程式。</span><span class="sxs-lookup"><span data-stu-id="0aaff-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="0aaff-116">請參閱 SVVP 清單中的[Windows Server 2016 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25)。</span><span class="sxs-lookup"><span data-stu-id="0aaff-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="0aaff-117">請參閱 SVVP 清單中的[Windows Server 2019 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25)。</span><span class="sxs-lookup"><span data-stu-id="0aaff-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="0aaff-118">壓力和效能工具</span><span class="sxs-lookup"><span data-stu-id="0aaff-118">Stress and performance tool</span></span>

<span data-ttu-id="0aaff-119">商務用 Skype Server 2019 應力和效能工具組含的工具可簡化商務用 Skype Server 2019 的容量規劃。</span><span class="sxs-lookup"><span data-stu-id="0aaff-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="0aaff-120">商務用 Skype Server 2019 應力和效能工具可協助您：</span><span class="sxs-lookup"><span data-stu-id="0aaff-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="0aaff-121">簡化您的商務用 Skype Server 2019 的硬體規劃</span><span class="sxs-lookup"><span data-stu-id="0aaff-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="0aaff-122">為您提供更多有關效能調整的知識和最佳作法</span><span class="sxs-lookup"><span data-stu-id="0aaff-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="0aaff-123">衡量預定商務用 Skype Server 2019 部署的效能</span><span class="sxs-lookup"><span data-stu-id="0aaff-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="0aaff-124">您可以從[這裡](https://www.microsoft.com/download/details.aspx?id=101447)下載工具。</span><span class="sxs-lookup"><span data-stu-id="0aaff-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
